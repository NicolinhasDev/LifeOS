# 08 - Database

## Objetivo

Este documento define a modelagem lógica do banco de dados do LifeOS. Seu objetivo é estruturar a persistência das informações de forma consistente, escalável e preparada para futuras evoluções do sistema.

A modelagem será baseada no Domain Model, respeitando os princípios da Clean Architecture e separando as regras de negócio da camada de persistência.

---

# Banco de Dados

O LifeOS utilizará:

* PostgreSQL
* Prisma ORM
* Migrations versionadas
* Relacionamentos explícitos
* Constraints de integridade
* Índices para otimização
* Soft Delete quando aplicável

---

# Princípios

A modelagem seguirá os seguintes princípios:

* Cada tabela representa uma entidade do domínio.
* Evitar duplicação de dados.
* Priorizar normalização.
* Utilizar chaves estrangeiras para garantir integridade.
* Facilitar futuras integrações e escalabilidade.

---

# Entidades Principais

## User

Representa o usuário da plataforma.

Campos sugeridos:

* id
* name
* email
* password
* avatar
* createdAt
* updatedAt

Relacionamentos:

* Accounts
* CreditCards
* Goals
* Assets
* Liabilities
* Habits
* Tasks
* Courses
* Jobs

---

# Finance

## Account

Representa contas financeiras.

Campos:

* id
* userId
* name
* institution
* type
* balance
* currency
* isActive

Relacionamentos:

* Transactions

---

## Transaction

Representa movimentações financeiras.

Campos:

* id
* accountId
* categoryId
* amount
* description
* transactionDate
* type
* status
* createdAt

Tipos:

* Income
* Expense
* Transfer

---

## Category

Campos:

* id
* userId
* name
* icon
* color
* parentCategoryId

Relacionamentos:

* Transactions

---

## CreditCard

Campos:

* id
* userId
* name
* brand
* limit
* closingDay
* dueDay

Relacionamentos:

* Invoice
* CardTransaction

---

## Invoice

Campos:

* id
* creditCardId
* month
* year
* total
* status

---

## Subscription

Campos:

* id
* userId
* name
* amount
* recurrence
* categoryId

---

# Patrimônio

## Asset

Campos:

* id
* userId
* type
* name
* currentValue
* acquisitionDate

Tipos:

* Cash
* Investment
* Real Estate
* Vehicle
* Crypto
* Other

---

## Liability

Campos:

* id
* userId
* type
* description
* totalAmount
* remainingAmount
* interestRate

---

# Objetivos

## Goal

Campos:

* id
* userId
* title
* description
* targetAmount
* currentAmount
* deadline
* priority
* status

---

## GoalContribution

Campos:

* id
* goalId
* transactionId
* amount
* contributionDate

---

# Saúde

## BodyMeasurement

Campos:

* id
* userId
* date
* weight
* bodyFat
* muscleMass
* bmi

---

## Workout

Campos:

* id
* userId
* name
* duration
* calories
* workoutDate

---

## Habit

Campos:

* id
* userId
* name
* frequency
* isActive

---

## HabitLog

Campos:

* id
* habitId
* date
* completed

---

# Estudos

## Course

Campos:

* id
* userId
* title
* platform
* progress
* status

---

## Book

Campos:

* id
* userId
* title
* author
* pages
* progress

---

## StudySession

Campos:

* id
* courseId
* duration
* studyDate
* notes

---

## Certification

Campos:

* id
* userId
* title
* issuer
* issueDate
* expirationDate

---

# Carreira

## Job

Campos:

* id
* userId
* company
* position
* startDate
* endDate

---

## SalaryHistory

Campos:

* id
* jobId
* salary
* effectiveDate

---

## PortfolioProject

Campos:

* id
* userId
* title
* repository
* demo
* description

---

## JobApplication

Campos:

* id
* userId
* company
* position
* status
* applicationDate

---

# Produtividade

## Task

Campos:

* id
* userId
* title
* description
* dueDate
* completed

---

## CalendarEvent

Campos:

* id
* userId
* title
* startDate
* endDate
* location

---

## Project

Campos:

* id
* userId
* title
* description
* status

---

# Analytics

As informações analíticas serão geradas a partir das demais tabelas, evitando redundância de dados.

Exemplos:

* Patrimônio líquido.
* Evolução mensal.
* Fluxo de caixa.
* Evolução salarial.
* Tempo estudado.
* Evolução física.

Esses indicadores poderão ser obtidos por consultas, *views* materializadas ou serviços especializados, conforme a necessidade de desempenho.

---

# Auditoria

Todas as tabelas deverão possuir, quando aplicável:

* createdAt
* updatedAt
* deletedAt (Soft Delete)

Futuramente poderão ser adicionados:

* createdBy
* updatedBy
* version

---

# Convenções

## Chaves Primárias

Todas as entidades utilizarão identificadores únicos (UUID).

---

## Datas

Todos os registros deverão utilizar UTC para armazenamento.

A conversão para o fuso horário do usuário ocorrerá na camada de aplicação.

---

## Relacionamentos

Todos os relacionamentos deverão utilizar chaves estrangeiras.

Exemplos:

* User → Account
* Account → Transaction
* Category → Transaction
* Goal → GoalContribution
* CreditCard → Invoice

---

# Índices

Serão criados índices para campos frequentemente utilizados em pesquisas e filtros.

Exemplos:

* userId
* accountId
* categoryId
* transactionDate
* createdAt
* status

---

# Migrações

Toda alteração estrutural deverá ser realizada por meio de migrations versionadas utilizando Prisma.

Não serão realizadas alterações manuais diretamente no banco de produção.

---

# Escalabilidade

A modelagem deverá permitir:

* Multiusuário.
* Múltiplas moedas.
* Integrações externas.
* Open Finance.
* Histórico de alterações.
* Novos módulos.
* Evolução para SaaS.

---

# Objetivo Final

A estrutura do banco de dados deverá fornecer uma base sólida, consistente e escalável para o LifeOS, suportando tanto o MVP quanto futuras expansões do produto. O foco será manter integridade, desempenho e facilidade de manutenção, garantindo que a camada de persistência acompanhe a evolução da aplicação sem comprometer sua arquitetura.
