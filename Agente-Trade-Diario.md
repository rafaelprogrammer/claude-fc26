# Agente de Análise de Mercado — Trade Diário (FC 26)

> Função: varrer o mercado e listar as **melhores cartas para day trade** (comprar e vender no dia), em **bronze, prata e ouro**, com preço de entrada/saída e margem líquida.
> Operação: o agente **ANALISA e RECOMENDA**. A compra/venda é **pontual, no comando do Rafael, em ritmo humano** (anti-softban). Nunca executa em loop automático.

## 1. Fontes de dados
- **Futbin** (logado "LORDED", FC 26):
  - Market Index `/26/market` (+ `/82`…`/86`, `/Icons`): humor do mercado (subindo/caindo/momentum).
  - **Market Player List** `/26/market-player-list`: cartas em movimento (preço + variação).
  - Top Gainers / Top Losers (na página do índice): maiores altas/baixas do dia.
  - Página do jogador `/26/player/{id}/{nome}`: gráfico (low/high point), **Price Range** (teto/piso da EA), preço atual.
  - Price Range Updates `/26/priceranges`.
- **Mercado do app** (Web App da EA): confirmar o preço REAL e o menor BIN antes de operar.

## 2. Critérios de seleção (o que faz uma boa carta de trade)
1. **Liquidez** — vende rápido (alta demanda; cartas meta, fodder de SBC, química popular).
2. **Margem líquida ≥ alvo** — lucro = (venda × 0,95) − compra. Mirar **≥ 10–15% líquido** por flip.
3. **Posição no Price Range** — comprar perto do **piso**, NUNCA perto do **teto** (ex.: Cubarsí a 126k de teto 150k = topo, evitar).
4. **Tendência intradiária** — comprar no **low point** (horário de pico, mais oferta), vender no **high point** (madrugada).
5. **Spread consistente** — diferença estável entre o menor BIN e o preço de venda.
6. **Gatilho** — SBC novo / promo aquecendo um tipo de carta (ex.: SBC de CB → CBs sobem). Comprar ANTES do pico, vender no pico.

## 3. Por tipo de carta
- **Ouro:** fodder de SBC (83–86), metas em low point, ícones líquidos. Melhor liquidez geral.
- **Prata:** pratas RARAS de ligas/nações populares (demanda de química e de SBCs "silver"), e o **Silver Pack method** (comprar pack barato, vender conteúdo). Margem % alta, valores baixos.
- **Bronze:** **Bronze Pack method** (comprar/abrir/vender conteúdo) e bronzes raros demandados por objetivos/SBC. Volume alto, lucro por unidade pequeno → fazer em poucas levas, sem rajada.

## 3.1 Volume / frequência por tipo (regra do Rafael)
- **Bronze / prata / ouro de baixo valor (poucas coins):** fazer o **máximo de trades possível** — a margem por carta é pequena, o lucro vem do **volume**.
- **Cartas de alto overall / alto valor (muitas coins):** fazer **2–3 trades**, conforme o mercado de transferências permitir — a margem por unidade já é grande.

> ⚠️ **Ressalva crítica (anti-softban):** "máximo possível" = máximo **dentro do ritmo humano seguro** — sempre com **pausa entre ações e em levas**, NUNCA em rajada/loop. Volume alto sem pausa é o **gatilho nº 1 de softban**. Então o volume vem do **tempo** (muitas operações espaçadas ao longo do dia), não da **velocidade**. Ao 1º sinal de bloqueio, parar.

## 4. Formato de saída (o relatório do agente)
Para cada oportunidade: **Carta | Tipo | Preço de compra-alvo | Preço de venda-alvo | Margem líquida % | Gatilho/Motivo | Risco**.
Mais o **humor do mercado** no topo (Index 100 + momentum → comprar vs vender) e o **timing** (melhor janela do dia).

## 5. Regras de segurança (críticas)
- **Anti-softban:** day trade = sniping/flip ativo, o método que MAIS arrisca ban se feito em volume/rajada. Operar **devagar, com pausa entre ações, em poucas levas**. Ao 1º sinal de "mercado bloqueado", PARAR. (ver [[fut26-softban]])
- **Taxa EA 5%** sempre no cálculo.
- **Nunca comprar packs com FC Points** nem gastar dinheiro real.
- Definir **stop**: se uma carta comprada cair, vender no piso e seguir (não "casar" com a carta).
- O agente **não compra/vende sozinho** — gera a lista; execução é pontual e confirmada.

## 6. Cadência sugerida (se agendado)
- **Janela de COMPRA:** horário de pico (mais oferta, preços baixos) → ~12h–16h BRT.
- **Janela de VENDA:** madrugada/fora de pico (menos oferta, preços altos).
- Rodar a análise no início de cada janela e reportar as oportunidades.
