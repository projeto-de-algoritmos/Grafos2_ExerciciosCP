# Sumário

- [Sumário](#sumário)
- [Flight Routes](#flight-routes)
  - [Entrada](#entrada)
  - [Saída](#saída)
  - [Restrições](#restrições)
  - [Exemplos](#exemplos)
    - [Entrada 1](#entrada-1)
    - [Saída 1](#saída-1)
    - [Explicação](#explicação)
- [Solução](#solução)

# [Flight Routes](https://cses.fi/problemset/task/1196)

Your task is to find the **k** shortest flight routes from Syrjälä to Metsälä. A route can visit the same city several times.

Note that there can be several routes with the same price and each of them should be considered (see the example).

## Entrada

The first input line has three integers **n**, **m**, and **k**: the number of cities, the number of flights, and the parameter **k**. The cities are numbered 1,2,…,**n**. City 1 is Syrjälä, and city **n** is Metsälä.

After this, the input has **m** lines describing the flights. Each line has three integers **a**, **b**, and **c**: a flight begins at city **a**, ends at city **b**, and its price is **c**. All flights are one-way flights.

You may assume that there are at least **k** distinct routes from Syrjälä to Metsälä.

## Saída

Print **k** integers: the prices of the **k** cheapest routes sorted according to their prices.

## Restrições

- 1 ≤ **n** ≤ 10<sup>5</sup>
- 1 ≤ **m** ≤ 2⋅10<sup>5</sup>
- 1 ≤ **a**,**b** ≤ **n**
- 1 ≤ **c** ≤ 10<sup>9</sup>
- 1 ≤ **k** ≤ 10

## Exemplos

### Entrada 1
```
4 6 3
1 2 1
1 3 3
2 3 2
2 4 6
3 2 8
3 4 1
```

### Saída 1
```
4 4 7
```

### Explicação

The cheapest routes are 1 → 3 → 4 (price 4), 1 → 2 → 3 → 4 (price 4) and 1 → 2 → 4 (price 7). 

# [Solução](./solution.cpp)

Para solucionar este problema, podemos utilizar o algoritmo de dijkstra para calcular o caminho de menor custo entre as duas cidades e guardar os **k** menores caminhos encontrados em uma fila de prioridades para cada cidade. Deste modo, é garantido que iremos iterar por cada vértice no máximo **k** vezes.
