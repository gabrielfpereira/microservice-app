# Microservice de Gerenciamento de Clientes

Este é um microservice em Laravel que gerencia usuarios e se comunica com outra aplicação via RabbitMQ para o envio de e-mails. O Usuário ao se cadastrar recebe um email de boas vindas feita pelo microservice de email.

[microservice-email](https://github.com/gabrielfpereira/microservice-email)

## Funcionalidades

- **Cadastro / Login de Usuario:** cadastra usuarios na aplicação e possibilita fazer login.
- **Comunicação Assíncrona:** Usa filas (queues) e jobs para processar o envio de e-mails de forma assíncrona.
- **Integração com RabbitMQ:** Envia mensagens para outra aplicação para o envio eficiente de e-mails.

## Requisitos

- PHP 8.x ou superior
- Composer
- RabbitMQ (com configurações adequadas)

Para esse projeto usamos o serviço da (CloudAMQP)[https://www.cloudamqp.com/] e da pacote (laravel-queue-rabbitmq)[https://github.com/vyuldashev/laravel-queue-rabbitmq]. Siga o processo de instalação e configuração de ambos.

## Instalação e Uso

1. Clone este repositório: `git clone https://github.com/seu-usuario/microservice-clientes.git`
2. Instale as dependências: `composer install`
3. Configure as variáveis de ambiente no arquivo `.env`, incluindo as credenciais do RabbitMQ.
4. Execute as migrações: `php artisan migrate`
5. Inicie o serviço: `php artisan serve`
6. Use as rotas para adicionar, atualizar, remover e listar clientes.

Não se esqueça de mudar no arquivo `.env` a chave para `QUEUE_CONNECTION=rabbitmq`

Ao se cadastrar um novo usuário, um job é automaticamente disparado para enviar um e-mail de boas-vindas através da integração com a aplicação [microservice-email](https://github.com/gabrielfpereira/microservice-email).

## Autor

Gabriel Pereira - [GitHub](https://github.com/gabrielfpereira)
