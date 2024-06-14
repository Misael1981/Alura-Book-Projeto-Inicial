# Método sort()

O método `sort()` de ` Array` instâncias ordena os elementos de um array no lugar e retorna a referência ao mesmo array, agora ordenado. A ordem de classificação padrão é crescente, baseada na conversão dos elementos em strings e, em seguida, na comparação de suas sequências de valores de unidades de código UTF-16.

A complexidade de tempo e espaço desse tipo não pode ser garantida, pois depende da implementação.

Para classificar os elementos em um array sem alterar o array original, use `toSorted()`.

## Sintaxe

```
sort()
sort(compareFn)
```

## Descrição

Se `compareFn` não for fornecido, todos undefinedos elementos que não sejam da matriz serão classificados convertendo-os em strings e comparando as strings na ordem das unidades de código UTF-16. Por exemplo, “banana” vem antes de “cereja”. Em uma classificação numérica, 9 vem antes de 80, mas como os números são convertidos em strings, “80” vem antes de “9” na ordem Unicode. Todos undefinedos elementos são classificados até o final do array.