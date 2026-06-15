# Fluxo Git / GitHub — Projeto claude-fc26

> Guia para versionar este projeto. Carregar junto com a base de conhecimento.

## Repositório
- **Remoto:** `https://github.com/rafaelprogrammer/claude-fc26.git`
- **Branch principal:** `main`
- **Identidade dos commits:** `rafaelprogrammer` / `rafa.jesuscristo@gmail.com`
- Pasta local (Mac do Rafael): `~/Documents/claude-fc26`
- No sandbox (bash): `/sessions/<sessão>/mnt/claude-fc26`

## Como COMMITAR a partir do sandbox

O mount protege exclusão de arquivos, então o git às vezes não consegue remover
`index.lock` / arquivos temporários. Para evitar isso, usar um **índice alternativo** em `/tmp`:

```bash
cd /sessions/<sessão>/mnt/claude-fc26
git config user.name "rafaelprogrammer"
git config user.email "rafa.jesuscristo@gmail.com"
export GIT_INDEX_FILE=/tmp/fc26.index
rm -f /tmp/fc26.index
git add -A
git commit -m "mensagem descritiva"
```

Avisos do tipo `unable to unlink ... Operation not permitted` são **inofensivos**
(só arquivos temporários que o mount não deixa apagar). O commit é gravado normalmente.

## PUSH — feito pelo Rafael

O push **não funciona pelo sandbox**:
- SSH bloqueado (sem resolução de DNS para github.com).
- HTTPS exige token/credencial, que não é inserido por aqui (regra de segurança).

Como o commit já fica gravado no `.git` da pasta local, **o push é feito pelo Rafael** no
terminal do Mac (onde o Keychain/credenciais do GitHub já estão configurados):

```bash
cd ~/Documents/claude-fc26
git push -u origin main      # primeira vez
git push                      # depois
```

> Se preferir automatizar: configurar um credential helper ou usar a CLI `gh auth login`
> uma vez no Mac; depois o push fica sem fricção. O token continua não sendo inserido por aqui.

## Rotina sugerida
1. Atualizar/criar arquivos do projeto (base de conhecimento, soluções de SBC, anotações).
2. Fazer `git add -A` + `git commit` (passo acima).
3. Avisar o Rafael que há commit(s) pendentes de push.
4. Rafael roda `git push` no Mac.
