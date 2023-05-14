# Sumário

- [Sumário](#sumário)
- [Flight-Discount](#flight-discount)
  - [Entrada](#entrada)
  - [Saída](#saída)
  - [Restrições](#restrições)
  - [Exemplos](#exemplos)
    - [Entrada 1](#entrada-1)
    - [Saída 1](#saída-1)
- [Solução](#solução)

# [Flight-Discount](https://cses.fi/problemset/task/1195)

Your task is to find a minimum-price flight route from Syrjälä to Metsälä. You have one discount coupon, using which you can halve the price of any single flight during the route. However, you can only use the coupon once.

## Entrada

The first input line has two integers **n** and **m**: the number of cities and flight connections. The cities are numbered 1,2,…,**n**. City 1 is Syrjälä, and city **n** is Metsälä.

After this there are **m** lines describing the flights. Each line has three integers **a**, **b**, and **c**: a flight begins at city **a**, ends at city **b**, and its price is **c**. Each flight is unidirectional.

You can assume that it is always possible to get from Syrjälä to Metsälä.

## Saída

Print one integer: the price of the cheapest route from Syrjälä to Metsälä.

When you use the discount coupon for a flight whose price is **x**, its price becomes ⌊**x**/2⌋ (it is rounded down to an integer).

## Restrições

- 1 ≤ **n** ≤ 10<sup>5</sup>
- 1 ≤ **m** ≤ 2⋅10<sup>5</sup>
- 1 ≤ **a**,**b** ≤ **n**
- 1 ≤ **c** ≤ 10<sup>9</sup>

## Exemplos

### Entrada 1
```
3 4
1 2 3
2 3 1
1 3 7
2 1 5
```

### Saída 1
```
2
```

# [Solução](./solution.cpp)

É importante notar que as vezes pode ser melhor pegar uma aresta com maior custo, visto que quanto maior o custo da aresta maior o desconto por pegá-la. Com isso, é fácil notar que não podemos apenas encontrar o caminho com menor custo e depois dividir o custo da maior aresta pela metade, já que pode valer mais a pena pegar uma aresta de 200 tendo um desconto de 100, do que pegar 3 arestas de 50.

Podemos calcular o caminho de menor custo partindo da cidade inicial para todas as outras utilizando dijkstra, e similarmente, calcular o menor custo da cidade final para todas as outras utilizando dijkstra no grafo reverso. Após esta etapa, basta encontrar duas cidades diretamente conectadas **A** e **B**, que exista um caminho da cidade inicial para **A** e um caminho de **B** para a cidade final, e aplicar o desconto na aresta que liga essas duas cidades.
