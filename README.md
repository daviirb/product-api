# Product API

Esta é uma API escrita em Go que permite a criação e consulta de produtos em um banco de dados PostgreSQL. A API e o banco de dados são executados em contêineres Docker, facilitando a configuração e o deploy.

## Arquitetura

A API segue uma arquitetura dividida em camadas:

- **Model**: Representa as estruturas de dados dos produtos.
- **Repository**: Responsável pela comunicação com o banco de dados (CRUD).
- **UseCases**: Contém a lógica de negócios da aplicação.
- **Controllers**: Gerencia as requisições HTTP e retorna respostas adequadas.

## Tecnologias utilizadas

- **Go**: Linguagem de programação principal da API.
- **PostgreSQL**: Banco de dados relacional para armazenamento dos produtos.
- **Docker**: Contêineres para rodar a aplicação e o banco de dados.

## Instalação e configuração

### Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Passos para rodar o projeto

1. Clone este repositório:

   ```bash
   git clone https://github.com/daviirb/product-api
   cd product-api
   ```

2. Execute os contêineres com o Docker Compose:
    ```bash
    docker-compose up --build
    ```
    Isso criará e iniciará os contêineres da API e do PostgreSQL.

3. Acesse a API em `http://localhost:8080`.
 
### Estrutura de Diretórios:
   ```bash
   ├── cmd/
     └── main.go              # Arquivo principal da aplicação
   ├── controller/     # Controladores que lidam com as requisições HTTP
   ├── db/              # Conexão com o banco de dados
   ├── model/          # Definições dos modelos de dados
   ├── repository/    # Código de acesso ao banco de dados
   ├── usecase/        # Lógica de negócios da aplicação
   ├── docker-compose.yml   # Configuração do Docker Compose
   └── Dockerfile           # Dockerfile da API em Go
```
         
## Endpoints da API

### Criar um produto

- **URL**: `/product`
- **Método**: `POST`
- **Body**:

  ```json
  {
    "name": "Produto Exemplo",
    "price": 100.50
  }

  ```

  Resposta: `201 Created`

  ### Buscar todos os produtos

- **URL**: `/products`
- **Método**: `GET`
- **Resposta**: `200 OK`
```json
  {
    {
    "id": 1,
    "name": "Produto Exemplo",
    "price": 100.50,
    "created_at": "2024-09-26T12:00:00Z"
    }
  }

  ```

### Buscar produto pelo id

- **URL**: `/product/1`
- **Método**: `GET`
- **Resposta**: `200 OK`
```json
  {
    {
    "id": 1,
    "name": "Produto Exemplo",
    "price": 100.50,
    "created_at": "2024-09-26T12:00:00Z"
    }
  }

  ```

### Criando novo produto e buscando todos os produtos
https://github.com/user-attachments/assets/32312871-a534-4a85-861b-36d1233145ec

### Consultando um produto pelo id

https://github.com/user-attachments/assets/f3614e50-a428-42dc-82db-b2aac4f4bfaf








