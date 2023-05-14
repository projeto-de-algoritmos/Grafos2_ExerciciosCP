# Sumário

- [Sumário](#sumário)
- [Road Reparation](#road-reparation)
  - [Entrada](#entrada)
  - [Saída](#saída)
  - [Restrições](#restrições)
  - [Exemplos](#exemplos)
    - [Entrada 1](#entrada-1)
    - [Saída 1](#saída-1)
- [Solução](#solução)

# [Road Reparation](https://cses.fi/problemset/task/1675)

There are **n** cities and **m** roads between them. Unfortunately, the condition of the roads is so poor that they cannot be used. Your task is to repair some of the roads so that there will be a decent route between any two cities.

For each road, you know its reparation cost, and you should find a solution where the total cost is as small as possible.

## Entrada

The first input line has two integers n and m: the number of cities and roads. The cities are numbered 1,2,…,**n**.

Then, there are **m** lines describing the roads. Each line has three integers **a**, **b** and **c**: there is a road between cities **a** and **b**, and its reparation cost is **c**. All roads are two-way roads.

Every road is between two different cities, and there is at most one road between two cities.

## Saída

Print one integer: the minimum total reparation cost. However, if there are no solutions, print "IMPOSSIBLE".

## Restrições

- 1 ≤ **n** ≤ 10<sup>5</sup>
- 1 ≤ **m** ≤ 2⋅10<sup>5</sup>
- 1 ≤ **a**,**b** ≤ **n**
- 1 ≤ **c** ≤ 10<sup>9</sup>

## Exemplos

### Entrada 1
```
5 6
1 2 3
2 3 5
2 4 2
3 4 8
5 1 7
5 4 4
```

### Saída 1
```
14
```

# [Solução](./solution.cpp)

Este problema é bem direto ao ponto, para solucioná-lo é necessário calcular a árvore geradora mínima do grafo dado e verificar se o grafo forma um componente conectado.

Para calcular a árvore geradora mínima é possível utilizar o algoritmo de Kruskal ou Prim. Para verificar se o grafo forma um componente conectado, basta verificar se a árvore geradora mínima possui **n - 1** arestas.
