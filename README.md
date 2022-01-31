# RPS
RPS model for three species on squared cyclical grids

Os efeitos das interações espaciais em competições cíclicas podem ser estudadas por
meio de uma versão do modelo May-Leonard, também chamado de jogo RPS estocástico N
de quatro estados: A, B, C e sítios vazios , com foco no modelo onde consideram-se
interações simétricas do tipo predador-presa nas quais um indivíduo de qualquer uma das
três espécies pode predar ou ser predado pelos indivíduos das demais espécies
com uma probabilidade p. Os indivíduos de todas as sub-populações são organizados em
uma rede bidimensional quadrada com condições de contorno periódicas. Denotamos por
N o tamanho linear da rede, portanto o número total de sítios é N^2 . Inicialmente, cada
sítio da rede é aleatoriamente ocupado por um dos indivíduos das três espécies ou por um
espaço vazio.
A cada passo de tempo é executado o seguinte procedimento:

1. Um indivíduo da rede é aleatoriamente escolhido, esse é chamado de indivíduo ativo.
2. Um dos quatro primeiros vizinhos do elemento ativo é sorteado e esse é denominado
de passivo.
3. Uma ação (mobilidade, reprodução e predação) é sorteada obedecendo as pesos
probabilísticos, definidos inicialmente.
4. No caso em que a mobilidade é sorteada, ocorre a troca de posição entre o ativo e
o passivo.
5. No caso da reprodução ser sorteada, é verificado se o elemento passivo é um sítio
vazio. Se for, o indivíduo ativo é duplicado.
6. Se a predação for sorteada, é necessário verificar se o ativo pode predar o passivo.
Se isso for possível, o sítio da passivo torna-se vazio, caso contrário nada ocorre.

Aqui, usamos Redes Neurais de Convolução (CNN) para tentar encontrar o momento em que a rede passa de 
um estado desordenado para a formação de estruturas organizadas.
Para isso, treinamos um modelo CNN apenas com redes no estado inicial e final, e usamos esse classificador
nos estados intermediário. Dessa forma, foi possível encontrar uma transição de fase no número de estados intermediários
que eram classificados como estado final. 
