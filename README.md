# Projeto banco financeiro

Este projeto configura um ambiente de desenvolvimento utilizando Docker Compose para provisionar um banco de dados PostgreSQL, executar migrações de banco de dados com Flyway e simular serviços AWS usando Localstack.

## Conteúdo

- **PostgreSQL**: Banco de dados relacional.
- **Flyway**: Ferramenta de migração de banco de dados.
- **Localstack**: Emulador de serviços da AWS.

## Pré-requisitos

- Docker
- Docker Compose

## Configuração

1. **PostgreSQL**:
   - Imagem: `postgres:13`
   - Container: `postgres_bank`
   - Responsável pelo banco de dados

2. **Flyway**:
   - Imagem: `flyway/flyway`
   - Container: `flyway_migration`
   - Responsável pela execução das migrations

3. **Localstack**:
   - Imagem: `localstack/localstack:latest`
   - Container: `bank_stack`
   - Responsável pelo fornecimento do SQS

## Como usar

1. **Clone o repositório**:
   ```sh
   git clone <URL_DO_REPOSITORIO>
   cd <NOME_DO_REPOSITORIO>

2. **De permissão necessária para o script de criação de queue**:
    ```sh
    chmod +x scripts/create_sqs_queues.sh;

3. **Inicie os containers**:
    ```sh
    docker-compose up -d;

4. **Serviços em funcionamento**:
- PostgreSQL: localhost:5432
- Localstack: localhost:4566