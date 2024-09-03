# Desafio - Clean Architecture

## Enunciado

Olá devs!
Agora é a hora de botar a mão na massa. Para este desafio, você precisará criar o usecase de listagem das orders.
Esta listagem precisa ser feita com:
- Endpoint REST (GET /order)
- Service ListOrders com GRPC
- Query ListOrders GraphQL
  Não esqueça de criar as migrações necessárias e o arquivo api.http com a request para criar e listar as orders.

Para a criação do banco de dados, utilize o Docker (Dockerfile / docker-compose.yaml), com isso ao rodar o comando docker compose up tudo deverá subir, preparando o banco de dados.
Inclua um README.md com os passos a serem executados no desafio e a porta em que a aplicação deverá responder em cada serviço.

# Projeto Clean Architecture
Este projeto é uma implementação da Clean Architecture em Go, com suporte a REST, GRPC e GraphQL para gerenciamento de ordens. A seguir estão as instruções para configurar e executar o projeto.

## 1. Clonar o repositório

Clone o repositório em sua máquina local:

   ```
   git clone https://github.com/vinicius-maker/clean-architecture.git
   cd clean-architecture
   ```
## 2. Instalar as dependências

Instale as dependências do projeto utilizando o Go Modules:
   
   ```bash
   go mod tidy
   ```

## 3. Subir os containers

Inicie os containers necessários utilizando Docker Compose:
   
   ```bash
   docker-compose up -d
   ```

## 4. **Iniciar o projeto:**

Navegue até o diretório do sistema de pedidos e inicie o projeto:

   ```
    cd cmd/ordersystem/
    go run main.go wire_gen.go
   ```

## 5. Cadastrar uma ordem

Para cadastrar uma nova ordem, acesse o arquivo api/create_order.http e execute a requisição.
   
   ```
    - api/create_order.http
   ```

## 6. Executar o Endpoint (GET /orders)

O serviço REST está disponível na porta 8000. Para listar todas as ordens:

    - Acesse: http://localhost:8000/orders
    - Ou execute a requisição no arquivo api/list_orders.http.

## 7. Service ListOrders com GRPC

O serviço GRPC está disponível na porta 50051. Para listar as ordens via GRPC:

   - Abra o REPL do Evans:
      
   ```
   evans -r repl
   ```

   - Chame o serviço ListOrders:
   
   ```
   call ListOrders
   ```

## 8. Query ListOrders com GraphQL

O serviço GraphQL está disponível na porta 8080. Para listar as ordens:
   
   ```
    - Acesse o GraphQL: http://localhost:8080
   ```

   ```
   - Execute a seguinte query:
   
      query listOrders {
       listOrders {
           id
           Price
           Tax
           FinalPrice
       }
   ```