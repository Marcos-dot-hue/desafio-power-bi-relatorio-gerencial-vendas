# 📊 Desafio Power BI — Relatório Gerencial de Vendas

Projeto desenvolvido como parte do desafio prático de **Power BI da DIO**, com o objetivo de aplicar os conhecimentos adquiridos durante o Bootcamp na construção, organização e análise de relatórios interativos.

O desafio consistiu na reprodução e evolução de páginas desenvolvidas durante o curso, utilizando diferentes recursos de visualização de dados, indicadores, filtros, segmentações e navegação.

Além dos requisitos propostos, o projeto foi personalizado com novos recursos de interação e apresentação, buscando melhorar a experiência de análise e explorar funcionalidades adicionais do Power BI.

---

## 🎯 Objetivo do Projeto

Construir um relatório gerencial capaz de apresentar informações relevantes sobre:

- vendas;
- unidades vendidas;
- descontos;
- custos;
- lucro;
- desempenho por produto;
- desempenho por segmento;
- desempenho por país;
- evolução dos resultados ao longo do tempo.

O relatório também foi estruturado para permitir diferentes formas de exploração dos dados por meio de filtros, segmentações e navegação entre páginas.

---

## 📈 Sales Report

A página **Sales Report** apresenta uma visão geral do desempenho comercial.

### Principais indicadores

- Sales
- Units Sold
- Discounts
- Vendas Brutas
- COGS

### Recursos utilizados

- cartões de indicadores (KPIs);
- gráfico de evolução das vendas por período;
- gráfico de vendas por produto;
- análise geográfica por país;
- segmentação por período;
- gráfico por segmento;
- botões para alternância entre visualizações;
- navegação para a página de análise de lucro.

### Interatividade

Foram utilizados **Indicadores (Bookmarks)** para permitir a alternância entre diferentes formas de visualização dos segmentos.

Os botões **Pizza** e **Barras** permitem trocar dinamicamente entre gráfico de pizza e gráfico de barras utilizando o mesmo espaço do relatório.

Também foi criado o botão **Lucro**, que direciona o usuário para a página **Lucro Report Detalhado**.

---

## 💰 Lucro Report Detalhado

A página **Lucro Report Detalhado** foi desenvolvida para aprofundar a análise da rentabilidade.

### Principais indicadores

- Lucro Total
- Vendas Brutas
- COGS
- Discounts

### Visualizações utilizadas

- gráfico de barras — lucro por produto;
- Treemap — lucro por segmento;
- gráfico de rosca — lucro por país;
- Ribbon Chart — evolução do lucro por período e produto;
- gráfico de cascata — contribuição dos produtos e segmentos para o resultado.

A página também possui segmentação por ano e botão de navegação para retornar ao **Sales Report**.

---

## 🗓️ Período de Análise

Foi criada uma segmentação de datas para permitir que o usuário escolha o intervalo desejado para análise.

O filtro modifica dinamicamente os indicadores e gráficos da página, permitindo analisar diferentes períodos sem alterar a estrutura do relatório.

Para melhorar a experiência visual, foi criada a identificação **Período de Análise →**, direcionando visualmente o usuário para o filtro de datas.

---

## 🧮 Medidas

Durante o desenvolvimento também foi criada uma medida de margem de lucro utilizando DAX:

```DAX
Margem Lucro % =
DIVIDE(
    SUM(financials[Lucro Total]),
    SUM(financials[Vendas Brutas]),
    0
)
