# 09 - API

## Objetivo

Este documento define os padrões de comunicação entre o frontend e o backend do LifeOS. O objetivo é garantir uma API consistente, previsível, segura e preparada para evoluir junto com a aplicação.

A API seguirá uma abordagem **API First**, permitindo que frontend, backend e futuras integrações sejam desenvolvidos de forma independente.

---

# Arquitetura

O backend será desenvolvido utilizando **NestJS**, seguindo os princípios da Clean Architecture.

Cada módulo da aplicação possuirá seus próprios endpoints, mantendo baixo acoplamento entre domínios.

Exemplo:

```text
/api

/auth
/users
/accounts
/transactions
/categories
/goals
/assets
/health
/studies
/career
/tasks
/analytics
```

---

# Convenções

## Formato

Todas as requisições e respostas utilizarão:

* JSON
* UTF-8
* HTTPS

---

## Versionamento

A API será versionada.

Exemplo:

```text
/api/v1
```

Isso permitirá futuras mudanças sem quebrar compatibilidade.

---

## Autenticação

A autenticação será baseada em JWT.

Fluxo:

1. Login
2. Geração de Access Token
3. Geração de Refresh Token
4. Renovação automática

Todos os endpoints protegidos exigirão um token válido.

---

# Estrutura das Respostas

## Sucesso

```json
{
  "success": true,
  "data": {},
  "message": "Operação realizada com sucesso."
}
```

---

## Erro

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Dados inválidos."
  }
}
```

---

# Endpoints

## Auth

### POST

```text
/auth/register
```

Cadastrar usuário.

---

### POST

```text
/auth/login
```

Autenticar usuário.

---

### POST

```text
/auth/refresh
```

Renovar token.

---

### POST

```text
/auth/logout
```

Encerrar sessão.

---

## Users

### GET

```text
/users/me
```

Retorna os dados do usuário autenticado.

---

### PATCH

```text
/users/me
```

Atualiza perfil.

---

## Accounts

### GET

```text
/accounts
```

Lista contas.

---

### POST

```text
/accounts
```

Cria conta.

---

### GET

```text
/accounts/:id
```

Obtém detalhes de uma conta.

---

### PATCH

```text
/accounts/:id
```

Atualiza conta.

---

### DELETE

```text
/accounts/:id
```

Remove conta.

---

## Transactions

### GET

```text
/transactions
```

Lista transações.

Filtros:

* Conta
* Categoria
* Tipo
* Data
* Valor

---

### POST

```text
/transactions
```

Cria transação.

---

### GET

```text
/transactions/:id
```

Detalhes da transação.

---

### PATCH

```text
/transactions/:id
```

Atualiza transação.

---

### DELETE

```text
/transactions/:id
```

Remove transação.

---

## Categories

### GET

```text
/categories
```

Lista categorias.

---

### POST

```text
/categories
```

Cria categoria.

---

### PATCH

```text
/categories/:id
```

Atualiza categoria.

---

### DELETE

```text
/categories/:id
```

Remove categoria.

---

## Goals

### GET

```text
/goals
```

Lista objetivos.

---

### POST

```text
/goals
```

Cria objetivo.

---

### GET

```text
/goals/:id
```

Detalhes do objetivo.

---

### PATCH

```text
/goals/:id
```

Atualiza objetivo.

---

### DELETE

```text
/goals/:id
```

Remove objetivo.

---

## Assets

Endpoints para gerenciamento do patrimônio.

Exemplos:

```text
GET    /assets
POST   /assets
PATCH  /assets/:id
DELETE /assets/:id
```

---

## Health

Endpoints relacionados à saúde.

Exemplos:

```text
GET    /health/measurements
POST   /health/measurements
GET    /health/workouts
POST   /health/workouts
```

---

## Studies

```text
GET    /courses
POST   /courses

GET    /books
POST   /books

GET    /study-sessions
POST   /study-sessions
```

---

## Career

```text
GET    /jobs
POST   /jobs

GET    /salary-history
POST   /salary-history
```

---

## Productivity

```text
GET    /tasks
POST   /tasks

GET    /projects
POST   /projects

GET    /calendar
POST   /calendar
```

---

## Analytics

Endpoints exclusivamente de leitura.

Exemplos:

```text
GET /analytics/dashboard

GET /analytics/net-worth

GET /analytics/monthly-expenses

GET /analytics/cash-flow

GET /analytics/goals

GET /analytics/studies

GET /analytics/health
```

---

## AI

```text
GET /insights

GET /forecast

GET /recommendations
```

Esses endpoints serão responsáveis por retornar informações geradas automaticamente pelo sistema.

---

# Paginação

Todos os endpoints de listagem deverão suportar paginação.

Parâmetros:

* page
* limit

Resposta:

```json
{
  "data": [],
  "meta": {
    "page": 1,
    "limit": 20,
    "total": 120,
    "pages": 6
  }
}
```

---

# Ordenação

Todos os endpoints deverão permitir:

* sortBy
* order

Exemplo:

```text
?sortBy=createdAt&order=desc
```

---

# Filtros

Filtros deverão utilizar query parameters.

Exemplo:

```text
?category=food

?status=completed

?type=expense

?month=6
```

---

# Validação

Toda entrada será validada utilizando DTOs no backend e Zod no frontend.

Nenhuma informação inválida deverá ser persistida.

---

# Segurança

Todos os endpoints protegidos deverão utilizar:

* JWT
* Refresh Token
* Validação de permissões
* Rate Limiting
* CORS
* Helmet
* Sanitização de entradas

---

# Documentação

A API será documentada utilizando Swagger.

Cada endpoint deverá conter:

* Descrição.
* Parâmetros.
* Corpo da requisição.
* Exemplos.
* Códigos de resposta.

---

# Códigos HTTP

Principais códigos utilizados:

* 200 OK
* 201 Created
* 204 No Content
* 400 Bad Request
* 401 Unauthorized
* 403 Forbidden
* 404 Not Found
* 409 Conflict
* 422 Unprocessable Entity
* 500 Internal Server Error

---

# Integrações Futuras

A arquitetura deverá permitir integração com:

* Open Finance.
* Google Calendar.
* Google Fit.
* Samsung Health.
* Apple Health.
* APIs bancárias.
* APIs de investimentos.
* Serviços de Inteligência Artificial.

---

# Objetivo Final

A API do LifeOS deverá ser consistente, previsível e modular, oferecendo uma base sólida para comunicação entre frontend, backend e futuras aplicações clientes. Sua estrutura deverá facilitar manutenção, evolução e integração com serviços externos, mantendo alta qualidade, segurança e desempenho ao longo do ciclo de vida do produto.
