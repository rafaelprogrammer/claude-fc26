# FC 26 Ultimate Team — Web App: Base de Conhecimento

> Referência para Claude atuar como especialista no clube **SELVA** do Rafael.
> Última atualização do mapeamento: **15/06/2026** (Season 8 — Festival of Football).
> Objetivo: carregar este arquivo em vez de re-navegar a web app a cada sessão.

---

## 1. ACESSO

- **URL:** https://www.ea.com/ea-sports-fc/ultimate-team/web-app/
- **Acesso:** via Claude in Chrome (MCP). Navegador conectado: "SIGA-Legado" (macOS).
- **Login:** feito **pelo Rafael** (Claude NÃO digita credenciais EA — e-mail, senha, 2FA são proibidos).
- **Overlay de terceiros:** há uma extensão "FC Enhancer" / "FUT Enhancer" sobreposta na página (mostra "Buy Subscription", "Sign in", preços BIN sugeridos, botões "Snipe With Vps/Trader", "FUTNEXT", "Trader", "Enhancer" no menu). NÃO é oficial da EA. Ignorar para ações oficiais.

### Como navegar (eficiência de tokens)
- Menu lateral fixo à esquerda. Coordenadas aproximadas (tela 1568px):
  - Home (29,19) · Squads (29,59) · SBC (29,95) · Evolutions (29,130) · Transfers (29,166) · Trader (29,202)* · Enhancer (29,236)* · Store (29,267) · Club (29,308) · Settings (29,748)
  - *Trader/Enhancer são da extensão, não oficiais.
- **Preferir `get_page_text`** em vez de screenshot para ler listas (SBCs, Transfer List, Packs) — muito mais barato em tokens.
- Usar screenshot só quando precisar confirmar layout/coordenadas ou badges visuais (ex: quantidade de packs).

---

## 2. MENUS / FUNCIONALIDADES

### HOME
Dashboard. Mostra: Unassigned Items, FC Hub (objetivos da temporada), atalho SBC, Path to Glory, Evolutions, Transfer List, Active Squad. Topo direito: saldo de **coins**, **FC Points**, e uma terceira moeda (provavelmente tokens/contador da extensão).

### SQUADS
- **Active Squad:** elenco titular. Mostra formação, Rating e Chemistry (química, máx 33).
- **Squad Management:** gerenciar/criar elencos.
- **Team of the Week:** TOTW.

### SBC (Squad Building Challenges)
- Abas: All · Favourites · Players · Upgrades · Challenges · Icons · Foundations · Swaps · Hidden.
- Botão **"Solve Daily SBCs"**. Limites: **Hourly Limit (ex: 60/90)** e **Daily Limit (ex: 116/300)** — quantos SBCs podem ser submetidos por hora/dia.
- Cada SBC mostra: requisitos, recompensa (Group Rewards), se é Repeatable, prazo (Expires In) e votos 👍/👎 da comunidade.
- **Submeter SBC consome jogadores do clube de forma irreversível** → sempre confirmar com o Rafael antes.

### EVOLUTIONS
- Abas: My Evolutions · Evolutions · (promo, ex: FoF Pelé) · PlayStyles+ Lab · PlayStyles Lab · Rewards · Roles · Cosmetics · Training Camp.
- Cada Evo: custo (coins/grátis), upgrades de atributos/PlayStyles, prazo, repetibilidade.
- Evoluir = melhorar um jogador do clube ao longo do tempo até o máximo indicado.

### TRANSFERS
- **Search the Transfer Market:** buscar/comprar/dar lance em jogadores e consumíveis.
- **Transfer List:** itens à venda/para vender (limite ~100). Campos: Selling / Sold / Bid Total / Bin Total.
- **Transfer Targets:** itens que você está dando lance/observando (Winning / Outbid).
- Opções por jogador: List on Transfer Market, List for Current Lowest BIN, Quick Sell, Compare Price, Price Trends, etc.

### STORE
- **Unassigned Items:** itens ganhos ainda não atribuídos ao clube (abrir/atribuir).
- **My Packs:** packs que o Rafael **já possui** (botão "Open"/"Quick Open"; selo verde no canto = quantidade). REGRA: pode abrir.
- **Packs** (Promo/Provisions/Packs For You/Classic): packs **à venda** → custam coins/Points → NÃO comprar.
- **Items:** cosméticos/itens à venda.
- **Points:** compra de FC Points com dinheiro real → NUNCA.
- Ícones nos packs: seta circular verde = tradeable/reciclável; ícone vermelho = untradeable.

### CLUB
Inventário completo do clube (jogadores, consumíveis, staff, stadium, etc).

---

## 3. CONCEITOS ESPECÍFICOS

- **Coins:** moeda principal. Saldo atual ~640k.
- **FC Points:** moeda premium (dinheiro real). NÃO gastar.
- **Fodder:** jogadores usados como "material" para SBCs/Token Swaps. Os 83 OVR comuns são o fodder mais útil.
- **BIN (Buy It Now):** preço de compra imediata no mercado.
- **OVR:** overall do jogador. SBCs/Swaps frequentemente pedem ratings exatos ou mínimos.
- **Token Swaps (FoF Tokens):** SBCs que trocam X jogadores de um OVR exato por tokens da promo. Tokens depois trocam por jogadores/packs. Quanto maior o OVR, mais tokens por jogador.
- **Chemistry (Química):** sinergia liga/nação/clube. 33/33 = máxima.
- **Untradeable:** item que não pode ser vendido no mercado (só usado em SBC/jogado).
- **Path to Glory (PTG) / Showdown / National Pride:** tipos de cartas especiais da promo Festival of Football (Season 8).

---

## 4. SNAPSHOT DO CLUBE SELVA (15/06/2026)

- **Coins:** 640.197
- **Elenco titular:** formação 4-4-1-1 (2), **Rating 95**, **Química 33/33** (máxima — não precisa ajuste).
- **Unassigned Items:** 1.
- **Transfer List:** 44 jogadores, NÃO listados (Selling 0). Maioria **83 OVR**. Exceções: Pajor 88, Irene Paredes 88, Koundé 87.
  - 83 OVR repetidos: vários Zubimendi, Kovačić, Rabiot, Kamara, Modrić, Retegui, Mané, Aleix García, Milenković, Rrahmani, etc. → fodder ideal para Token Swaps 83.

### Inventário de PACKS (My Packs — Claude pode abrir)
| Pack | Qtd | Conteúdo |
|---|---|---|
| Silver Pack | 78 | 12 silver, 1 raro |
| Bronze Players Premium | 42 | 12 bronze, 3 raros |
| Silver Players Premium | 28 | 12 silver, 3 raros |
| x2 Players Pack | 22 | 2 jogadores, 1 raro |
| Provisions Pack | 13 | 40 jogadores ≤80 OVR |
| 11x Gold Players Pack | 5 | 10 comuns + 1 raro gold |
| 5x Max.78 Rare Gold | 5 | 5 raros gold ≤78 |
| Small Gold Players | 2 | 6 gold, 1 raro |
| 2x 84+ Rare Gold | 1 | 2 raros gold 84+ |

---

## 5. SBCs ABERTOS (snapshot 15/06/2026)

**Jogadores especiais (PTG / Icon / Showdown):**
- Nemanja Vidić (eCL Champion ICON 94) — 0/11 — 9 dias
- Bafana Bafana's Dream → **Future Stars ICON Xavi** (~620k fodder) — 0/3 — 23 dias
- Alexia Putellas (End of an Era 96) — **8/18** — 19 dias
- Martin Ødegaard PTG 95 — 0/5 · Pedro Neto PTG 95 — 0/9 · Mac Allister PTG 95 — 0/10 · Mazraoui PTG 93 · Schlager PTG 93 · Chris Richards 93 · Livramento 91 · Baturina 91

**Picks / Upgrades úteis:**
- 1 of 3 91+ TOTS Nations/UEFA Pick · 1 of 4 90+ Encore Icon Pick · 1 of 3 93+ UEFA/TOTS Pick
- Provisions Upgrade (rep 7) · 5x 77+ (rep) · 2x 84+ (rep) · 84+ TOTW Upgrade · Mixed Leagues Upgrade
- Bronze/Silver/Gold Upgrade (reciclar fodder)

**Token Swaps (Festival of Football Tokens) — repetível 1x cada, expira em ~23 dias:**
| Swap | Jogadores necessários | Tokens |
|---|---|---|
| 83 OVR | 22x (83 exato) | 10 |
| 84 OVR | 18x | 10 |
| 85 OVR | 8x | 10 |
| 86 OVR | 8x | 15 |
| 87 OVR | 7x | 30 |
| 88 OVR | 5x | 40 |
| 89 OVR | 5x | 50 |
| 90 OVR | 5x | 60 |
| 91 OVR | 5x | 75 |

> Oportunidade-chave: o Rafael tem ~41 jogadores 83 OVR na Transfer List → cobre quase 2x o "83 OVR Token Swap".

---

## 6. FUTBIN (https://www.futbin.com/) — ferramenta de apoio

Site de referência externo (parceiro oficial EA) para preços, melhores jogadores e soluções de SBC.
Acessado via Chrome MCP. Conta logada: **"LORDED"**. Seletor de jogo no topo deve estar em **FC 26** (combobox, value="26").

> Dica de eficiência: as URLs abaixo abrem direto a seção. Navegar pela URL (`navigate`) + `get_page_text` é muito mais barato que clicar pelos menus. Páginas de jogador/SBC podem ser client-rendered — se `get_page_text`/`web_fetch` vier vazio, usar `navigate` + `get_page_text` no Chrome (renderiza JS).

### Menu PLAYERS — base de jogadores e preços
- Base de jogadores: `/26/players` (filtros por rating, posição, liga, nação, preço, PlayStyles)
- Popular Players: `/popular` · New Players: `/26/latest`
- Trackers (preços dinâmicos): `/dynamic-players`
- Upgrades & Downgrades (variação de preço): `/26/fc-upgrades`
- Roles: `/26/roles` · Playstyles: `/26/playstyles`
- Player Game Performance: `/26/pgp` · Perfect Chemistry: `/26/perfect-chemistry`
- **Página de cada jogador:** `/26/player/{ID}/{nome}` → preço atual por plataforma, histórico, PlayStyles, química, comparações. Ex: Mbappé `/26/player/40/kylian-mbappe`.

### Menu SBCs — soluções (caso de uso principal)
- **Active SBCs:** `/26/squad-building-challenges` (todos os SBCs ativos com custo estimado)
- **Cheapest Player By Rating:** `/26/squad-building-challenges/cheapest` (jogador mais barato de cada OVR — essencial para montar fodder)
- **Community SBC Solutions:** `/26/squad-building-challenges/squads` (soluções enviadas pela comunidade, mais baratas)
- **SBC Rating Combinations:** `/26/squad-building-challenges/rating-combinations` (calcula combinações de OVR para atingir rating-alvo de um time)
- **Best value SBCs:** `/26/squad-building-challenges/best-sbcs` (custo x recompensa)

### Menu MARKET — preços de mercado
- Market Player List: `/26/market-player-list` · Index 100: `/26/market`
- Price Range Updates: `/26/priceranges` · Manager Prices: `/26/manager-prices`
- Consumable Prices: `/26/consumables`

### Menu SQUAD BUILDER / SQUADS / EVOLUTIONS
- Squad Builder: `/26/squad-builder` · Community Squads: `/26/community/squads/builder`
- Tactics: `/26/tactics-and-formations/builder`
- Promo squads: `/26/squads` · TOTW/Promo: ex `/26/totw/PathToGlory`, `/26/totw/UCLWinners`
- Evolutions: `/26/evolutions` · Evolution Builder: `/26/evolutions/builder` · Evolution Players: `/26/players/evolutions`
- Leaderboards `/26/leaderboards` · Hubs: Clubs/Leagues/Nations `/hubs/...` · Objectives `/26/objectives`

### Outros úteis
- **Token Store (FoF):** `/token-store?token=fof&page=spend` — ver pelo que os FoF Tokens trocam (relevante p/ os Token Swaps do clube).
- FUT Card Creator `/26/fut-card-creator` · Tier list `/tier-list-builder` · News `/news`
- Banner "Try Ad-Free / Subscription" (`/subscription`) → é assinatura paga, NÃO assinar.

### Como usar Futbin + Web App juntos
1. SBC novo aparece na Web App → abrir `/26/squad-building-challenges` no Futbin p/ ver custo e melhor solução.
2. Para fodder de rating exato → `Cheapest Player By Rating` mostra o mais barato de cada OVR.
3. Antes de vender/comprar carta → checar preço na página do jogador no Futbin.
4. Conferir o preço real no mercado da Web App antes de fechar (preços do Futbin são referência, podem divergir).

---

## 7. REGRAS DE ATUAÇÃO (definidas pelo Rafael)

1. **NUNCA comprar packs** (gasta coins/FC Points). Só ABRIR packs que ele já possui (My Packs / Unassigned).
2. **NUNCA comprar FC Points** nem gastar dinheiro real.
3. Claude **não digita credenciais EA** (login é do Rafael).
4. Antes de qualquer ação **irreversível que consome jogadores** (submeter SBC, quick sell, descartar), **confirmar** com o Rafael.
5. Comprar jogadores no mercado (gasta coins) → confirmar antes.
6. Ler listas com `get_page_text` para economizar tokens.

---

## 8. SOFT BAN — cuidado crítico ao operar pelo navegador

**O que é:** punição temporária da EA quando detecta muitas ações em curto período. Afeta principalmente o Mercado de Transferências (fica "locked"), mas também pode bloquear abrir packs / resolver SBCs / atualizar coins. A EA NÃO divulga os limites exatos. Automação e cliques rápidos são gatilhos clássicos → como o Claude opera via Chrome MCP, o risco é real.

**Sintomas:** "Transfer Market locked", erro ao listar/comprar, "credits cannot be updated", mercado não carrega, ações que não respondem. Dura de minutos a horas.

**Limites visíveis na própria web app:**
- SBC: **Hourly Limit (90/h)** e **Daily Limit (300/dia)** — respeitar; não submeter SBCs em massa.

**Regras de ritmo do Claude (anti-softban):**
1. **Pausar entre ações** — usar `wait` (~2-4s) entre cliques/transações; nunca disparar rajadas.
2. **Não encadear muitas ações** seguidas (listar/comprar/abrir pack/submeter SBC) sem intervalo.
3. **Abrir packs com calma**, um de cada vez, com pausa — não abrir dezenas em sequência.
4. **No mercado**, espaçar buscas/lances/compras; evitar muitas páginas rápidas.
5. Se surgir qualquer sinal de bloqueio, **PARAR imediatamente** e avisar o Rafael; não insistir (insistir estende o ban).
6. Preferir poucas ações planejadas em vez de muitas pequenas e rápidas.

> Pendência: o SBC "84+ TOTW Upgrade" foi ocultado por engano (botão "ocultar"); reverter na aba **Hidden** do menu SBC ao retomar — com calma.
