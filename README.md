# Projeto de Modelagem de Dados com Power BI

Este repositório contém um projeto de Business Intelligence desenvolvido em Power BI. O objetivo principal foi transformar uma tabela de dados única (*flat table*) em um modelo dimensional otimizado no formato Star Schema (esquema estrela).

## 📖 Descrição do Projeto

O desafio consistiu em pegar uma tabela única chamada `Financial Sample` e, a partir dela, criar um conjunto de tabelas dimensão e uma tabela fato. O processo envolveu a criação de novas tabelas com base na original e a seleção de colunas específicas para compor cada uma delas.

## 🛠️ Etapas e Funcionalidades Utilizadas

### 1. Criação das Tabelas

A partir da tabela principal, foram criadas as seguintes tabelas:

* **`Financials_origem`**: Uma cópia de backup da tabela original, mantida em modo oculto.
* **`F_Vendas` (Tabela Fato)**: A tabela central do modelo, contendo as métricas de vendas e as chaves para as dimensões. Inclui colunas como `SK_ID`, `ID_Produto`, `Produto`, `Units Sold`, `Sales Price`, `Discount Band`, `Segment`, `Country`, `Salers`, `Profit` e `Date`.
* **`D_Produtos` (Tabela Dimensão)**: Contém informações agrupadas sobre os produtos. As colunas incluem `ID_produto`, `Produto` e métricas agregadas como `Média de Unidades Vendidas`, `Média do valor de vendas`, `Mediana do valor de vendas`, `Valor máximo de Venda` e `Valor mínimo de Venda`.
* **`D_Produtos_Detalhes` (Tabela Dimensão)**: Contém detalhes específicos de cada produto, como `ID_produtos`, `Discount Band`, `Sale Price`, `Units Sold` e `Manufacturing Price`.
* **`D_Descontos` (Tabela Dimensão)**: Dimensão focada nos descontos aplicados, contendo `ID_produto`, `Discount` e `Discount Band`.
* **`D_Detalhes` (Tabela Dimensão)**: Tabela criada para armazenar informações de vendas que não foram contempladas nas demais dimensões.
* **`D_Calendário` (Tabela Dimensão)**: Criada inteiramente com a função DAX `CALENDAR()`.

### 2. Transformações no Power Query

Para construir o modelo, diversas funcionalidades do Power Query foram utilizadas:

* **Agrupamento de Informações**: A ferramenta **Agrupar por** foi usada para criar métricas agregadas na tabela `D_Produtos`.
* **Criação de Coluna Condicional**: Foi adicionada uma coluna condicional para criar um índice numérico para os produtos (`ID_Produto`).
* **Reorganização de Colunas**: As colunas foram renomeadas e reorganizadas para tornar o modelo mais claro e intuitivo.

### 3. Funções DAX

* **`CALENDAR()`**: Utilizada para a criação da tabela `D_Calendário`.

---

**JONTHAN SALLES QUEIROZ**
