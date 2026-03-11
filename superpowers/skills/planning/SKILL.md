---
name: planning
description: Use esta skill para planejar uma especificação em documento.
model: opus
allowed-tools: Read, Grep, Glob, Bash, WebSearch, WebFetch
---

## Visão Geral

Criar um plano de implementação detalhado e estruturado a partir de um documento de especificação. O plano deve ser claro o suficiente para ser seguido por um agente sem conhecimento prévio do projeto, garantindo que todas as tarefas sejam bem estruturadas com objetivo, contexto de implementação, caminhos exatos e dependências explícitas.

**PRINCÍPIO FUNDAMENTAL:** Um bom plano é tão claro e detalhado que pode ser executado por um agente que não conhece o codebase. Se o agente precisar adivinhar algo, o plano está incompleto.

O documento da especificação para executar a skill:
```
$ARGUMENTS
```

## Processo

1. Analisar a especificação: Extrair informações relevantes, como objetivos, requisitos, arquitetura, restrições e critérios de sucesso.
2. Explorar o codebase: Use as ferramentas `Read`, `Grep` e `Glob` para explorar o codebase e entender a estrutura do projeto, identificar arquivos relevantes, padrões de código e dependências.
3. Explorar tecnologias: Caso você precise saber mais sobre alguma tecnologia, framework ou biblioteca específica mencionada na especificação ou no codebase, use o MCP `Context7` para buscar a documentação oficial e entender melhor sobre o assunto.

**ATENÇÃO:** Se o MCP `Context7` não estiver disponível, use as ferramentas `WebSearch` e `WebFetch`.

4. Consolidação da plano:
  - Após exploração das etapas 1 e 2, consolide um plano de implementação detalhado, estruturado e claro (**SEGUINDO EXTAMENTE O MODELO `./plan.md`, SEM ADICIONAR OU REMOVER SEÇÕES, ALTERAR A ESTRUTURA E REMOVER TEXTOS**) e salve no caminho `docs/.superpowers/plans/AAAA-MM-DD-<solucao>.md`.
  - Na seção "Pilhas de Tecnologias", liste as tecnologias, frameworks e bibliotecas que serão usadas para implementar a solução, garantindo que estejam alinhadas com a especificação e o codebase.
  - Na seção "Tarefas", detalhe cada tarefa em ordem de implementação, incluindo o objetivo, o contexto e os arquivos que precisam ser criados ou modificados, garantindo que cada tarefa seja atômica e tenha dependências explícitas para que um agente possa seguir o plano sem adivinhações.

## Instruções

- Siga **RIGOROSAMENTE** o modelo `./plan.md` para garantir que o plano esteja bem estruturado e claro.
- Nunca escreva um plano sem antes ler os arquivos relevantes do projeto.
- Toda tarefa deve ter o caminho explícito dos arquivos a serem criados ou modificados, incluindo números de linhas quando necessário.
- Tarefas atômicas, ou seja, cada tarefa deve ser independente e ter um objetivo claro, evitando a necessidade de adivinhação ou suposições por parte do agente que irá executar o plano.
- Cada tarefa entrega um componente funcional específico. Não use "Fase 1: Preparação" ou "Fase 2: Desenvolvimento". Cada tarefa deve ser nomeada de acordo com o componente que entrega, por exemplo, "Tarefa 1: Implementar API de Autenticação".
- As tarefas devem ter dependências explícitas, ou seja, se a Tarefa 2 depende da Tarefa 1, isso deve ser claramente indicado no plano. Evite dependências implícitas ou suposições sobre a ordem de implementação.
- Respeite **RIGOROSAMENTE** as regras do projeto. Ao criar tarefas, certifique-se de que elas estejam alinhadas com as diretrizes do projeto para garantir consistência e qualidade.
- Utilize YAGNI (You Aren't Gonna Need It) para evitar a tentação de adicionar detalhes desnecessários ao plano. Concentre-se apenas no que é essencial para resolver a especificação.
- Utilize DRY (Don't Repeat Yourself) para evitar redundâncias no plano.

## Saída

Após a conclusão do processo, informe **SOMENTE E EXCLUSIVAMENTE** o caminho do plano salva para o usuário, por exemplo: "O plano foi salvo em `docs/.superpowers/plans/2024-06-30-nome-da-solucao.md`".