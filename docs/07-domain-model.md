# 07 - Domain Model

## Objetivo

O Domain Model define os principais conceitos de negócio do LifeOS e os relacionamentos entre eles. Diferente da modelagem do banco de dados, este documento representa o domínio do problema, ou seja, como o sistema enxerga a realidade.

Todas as decisões de arquitetura, banco de dados e implementação deverão partir deste modelo.

---

# Princípios

O modelo de domínio deverá seguir os seguintes princípios:

* Representar conceitos reais do negócio.
* Ser independente de banco de dados.
* Não depender de frameworks.
* Priorizar clareza e simplicidade.
* Centralizar as regras de negócio.

---

# Entidade Principal

## User

O usuário é a entidade central do sistema.

Todos os demais domínios pertencem a um usuário.

O LifeOS deverá ser multiusuário desde sua primeira versão.

---

# Domínio Financeiro

## Account

Representa uma conta financeira.

Exemplos:

* Conta corrente
* Conta poupança
* Carteira
* Conta internacional

Relacionamentos:

* Possui transações.
* Possui saldo.
* Pertence a um usuário.

---

## Credit Card

Representa um cartão de crédito.

Relacionamentos:

* Possui faturas.
* Possui lançamentos.
* Pertence a um usuário.

---

## Transaction

Representa qualquer movimentação financeira.

Pode ser:

* Receita
* Despesa
* Transferência

Atributos principais:

* Valor
* Data
* Categoria
* Conta
* Descrição
* Tipo
* Status

---

## Category

Agrupa transações.

Exemplos:

* Alimentação
* Transporte
* Moradia
* Lazer
* Educação

Categorias poderão possuir subcategorias.

---

## Subscription

Representa despesas recorrentes.

Exemplos:

* Netflix
* Spotify
* Academia

---

# Domínio Patrimonial

## Asset

Representa qualquer bem.

Exemplos:

* Dinheiro
* Investimentos
* Imóveis
* Veículos
* Criptomoedas

---

## Liability

Representa qualquer obrigação financeira.

Exemplos:

* Empréstimos
* Financiamentos
* Parcelamentos

---

## Net Worth

Entidade calculada.

Representa:

Patrimônio Líquido = Ativos - Passivos

---

# Domínio de Objetivos

## Goal

Representa qualquer meta.

Exemplos:

* Apartamento
* Casa
* Moto
* Viagem
* Reserva de emergência

Cada objetivo deverá possuir:

* Valor alvo
* Valor atual
* Prioridade
* Prazo
* Status

---

## Goal Contribution

Representa aportes realizados para um objetivo.

Permite acompanhar:

* Histórico
* Evolução
* Percentual concluído

---

# Domínio de Saúde

## Body Measurement

Representa medições corporais.

Exemplos:

* Peso
* IMC
* Gordura corporal
* Massa magra

---

## Workout

Representa um treino realizado.

---

## Habit

Representa um hábito.

Exemplos:

* Dormir cedo
* Beber água
* Caminhar
* Ler

---

# Domínio de Estudos

## Course

Curso em andamento ou concluído.

---

## Book

Livro.

---

## Study Session

Sessão de estudos.

Possui:

* Duração
* Data
* Curso
* Observações

---

## Certification

Certificação obtida.

---

# Domínio de Carreira

## Job

Emprego.

---

## Salary History

Histórico salarial.

---

## Resume

Currículo.

---

## Portfolio Project

Projeto de portfólio.

---

## Job Application

Candidatura.

---

# Domínio de Produtividade

## Task

Representa uma tarefa.

---

## Calendar Event

Evento.

---

## Daily Checklist

Checklist diário.

---

## Project

Projeto.

---

# Domínio Analytics

## Dashboard

Representa uma coleção de indicadores.

---

## KPI

Indicador.

Exemplos:

* Patrimônio
* Economia mensal
* Peso
* Horas estudadas

---

## Report

Relatórios.

---

# Domínio IA

## Insight

Informação gerada automaticamente.

Exemplos:

* Seu patrimônio cresceu 12%.
* Você gastou acima da média.
* Esta compra atrasou sua meta em 18 dias.

---

## Forecast

Representa previsões.

Exemplos:

* Patrimônio futuro.
* Data prevista para concluir metas.
* Evolução financeira.

---

## Recommendation

Sugestões geradas automaticamente.

Exemplo:

"Investindo R$ 300 a mais por mês você alcançará sua meta 10 meses antes."

---

# Relacionamentos

O relacionamento entre os principais domínios pode ser representado da seguinte forma:

```text
User
├── Accounts
│   └── Transactions
│       └── Categories
│
├── Credit Cards
│   └── Invoices
│
├── Assets
├── Liabilities
│
├── Goals
│   └── Goal Contributions
│
├── Habits
├── Workouts
├── Body Measurements
│
├── Courses
├── Books
├── Study Sessions
├── Certifications
│
├── Jobs
├── Salary History
├── Portfolio Projects
├── Job Applications
│
├── Tasks
├── Calendar Events
├── Projects
│
└── Analytics
    ├── KPIs
    ├── Reports
    ├── Insights
    ├── Forecasts
    └── Recommendations
```

---

# Regras Gerais

Todas as entidades deverão:

* Possuir identificador único.
* Possuir data de criação.
* Possuir data de atualização.
* Pertencer a um usuário.
* Ser fortemente tipadas.
* Possuir regras de negócio próprias.

Sempre que possível, regras de negócio deverão permanecer no domínio, evitando dependências da camada de infraestrutura.

---

# Objetivo Final

O Domain Model representa a linguagem do negócio do LifeOS. Ele servirá como referência para a modelagem do banco de dados, definição das APIs, implementação das regras de negócio e evolução da arquitetura, garantindo consistência entre todos os módulos do sistema ao longo do desenvolvimento.
