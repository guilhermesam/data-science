## Relatório

Dados extraídos do site de dados abertos do Governo Federal. Devido ao arquivo .csv utilizado ser grande demais para ser armazenado no GitHub, ele não está disponível no repositório do projeto, mas pode ser acessado [aqui](http://dados.gov.br/dataset/serie-historica-de-precos-de-combustiveis-por-revenda). Nele, constam informações sobre a compra e venda de combustíveis automotivos no primeiro semestre de 2019.

Questões iniciais:
- Preço médio da gasolina por estado;
- Média do preço da gasolina na cidade de Alegrete;

### Data Cleansing
Dos dados, apenas o valor de compra apresentava valores missing, já que não o iríamos utilizar, se fez desnecessário seu preenchimento. Além disso, valores de ponto flutuante, como valor de venda e valor de compra, estavam na notação brasileira que utiliza vírgula para separar a casa decimal, o que para o Python representava uma string. Foi aplicado brevemente uma função anônima, utilizando o método apply() do dataframe, que percorria estas colunas e substituia a vírgula pelo ponto e, após isso, convertia tal valor para float.

### Data Analysis
Após o processo de limpeza, o objetivo foi criar novos conjuntos de dados específicos para cada questão a ser respondida. Para a primeira questão, foi criado um novo dataset com todos os estados, que se repetiam cinco vezes, uma para cada tipo de combustível bem como o preço médio. 

![price_by_state_df](https://github.com/guilhermesam/data-science/blob/master/projects/fuel_2019/images/price_by_state_df.png)

Para responder à segunda questão, o dataframe original foi desfragmentado em uma série temporal do Pandas, cujo índice e valores são a data de coleta e preço médio de venda, respectivamente. O preço médio foi obtido com a função `groupby`, sobrescrevendo a coluna original de preço de venda pela média de cada valor do índice.

### Data Visualization
Com o dataframe de preço por estado gerado, foi gerado um gráfico estilo heatmap do Seaborn, cujo eixo x exibe o tipo de combustível e o eixo y exibe a sigla de cada estado do Brasil. Cada ponto do gráfico mostra o preço médio de cada combustível para cada estado.

![price_by_state_heatmap](https://github.com/guilhermesam/data-science/blob/master/projects/fuel_2019/images/fuel2019.jpg)

Respondendo à segunda questão, foi gerado um gráfico do matplotlib.pyplot, do estilo plot, cujo eixo x representa a data de coleta, exibida em mês, e o eixo y representa o preço médio de venda. 

![alegrete_fuel](https://github.com/guilhermesam/data-science/blob/master/projects/fuel_2019/images/alegrete_fuel.jpg)
