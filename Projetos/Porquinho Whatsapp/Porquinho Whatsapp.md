# Porquinho Whatsapp - Dashboard do Projeto

Documentação de acompanhamento e ideias para a evolução do projeto **Porquinho Whatsapp**.

## Caminho Local
[Pasta do Projeto](file:///D:/TRABALHO/Porquinho%20Whatsapp)

## Sobre
Documentação central e anotações gerais sobre o projeto Porquinho Whatsapp.

## Tarefas Principais
- [ ] Mapear as próximas atividades do projeto.

## Ideias Futuras
- [ ] Melhorar a tipagem do projeto, garantindo que todos os dados vindos do Supabase sejam tipados ou convertidos de forma segura antes de serem utilizados.

## Problemas e Pontos de Atenção
- Evitar chamar métodos em variáveis que possam ser `None` vindas do Supabase. Utilizar guardas explícitas (ex: `if obj is not None:` ou `if isinstance(obj, dict):`).
