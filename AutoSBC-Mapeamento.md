# Mapeamento — Como funciona um "AutoSBC" (botão que resolve o SBC)

> Documento de **referência técnica** (como o mecanismo funciona). Não é um bot pronto.
> Ferramentas como FC Enhancer (AutoSBC) e Paletools fazem isso por cima da **mesma camada `window.services`** do app — não há "API secreta".
> Base levantada ao vivo no FC 26 Web App (16/06/2026).

## 1. Visão geral
Um "AutoSBC" é um botão que, ao ser clicado, **monta e (opcionalmente) submete** a solução de um SBC automaticamente. Por dentro ele só orquestra chamadas à camada de serviço do app (a mesma que o app usa quando você clica manualmente). Os passos são:

1. **Ler o desafio** (requisitos: nº de jogadores, rating mínimo, química, qualidade, raridade, liga/nação, etc.).
2. **Buscar cartas elegíveis no clube** (filtros: untradeable, OVR, qualidade, raridade…).
3. **Resolver a combinação** (algoritmo de otimização) que satisfaz TODOS os requisitos ao **menor custo**.
4. **Preencher o squad de trabalho** com as cartas escolhidas.
5. **Submeter** o desafio.

## 2. Camada de API do app (window.services) — por passo

| Passo | Serviço / método | Observação |
|---|---|---|
| Ler sets/desafios | `services.SBC.requestSets`, `requestChallengesForSet`, `loadChallenge(challenge)` | challenge traz os requisitos |
| Buscar cartas no clube | `services.Club.search(UTSearchCriteriaDTO)` → observável `.observe(ctx,(s,e)=>e.items)` | filtros: `level`, `rarities`, `ovrMin/Max`, `_position`, `sortBy`, `_untradeables`, `count`, `offset` |
| Química | `services.Chemistry.*` (cálculo de química do squad) | usado para validar requisito de química |
| Montar squad de trabalho | view/controller do SBC (não exposto globalmente) ou `repositories.Squad` | a UI mantém o squad temporário; submit lê dele |
| Salvar/Submeter | `services.SBC.saveChallenge(...)`, `services.SBC.submitChallenge(...)` | **submit consome as cartas — irreversível e toca a EA** |
| Pós-submit | `services.SBC.nItemMoved`, `removeItemsById`, `replaceItemsInSquads` | sincroniza inventário |

> Item de carta (`e.items[i]`): `.rating` (OVR), `.rareflag` (1=rare/0=common), `.untradeable`, `.staticData.name`, `defId`, ids únicos.

## 3. O "cérebro": algoritmo de seleção/otimização
O passo difícil é o passo 3. É um **problema de otimização combinatória**: escolher 11 (ou N) cartas do clube que satisfaçam simultaneamente:
- **Rating do time ≥ alvo** (a fórmula do FUT é não-linear — ver `SBCs-Solucoes.md`, seção da fórmula);
- **Química mínima** (liga/nação/clube + posições);
- **Qualidade/raridade/quantidade** (ex.: "min. gold", "11 rare", "min 6 da liga X");
- **Custo mínimo** (preferir o fodder mais barato / que se quer descartar).

Como resolvem na prática (heurística, não força bruta):
1. Pré-filtram o clube pelos requisitos "duros" (qualidade, raridade, liga/nação).
2. Ordenam por custo (ou por OVR, conforme a estratégia).
3. **Guloso + ajuste:** preenchem com as cartas mais baratas e vão **trocando as de menor OVR por outras um pouco maiores** até o rating do time bater o alvo (exatamente a lógica de "escada" que usamos manualmente).
4. Validam química; se faltar, trocam cartas por outras da liga/nação certa.
5. Param na **primeira combinação válida** (não buscam o ótimo global — buscam "válido e barato o suficiente").

Para o cálculo de rating-alvo, ferramentas usam tabelas de combinação (igual ao Futbin **SBC Rating Combinations**, `/26/squad-building-challenges/rating-combinations`).

## 4. Limites e detecção (por que o loop é arriscado)
- O app expõe **`UTCaptchaDAO`** → a EA injeta CAPTCHA contra automação.
- SBC tem **Hourly Limit (90/h)** e **Daily Limit (300/dia)** visíveis no app.
- O risco de ban **não** vem de "usar a API" (o app inteiro usa) — vem de **submeter em massa/alta frequência** sem ritmo humano. É isso que os ToS proíbem e o que dispara soft ban / ban de mercado.

## 5. Como eu (assistente) opero — a linha
- **Passos 1–3 (ler, buscar, calcular)** → faço 100% via API/JS (rápido, sem print, baixo risco — é só consulta/cálculo). É o grosso do valor.
- **Passo 4 (montar)** → pela UI (são ações locais, não tocam a EA), guiado por JS.
- **Passo 5 (submeter)** → **pontual, com confirmação sua, em ritmo humano**. NÃO em loop/lote automático.
- O que NÃO implemento: o botão "resolve-e-submete-tudo-sozinho" em loop (auto-SBC/auto-buyer contínuo). Esse é o componente que viola ToS e concentra o risco de ban.

> Resumo: o "AutoSBC" = `Club.search` (achar fodder) + solver de combinação (escada de rating + química) + `submitChallenge`. Tudo isso roda sobre `window.services`. A diferença entre uso seguro e arriscado é o **ritmo e o volume da submissão**, não a tecnologia.
