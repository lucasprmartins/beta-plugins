---
name: commit
description: Use quando precisar commitar alterações no git de forma atômica. Acionado por pedidos como "commita", "faz commit", "git commit", ou quando há alterações staged/unstaged prontas para serem commitadas.
model: haiku
---

# Commits Atômicos

## Overview

Técnica para criar commits git agrupados por unidade lógica, onde cada commit representa UMA mudança coerente e independente.

## Contexto

- Status: !`git status`
- Alterações (resumo): !`git diff HEAD --name-status`
- Diff completo: !`git diff HEAD`
- Branch: !`git branch --show-current`
- Commits recentes (estilo): !`git log --oneline -10`

## Quando Usar

- Há alterações staged ou unstaged prontas para commit
- O usuário pede para commitar ou "fazer commit"

**Quando NÃO usar:** não há alterações no repositório

## Workflow

### 1. Analisar e Agrupar

Examine o diff e identifique grupos lógicos. Cada grupo = UMA mudança coerente descritível em uma única mensagem.

**Critérios de agrupamento (por prioridade):**
1. Mesma funcionalidade ou correção (arquivos que juntos formam uma mudança coerente)
2. Mesmo tipo de alteração (feat, fix, refactor, docs, chore, test, style)
3. Se a mensagem precisaria de "e" para conectar coisas não relacionadas → separe

**Quando NÃO separar:**
- Se todas as alterações são uma única unidade lógica → um commit só
- Não divida artificialmente

**Arquivo com mudanças de dois grupos:** Inclua no grupo mais significativo. Staging é por arquivo, não por trecho — um arquivo só aparece em UM commit, todas as suas alterações vão juntas. Não tente stager o mesmo arquivo em commits diferentes.

### 2. Executar os Commits

Para cada grupo, na ordem que mantenha o repositório válido a cada commit (dependências antes de dependentes):

```bash
git add <arquivo1> <arquivo2>
git commit -m "<tipo>: <descrição curta>"
```

**Formato:** Conventional Commits em português, seguindo o estilo dos commits recentes do repositório. Mensagem curta e descritiva — sem body multi-line.

### Restrições

- **SEMPRE** especifique arquivos: `git add <arquivo>`
- **NUNCA** use `git add .` nem `git add -A` — sempre liste os arquivos
- **NUNCA** use `git add -p` nem `git add -i` — staging é por arquivo
- Execute todos os commits em uma única resposta, sem texto ou mensagens adicionais

## Referência Rápida

| Tipo | Uso |
|------|-----|
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `refactor` | Reestruturação sem mudar comportamento |
| `docs` | Documentação |
| `chore` | Tarefas de manutenção |
| `test` | Testes |
| `style` | Formatação, espaçamento |

## Erros Comuns

| Erro | Correção |
|------|----------|
| `git add .` ou `git add -A` | Sempre especifique os arquivos por nome |
| `git add -p` ou `git add -i` | Staging é por arquivo; inclua no grupo mais significativo |
| Um commit gigante com tudo | Analise o diff e separe por unidade lógica |
| Separar artificialmente | Se é uma unidade lógica, faça UM commit |
| Mensagem vaga ("atualizações") | Use tipo + descrição curta em português |
| Mensagem com body extenso | Uma linha só: `<tipo>: <descrição>` |
| Ordem errada de commits | Dependências primeiro, dependentes depois |
| Mesmo arquivo em 2 commits | Impossível: staging é por arquivo, todas as mudanças vão juntas |
