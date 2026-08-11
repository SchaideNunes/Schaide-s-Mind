# WhatsappBot_Local - Dashboard do Projeto

Documentação de acompanhamento e ideias para a evolução do projeto **WhatsappBot_Local**.

## Caminho Local
[Pasta do Projeto](file:///D:/TRABALHO/WhatsappBot_Local)

## Sobre
Documentação central e anotações gerais sobre o projeto WhatsappBot_Local.

## Tarefas Principais
- [ ] Mapear as próximas atividades do projeto.

## Ideias Futuras
- [ ] Aplicar fortemente o princípio de "Separar Responsabilidades".
- [ ] Migrar o parseamento de variáveis de ambiente (`os.getenv`) para utilizar o `Pydantic`. Isso permitirá converter tipos automaticamente (bool, int) e evitará bugs silenciosos de tipagem no Python.

## Problemas e Pontos de Atenção
- Atualmente, as variáveis de ambiente lidas por `os.getenv` retornam apenas String, o que pode causar inconsistências.
