# forEach()

O `forEach()` método é uma ferramenta poderosa para iterar os elementos de um array. Ele executa uma função fornecida uma vez para cada elemento do array, permitindo realizar operações em cada item.

### Sintaxe

```
array.forEach(function(currentValue, index, arr), [thisArg])
```

- **array**: o array sobre o qual você deseja iterar.

- **function(currentValue, index, arr)**: A função de retorno de chamada que será executada para cada elemento.

- **currentValue**: O elemento atual que está sendo processado na iteração.

- **index**: O índice numérico do elemento atual (opcional).
- **arr**: todo o array sendo iterado (opcional).
- **[thisArg]**: Um argumento opcional que especifica o valor de `this` dentro da função de retorno de chamada (raramente usado).


### Como funciona:

1- O `forEach()` usa o array fornecido e a função de retorno de chamada como argumentos.

2- Ele itera sobre os elementos do array na ordem em que aparecem .

3- Para cada elemento, ele chama a função de retorno de chamada, passando três argumentos:

- `currentValue`: O valor do elemento atual.
- `índice (opcional)`: O índice numérico do elemento atual (começa em 0).
- `arr (opcional)`: todo o array que está sendo iterado.
- A função de retorno de chamada pode executar qualquer operação necessária no elemento atual, como registrar em log, modificar ou adicioná-lo a outra estrutura de dados.
- O método `forEach()` continua iterando e chamando a função de retorno de chamada para cada elemento do array até chegar ao fim.

### Pontos importantes:

- `forEach()` não modifica o array original . Ele itera sobre os elementos e executa a função de retorno de chamada, mas não altera os valores no próprio array.
- `forEach()` sempre retorna indefinido . É usado principalmente para realizar efeitos colaterais nos elementos, não para criar um novo array ou valor.
- Se você precisar criar um novo array baseado nos elementos do array original, considere usar outros métodos como `map()` ou `filter()`.

# Funções Assíncronas

Introduzidas no ECMAScript 2017 (ES2017), as funções assíncronas permitem escrever código assíncrono de forma mais intuitiva e estruturada, utilizando uma sintaxe semelhante ao código síncrono. Eles são definidos utilizando a palavra-chave `async` antes do nome da função.

### Funcionamento:

- Uma função assíncrona sempre retorna uma promessa (` Promise`).
- Se o valor de retorno não for explicitamente uma promessa, ele será implicitamente encapsulado em uma.
- Dentro de uma função assíncrona, podemos usar uma palavra-chave `await` antes de qualquer expressão que retorne uma promessa.
- Ao utilizar `await`, a execução da função assíncrona é pausada até que a promessa seja resolvida ou rejeitada.
- O valor resolvido da promessa se torna o valor de retorno da expressão `await`.
- Em caso de exclusão da promessa, uma exceção é lançada.

### Vantagens:

- Simplificamos a escrita e a leitura do código assíncrono, tornando-o mais legível e compreensível.
- Permitem estruturar o código assíncrono de forma linear, semelhante ao código síncrono, facilitando o resumo e a manutenção do código.
- Elimina a necessidade de utilizar callbacks aninhados, tornando o código mais conciso e organizado.

### Exemplo:

```
async function buscarDados() {
  const resposta = await fetch('https://exemplo.com/dados');
  const dados = await resposta.json();
  return dados;
}

buscarDados().then(dados => {
  console.log(dados);
}).catch(erro => {
  console.error(erro);
});
```

## Objeto "assíncrono":

O objeto `async` é um objeto global introduzido no Node.js 10.0 que fornece métodos importantes para trabalhar com operações assíncronas. Ele oferece funcionalidades como:

- Criar iteradores assíncronos.
- Gerenciar filas de tarefas assíncronas.
- Limitar a simultaneidade de tarefas assíncronas.

### Exemplo:

```
const { async, each, map } = require('async');

async.each([1, 2, 3], async (numero) => {
  console.log(numero);
  await new Promise((resolve) => setTimeout(resolve, 1000));
});

async.map([1, 2, 3], async (numero) => {
  return numero * 2;
}, (erro, resultado) => {
  if (erro) {
    console.error(erro);
  } else {
    console.log(resultado);
  }
});
```

### Resumo:

- As funções assíncronas facilitam a escrita do código assíncrono em JavaScript, utilizando uma sintaxe semelhante ao código síncrono.
- O objeto `async` do Node.js fornece métodos importantes para trabalho com operações assíncronas.

### Lembre-se:

- A programação assíncrona é essencial para lidar com operações que podem levar tempo para serem concluídas, como requisições de rede ou acesso a arquivos.
- As funções assíncronas e o objeto `async` são ferramentas poderosas para escrever código assíncrono eficiente e organizado.


# O que é fetch() em JavaScript?

O `fetch()`é uma interface introduzida no ECMAScript 2015 (ES6) que fornece uma maneira moderna e simplificada de realizar requisições HTTP assíncronas em JavaScript. Ela substitui métodos anteriores como o XMLHttpRequest (XHR), oferecendo diversas vantagens, como:

### 1. Sintaxe mais simples e intuitiva:

O `fetch()` utiliza promessas ( `Promises`), permitindo escrever código assíncrono de forma mais legível e estruturada, semelhante ao código síncrono.

### 2. Maior expressividade:

O `fetch()` oferece diversas opções para personalizar as requisições, como definir títulos, métodos HTTP (GET, POST, PUT, DELETE, etc.) e corpo da requisição.

### 3. Integração com promessas:

O `fetch()` retorna uma promessa que é resolvida com a resposta da requisição, facilitando o tratamento de resultados e erros assíncronos.

### 4. Suporte nativo para CORS:

O `fetch()` possui suporte nativo para CORS (Cross-Origin Resource Sharing), permitindo realizar requisições entre diferentes domínios.

## Como usar o fetch():

A forma mais simples de usar `fetch()` é passar a URL do recurso que deseja recuperar como argumento:

```
fetch('https://exemplo.com/dados')
  .then(resposta => resposta.json())
  .then(dados => console.log(dados))
  .catch(erro => console.error(erro));
```
### Explicação do código:

- 1- A função `fetch()`recebe a URL do recurso como argumento e retorna uma promessa.
- 2- O método `then()` é utilizado para tratar a resposta da requisição.
- 3- Dentro de `then()`, o método `json()` da resposta é chamado para converter o corpo da resposta no formato `JSON`.
- 4- Outro `then()`é utilizado para tratar o `JSON` convertido.
- 5- O método `catch()` é utilizado para tratar erros que podem ocorrer durante uma requisição.

### Vantagens do fetch():

**Simplicidade**: O `fetch()` oferece uma sintaxe mais simples e intuitiva do que o XHR.

**Expressividade**: O `fetch()` oferece diversas opções para personalizar as requisições.

**Promessas**: O `fetch()` integra-se perfeitamente com promessas, facilitando o tratamento assíncrono.

**CORS**: O `fetch()` possui suporte nativo para CORS.

