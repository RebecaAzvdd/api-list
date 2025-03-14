---

# User Management API

Esta é uma API para gerenciamento de usuários, construída com **Spring Boot** e **PostgreSQL**. Ela fornece funcionalidades para criar, excluir e buscar usuários.

## Tecnologias

- **Java**: Linguagem principal da aplicação.
- **Spring Boot**: Framework para construção da API.
- **PostgreSQL**: Banco de dados utilizado.

## Requisitos

Antes de começar, verifique se você tem as seguintes ferramentas instaladas:

- **Java 11 ou superior** (JDK 11+)
- **Maven** para gerenciamento de dependências e construção do projeto.
- **PostgreSQL** (ou banco de dados configurado) com a base de dados e tabelas apropriadas.

## Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```

2. Configure o banco de dados no arquivo `application.properties`:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/seu-banco
   spring.datasource.username=seu-usuario
   spring.datasource.password=sua-senha
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   ```

3. Compile o projeto:

   ```bash
   mvn clean install
   ```

4. Inicie o servidor:

   ```bash
   mvn spring-boot:run
   ```

A aplicação estará disponível em `http://localhost:8080/swagger-ui.html`.

## Endpoints

### 1. **Criar um Usuário**

**Método:** `POST`

**Endpoint:** `/users`

**Descrição:** Cria um novo usuário na aplicação.

**Corpo da Requisição (JSON):**

```json
{
  "name": "João Silva",
  "account": {
    "number": "987654321",
    "agency": "1234",
    "balance": 5000,
    "limit": 2000
  },
  "card": {
    "number": "4111222233334444",
    "limit": 3000
  },
  "features": [
    {
      "icon": "credit_card",
      "description": "Cartão de crédito com limite de até R$ 3000"
    },
    {
      "icon": "cash",
      "description": "Saque em caixas eletrônicos sem taxas"
    }
  ],
  "news": [
    {
      "icon": "announcement",
      "description": "Novo aplicativo para gestão de contas e cartões disponível."
    },
    {
      "icon": "alert",
      "description": "Alteração nas taxas de juros para empréstimos a partir do próximo mês."
    }
  ]
}

```

**Resposta (JSON):**

```json
{
  "id": 1,
  "name": "João Silva",
  "email": "joao.silva@example.com",
  "account": {
    "number": "12345"
  }
}
```

**Status:** `201 Created`

---

### 2. **Buscar Usuário por ID**

**Método:** `GET`

**Endpoint:** `/users/{id}`

**Descrição:** Recupera os dados de um usuário específico com base no ID.

**Parâmetros de Rota:**
- `id`: O ID do usuário.

**Resposta (JSON):**

```json
{
  "id": 1,
  "name": "João Silva",
  "email": "joao.silva@example.com",
  "account": {
    "number": "12345"
  }
}
```

**Status:** `200 OK`

---

### 3. **Excluir um Usuário**

**Método:** `DELETE`

**Endpoint:** `/users/{id}`

**Descrição:** Exclui um usuário com base no ID.

**Parâmetros de Rota:**
- `id`: O ID do usuário a ser excluído.

**Resposta:**

Status `204 No Content` (sem conteúdo na resposta).

---

## Mensagens de Erro

A API retorna mensagens de erro em formato JSON. Por exemplo:

### 1. **Erro de Validação (400 Bad Request)**

```json
{
  "status": "error",
  "message": "Invalid user data"
}
```

### 2. **Erro de Recurso Não Encontrado (404 Not Found)**

```json
{
  "status": "error",
  "message": "User not found with id 1"
}
```

---

## Conclusão

Agora você está pronto para usar a **User Management API**! Utilize os endpoints fornecidos para criar, excluir e buscar usuários.

Se precisar de mais detalhes, consulte a documentação ou entre em contato com a equipe de desenvolvimento!

--- 


