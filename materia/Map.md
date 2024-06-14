# Método `map()`

## Descrição

O método map chama a função `callback` recebida por parâmetro para cada elemento do Array original, em ordem, e constrói um novo array com base nos retornos de cada chamada. A função `callback` é chamada apenas para os elementos do array original que tiverem valores atribuídos; os elementos que estiverem como undefined, que tiverem sido removidos ou os que nunca tiveram valores atribuídos não serão considerados.

A função `callback` é chamada com três argumentos:

 1- valor do elemento corrente;

 2- índice do elemento corrente;

3- O array original que está sendo percorrido.

Se o parametro `thisArg` foi passado para o método `map`, ele será repassado para a função `callback` no momento da invocação para ser utilizado como o `this`. Caso contrário, o valor `undefined` será repassado para uso como o `this`. O valor do `this` a ser repassado para o `callback` deve respeitar as regras para determinar como o `this` é acessado por uma função.

O método `map` não modifica o array original. No entanto, a função `callback` invocada por ele pode fazê-lo.

A lista de elementos que serão processados pelo `map` é montada antes da primeira invocação à função `callback`. Se um elemento for acrescentado ao array original após a chamada ao map, ele não será visível para o callback. Se os elementos existentes forem modificados, os valores que serão repassados serão os do momento em que o método map invocar o callback. Elementos removidos não serão visitados.

[fonte: Site Mozila](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/map)