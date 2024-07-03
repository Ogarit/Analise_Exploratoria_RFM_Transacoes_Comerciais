# Análise de Dados de Transações Comerciais

#### Visão Geral

Este projeto envolve a análise de um conjunto de dados que contém informações fictícias sobre transações comerciais. O objetivo é realizar uma análise exploratória dos dados e limpar o conjunto de dados para obter insights significativos. As transações são descritas por várias colunas, como `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country` e `TotalPrice`.

#### Estrutura do Notebook

1. **Importação das Bibliotecas**
    - Utilizamos as bibliotecas `numpy` e `pandas` para manipulação e análise de dados.
    ```python
    import numpy as np
    import pandas as pd
    ```

2. **Carregamento dos Dados**
    - Os dados são carregados a partir de um arquivo CSV utilizando o `pandas`.
    ```python
    df = pd.read_csv('Data.csv', delimiter=',')
    df.head()
    ```

3. **Limpeza dos Dados**
    - Remoção de espaços em branco das colunas e substituição de valores vazios por `NaN`.
    ```python
    df.columns = [col.strip() for col in df.columns]
    df = df.applymap(lambda x: x.strip() if isinstance(x, str) else x)
    df = df.applymap(lambda x: np.nan if x == '' else x)
    ```

4. **Análise Descritiva Inicial**
    - Utilização do método `describe` do `pandas` para obter estatísticas descritivas das colunas numéricas.
    ```python
    df.describe()
    ```

5. **Exploração de Dados e Visualizações**
    - A análise inclui exploração de dados por meio de visualizações, usando bibliotecas como `matplotlib` e `seaborn` para gerar gráficos que ajudam a entender melhor as tendências e padrões nos dados.

6. **Tratamento de Valores Nulos**
    - Identificação e tratamento de valores nulos, como substituição por média/mediana ou exclusão, conforme apropriado.

7. **Análise de Outliers**
    - Detecção e tratamento de outliers para garantir que a análise não seja distorcida por valores anômalos.

8. **Geração de Novas Features**
    - Criação de novas features a partir dos dados existentes, como `TotalPrice`, calculada como `Quantity` multiplicado pelo `UnitPrice`.

9. **Conclusão e Insights**
    - Discussão sobre os principais insights obtidos a partir da análise e sugestões de ações ou investigações futuras com base nos resultados.

#### Como Utilizar Este Notebook

1. **Requisitos**
    - Certifique-se de ter `Python` instalado juntamente com as bibliotecas `numpy`, `pandas`, `matplotlib` e `seaborn`.

2. **Execução**
    - Clone o repositório e navegue até o diretório.
    - Coloque o arquivo de dados `Data.csv` no mesmo diretório que o notebook.
    - Abra o Jupyter Notebook e execute todas as células sequencialmente.

3. **Modificação**
    - Você pode adaptar este notebook para atender às suas necessidades específicas, alterando os parâmetros de análise ou adicionando novas seções conforme necessário.

#### Estrutura dos Dados

- **InvoiceNo**: Número da fatura.
- **StockCode**: Código do item.
- **Description**: Descrição do item.
- **Quantity**: Quantidade comprada.
- **InvoiceDate**: Data da fatura.
- **UnitPrice**: Preço unitário.
- **CustomerID**: ID do cliente.
- **Country**: País do cliente.
- **TotalPrice**: Preço total (calculado como Quantity * UnitPrice).
