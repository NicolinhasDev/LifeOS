# 03 - Requisitos

## Objetivo

Este documento define os requisitos funcionais e não funcionais do LifeOS. Seu objetivo é servir como referência para o desenvolvimento, garantindo que todas as funcionalidades estejam alinhadas com a visão do produto e que decisões técnicas sejam tomadas de forma consistente.

---

# Requisitos Funcionais (RF)

## RF001 — Autenticação

O sistema deve permitir:

* Cadastro de usuários.
* Login.
* Logout.
* Recuperação de senha.
* Alteração de senha.
* Gerenciamento de perfil.

---

## RF002 — Dashboard

O sistema deve apresentar um painel inicial contendo:

* Saldo atual.
* Patrimônio líquido.
* Objetivos em andamento.
* Indicadores financeiros.
* Resumo de receitas e despesas.
* Próximos vencimentos.
* Evolução patrimonial.
* Hábitos do dia.
* Agenda do dia.
* Insights inteligentes.

---

## RF003 — Finanças

O sistema deve permitir:

* Cadastro de contas bancárias.
* Cadastro de carteiras.
* Cadastro de cartões de crédito.
* Cadastro de receitas.
* Cadastro de despesas.
* Cadastro de transferências.
* Cadastro de categorias.
* Cadastro de subcategorias.
* Cadastro de recorrências.
* Controle de assinaturas.

---

## RF004 — Patrimônio

O sistema deve permitir registrar:

* Dinheiro em conta.
* Investimentos.
* Imóveis.
* Veículos.
* Bens pessoais.
* Criptomoedas.
* Dívidas.
* Financiamentos.

O patrimônio líquido deverá ser calculado automaticamente.

---

## RF005 — Objetivos

O sistema deve permitir criar metas como:

* Apartamento.
* Casa.
* Moto.
* Carro.
* Reserva de emergência.
* Viagem.
* Aposentadoria.
* Cidadania portuguesa.
* Objetivos personalizados.

Cada objetivo deverá possuir:

* Valor alvo.
* Valor atual.
* Data prevista.
* Prioridade.
* Percentual de conclusão.
* Previsão automática de conclusão.

---

## RF006 — Saúde

O sistema deverá permitir registrar:

* Peso.
* Altura.
* IMC.
* Percentual de gordura.
* Circunferências corporais.
* Treinos.
* Evolução física.
* Hábitos saudáveis.

---

## RF007 — Estudos

O sistema deverá permitir:

* Cadastro de cursos.
* Cadastro de livros.
* Registro de tempo estudado.
* Controle de progresso.
* Certificações.
* Trilhas de aprendizado.

---

## RF008 — Carreira

O sistema deverá permitir:

* Histórico salarial.
* Empresas.
* Currículo.
* Portfólio.
* Certificações.
* Objetivos profissionais.
* Controle de candidaturas.

---

## RF009 — Produtividade

O sistema deverá permitir:

* Calendário.
* Checklist diário.
* Hábitos.
* Tarefas.
* Projetos.
* Eventos.

---

## RF010 — Analytics

O sistema deverá gerar dashboards contendo:

* Evolução financeira.
* Evolução patrimonial.
* Evolução de hábitos.
* Evolução da saúde.
* Evolução profissional.
* Evolução dos estudos.
* Comparativos mensais.
* Indicadores personalizados.

---

## RF011 — Inteligência

O sistema deverá gerar automaticamente insights como:

* Impacto dos gastos sobre objetivos.
* Projeções financeiras.
* Previsão de patrimônio.
* Identificação de tendências.
* Alertas.
* Recomendações.
* Classificação automática de transações.
* Resumos inteligentes.

---

## RF012 — Integrações

O sistema deverá suportar futuramente:

* Open Finance.
* Importação OFX.
* Importação CSV.
* Google Calendar.
* Google Fit.
* Samsung Health.
* Apple Health.
* APIs bancárias.
* APIs de investimentos.

---

# Requisitos Não Funcionais (RNF)

## Arquitetura

* Clean Architecture.
* SOLID.
* Feature Based Folder Structure.
* Componentização.
* Design System próprio.
* Separação clara entre domínio, aplicação e infraestrutura.

---

## Front-end

* React.
* TypeScript.
* Vite.
* Tailwind CSS.
* shadcn/ui.
* React Router.
* TanStack Query.
* React Hook Form.
* Zod.
* Recharts.

---

## Back-end

* NestJS.
* Prisma ORM.
* PostgreSQL.
* Docker.

---

## Interface

* Mobile First.
* Responsiva.
* Dark Mode.
* Aparência premium.
* Navegação intuitiva.
* Alto desempenho.
* Acessibilidade.

---

## Qualidade

* Código limpo.
* Alta reutilização.
* Tipagem forte.
* Baixo acoplamento.
* Alta coesão.
* Testes automatizados.

---

## Segurança

* Autenticação JWT.
* Criptografia de senhas.
* Controle de permissões.
* Validação de entrada.
* Proteção contra ataques comuns.

---

## Infraestrutura

* Docker.
* Docker Compose.
* CI/CD.
* Versionamento Git.
* Deploy automatizado.
* Variáveis de ambiente.

---

## Escalabilidade

O sistema deverá ser preparado desde a primeira versão para suportar:

* Múltiplos usuários.
* Crescimento modular.
* Novos domínios.
* Integrações externas.
* Evolução para um produto SaaS.

---

# Critérios de Sucesso

O LifeOS será considerado bem-sucedido quando conseguir:

* Centralizar as principais informações da vida do usuário.
* Fornecer indicadores claros e úteis.
* Gerar previsões confiáveis.
* Auxiliar na tomada de decisões.
* Reduzir a necessidade de múltiplos aplicativos.
* Servir como base para evolução contínua e futura comercialização como plataforma SaaS.
