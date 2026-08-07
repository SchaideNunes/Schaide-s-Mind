# Instruções para Inteligências Artificiais

Esta pasta (`Projetos`) funciona como o diretório central de gerenciamento de todos os projetos em andamento.

**REGRA DE CRIAÇÃO DE NOVOS PROJETOS:**
Sempre que uma I.A. for solicitada para criar ou iniciar um novo projeto nesta pasta, ela DEVE obrigatoriamente realizar os seguintes passos:

1. Criar a pasta do novo projeto dentro de `Projetos`.
2. Criar **apenas uma** nota raiz (Dashboard/Index) com o nome exato do projeto (ex: `Nome Do Projeto.md`) dentro dessa pasta. Tudo sobre o projeto (Ideias, Tarefas, Documentação) deve ser centralizado nesta única nota.
3. Adicionar automaticamente um link para essa **nota raiz** no arquivo `Kanban Projetos.md`.
4. O link deve ser adicionado na coluna `## Backlog` (ou `## Em Andamento`, se o projeto já iniciar com tarefas ativas).
   - **MUITO IMPORTANTE:** Use o formato `- [ ] [[Nome Do Projeto]]`. Não crie e não linke para múltiplos arquivos dentro da pasta do projeto (como criar um arquivo separado para "Ideias e Tarefas"). O usuário não quer que o projeto tenha "múltiplas linhas/bolinhas" poluindo a Visualização em Gráfico (Graph View). Cada projeto deve ser representado no Kanban por um único link apontando para a sua nota centralizada.

A falha em adicionar o projeto ao Kanban quebra o fluxo de trabalho de organização visual.
