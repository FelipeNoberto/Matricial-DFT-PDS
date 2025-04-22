# Implementação da DFT pelo Método Matricial

Este repositório contém a implementação da Transformada Discreta de Fourier (DFT) utilizando o **método matricial**.

## A DFT

A DFT converte uma sequência finita de amostras igualmente espaçadas de uma função em uma sequência de mesmo comprimento de amostras igualmente espaçadas da transformada de Fourier em tempo discreto, que é uma função de frequência de valor complexo.
Ou seja, ela transforma um sinal no tempo (como um som ou variação de tensão) em sua representação no domínio da frequência, mostrando quais frequências estão presentes e com que intensidade. Essa conversão permite analisar e processar sinais de forma mais eficiente, identificando padrões que não são visíveis no tempo.

Sua forma é tal que, dada uma sequência de entrada \( x[0], x[1], ... , x[N-1] \), podemos calcular cada valor \( X[k] \) da DFT pela seguinte fórmula:

```math
X[k] = \sum_{n=0}^{N-1} x[n] \cdot e^{-j \cdot 2\pi \cdot kn / N}
```

Assim, usando o método matricial, vamos calcular a DFT através da multiplicação de matrizes. Para isso, organizamos uma matriz 𝑊 W de tamanho 𝑁×𝑁, onde cada elemento é definido como:

```math
W[k, n] = e^{-j \cdot 2\pi \cdot kn / N}
```

Com isso, podemos calcular todos os valores da DFT de uma só vez, realizando a multiplicação da matriz 𝑊 W pelo vetor de entrada 𝑥

𝑋 = 𝑊 ⋅ 𝑥

O vetor resultante 𝑋 contém todas as 𝑁 frequências discretas da transformada. Esse método é chamado de DFT pelo método matricial.

# Implementação

No estudo, buscamos entender como é o desempenho desse modelo avaliando o tempo de execução de acordo com valores N de operações, onde pudemos constatar que, dada a ordem NxN, seu tempo de execução cresce bastante quanto maior a operação.

Analisamos um primeiro caso, com vetores aleatórios de entrada buscando o pior caso e ao final do projeto simulamos também com uma entrada mais padronizada sen(n).

Também, para avaliar o desempenho da DFT, fizemos o calculo da DFT de dois sinais, para avaliar o projeto e seus resultados.
