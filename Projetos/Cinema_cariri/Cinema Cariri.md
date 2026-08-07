# Cinema Cariri - Dashboard do Projeto

Documentação de acompanhamento e ideias para a evolução do projeto **Cinema Cariri**.

## Tarefas Principais

1. **Deixar o frontend/design mais apresentável (em andamento)**
   - Otimizar responsividade.
   - Melhorar o visual da página de compra de ingressos.
   - Refinar os estilos e paleta de cores.

2. **Testar a tela de admin e deixar o mais intuitivo possível**
   - Garantir que um administrador consiga gerenciar filmes e salas sem dificuldades.
   - Simplificar fluxos complexos para facilitar a operação diária do cinema.

3. **Criar um sistema de pagamento real**
   - Integrar uma API de pagamentos (como Stripe, MercadoPago ou Pagar.me) no momento do checkout.
   - Tratar retornos de sucesso/falha do pagamento antes de gerar o ingresso final.

## Ideias de Escalabilidade (Alta Concorrência)

4. **Gerenciamento de Fila e Cache (Escalabilidade)**
   - **Problema:** Em dias de estreias de filmes muito aguardados (ex: Vingadores, Homem-Aranha), milhares de usuários tentam comprar ingressos ao mesmo tempo, podendo derrubar o banco de dados principal e causando problemas como vendas duplicadas (*Double Booking*).
   - **Solução:** 
     - **Bloqueio Temporário (Temporary Lock):** Quando o usuário seleciona a quantidade de ingressos e clica em "Comprar", esses ingressos são temporariamente retirados da contagem geral e colocados em um banco em memória ultrarrápido (como o **Redis**) por 5 minutos, garantindo a reserva enquanto ele finaliza o pagamento.
     - **Arquitetura Microservices (Opção Futura):** Separar o serviço de `Pagamentos` do serviço de `Reservas`, para que a falha em um sistema não comprometa o acesso aos filmes pelo site.

5. **Notificação por E-mail**
   - **Objetivo:** Enviar os ingressos comprados no formato PDF/QR Code diretamente para o e-mail do cliente, além de avisos importantes.
   - **Solução:** Integrar o envio de e-mails usando serviços como SendGrid, Amazon SES ou Resend. Esse envio deve ser acionado de forma assíncrona (via *background tasks* do FastAPI ou filas como Celery/RabbitMQ), garantindo que a resposta de sucesso da compra na tela do usuário seja imediata.
