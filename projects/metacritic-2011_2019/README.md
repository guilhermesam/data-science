## Relatório

Dados extraídos do metacritic.com.
Aqui constam informações referentes a jogos da 8ª geração de videogames, desde 2011 até 2019.

Questões iniciais: 

- Gêneros favoritos;
- Lançamentos para cada plataforma;

O dataset original é um arquivo .csv obtido do site [Kaggle](https://www.kaggle.com/). A arquivo continha informações sobre os games (nome, desenvolvedora, plataforma, ano de lançamento, etc.) e informações sobre sua avaliação, tanto do público geral quanto do próprio Metacritics. Primeiramente, foi realizada uma verificação sobre quais campos apresentavam valores faltantes. Dos campos que eram interessantes para o processo de análise, apenas o nome da desenvolvedora se mostrava faltante. Para contornar isso, foi efetuada uma consulta em API pública para obter o nome da desenvolvedora passando o nome do jogo. Após o processo de limpeza dos dados, foram gerados dois novos datasets, um que armazenava informações sobre os gêneros cuja avaliação média dos jogos era maior, em ordem decrescente e outro que continha a soma dos jogos lançados para cada plataforma. Nesta etapa, foram identificados alguns problemas no levantamento das questões originais, que serão abordados adiante.

No processo de visualização de dados, foram então construídos dois barplots, que demonstram visualmente os gêneros favoritos e as plataformas com maior número de jogos.

![games_per_platform](https://github.com/guilhermesam/data-science/blob/master/projects/metacritic-2011_2019/images/games_per_platform.jpg)

No período de análise de dados, foi identificado um problema na maneira que a busca por uma resposta para gêneros favoritos apresentava. Não era suficiente apenas somar as avaliações dos jogos agrupados por gênero, já que essa média seria enganosa em casos de gêneros com poucos jogos, como foi o caso do gênero "3D". Este problema está sendo resolvido, porém considerei interessante realizar este relato da importância de não apenas fazer ciência de dados, mas fazer a ciência de dados correta, que consiga demonstrar a realidade como ela é, evitando criar uma realidade farsante.

![favorite_genres](https://github.com/guilhermesam/data-science/blob/master/projects/metacritic-2011_2019/images/favorite_genres.jpg)

É interessante observar, por exemplo, que o gênero "3D", dentre 54 gêneros, ocupa a sexta posição como mais popular, porém isso reflete corretamente a realidade? Se formos analisar nosso dataset, veremos que dentre 5699 registros, existem apenas 2 que constam como gênero 3D, o que torna a análise insuficiente por falta de dados. É importante que um cientista de dados consiga realizar uma validação de seus dados, se estão corretamente representando a realidade para o qual foram analisados.
