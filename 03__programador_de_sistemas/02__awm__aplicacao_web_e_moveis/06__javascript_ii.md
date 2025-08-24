# JavaScript II

## DOM - Document Object Model

* **O que é?** É uma interface de programação de aplicações (API) para HTML e XML.
* **O que ele faz?** Define a estrutura lógica de documentos e a forma como são acessados e manipulados.
* **Como ele enxerga?** Enxerga todo documento HTML como uma árvore de objetos.

## Manipulando o DOM

* **Selecionando elementos**:
    * `document.getElementById('id')`: Seleciona um elemento pelo seu ID.
    * `document.getElementsByClassName('class')`: Seleciona todos os elementos com a mesma classe, retornando um *array* de elementos.
    * `document.getElementsByTagName('tag')`: Seleciona todos os elementos com a mesma tag, retornando um *array* de elementos.
    * `document.querySelector('seletor')`: Seleciona o primeiro elemento que corresponde a um seletor CSS, como `#id`, `.classe`, `tag`.
    * `document.querySelectorAll('seletor')`: Seleciona todos os elementos que correspondem a um seletor CSS, retornando um *array* de elementos.
* **Manipulando o conteúdo**:
    * `elemento.innerHTML = 'novo conteúdo'`: Altera o conteúdo HTML de um elemento.
    * `elemento.textContent = 'novo texto'`: Altera apenas o texto de um elemento, sem interpretar tags HTML.
* **Manipulando atributos**:
    * `elemento.setAttribute('nome_atributo', 'valor')`: Define ou altera o valor de um atributo.
    * `elemento.getAttribute('nome_atributo')`: Retorna o valor de um atributo.
    * `elemento.removeAttribute('nome_atributo')`: Remove um atributo.

## Eventos

* **O que são?** Ações ou ocorrências que acontecem no sistema que o código pode ouvir e responder.
* **Adicionando ouvintes de eventos**:
    * `elemento.addEventListener('evento', função_de_callback)`: Adiciona uma função que será executada quando o evento especificado ocorrer.

## Funções

* **O que são?** Blocos de código reutilizáveis que podem ser chamados para executar uma tarefa específica.
* **Funções nomeadas**: Definidas com a palavra-chave `function` e um nome.
* **Funções anônimas**: Funções sem nome, geralmente atribuídas a uma variável.
* **Arrow Functions (ES6)**: Uma sintaxe mais curta para escrever funções.

## Promises

* **O que são?** Objetos que representam a conclusão (ou falha) eventual de uma operação assíncrona.
* **Estados da Promise**:
    * `pending`: Estado inicial.
    * `fulfilled`: A operação foi concluída com sucesso.
    * `rejected`: A operação falhou.
* **`async/await`**: Uma forma moderna e síncrona de trabalhar com Promises.

## Módulos ES6

* **O que são?** Uma forma de organizar o código em arquivos separados, facilitando a reutilização e manutenção.
* **`export`**: Usado para exportar itens de um módulo.
* **`import`**: Usado para importar itens exportados de outro módulo.

## Arrays

* **O que são?** Estruturas de dados que armazenam uma coleção de elementos.
* **Métodos úteis**:
    * `array.push(elemento)`: Adiciona um elemento ao final.
    * `array.pop()`: Remove o último elemento.
    * `array.shift()`: Remove o primeiro elemento.
    * `array.unshift(elemento)`: Adiciona um elemento no início.
    * `array.indexOf(elemento)`: Retorna o índice de um elemento.
    * `array.includes(elemento)`: Verifica se o array contém um elemento.
    * `array.slice(inicio, fim)`: Retorna uma cópia de parte do array.
    * `array.splice(inicio, deletar, adicionar)`: Altera o conteúdo do array.
    * `array.length`: Propriedade para verificar a quantidade de elementos de um array.

## Métodos de Iteração de Arrays

* `array.forEach(callback)`: Executa uma função para cada elemento.
* `array.map(callback)`: Retorna um *novo array* com os resultados de uma função aplicada a cada elemento.
* `array.filter(callback)`: Cria um novo array com elementos que passam em um teste.
* `array.reduce(callback, valorInicial)`: Reduz o array a um único valor.
* **`for...of`**: Laço dedicado ao uso com arrays, executado para cada elemento do array.

## Classes (ES6)

* **O que são?** "Modelos" para criar objetos.
* **Sintaxe básica**: Utiliza a palavra-chave `class` para definir o modelo e `constructor` para inicializar as propriedades.
* **Herança**: Classes podem herdar propriedades e métodos de outras classes com a palavra-chave `extends`.

## JSON - JavaScript Object Notation

* **O que é?** Um formato leve de troca de dados.
* **Características**:
    * Baseado na sintaxe de objetos de JavaScript.
    * Usa pares de chave/valor.
    * Chaves são strings entre aspas duplas.
* **Métodos para trabalhar com JSON em JavaScript**:
    * `JSON.parse(string)`: Converte uma string JSON em um objeto JavaScript.
    * `JSON.stringify(objeto)`: Converte um objeto JavaScript em uma string JSON.

## Tipos de Dados

* **Tipos de dados primitivos**: incluem `boolean`, `number`, `BigInt`, `string` e `undefined`.
* **Objetos**: Estruturas de dados complexas, conhecidas como "registro", que são uma coleção não ordenada de campos nomeados, que em JavaScript são chamados de **propriedades**.
* **Como criar um objeto**: Pode-se usar o literal de chaves `{}` ou o operador `new` com um construtor, como `new Object()`. Para criar objetos com propriedades, usa-se a sintaxe de pares **chave-valor**.
* **Funções Construtoras**: Funções que criam novos objetos. É uma convenção usar Pascal Case (inicial em maiúscula) para nomeá-las.
* **Como iterar por um objeto**: O laço `for...in` interage sobre as propriedades enumeradas de um objeto.