# Trading no Mercado de Transferências — FC 26 (Club SELVA)

> Base de conhecimento para fazer **trade e lucrar coins** no FC 26 Ultimate Team.
> Foco: ler tendências (Futbin + mercado do app) e comprar barato / vender caro.
> Saldo atual do Rafael: ~709k coins. Atualizado: 16/06/2026.

## 1. Conceitos-chave
- **BIN (Buy It Now):** preço de compra imediata. **Bid (lance):** leilão, pode sair mais barato.
- **EA Tax: 5%** sobre TODA venda. Lucro real = (preço de venda × 0,95) − preço de compra. Sempre calcular o líquido.
- **Peak hours** (mais gente jogando, ~16h–20h horário UK / ~12h–16h BRT): preços tendem a **cair** (mais oferta) → bom para **COMPRAR**.
- **Non-peak hours** (noite/madrugada UK): menos oferta → preços **sobem** → bom para **VENDER**.
- **Price ranges:** cada carta tem preço mínimo e máximo definido pela EA; preço nunca sai dessa faixa.

## 2. Métodos de trade (do mais ativo ao mais passivo)
| Método | Como funciona | Perfil |
|---|---|---|
| **Sniping** | Filtrar o mercado com BIN baixo e atualizar rápido em horário de pico p/ pegar listagens subvalorizadas. | Ativo, exige velocidade — **cuidado com softban** (sem rajadas) |
| **BIN flipping** | Comprar um snipe bem abaixo do valor e revender no BIN normal. | Médio; poucos snipes, mas lucro alto por carta |
| **Card flipping** | Acompanhar 5–10 cartas, anotar mínimo (madrugada) e máximo (pico), comprar barato e vender no pico. | Médio, baseado em tendência |
| **Bidding / Mass bidding** | Dar lances um pouco abaixo do BIN em vários itens que vendem rápido; relistar com pequeno lucro. | Bom para volume com menos competição de snipers |
| **Club stocking** | Estocar fodder de SBC popular / TOTW / gold quando o preço cai, vender quando a demanda volta (novos SBCs). | Passivo, longo prazo, mais seguro |
| **Bronze/Silver packs** | Comprar packs baratos, abrir e vender o conteúdo (jogadores/consumíveis com demanda). | Estável o ciclo todo |

## 3. Fontes de mercado (Futbin e outras)
**Futbin** (https://www.futbin.com/ — conta "LORDED", jogo em FC 26):
- **Market Index** (`/market` = Index 100; `/market/83`, `/market/85`, `/market/86`, `/market/Icons`): "cestas" de cartas que mostram **inflação/queda/recuperação** do mercado em tempo real. Index 100 = 83 gold + 16 silver + 1 bronze (mercado padrão).
  - Gráfico **Daily** e **Hourly**, filtrável por plataforma.
- **Market Player List** (`/market-player-list`): jogadores em movimento de preço.
- **Price Range Updates** (`/priceranges` ou `/prp`): mudanças de faixa de preço da EA.
- **Página do jogador** (`/26/player/{id}/{nome}`): gráfico histórico de preço, preço atual por plataforma, previsão.
- **Trackers / Upgrades & Downgrades** (`/dynamic-players`, `/26/fc-upgrades`): quem está subindo/caindo.

**Outras fontes:** FUT.GG, FUTWIZ (preços e gráficos alternativos), comunidades (Reddit r/fut, YouTube de trading) para descobrir SBCs novos que aquecem fodder.

## 4. Como ler tendência e decidir
1. **Mercado geral:** olhar o Market Index (subindo = mercado inflando, bom p/ vender estoque; caindo/crash = bom p/ comprar barato).
2. **Carta específica:** abrir a página no Futbin → gráfico → identificar **low point** (comprar) e **high point** (vender).
3. **Gatilhos de alta:** novo SBC que pede aquele fodder, nova promo, jogador "meta". **Gatilhos de baixa:** fim de promo, lightning rounds, packs no mercado.
4. **Sempre** conferir o preço REAL no mercado do app antes de fechar (Futbin é referência, pode divergir).

## 5. Onde estamos posicionados (Club SELVA)
- **44 jogadores ~83 OVR** na Transfer List (fodder) — candidatos a venda/club stocking conforme SBCs aquecerem.
- ~709k coins de banca para investir.

## 6. Regras de operação (trading)
- **EA Tax 5%** sempre no cálculo de lucro.
- **Anti-softban (crítico):** comprar/vender/dar lance com **pausa entre ações, sem rajada/loop**. Sniping em alta frequência é o maior gatilho de ban → fazer devagar. Ao 1º sinal de "mercado bloqueado", PARAR. (ver memória [[fut26-softban]])
- **Leitura/análise via JS/API e Futbin** (rápido, seguro); **compras/vendas pontuais com confirmação do Rafael**.
- **Nunca** comprar packs nem gastar FC Points (regra do Rafael).
- Definir **margem mínima de lucro** por trade (ex.: ≥10% líquido) antes de comprar.
