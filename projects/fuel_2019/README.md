## Relatório

Dados extraídos do site de dados abertos do Governo Federal. Devido ao arquivo .csv utilizado ser grande demais para ser armazenado no GitHub, ele não está disponível no repositório do projeto, mas pode ser acessado [aqui](http://dados.gov.br/dataset/serie-historica-de-precos-de-combustiveis-por-revenda). Nele, constam informações sobre a compra e venda de combustíveis automotivos no primeiro semestre de 2019.

Questões iniciais:
- Preço médio da gasolina por estado;

### Data Cleansing
Dos dados, apenas o valor de compra apresentava valores missing, já que não o iríamos utilizar, se fez desnecessário seu preenchimento. Além disso, valores de ponto flutuante, como valor de venda e valor de compra, estavam na notação brasileira que utiliza vírgula para separar a casa decimal, o que para o Python representava uma string. Foi aplicado brevemente uma função anônima, utilizando o método apply() do dataframe, que percorria estas colunas e substituia a vírgula pelo ponto e, após isso, convertia tal valor para float.

### Data Analysis
Após o processo de limpeza, o objetivo foi criar novos conjuntos de dados específicos para cada questão a ser respondida. Foi criado um novo dataset com todos os estados, que se repetiam cinco vezes, uma para cada tipo de combustível bem como o preço médio.

![price_by_state_df](https://github.com/guilhermesam/data-science/blob/master/projects/fuel_2019/images/price_by_state_df.png)

### Data Visualization
Com o dataframe de preço por estado gerado, foi gerado um gráfico estilo heatmap do Seaborn.

![price_by_state_heatmap](https://github.com/guilhermesam/data-science/blob/master/projects/fuel_2019/images/fuel2019.jpg)
