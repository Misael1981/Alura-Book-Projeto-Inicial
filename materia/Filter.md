# Método filter()

O método `filter()` cria um novo array com todos os elementos que passaram no teste implementado pela função fornecida.

## Descrição

`filter()` chama a função `callback` fornecida, uma vez para cada elemento do array, e constrói um novo array com todos os valores para os quais o `callback` retornou o valor true ou um valor que seja convertido para true. O `callback` é chamado apenas para índices do array que possuem valores atribuídos; Ele não é invocado para índices que foram excluídos ou para aqueles que não tiveram valor atribuído. Elementos do array que não passaram no teste do `callback` são simplesmente ignorados, e não são incluídos no novo array.

`callback` é invocado com estes três argumentos:

- 1- o valor do elemento
- 2- o índice do elemento
- 3- o objeto do array a ser preenchido

[fonte mozilla](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)