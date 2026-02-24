---
name: pr
description: Use quando precisar criar uma pull request a partir das alterações atuais do repositório. Acionado por pedidos como "cria uma PR", "abre PR", "manda pra review".
model: haiku
---

# Criar Pull Request

## Overview

Workflow para criar pull requests padronizadas como rascunho, com rastreabilidade de task e formato consistente de body.

## Contexto

Colete o estado atual do repositório:

- Status do Git: !`git status`
- Diff completo: !`git diff HEAD`
- Branch atual: !`git branch --show-current`

## Workflow

### 1. Perguntar o Task ID

**OBRIGATÓRIO:** Use `AskUserQuestion` para perguntar ao usuário o ID da task relacionada. Nunca invente, assuma ou peça para o usuário "substituir depois".

Exemplo: "Qual o ID da task relacionada a esta PR? (ex: 82)"

O valor será usado no título: `<tipo>: <descrição> [TASK-<id>]`

### 2. Criar branch (se estiver na main)

Se a branch atual for `main`, crie uma nova branch baseada no Task ID:

```bash
git checkout -b TASK-<id>
```

### 3. Commit

Adicione os arquivos e crie um commit com mensagem descritiva:

```bash
git add <arquivos relevantes>
git commit -m "<tipo>: <descrição da alteração>"
```

### 4. Push

```bash
git push -u origin <nome-da-branch>
```

### 5. Criar a PR como rascunho

**OBRIGATÓRIO: Sempre use `--draft`.** Nunca omita essa flag.

```bash
gh pr create --draft --title "<tipo>: <descrição curta> [TASK-<id>]" --body "$(cat <<'EOF'
## Resumo
<texto livre descrevendo o que foi feito e por quê>

## Alterações
- <alteração 1>
- <alteração 2>

## Critérios de Verificação
- [ ] <critério para o Tester verificar>
- [ ] <critério para o Tester verificar>

## Breaking changes
<descrever se houver, ou remover seção>
EOF
)"
```

### 6. Execução única

Todas as chamadas de ferramentas devem ser feitas em uma única mensagem. Não envie texto adicional além das chamadas.

## Erros Comuns

| Erro | Correção |
|------|----------|
| Inventar Task ID | **Sempre** perguntar ao usuário com `AskUserQuestion` |
| Omitir `--draft` | Flag `--draft` é obrigatória em toda PR |
| Push direto na main | Criar branch `TASK-<id>` antes |
| Body sem formato padrão | Usar as 4 seções: Resumo, Alterações, Critérios de Verificação, Breaking changes |
| Enviar várias mensagens | Tudo deve ser feito em uma única resposta |
