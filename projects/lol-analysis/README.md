# LoL Analysis

## Sobre o jogo
League of Legends é um jogo de estratégia em que duas equipes de cinco, entre mais de 140, poderosos Campeões se enfrentam para destruir a base uma da outra. O mapa é dividido em três rotas, chamadas de rota superior, rota do meio e rota inferior, além da selva, que é o espaço que compreende o intervalo entre as rotas. O Nexus é o grande objetivo do jogo. Ele fica localizado ao centro da base inimiga, dentro do mapa, e precisa ser destruído para que você alcance a vitória. Porém, a tarefa não é fácil, já que ele é protegido pelo caminho por torres, tropas e campeões do time adversário. Além disso, o Nexus tem uma vida longa e nem sempre será fácil destroçá-lo. Manter o controle das tropas nas rotas é fundamental, pois sem elas, não é possível derrubar uma torre, além de serem a principal fonte de obtenção de ouro na partida.

![map](https://vignette.wikia.nocookie.net/leagueoflegends/images/5/53/Summoner%27s_Rift_Update_Map.png/revision/latest?cb=20170223053555)

### Mecânica de Partidas
Em uma partida, podem participar 10 jogadores, distribuídos em 2 equipes, cada qual com uma função específica, sendo elas: toplaner, responsável pela rota do topo; caçador, responsável pela selva e com a função de ajudar as rotas a ganharem vantagem; midlaner, responsável pela rota do meio; atirador, responsável pela rota inferior e por ser a principal fonte de dano da equipe; suporte, responsável por proteger o atirador e espalhar visão pelo mapa, com o objetivo de identificar a localização do time inimigo. Por mais que estas atribuições sejam fixas no 
do jogo, com o decorrer do tempo elas podem mudar, seja para controlar algum objetivo como o Dragão ou o Barão, ou para eliminar algum inimigo. Em uma partida, cada jogador tem o direito de banir um campeão, que não poderá ser utilizado naquela partida por nenhuma das equipes, e escolher um campeão para utilizar naquela partida. Cada campeão possui mecânicas e habilidades únicas, e o conjunto final de escolhas de campeões de uma equipe para utilização é chamada de draft, onde a equipe prioriza campeões que satisfaçam a maneira como querem jogar o jogo: alguns campeões são mais fortes no início do jogo que outros (período chamado de early game), porém, em compensação, perdem poder no final do jogo (período chamado de late game), outros são melhores para jogo agressivo, enquanto outros, para um jogo passivo. Portanto, um bom draft é uma condição fundamental para a vitória.

### Itemização
É possível comprar itens nas lojas dentro das partidas em League of Legends, mas eles duram apenas a própria partida e servem para melhorar seu campeão – seja na velocidade de movimento, de ataque, poder, defesa, magia, entre outros. O dinheiro é obtido ao derrotar tropas, personagens inimigos ou torres. Obter itens o mais rápido possível é fundamental para campeões que querem chegar no late game, pois irão se beneficiar melhor dos itens do que campeões de early game. Além disso, uma boa itemização, chamada de build, também é fundamental para a vitória: se a função do seu campeão é ser a linha de frente e segurar o dano, talvez seja melhor comprar itens de resistência mágica e armadura do que comprar itens para aumentar o seu dano.

## Análise de partidas competitivas

### O Draft
Como dito anteriormente, o draft é uma das principais condições de vitória de um time. Além das características como força em cada momento de jogo, em partidas competitivas existe um outro atributo chamado de meta, ou seja, itens, armas, personagens, cartas, estratégias, técnicas e abordagens que estão mais dominantes ou populares no LoL. Muitas vezes, determinado campeão recebe melhorias, chamado de buff, o que pode o tornar desproporcionalmente forte em relação a outros, o que o torna prioridade no draft. Podemos analisar os campeões mais selecionados em cada rota para determinar o meta daquele ano.

![picks2018](https://github.com/guilhermesam/data-science/blob/master/projects/lol-analysis/images/picks/picks2018.png)

Podemos verificar, por exemplo, que os campeões mais selecionados na selva são, majoritariamente, tanks. Isso se deve ao fato de que, neste ano, itens de tank receberam vários buffs, o que fazia com que campeões que se beneficiavam destes itens causassem muito dano ao mesmo tempo que sofriam pouquíssimo dano de volta. Para contornar esse meta, na rota do meio, campeões com DpS (dano por segundo) alto eram muito mais selecionados, pois conseguiam lidar muito bem com tanques, ao passo que campeões de burst (explosão de dano) não conseguiam lidar tão bem, visto que causavam uma "rajada" de dano alto e precisavamm aguardar alguns segundos até terem suas habilidades novamente, e nesse intervalo, provavelmente o tank inimigo já teria regenerado ou automitigado boa parte desse dano. Por consequência, para os suportes, campeões que conseguissem proteger os seus aliados fontes de dano (conhecidos como carry) também eram muito escolhidos.

### Os abates

Além das tropas, campos da selva e estruturas, outra forma de ganhar ouro no LoL é abatendo campeões. Sem dúvida, um abate na hora certa é um fator chave para a virada de um jogo ou o fortalecimento de um campeão que estava atrás no jogo. O ouro fornecido pelos abates é escalar, ou seja, o abate de um campeão que está muito forte, ou seja, com muito ouro acumulado, com mais abates realizados, ou com um farm alto, vale mais do que abater um campeão que está fraco. Não apenas em questão de ouro, abater um campeão durante o surgimento de algum objetivo neutro como o Barão ou durante uma investida contra a base inimiga é muito importante, visto que, com o decorrer do jogo, o tempo de ressurgimento de um campeão abatido aumenta, ou seja, a equipe que perdeu um jogador precisará defender sua base ou contestar um objetivo com jogadores a menos. Portanto, é interessante analisarmos, em partidas competitivas, em quais lugares do mapa ocorrem abates em relação ao período do jogo, como visto anteriormente, early, mid ou late game.

![kills](https://github.com/guilhermesam/data-science/blob/master/projects/lol-analysis/images/kills.png)

As cores no mapa simbolizam abates, e estão distribuídas da seguinte forma:

- **Early Game**: Cor branca - Período aproximado entre 0 e 16 minutos de partida;

- **Mid Game**: Cor azul-clara - Período aproximado entre 16 e 25 minutos de partida; 

- **Late Game**: Cor azul-escura - Período aproximado entre 25 minutos e o final da partida;

Observando o mapa, podemos levantar algumas conclusões, tais como:
- Os abates no early game concentram-se em maioria nas rotas, com alguns pontos no spawn do dragão, visto que o mesmo surge aos 6 minutos de jogo. Uma jogada muito comum é o chamado gank, que é quando algum jogador sai de sua rota e vai até outra tentar eliminar algum jogador inimigo. Em situações normais de early game, os jogadores que recebem o gank tentam correr para sua torre, o que explica o alto número de pontos brancos ao redor das primeiras torres da rota (chamadas de tier 1 ou apenas t1).

- Os abates no mid game se concentram no rio, perto de ambos os pits tanto do Barão quanto do Dragão. Além deles, existe um terceiro objetivo neutro, chamado de Arauto do Vale, que é usado para derrubar torres de uma só rota com extrema facilidade. Devido ao Arauto surgir aos 10 minutos de jogo, e o Barão aos 20, os times tendem a abandonar suas rotas e lutar por esses objetivos, o que justifica a quantidade de pontos azuis-claro ao redor desses lugares.

- No late game, os times já estão fortes o suficiente para lutarem nas chamadas teamfights (ou lutas em equipe) por espaço no mapa. Neste ponto, uma simples eliminação causa um impacto gigantesco, e muito provavelmente um time estará bem mais forte do que o outro. Por isso, os abates representados pelos pontos azuis-escuro se concentram ao redor das bases que abrigam o Nexus, ou seja, o jogo já está próximo do fim!
