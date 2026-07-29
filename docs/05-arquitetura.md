# 05 - Arquitetura

## Objetivo

Este documento descreve a arquitetura de software do LifeOS, estabelecendo os princípios, padrões e tecnologias que guiarão o desenvolvimento da aplicação. O objetivo é garantir escalabilidade, manutenibilidade, baixo acoplamento e alta coesão, permitindo que o projeto evolua de uma aplicação pessoal para um produto SaaS.

---

# Princípios Arquiteturais

O desenvolvimento do LifeOS seguirá os seguintes princípios:

* Clean Architecture.
* SOLID.
* Separation of Concerns (SoC).
* Domain-Driven Design (DDD) quando aplicável.
* Feature-Based Architecture.
* Componentização.
* Design System.
* API First.
* Type Safety em toda a aplicação.
* Escalabilidade desde a primeira versão.

---

# Stack Tecnológica

## Front-end

* React
* Vite
* TypeScript
* Tailwind CSS
* shadcn/ui
* React Router
* TanStack Query
* React Hook Form
* Zod
* Recharts

---

## Back-end

* NestJS
* Prisma ORM
* PostgreSQL
* JWT
* Docker

---

## Ferramentas

* Git
* GitHub
* Docker Compose
* ESLint
* Prettier
* Husky
* Commitlint
* GitHub Actions

---

# Arquitetura Geral

O projeto será organizado como um monorepo, permitindo compartilhamento de código entre aplicações e facilitando a evolução para múltiplos clientes (web, mobile e APIs).

```text
lifeos/

├── apps/
│   ├── web/
│   └── api/
│
├── packages/
│   ├── ui/
│   ├── shared/
│   ├── types/
│   ├── config/
│   └── eslint-config/
│
├── docs/
│
├── docker/
│
└── .github/
```

---

# Organização do Front-end

A estrutura do front-end será baseada em funcionalidades (Feature-Based Folder Structure), evitando organização por tipo de arquivo.

```text
src/

features/

shared/

layouts/

routes/

hooks/

lib/

styles/

assets/
```

Cada módulo possuirá sua própria estrutura interna.

Exemplo:

```text
finance/

components/

pages/

hooks/

schemas/

types/

services/

api/

utils/
```

Essa abordagem reduz o acoplamento entre módulos e facilita a manutenção e escalabilidade do sistema.

---

# Organização do Back-end

O back-end seguirá uma arquitetura modular baseada em domínio.

```text
src/

modules/

common/

config/

database/

main.ts
```

Cada módulo conterá:

```text
finance/

controllers/

services/

repositories/

entities/

dto/

use-cases/

mappers/

validators/
```

Cada domínio será responsável apenas por suas próprias regras de negócio.

---

# Clean Architecture

Cada funcionalidade deverá respeitar as seguintes camadas:

```text
Presentation

↓

Application

↓

Domain

↓

Infrastructure
```

## Presentation

Responsável por:

* Interfaces.
* Controllers.
* Rotas.
* Componentes.
* Validação inicial.

---

## Application

Responsável por:

* Casos de uso.
* Regras de aplicação.
* Orquestração.

---

## Domain

Responsável por:

* Entidades.
* Objetos de valor.
* Regras de negócio.
* Interfaces.

Esta camada não deverá depender de frameworks.

---

## Infrastructure

Responsável por:

* Banco de dados.
* Prisma.
* APIs externas.
* Open Finance.
* Serviços externos.
* Persistência.

---

# Comunicação entre Camadas

As dependências deverão apontar sempre para o domínio.

```text
UI

↓

Use Cases

↓

Domain

↑

Infrastructure
```

Isso garante baixo acoplamento e facilita testes e manutenção.

---

# Design System

Todos os componentes reutilizáveis serão centralizados em um pacote próprio.

Exemplos:

* Button
* Input
* Card
* Badge
* Modal
* Dialog
* Table
* Select
* Avatar
* Tabs
* Sidebar
* Navbar
* Charts

Os componentes deverão ser independentes das regras de negócio.

---

# Gerenciamento de Estado

A estratégia será baseada na responsabilidade de cada tipo de dado.

## Estado do Servidor

Gerenciado com:

* TanStack Query

Responsável por:

* Cache.
* Sincronização.
* Atualizações.
* Requisições.

---

## Estado da Interface

Utilizar:

* Context API quando necessário.
* Hooks locais.
* Component State.

Evitando gerenciamento global desnecessário.

---

# Validação

Todas as validações deverão utilizar Zod.

O mesmo schema poderá ser compartilhado entre frontend e backend sempre que possível.

---

# Banco de Dados

O banco será PostgreSQL utilizando Prisma ORM.

Características:

* Migrações versionadas.
* Relacionamentos explícitos.
* Soft Delete quando necessário.
* Auditoria futura.
* Multiusuário.

---

# Autenticação

O sistema utilizará:

* JWT.
* Refresh Token.
* Hash de senha.
* Controle de permissões.
* Proteção de rotas.

A arquitetura deverá permitir futuramente integração com OAuth e provedores externos.

---

# Escalabilidade

O projeto será preparado para suportar:

* Novos módulos.
* Novos domínios.
* Integrações.
* Aplicativo mobile.
* APIs públicas.
* Inteligência Artificial.
* Evolução para SaaS.

Sem necessidade de grandes refatorações estruturais.

---

# Convenções

Todo o projeto deverá seguir convenções padronizadas.

## Código

* TypeScript Strict Mode.
* ESLint.
* Prettier.
* Imports organizados.
* Nomenclatura consistente.

## Git

* Git Flow simplificado.
* Conventional Commits.
* Pull Requests.
* Code Review.

---

# Objetivo Final

A arquitetura do LifeOS deverá priorizar simplicidade, organização e escalabilidade. Cada decisão técnica deverá facilitar a evolução do projeto ao longo do tempo, permitindo adicionar novos módulos sem comprometer a qualidade do código ou a experiência do usuário.

A estrutura proposta busca reproduzir padrões encontrados em produtos modernos de alto nível, tornando o LifeOS um projeto sólido tanto para uso pessoal quanto para um futuro produto comercial.
