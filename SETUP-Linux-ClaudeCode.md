# Setup — Agente de Mercado no Claude Code (Linux)

> Roda o agente de análise de mercado fora do Cowork, direto no seu Linux, via **Claude Code**.
> O agente **analisa e recomenda** (lê o Futbin por fetch simples). **Não executa trades** no Linux — a compra/venda no app da EA precisa do navegador logado (Cowork no Mac ou manual).

## 1. Pré-requisitos
- Linux (Ubuntu/Debian/Fedora/RHEL/Arch/Alpine).
- Conta Anthropic com acesso ao Claude Code.
- `git`.

## 2. Instalar o Claude Code
Use o **instalador nativo** (o pacote npm `@anthropic-ai/claude-code` foi **descontinuado** na v2.1.113 — não use npm):
```bash
# instalador nativo (confira o comando atual em https://code.claude.com/docs/en/setup)
curl -fsSL https://claude.ai/install.sh | bash
claude --version          # confirma a instalação
claude                    # 1ª vez: faz login/autentica
```

## 3. Clonar o projeto
```bash
git clone https://github.com/rafaelprogrammer/claude-fc26.git
cd claude-fc26
```
O Claude Code lê o `CLAUDE.md` automaticamente — ele já contém as instruções do agente.

## 4. Rodar o agente
**Interativo** (você acompanha):
```bash
cd ~/claude-fc26
claude
# então digite:  roda o agente
```
**Headless / uma tacada** (para scripts e cron) — flag `-p`/`--print`:
```bash
cd ~/claude-fc26 && claude -p "roda o agente de análise de mercado e salve o relatório em relatorio-mercado.md"
```
O relatório sai em `relatorio-mercado.md`.

## 5. Agendar (cron) — rodar sozinho nas janelas
`crontab -e` e adicione (ajuste o fuso; exemplos em BRT):
```cron
# Análise de COMPRA — pico (mais oferta, preços baixos) ~13h BRT = 16h UTC
0 16 * * *  cd /home/SEU_USUARIO/claude-fc26 && /CAMINHO/claude -p "roda o agente (foco COMPRA)" >> agente.log 2>&1
# Análise de VENDA — madrugada (preços altos) ~2h BRT = 5h UTC
0 5  * * *  cd /home/SEU_USUARIO/claude-fc26 && /CAMINHO/claude -p "roda o agente (foco VENDA)" >> agente.log 2>&1
```
Notas de cron (importantes):
- Use o **caminho completo** do binário: descubra com `which claude`.
- O cron **não carrega seu shell profile** → exporte a credencial na própria linha (ex.: `ANTHROPIC_API_KEY=...`) ou faça `source ~/.env` antes do comando.
- Para rodar sem prompts de permissão no modo automático, pode-se usar `--print --dangerously-skip-permissions` (avalie o risco; aqui o agente só lê a web e escreve arquivos locais).

## 6. O que NÃO roda no Linux
- **Comprar/vender no app da EA** (precisa da sessão logada no navegador). No Linux o agente só faz a **análise/recomendação**; a execução fica no Cowork (Mac) ou manual.
- Se quiser, o relatório gerado aqui pode ser commitado/pushado e usado como base para executar os trades no Mac.

Sources: [Claude Code Docs — headless](https://code.claude.com/docs/en/headless) · [Claude Code Linux install guide](https://www.morphllm.com/claude-code-linux)
