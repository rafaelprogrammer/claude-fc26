# SBCs — Regras e Soluções (Club SELVA)

> Registro de como resolver cada SBC, com as regras de preservação de cartas definidas pelo Rafael.
> Atualizar conforme novos SBCs e regras forem definidos.

## Como resolver um SBC na Web App (fluxo geral)
1. **SBC** (menu lateral) → aba **All** → buscar o nome na barra de busca → clicar no SBC.
2. Ler **Challenge Requirements** (canto direito): nº de jogadores, qualidade mínima, raridade, rating mínimo do time, química, nacionalidade/liga, etc.
3. Clicar num slot ativo → **Add Player** → abre o **Club Search** com filtros:
   - **OVR Range** (Min/Max) · **Quality** (Bronze/Silver/Gold) · **Rarity** (Common/Rare) · **Position** · **Chemistry Style**
   - Toggles: *Untradeables Only*, *Exclude Active Squad Players*.
   - O dropdown **Rarity** mostra a **contagem** de cartas que batem os filtros atuais (ótimo para saber quanto fodder existe).
4. Adicionar os jogadores aos slots respeitando as regras.
5. Conferir requisitos satisfeitos (barra "Requirements x/x") e **Submit** (consome as cartas — irreversível → confirmar com o Rafael).

### Mecanismos úteis
- **"Exclude from SBC Solutions"** (no menu de cada carta): impede que a auto-solução use a carta. Ideal para proteger titulares/cartas reservadas.
- **Unassigned Items bloqueiam a abertura de novos packs**: é preciso atribuir/descartar os itens não atribuídos antes de abrir pack.
- **SBC Storage** tem limite de **100 itens** (duplicatas untradeable vão pra lá). Cheio = duplicatas ficam presas no Unassigned.
- Auto-solução da web app (Generate Solution / Solve Challenge) busca o mais barato e **NÃO respeita regras de OVR** — para regras como "≤82", montar manualmente via filtros.

---

## SBC: 2x 84+ Upgrade
- **Tipo:** Upgrade, **Repeatable**. Recompensa: 1x pack "2x 84+ Rare Gold Players" (untradeable). Expira em ~3 dias (recorrente).
- **Requisitos do time:**
  - Número de jogadores: **6**
  - Player Quality: **Mín. Ouro**
  - Rare: **Mín. 6** (todos os 6 precisam ser raros)
  - Sem exigência de rating do time nem de química.

### Regra do Rafael para este SBC
- Pode usar cartas do clube com **overall ATÉ 82 (≤82), somente**.
- Se faltar carta, **abrir os packs do Rafael** (que podem conter cartas elegíveis). NÃO comprar.

### Situação do clube (15/06/2026)
- Filtro Gold + Rare + OVR ≤82 → só **2 cartas** no clube:
  - **Vicario** 82 GK
  - **Adama Traoré** 76 (PAC 94)
- Faltam **4** cartas Gold Rare ≤82.

### Solução planejada
- Abrir **1× "5x Max.78 Rare Gold Players Pack"** (Rafael tem 5 unidades) → garante **5 cartas Rare Gold ≤78** (todas dentro da regra).
- Montar: 2 do clube (Vicario, Adama) + 4 do pack = 6 jogadores. Submeter.

### Bloqueio encontrado (pendente de decisão)
- Ao tentar abrir o pack: **Unassigned Items Remain**. Item preso: **Reijnders 86 CM (duplicata untradeable)**.
- **SBC Storage cheio (100/100)** → a duplicata não tem pra onde ir.
- Para desbloquear é preciso: reciclar/quick-sell o Reijnders, OU liberar espaço no SBC Storage.
- Obs: Reijnders 86 pode ser útil no **86 OVR Token Swap** (pede 8x cartas 86 exatas) → avaliar antes de descartar.
- **Status: aguardando decisão do Rafael. Nada foi descartado nem submetido.**

---

## SBC: 84+ TOTW Upgrade
- **Tipo:** Upgrade, **Repeatable**. Recompensa: 1x pack "84+ TOTW 1-30 Player" (1 jogador TOTW das semanas 1–30, rating 84+, untradeable). Expira em ~17 dias.
- **Requisitos do time:**
  - Número de jogadores: **11** (time completo)
  - **Team Rating: mín. 84**
  - Sem exigência de química.

### Objetivo do Rafael
- Usar este SBC para **escoar o SBC Storage** (quando 100/100) e gerar TOTW para outros SBCs.

### Regra de cartas (definida pelo Rafael)
- **Somente OURO RARO** (gold rare) — nada de cartas especiais (TOTW/promo/roxas).
- Pode usar **tradeable E untradeable**, OVR **até 86**.
- **Estratégia de economia (equilíbrio):** começar sempre pelas cartas de **MENOR overall** (ex: 82, 83, 83…) e usar as mais altas (85/86) **só para complementar** até o time atingir **rating 84**. Minimizar o gasto de cartas altas.
  - Caso só haja cartas altas (ex: só 86), usar — mas o ideal é equilibrar.
  - Ir ajustando até fechar 84 com o melhor equilíbrio possível.
- **Escada de troca (menor desperdício):** ao complementar para subir de 83→84, trocar primeiro pelas cartas de **menor overall que ainda resolvam**: usar **84** (se houver quantidade suficiente), senão completar com **85**, só então **86**. Sempre checar se há carta menor que feche o resultado antes de usar uma maior.
- **Método:** ler via JS o inventário de gold rare por OVR (quantas 83/84/85/86 disponíveis) e calcular a combinação ótima (máximo de cartas baixas) que atinge rating de time 84, antes de fazer as trocas.
- Proteger cartas premium / elenco titular (não usar).
- Ferramenta de apoio: Futbin **SBC Rating Combinations** (`/26/squad-building-challenges/rating-combinations`) calcula a combinação de OVR mais barata para um rating-alvo.

### Execução no Squad Builder
- Filtros: Quality=**Gold**, Rarity=**Rare**, Max OVR=**86**, **Exclude Active Squad Players** ON, Untradeables Only **OFF** (pode usar ambos), Sort By=**Rating Low to High** (pega as menores primeiro). Build e ajustar manualmente se rating < 84.

### Nota importante (extensão)
- A extensão **FC Enhancer deve estar desativada** — com ela ativa, os cards de SBC não abrem (overlay intercepta o clique). Rafael desativou em chrome://extensions + refresh. Ver [[fut26-fc-enhancer-off]] na memória.
- **Status: requisitos aprendidos; estratégia de montagem a confirmar com o Rafael.**
