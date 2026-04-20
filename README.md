# Min-Max Tic-Tac-Toe:

Este trabalho aborda a implementação de dois agentes inteligentes baseados no algoritmo Min-Max, onde há um ambiente multiagente, parcialmente observável onde cada agente toma uma decisão baseado em maximizar (ou minimizar) sua utilidade de movimento, enquanto minimiza (ou maximiza) a próxima ação do seu adversário. Um agente tenta maximizar sua utilidade (MAX), enquanto o outro tenta minimizá-la (MIN).

O jogo da velha, por ter um tamanho reduzido, é um ótimo problema que pode ser modelado através desse algoritmo. Utilizei a ideia de árvores de decisão, em que calculamos um score, porém, coloquei funções de fallback, para evitar de escrever mais uma matriz na memória, apenas a fim de calcular o movimento do adversário.

No primeiro agente, além da implementação padrão do Min-Max, foi introduzido um mecanismo inspirado em simulated annealing, utilizando um parâmetro de temperatura para controlar o nível de exploração. Quando a temperatura é maior que zero, o agente não escolhe necessariamente a melhor jogada, mas sim uma jogada baseada em uma distribuição de probabilidade (softmax) sobre os valores retornados pelo Min-Max. Isso permite explorar diferentes caminhos da árvore, evitando comportamento totalmente determinístico de um Climb Hill.

Além disso, foi implementado um segundo agente com comportamento subótimo controlado, que ainda utiliza o Min-Max para avaliar os estados, que apenas escolhe com base em Min-Max, o que pode desperdiçar o primeiro movimento quando começa, mas ainda joga bem o suficiente para empatar. Porém, raramente consegue vencer.
