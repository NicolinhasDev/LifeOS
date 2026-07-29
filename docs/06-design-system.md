# 06 - Design System

## Objetivo

O Design System do LifeOS tem como objetivo garantir consistência visual, reutilização de componentes e uma excelente experiência de uso em toda a aplicação. Ele servirá como base para o desenvolvimento da interface, reduzindo inconsistências e acelerando a criação de novas funcionalidades.

A identidade visual será inspirada em produtos modernos como **Linear**, **Stripe**, **Notion**, **GitHub**, **Raycast** e **Vercel**, priorizando simplicidade, clareza e sofisticação.

---

# Princípios de Design

Toda a interface deverá seguir os seguintes princípios:

* Simplicidade acima de complexidade.
* Consistência em todos os módulos.
* Hierarquia visual clara.
* Espaçamento generoso.
* Baixa carga cognitiva.
* Feedback imediato para ações do usuário.
* Acessibilidade.
* Mobile First.
* Dark Mode como padrão.

---

# Identidade Visual

## Estilo

O LifeOS adotará uma identidade moderna e minimalista.

Características:

* Visual limpo.
* Poucos elementos decorativos.
* Bordas suaves.
* Cantos arredondados.
* Sombras discretas.
* Contraste equilibrado.
* Uso estratégico de cores para destacar informações importantes.

---

# Paleta de Cores

## Cores Primárias

Responsáveis por ações principais, links e destaques.

Exemplo:

* Primary
* Primary Hover
* Primary Foreground

---

## Cores Secundárias

Utilizadas para elementos de apoio.

* Secondary
* Secondary Hover

---

## Cores Semânticas

Representam estados do sistema.

* Success
* Warning
* Error
* Info

---

## Tons Neutros

Utilizados para:

* Fundo.
* Cards.
* Bordas.
* Texto.
* Elementos desabilitados.

A paleta deverá ser baseada em tokens, permitindo alteração futura sem impacto nos componentes.

---

# Tipografia

A tipografia deverá priorizar legibilidade.

## Hierarquia

* Display
* Heading 1
* Heading 2
* Heading 3
* Heading 4
* Body Large
* Body
* Small
* Caption

Cada nível deverá possuir tamanho, peso e espaçamento padronizados.

---

# Espaçamento

Será utilizada uma escala consistente de espaçamento.

Exemplo:

* 4 px
* 8 px
* 12 px
* 16 px
* 24 px
* 32 px
* 48 px
* 64 px

Todo componente deverá seguir essa escala.

---

# Grid

O sistema deverá utilizar:

* Grid responsivo.
* Containers centralizados.
* Layout fluido.
* Espaçamento consistente entre elementos.

---

# Bordas

Os componentes utilizarão cantos arredondados padronizados.

Exemplo:

* Small
* Medium
* Large
* Extra Large

---

# Sombras

Sombras deverão ser discretas e utilizadas apenas para reforçar profundidade.

Níveis:

* Small
* Medium
* Large

Evitar excesso de efeitos visuais.

---

# Ícones

Todos os ícones deverão pertencer à mesma biblioteca.

Requisitos:

* Estilo consistente.
* Traços uniformes.
* Fácil reconhecimento.
* Compatibilidade com Dark Mode.

---

# Componentes

Todos os componentes reutilizáveis serão centralizados em um pacote dedicado.

## Componentes Base

* Button
* IconButton
* Input
* Textarea
* Checkbox
* Radio
* Switch
* Select
* Combobox
* Badge
* Avatar
* Tooltip
* Dialog
* Drawer
* Popover
* Tabs
* Accordion
* Card
* Table
* Pagination
* Skeleton
* Progress
* Alert
* Toast
* Spinner

---

# Componentes de Layout

* Sidebar
* Navbar
* Header
* Footer
* Container
* Section
* Grid
* Divider
* Breadcrumb

---

# Componentes de Dashboard

* Stat Card
* Metric Card
* Chart Card
* Progress Card
* Goal Card
* Timeline
* Activity Feed
* KPI Widget

---

# Componentes Financeiros

* Balance Card
* Account Card
* Credit Card
* Transaction List
* Investment Card
* Goal Progress
* Expense Breakdown
* Income Summary

---

# Estados dos Componentes

Todos os componentes deverão possuir estados padronizados.

* Default
* Hover
* Active
* Focus
* Disabled
* Loading
* Success
* Error

---

# Formulários

Todos os formulários seguirão o mesmo padrão.

Elementos obrigatórios:

* Label.
* Campo.
* Texto de ajuda.
* Mensagem de erro.
* Validação em tempo real.
* Feedback visual.

---

# Gráficos

Os gráficos deverão seguir uma identidade única.

Princípios:

* Poucas cores.
* Alto contraste.
* Boa legibilidade.
* Interatividade.
* Responsividade.

Tipos previstos:

* Linha.
* Barras.
* Área.
* Pizza.
* Radar.
* Heatmap.
* Indicadores.

---

# Animações

As animações deverão ser sutis e rápidas.

Exemplos:

* Fade.
* Slide.
* Scale.
* Hover.
* Loading.
* Skeleton.

O objetivo é transmitir fluidez sem comprometer desempenho.

---

# Dark Mode

O Dark Mode será considerado o tema principal da aplicação.

Todos os componentes deverão funcionar corretamente tanto no tema escuro quanto no claro.

Nenhum componente poderá depender de cores fixas.

---

# Responsividade

A interface deverá funcionar em:

* Smartphones.
* Tablets.
* Notebooks.
* Monitores ultrawide.

Todo componente deverá ser desenvolvido com comportamento responsivo desde sua criação.

---

# Acessibilidade

O sistema deverá seguir boas práticas de acessibilidade.

Incluindo:

* Navegação por teclado.
* Contraste adequado.
* Estados de foco.
* Labels acessíveis.
* Compatibilidade com leitores de tela.

---

# Convenções de Componentes

Todo componente deverá ser:

* Reutilizável.
* Independente das regras de negócio.
* Fortemente tipado.
* Bem documentado.
* Testável.
* Responsivo.

Sempre que possível, utilizar composição em vez de herança.

---

# Objetivo Final

O Design System do LifeOS deverá servir como uma fundação sólida para toda a interface da aplicação, garantindo consistência, escalabilidade e uma experiência premium. Cada novo componente deverá seguir os padrões estabelecidos neste documento, permitindo que o produto evolua mantendo identidade visual, qualidade e facilidade de manutenção.
