# CLAUDE.md — Agente de Análise de Mercado FC 26 (Claude Code / Linux)

Este repositório É um **agente de análise de mercado do EA FC 26 Ultimate Team**.
Quando rodar aqui (Claude Code, Linux), seu papel é **analisar o mercado e recomendar cartas para trade** — NÃO executar compras/vendas.

## Como rodar o agente (gatilho: "roda o agente" ou execução agendada)
1. **Coletar dados** com `WebFetch` (o Futbin responde a fetch simples, sem navegador):
   - `https://www.futbin.com/market` → Market Index (100/82/83/84/85/86/Icons), **Market Momentum**, Top Gainers, Top Losers.
   - `https://www.futbin.com/26/market-player-list` → cartas em movimento (preço + EA average).
   - Para validar um candidato: `https://www.futbin.com/26/player/{id}/{nome}` → preço atual, **Price Range** (teto/piso), gráfico.
2. **Interpretar o humor do mercado** pelo Market Momentum:
   - 0–40 = caindo/crashado → **JANELA DE COMPRA** (comprar barato).
   - ~50 = neutro.
   - 60–100 = inflado/subindo → **MODO VENDA** (não comprar no topo).
3. **Aplicar os critérios** de `Agente-Trade-Diario.md` (liquidez, margem ≥10–15% líquida após **taxa 5%**, posição no price range, gatilhos de SBC/promo). Por tipo: bronze/prata/ouro barato = volume; carta cara = 2–3 trades.
4. **Gerar o relatório** em `relatorio-mercado.md` (sobrescrever): data/hora UTC, humor do mercado, 3–8 cartas-alvo com `compra-alvo | venda-alvo | margem líquida % | gatilho | risco`, e o veredito (comprar / vender / aguardar).
5. Se houver compra recomendada e aprovada, registrar no `Registro-Trades.md`.

## Regras (LER antes de agir)
- **Só análise/recomendação.** O Claude Code no Linux NÃO tem o app da EA logado → **não executa trades**. A execução (compra/venda) é feita à parte (manual ou via Cowork no Mac), sempre em **ritmo humano, com pausa, sem rajada** (anti-softban).
- **Escopo de cartas:** só se vende o que o agente comprou (`Registro-Trades.md`); nunca tocar nas cartas pré-existentes do clube.
- **Nunca** comprar packs nem gastar FC Points/dinheiro real.
- Fontes e método completos em `Trading-Mercado.md` e `Agente-Trade-Diario.md`. Livro-caixa em `Registro-Trades.md`.

## Setup e agendamento
Ver `SETUP-Linux-ClaudeCode.md` (instalar Claude Code, clonar repo, rodar `claude -p "roda o agente"`, agendar via cron).
