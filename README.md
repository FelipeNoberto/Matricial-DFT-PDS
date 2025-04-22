# Implementação da DFT pelo Método Matricial

Este repositório contém a implementação da Transformada Discreta de Fourier (DFT) utilizando o **método matricial**.

## A DFT

A DFT converte uma sequência finita de amostras igualmente espaçadas de uma função em uma sequência de mesmo comprimento de amostras igualmente espaçadas da transformada de Fourier em tempo discreto, que é uma função de frequência de valor complexo.
Ou seja, ela transforma um sinal no tempo (como um som ou variação de tensão) em sua representação no domínio da frequência, mostrando quais frequências estão presentes e com que intensidade. Essa conversão permite analisar e processar sinais de forma mais eficiente, identificando padrões que não são visíveis no tempo.



Sua forma é tal que, dada uma sequência de entrada \( x[0], x[1], ... , x[N-1] \), podemos calcular cada valor \( X[k] \) da DFT pela seguinte fórmula:


```math
X[k] = \sum_{n=0}^{N-1} x[n] \cdot e^{-j \cdot 2\pi \cdot kn / N}
```



# Implementação
A implementação foi realizada em Python, utilizando bibliotecas como `numpy`, `matplotlib` e `time`. O objetivo foi construir a DFT a partir de sua definição original, utilizando o método matricial.

A DFT foi implementada por meio da criação de uma matriz (NxN) de coeficientes complexos \( W \), cujos elementos seguem a equação:

```math
W[k, n] = e^{-j \cdot 2\pi \cdot kn / N}
```

Essa matriz foi então multiplicada pelo vetor de entrada \( x \), resultando no vetor de saída \( X \), que representa a transformada no domínio da frequência. Esse cálculo foi encapsulado na função `dft_matricial(x)`.

𝑋 = 𝑊 ⋅ 𝑥

O vetor resultante 𝑋 contém todas as 𝑁 frequências discretas da transformada. Esse método é chamado de DFT pelo método matricial.

Além da implementação da transformada, também foi realizado um estudo de desempenho. A função foi executada para diferentes tamanhos de entrada \( N \), variando de 2 a 1024, e foi medido o tempo de execução para cada caso. Os resultados foram armazenados e exibidos em um gráfico que mostra o crescimento do tempo em função de \( N \), evidenciando a complexidade computacional da DFT, que é da ordem de N ao quadrado.


No estudo, buscamos entender como é o desempenho desse modelo avaliando o tempo de execução de acordo com valores N de operações, onde pudemos constatar que, dada a ordem NxN, seu tempo de execução cresce bastante quanto maior a operação.

Analisamos um primeiro caso, com vetores aleatórios de entrada buscando o pior caso e ao final do projeto simulamos também com uma entrada mais padronizada sen(n).

Também, para avaliar o desempenho da DFT, fizemos o calculo da DFT de dois sinais, para avaliar o projeto e seus resultados, com funções de entrada x(n) = sen(n) e também uma senoide de 5 ciclos completos, podendo afirmar a confiabilidade do método.

Como na primeira simulação usamos um vetor de entrada com valores aleatórios, para simular o pior caso para a execução, no final, fizemos uma nova avaliação de desempenho comuma função de entrada x(n) = sen(n), verificando que o comportamento do crescimento acelerado com o aumento de N confere com o previsto.







