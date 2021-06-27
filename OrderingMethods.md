### Unipar - Universidade Paranaense - Curso de Análise e Desenvolvimento de Sistemas - 2° Série

Aluno: Guilherme Henrique Boffo <br/>
RA: 00211995

Professor: Geferson Luis Simonette <br/>
Matéria: Estrutura e classificação de dados

---

# Métodos de Ordenação
## Dentre os métodos de ordenação existentes, os principais são os métodos:

- Quick sort
- Bubble sort
- Insertion sort
- Selection Sort

## Quick sort

O Quicksort é o algoritmo mais eficiente na ordenação por comparação. Nele se escolhe um elemento chamado de pivô, a partir disto é organizada a lista para que todos os números anteriores a ele sejam menores que ele, e todos os números posteriores a ele sejam maiores que ele. Ao final desse processo o número pivô já está em sua posição final. Os dois grupos desordenados recursivamente sofreram o mesmo processo até que a lista esteja ordenada.

### Funciona da seguinte forma:

![QuickSort](https://arquivo.devmedia.com.br/artigos/Bruno_Almeida_Honorato/Algoritmos-Resolucao-Problemas/5.jpg)

- O número 3 foi escolhido como pivô, nesse passo é procurado à sua direita um número menor que ele para ser passado para a sua esquerda. O primeiro número menor encontrado foi o 1, então eles trocam de lugar.
- Agora é procurado um número à sua esquerda que seja maior que ele, o primeiro número maior encontrado foi o 5, portanto eles trocam de lugar.
- O mesmo processo do passo 1 acontece, o número 2 foi o menor número encontrado, eles trocam de lugar.
- O mesmo processo do passo 2 acontece, o número 4 é o maior número encontrado, eles trocam de lugar.
- O vetor desse exemplo é um vetor pequeno, portanto ele já foi ordenado, mas se fosse um vetor grande, ele seria dividido e recursivamente aconteceria o mesmo processo de escolha de um pivô e comparações.
- 
## Bubble Sort

Bubble sort é o algoritmo mais simples, mas o menos eficientes. Neste algoritmo cada elemento da posição i será comparado com o elemento da posição i + 1, ou seja, um elemento da posição 2 será comparado com o elemento da posição 3. Caso o elemento da posição 2 for maior que o da posição 3, eles trocam de lugar e assim sucessivamente. Por causa dessa forma de execução, o vetor terá que ser percorrido quantas vezes que for necessária, tornando o algoritmo ineficiente para listas muito grandes.

### Funciona da seguinte forma:

![BubbleSort](https://arquivo.devmedia.com.br/artigos/Bruno_Almeida_Honorato/Algoritmos-Resolucao-Problemas/2.jpg) 

- É verificado se o 3 é maior que 5, por essa condição ser falsa, não há troca.
- É verificado se o 5 é maior que 1, por essa condição ser verdadeira, há uma troca.
- É verificado se o 5 é maior que 2, por essa condição ser verdadeira, há uma troca.
- É verificado se o 5 é maior que 4, por essa condição ser verdadeira, há uma troca.
- O método retorna ao início do vetor realizando os mesmos processos de comparações, isso é feito até que o vetor esteja ordenado.

## Insertion sort

Insertion sort é um algoritmo simples e eficiente quando aplicado em pequenas listas. Neste algoritmo a lista é percorrida da esquerda para a direita, à medida que avança vai deixando os elementos mais à esquerda ordenados. <br/>
O algoritmo funciona da mesma forma que as pessoas usam para ordenar cartas em um jogo de baralho como o pôquer.

### Funciona da seguinte forma:

![InsertionSort](https://arquivo.devmedia.com.br/artigos/Bruno_Almeida_Honorato/Algoritmos-Resolucao-Problemas/4.jpg)

- Neste passo é verificado se o 5 é menor que o 3, como essa condição é falsa, então não há troca.
- É verificado se o quatro é menor que o 5 e o 3, ele só é menor que o 5, então os dois trocam de posição.
- É verificado se o 2 é menor que o 5, 4 e o 3, como ele é menor que 3, então o 5 passa a ocupar a posição do 2, o 4 ocupa a posição do 5 e o 3 ocupa a posição do 4, assim a posição do 3 fica vazia e o 2 passa para essa posição.

O mesmo processo de comparação acontece com o número 1, após esse processo o vetor fica ordenado.

## Selection Sort

Este algoritmo é baseado em se passar sempre o menor valor do vetor para a primeira posição (ou o maior dependendo da ordem requerida), depois o segundo menor valor para a segunda posição e assim sucessivamente, até os últimos dois elementos. <br/>
Neste algoritmo de ordenação é escolhido um número a partir do primeiro, este número escolhido é comparado com os números a partir da sua direita, quando encontrado um número menor, o número escolhido ocupa a posição do menor número encontrado. Este número encontrado será o próximo número escolhido, caso não for encontrado nenhum número menor que este escolhido, ele é colocado na posição do primeiro número escolhido, e o próximo número à sua direita vai ser o escolhido para fazer as comparações. É repetido esse processo até que a lista esteja ordenada.
  
### Funciona da seguinte forma:
  
![SelectionSort](https://arquivo.devmedia.com.br/artigos/Bruno_Almeida_Honorato/Algoritmos-Resolucao-Problemas/3.jpg)

- Neste passo o primeiro número escolhido foi o 3, ele foi comparado com todos os números à sua direita e o menor número encontrado foi o 1, então os dois trocam de lugar.
- O mesmo processo do passo 1 acontece, o número escolhido foi o 5 e o menor número encontrado foi o 2.
- Não foi encontrado nenhum número menor que 3, então ele fica na mesma posição.
- O número 5 foi escolhido novamente e o único número menor que ele à sua direita é o 4, então eles trocam.
- Vetor já ordenado.

# Comparação

é necessário Verificar o comportamento dos algoritmos em relação ao tempo, comparações e movimentações de trocas.
Foram testadas 3 ordens de listas com 3 tamanhos diferentes cada:
- Ordem 1: lista ordenada em ordem crescente.
- Ordem 2: lista ordenada em ordem decrescente.
- Ordem 3: lista desordenada com números aleatórios.

Ficando assim então:

# Ordem 1

## Tamanho do vetor: 100     

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,0141 | 606 | 189 |
| Bubble sort | 0,0988 | 5050 | 0 |
| Insertion sort | 0,0038 | 99 | 198 |
| Selection Sort | 0,0602 | 4950 | 297 | 

## Tamanho do vetor: 1000

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,1602 | 9009 | 1533 |
| Bubble sort | 9,5415 | 500500 | 0 |
| Insertion sort | 0,0359 | 999 | 1998 |
| Selection Sort | 5,4587 | 499500 | 2997 | 

## Tamanho do vetor: 10000

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 2,0824 | 125439 | 17712 |
| Bubble sort | 934,5364 | 50005000 | 0 |
| Insertion sort | 0,3558 | 9999 |19998 |
| Selection Sort | 508,5891 | 49995000 | 29997 |

# Ordem 2

Tamanho do vetor: 100
| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,0147 | 610 | 336 |
| Bubble sort | 0,2045 | 5050 | 14850 |
| Insertion sort | 0,1173 | 99 | 5148 | 
| Selection Sort | 0,0750 | 4950 | 297 |

## Tamanho do vetor: 1000

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,1622 | 9016 | 3030 |
| Bubble sort | 20,3377 | 500500 | 1498500 |
| Insertion sort | 11,4277 | 999 | 501498 |
| Selection Sort | 6,9038 | 499500 | 2997 |

## Tamanho do vetor: 10000

| Algoritmo | Tempo   | Comparações | Movimentações |
| --------- | ------- | ----------- | ------------- |
| Quick sort | 2,1279 | 125452 | 32712 |
| Bubble sort | 1838,0272 | 50005000 | 149985000 |
| Insertion sort | 1074,1171 | 9999 | 50014998 |
| Selection Sort | 665,2050 | 49995000 | 29997 |

# Ordem 3

## Tamanho do vetor: 100

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,0314 | 897 | 576 |
| Bubble sort | 0,1596 | 5050 | 6777 |
| Insertion sort | 0,0570 | 99 | 2457 |
| Selection Sort | 0,0698 | 4950 | 297 |

## Tamanho do vetor: 1000

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 0,3725 | 13138 | 7983 |
| Bubble sort |	16,6730 | 500500 | 756840 |
| Insertion sort | 5,7523 | 999 | 254278 |
| Selection Sort | 5,6664 | 499500 | 2997 |

## Tamanho do vetor: 10000

| Algoritmo | Tempo | Comparações | Movimentações |
| --------- | ----- | ----------- | ------------- |
| Quick sort | 4,5072 | 176065 | 103635 |
| Bubble sort | 1455,9734 | 50005000 | 74237889 |
| Insertion sort | 539,6891 | 9999 | 24765961 |
| Selection Sort | 545,1068 | 49995000 | 29997 |

# Conclusão

Com base nas ordens apresentadas acima, chegamos a conclusçao que:

## Quick Sort

O quick sort certamente é o algoritmo mais eficiente em listas totalmente desordenadas, ele se torna muito eficiente em relação aos outros no quesito de tempo. Na lista de ordem 3 e na de ordem 2 a diferença de tempo do quick sort em comparação aos outros foi absurdamente grande.

## Bubble sort

Para listas já ordenadas em ordem crescente é o único algoritmo que não realiza movimentações, mas em compensação é o que tem o maior tempo e o maior número de comparações. Não só em listas já ordenadas, mas em todos os casos o bubble sort se mostrou um algoritmo ineficiente.

## Insertion Sort

Na lista de ordem 1, o Insertion sort se mostrou mais eficiente que todos os outros algoritmos em relação ao tempo e comparações. Na lista de ordem 2 foi menos eficiente do que o selection sort e na lista de ordem 3 a diferença de tempo entre o insertion e o selection foi pequena.

## Selection sort

Nas listas de ordem 1 e ordem 3, o selection sort foi o segundo pior algoritmo, mas se mostrou mais eficiente do que o Insertion sort em relação ao tempo e a quantidade de movimentações na lista de ordem 2.

Ref: https://www.devmedia.com.br/algoritmos-de-ordenacao-analise-e-comparacao/28261
