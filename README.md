# Resolução de exercícios e HUnit

## Exercício 5
Escreva uma função que receba um número e uma lista de raios de círculos. Essa função deverá retornar somente aqueles raios de círculos cuja área seja maior que o número passado como primeiro argumento. Resolva esta questão usando lambda.

![Demonstração](exercicio5.gif)

```haskell
bigCircles :: Float -> [Float] -> [Float]
bigCircles area_minima lista_raios = filter (\r -> r * r * pi > area_minima) lista_raios
````

A função recebe uma área mínima e uma lista com valores de raios. Usando o filter e uma função lambda, ela retorna uma lista apenas com os valores que passaram na função lambda.
Minha maior dificuldade foi em como fazer para verificar se a área de cada raio é maior que o número passado como argumento.

## Exercício 6
Escreva uma função que receba uma lista de tuplas com nomes de pessoas e suas temperaturas, e selecione aquelas tuplas que correspondem a pessoas com febre.

![Demonstração](exercicio6.gif)

```haskell
quarentine :: [(String, Float)] -> [(String, Float)]
quarentine lista = filter (\(_,temperatura) -> temperatura > 37.8) lista
```

Novamente, o filter é usado junto com uma função lambda, dessa vez para testar se a temperatura indica febre ou não.
Achei mais difícil usar o lambda para uma tupla, já que até aqui os exercícios eram resolvidos com o lambda recebendo apenas um número ou char/string como argumento.

Antes da versão final, havia tentado da seguinte maneira:
`quarentine lista = filter (\t -> t > 37.8) lista`
Nesse caso, falta indicar que o que tem dentro da lista é uma tupla e que queremos sempre o segundo elemento dela que representa a temperatura.

## Exercício 8
Escreva uma função que receba uma lista de nomes e adicione o prefixo "Super " às strings que começarem com a letra `A` (maiúscula), deixando as demais inalteradas.

![Demonstração](exercicio8.gif)

```haskell
superNames :: [String] -> [String]
superNames lista = map (\n -> if head n == 'A' then "Super " ++ n else n) lista
```
A ideia é usar o map de maneira que ele modifique apenas as strings que começarem com 'A'. Para isso, usamos o if para selecionar quando tem que adicionar o "Super " ou deixar a string sem alterações.
A maior dificuldade do exercício é o uso do `if` dentro do map.




