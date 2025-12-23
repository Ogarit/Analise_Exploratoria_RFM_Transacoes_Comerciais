# 🚀 Análise Exploratória de Dados de Transações Comerciais (EDA)

## Visão Geral

Este projeto realiza uma **Análise Exploratória de Dados (EDA)** detalhada em um conjunto de transações comerciais. O objetivo é transformar dados brutos de vendas em *insights* acionáveis para a gestão comercial, focando na compreensão do comportamento do cliente e na otimização estratégica.

### 📊 1. Contexto de Negócio

Este projeto simula um cenário de uma **empresa comercial de varejo (e-commerce ou atacado)**. A organização necessita aprofundar a compreensão sobre o comportamento de compra de seus clientes para melhorar sua **estratégia de vendas e relacionamento (CRM)**.

A análise lida com desafios comuns, como a identificação de clientes de alto valor, a compreensão da sazonalidade e a avaliação do impacto geográfico nas vendas, essenciais para **impulsionar o crescimento e a retenção**.

### 📌 2. Objetivo da Análise

O objetivo principal desta análise é **explorar, limpar e estruturar** os dados de transações para:

1. **Identificar Padrões de Comportamento:** Mapear a distribuição de compras por cliente, item e localização geográfica.
2. **Gerar Métricas Chave:** Criar *features* importantes, como o Preço Total (`TotalPrice`) por transação.
3. **Apoiar Decisões Comerciais:** Fornecer *insights* claros que apoiem a segmentação de clientes, otimização de estoque e direcionamento de campanhas promocionais.

### 🛠️ 3. Abordagem Analítica e Ferramentas Utilizadas

As análises foram realizadas utilizando ferramentas padrão do ecossistema de Data Science em Python:

* **Python (Pandas, NumPy):** Para carregamento, limpeza eficiente, padronização e manipulação dos dados, incluindo o tratamento de valores nulos e *outliers*.
* **Matplotlib e Seaborn:** Para a criação de visualizações robustas que revelam padrões e tendências (distribuição de quantidade, preço e país).
* **Jupyter Notebook:** Para documentação completa e garantia de reprodutibilidade do fluxo de trabalho.

### 📈 4. Principais Insights

A exploração detalhada dos dados revelou os seguintes padrões de negócio:

* **Distribuição de Receita:** Foi identificado que uma pequena parcela de clientes concentra a maior parte da receita total (**Princípio de Pareto ou 80/20**), indicando a criticidade de estratégias de fidelização.
* **Análise Geográfica:** Embora o volume de transações seja dominante em um país, outros países com menor frequência de compras apresentaram um **ticket médio (Average UnitPrice)** elevado, sugerindo mercados de alto valor.
* **Itens de Alto Volume:** Certos itens são consistentemente comprados em grandes quantidades, classificando-os como *key products* que requerem atenção especial na **gestão de estoque e suprimentos**.

### 🎯 5. Possíveis Decisões de Negócio

Com base nos *insights* obtidos, a empresa pode implementar as seguintes ações estratégicas:

* **Estratégias de Fidelização:** Criar programas de recompensas e atendimento premium **focados nos clientes de alto valor** identificados, visando maximizar a retenção.
* **Campanhas de Segmentação:** Desenvolver campanhas promocionais e de expansão específicas para mercados geográficos (países) que demonstram alto ticket médio, priorizando o lucro sobre o volume.
* **Otimização de Estoque:** Utilizar a análise de volume e frequência dos itens mais vendidos para otimizar os níveis de estoque e **prevenir rupturas**, melhorando a eficiência operacional.

## 🔧 Estrutura do Projeto e Execução

### Estrutura dos Dados

O conjunto de dados contém as seguintes colunas essenciais:

| Coluna | Descrição |
| --- | --- |
| **InvoiceNo** | Identificador Único da Transação/Fatura. |
| **StockCode** | Código de Identificação do Produto (SKU). |
| **Description** | Descrição do item comprado. |
| **Quantity** | Quantidade de itens comprados na transação. |
| **InvoiceDate** | Data e Hora da realização da transação. |
| **UnitPrice** | Preço unitário do item. |
| **CustomerID** | ID do Cliente que realizou a compra. |
| **Country** | País de localização da transação. |
| **TotalPrice** | Preço total (Calculado: `Quantity * UnitPrice`). |

### Requisitos e Instalação

* Python 3.x
* Bibliotecas: `numpy`, `pandas`, `matplotlib`, `seaborn`

Instale as dependências necessárias com o seguinte comando:

```bash
pip install numpy pandas matplotlib seaborn

```

### Execução

1. Clone o repositório:
```bash
git clone https://github.com/Ogarit/Analise_Exploratoria_RFM_Transacoes_Comerciais.git

```


2. Navegue até o diretório do projeto:
```bash
cd Analise_Exploratoria_RFM_Transacoes_Comerciais

```


3. Coloque o arquivo de dados `Data.csv` no mesmo diretório que o notebook.
4. Abra o Jupyter Notebook e execute as células sequencialmente para replicar a análise.
