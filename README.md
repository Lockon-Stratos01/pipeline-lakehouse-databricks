# 🛒 Pipeline de Vendas em Arquitetura Medallion (Databricks & PySpark)

Este projeto demonstra a construção de um pipeline de dados ponta a ponta seguindo o conceito de **Lakehouse** e a **Arquitetura Medallion (Bronze, Silver e Gold)** no ambiente do **Databricks Community Edition**.

---

## 🏗️ Arquitetura do Projeto

O fluxo de dados foi dividido em 3 camadas de maturação:

1. **Camada Bronze (Raw Data):**
   - Ingestão dos dados brutos de pedidos de e-commerce.
   - Carga inicial em DataFrame distribuído via **Apache Spark (PySpark)**.

2. **Camada Silver (Clean & Trusted Data):**
   - Limpeza e padronização das informações.
   - Conversão da coluna `data_pedido` de texto para o tipo primitivo `Date`.
   - Padronização de nomes de categorias em maiúsculas (`upper`).
   - Criação de coluna calculada de imposto estimado (10% sobre o valor da venda).

3. **Camada Gold (Business Level / Analytics):**
   - Agrupamento de métricas estratégicas por categoria de produto (`groupBy` e `agg`).
   - Cálculo de **Faturamento Total**, **Imposto Total** e **Total de Pedidos**.
   - Ordenação decrescente por faturamento para análise de pareto/ranking de desempenho.
   - Geração de visualização executiva (gráfico de barras ordenado com formatação em moeda).

---

## 🛠️ Tecnologias e Ferramentas

* **Plataforma:** Databricks (Serverless Compute)
* **Linguagem:** Python / PySpark
* **Framework de Big Data:** Apache Spark
* **Paradigma:** Lakehouse / Arquitetura Medallion

---

## 📊 Principais Resultados

A categoria de **Eletrônicos** liderou com folga o faturamento da empresa (R$ 4.700), seguida por **Móveis** (R$ 950) e **Acessórios** (R$ 410), fornecendo subsídios claros para decisões de estoque e campanhas de marketing.

---

## 👤 Autor
Desenvolvido por **Cassio** durante a jornada de aprendizado em Ciência de Dados e Big Data na DIO.
