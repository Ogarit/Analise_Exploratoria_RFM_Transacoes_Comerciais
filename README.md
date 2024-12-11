# Análise de Dados de Transações Comerciais

## Visão Geral

Este projeto tem como objetivo realizar uma **análise exploratória de dados** (EDA) de transações comerciais fictícias. O conjunto de dados contém informações sobre transações, incluindo o número da fatura, código do item, descrição do item, quantidade comprada, data da fatura, preço unitário, ID do cliente, país e preço total.

A análise envolve o **tratamento de dados**, **exploração de padrões** e a geração de **insights úteis** para entender o comportamento de compra dos clientes.

## Estrutura do Notebook

### 1. **Importação das Bibliotecas**

Inicialmente, são importadas as bibliotecas necessárias para manipulação e análise dos dados.

   ```python
    import numpy as np
    import pandas as pd
    import matplotlib.pyplot as plt
    import seaborn as sns
   ```

### 2. **Carregamento dos Dados**

Os dados são carregados de um arquivo CSV utilizando o `pandas`.

   ```python
    df = pd.read_csv('Data.csv', delimiter=',')
    df.head()
   ```

### 3. **Limpeza dos Dados**

Realiza-se a remoção de espaços em branco das colunas e substituição de valores vazios por `NaN`.

   ```python
    df.columns = [col.strip() for col in df.columns]
    df = df.applymap(lambda x: x.strip() if isinstance(x, str) else x)
    df = df.applymap(lambda x: np.nan if x == '' else x)
   ```

### 4. **Análise Descritiva Inicial**

A função `describe()` é utilizada para obter estatísticas descritivas das colunas numéricas do dataset.

   ```python
    df.describe()
   ```

### 5. **Exploração de Dados e Visualizações**

Foi utilizadas bibliotecas como `matplotlib` e `seaborn` para gerar gráficos e explorar padrões e tendências dos dados, como a distribuição de compras por cliente, por país, entre outros.

### 6. **Tratamento de Valores Nulos**

Identifiquei e tratei valores nulos por meio de técnicas como a substituição por médias ou a exclusão de registros incompletos, conforme apropriado.

### 7. **Análise de Outliers**

Detectaei e tratei valores atípicos que poderiam afetar a análise, garantindo uma interpretação mais precisa dos dados.

### 8. **Geração de Novas Features**

Criei novas colunas a partir dos dados existentes, como o `TotalPrice`, calculado pela multiplicação da `Quantity` pelo `UnitPrice`.

   ```python
    df['TotalPrice'] = df['Quantity'] * df['UnitPrice']
   ```

### 9. **Conclusão e Insights**

A análise resulta em insights sobre o comportamento de compra, como a identificação de clientes mais valiosos, os itens mais comprados, padrões de compra por país, entre outros. Além disso, são feitas recomendações para ações futuras, como melhorar o atendimento aos clientes mais frequentes.

## Como Utilizar Este Notebook

### 1. **Requisitos**

- Python 3.x
- Bibliotecas necessárias:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
Você pode instalar as dependências necessárias com o seguinte comando:

    ```bash
    pip install numpy pandas matplotlib seaborn
    ```

### 2. **Execução**

1. Clone o repositório:
   ```bash
   git clone https://github.com/Ogarit/Analise_Exploratoria_RFM_Transacoes_Comerciais.git
2. Navegue até o diretório do projeto:
   ```bash
   cd Analise_Exploratoria_RFM_Transacoes_Comerciais
3. Coloque o arquivo de dados `Data.csv` no mesmo diretório que o notebook.
4. Abra o Jupyter Notebook e execute todas as células sequencialmente.

### 3. **Modificação**

Este notebook é flexível e pode ser modificado para atender a necessidades específicas, como alteração de parâmetros de análise ou adição de novas seções.

## Estrutura dos Dados

O conjunto de dados contém as seguintes colunas:
- **InvoiceNo**: Número da fatura (identificador único para cada transação).
- **StockCode**: Código do item (identificador do produto).
- **Description**: Descrição do item.
- **Quantity**: Quantidade comprada do item.
- **InvoiceDate**: Data da fatura (momento da transação).
- **UnitPrice**: Preço unitário do item.
- **CustomerID**: ID do cliente que realizou a compra.
- **Country**: País onde o cliente está localizado.
- **TotalPrice**: Preço total (calculado como `Quantity * UnitPrice`).
