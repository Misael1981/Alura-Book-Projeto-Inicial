# Método reduce()

O `reduce()` método instâncias executa uma função de retorno de chamada "redutor" fornecida pelo usuário em cada elemento da matriz, em ordem, passando o valor de retorno do cálculo no elemento anterior. O resultado final da execução do redutor em todos os elementos da matriz é um valor único.

Na primeira vez que o retorno de chamada é executado, não há "valor de retorno do cálculo anterior". Se fornecido, um valor inicial poderá ser usado em seu lugar. Caso contrário, o elemento da matriz no índice 0 será usado como valor inicial e a iteração começará a partir do próximo elemento (índice 1 em vez do índice 0).

## Sintaxe 

```
reduce(callbackFn)
reduce(callbackFn, initialValue)
```

## Parâmetros

Uma função a ser executada para cada elemento da matriz. Seu valor de retorno se torna o valor do **accumulator** parâmetro na próxima invocação de `callbackFn`. Para a última invocação, o valor de retorno se torna o valor de retorno de `reduce()`. A função é chamada com os seguintes argumentos:



### `accumulator`

- O valor resultante da chamada anterior para `callbackFn`. Na primeira chamada, seu valor será `initialValuese` este for especificado; caso contrário, seu valor é array[0].

### `currentValue`

- O valor do elemento atual. Na primeira chamada, seu valor é `array[0]` if `initialValue` especificado; caso contrário, seu valor é array[1].

### `currentIndex`

- A posição do índice `currentValue` na matriz. Na primeira chamada, seu valor é especificado 0 if `initialValue`, caso contrário 1, 

### `array`

- A matriz `reduce()` foi chamada.

### `initialValue` (Opcional)

Um valor para o qual `accumulator` é inicializado na primeira vez que o retorno de chamada é chamado. Se `initialValue` for especificado, `callbackFn` inicia a execução com o primeiro valor da matriz como `currentValue`. Se não `initialValue` for especificado, será inicializado com o primeiro valor da matriz e começará a ser executado com o segundo valor da matriz como . Nesse caso, se o array estiver vazio (de forma que não haja um primeiro valor para retornar como ), um erro será gerado. `accumulator callbackFn currentValue accumulator`

## Diferança entre métodos

O que diferencia um método do outro dos que foram tratados até aqui?

<img src= '../imagens/meme-metodos.png'>


- `map()`: cria um novo array, transformando cada elemento num array individual, irá criar um novo array, uma nova lista.

- `filter()`: O filter irá remover todos os elementos que não são estamos selecionando e criar um array apenas com aqueles que chamamos. 

- `reduce()`: Vai pegar topos os elementos de um array e produzir um único valor.