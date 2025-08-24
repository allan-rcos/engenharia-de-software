### Introdução

* **Contexto histórico**:
    * Em 1990, a internet era estática.
    * Em 1995, Brendan Eich criou o LiveScript, que se tornou o JavaScript.
    * JavaScript é uma linguagem interpretada, também conhecida como ECMAScript.
* **Utilização**:
    * O JavaScript pode ser executado no lado do cliente, em um navegador (`browser`).
    * Também pode ser executado no lado do servidor, utilizando o `Node.js`.
    * É utilizado para adicionar funcionalidades, verificar formulários e comunicar com servidores.
    * Permite programar o comportamento da página web em resposta a eventos.

### Inserindo JavaScript no HTML

* **Como incluir o código**:
    * O código JavaScript pode ser embutido diretamente no documento HTML, dentro da tag `<script>`.
    * O código também pode ser inserido em um arquivo externo com a extensão `.js`.
    * Usar arquivos externos é uma boa prática para separar HTML e JavaScript, tornando o código mais fácil de ler e manter.
    * O link para o arquivo externo é adicionado usando o atributo `src` na tag `<script>`.
    * É recomendado colocar scripts imediatamente antes do fechamento da tag `</body>` para melhorar o carregamento da página.
    * Scripts externos não podem conter a tag `<script>`.

### Variáveis e Constantes

* **Variáveis**:
    * Declaradas com `let` ou `var`.
    * Podem ser globais se declaradas fora de blocos de código delimitados por `{}` ao usar `let` e `const`.
    * O JavaScript é uma linguagem de tipagem dinâmica, ou seja, não é necessário declarar o tipo de uma variável.
* **Constantes**:
    * Declaradas com `const`.
    * Exemplo: o valor de $\pi$.

### Tipos de Dados

* **Tipos de dados primitivos**:
    * Existem seis tipos de dados literais primitivos.
    * `Boolean`: `true` ou `false`.
    * `Number`: números reais, incluindo decimais e inteiros.
    * `BigInt`: números inteiros de qualquer tamanho.
    * `String`: representa uma sequência de caracteres.
    * `Undefined`: valor padrão de uma variável sem valor atribuído.
    * `Symbol`.
    * `Null`: valor de uma variável que não se refere a nenhum objeto.
* **Objetos**:
    * Estruturas de dados complexas, também conhecidas como "registro", que são uma coleção não ordenada de campos nomeados, que em JavaScript são chamados de **propriedades**.
    * Pode-se criar um objeto usando a sintaxe de chaves `{}` ou o operador `new` com um construtor, como `new Object()`.

### Métodos e Interpolação

* **Interpolação de expressões**:
    * Permite inserir variáveis em strings, como em `console.log( 'O resultado da operação é ${a+b}' )`.
* **Métodos de `String`**:
    * `length`: propriedade que informa o número de caracteres de uma string.
    * `charAt(index)`: informa o caractere na posição `index` da string (a contagem começa em zero).
    * `slice(beginIndex, [opcional] endIndex)`: retorna uma nova string a partir dos caracteres entre `beginIndex` (incluído) e `endIndex` (excluído).
    * `split(separator, [opcional] limit)`: divide a string em substrings e retorna um array dessas substrings.
* **Métodos de saída**:
    * `console.log()`: Exibe dados no console do navegador.
    * `window.alert()`: Exibe dados em uma caixa de alerta.
    * `document.write()`: Escreve no próprio HTML.
    * `elemento.innerHTML`: Escreve em um elemento HTML.

### Operadores

* **Operadores de Atribuição**:
    * `=` (atribuição simples).
    * `+=` (atribuição de adição).
    * `-=` (atribuição de subtração).
    * `*=` (atribuição de multiplicação).
    * `/=` (atribuição de divisão).
    * `%=` (atribuição de resto).
    * `**=` (atribuição de exponenciação).
* **Operadores Aritméticos**:
    * `+` (adição).
    * `-` (subtração).
    * `*` (multiplicação).
    * `/` (divisão).
    * `%` (resto da divisão).
    * `**` (exponenciação).
    * `++` (incremento).
    * `--` (decremento).
* **Operadores Relacionais**:
    * `==` (igual).
    * `===` (exatamente igual, compara conteúdo e tipo de dado).
    * `!=` (diferente).
    * `!==` (exatamente diferente, compara conteúdo e tipo de dado).
    * `<` (menor).
    * `<=` (menor ou igual).
    * `>` (maior).
    * `>=` (maior ou igual).
* **Operadores Lógicos**:
    * `&&` (E / AND).
    * `||` (OU / OR).
    * `!` (NÃO / NOT).

### Interação com o Usuário

* **Caixas de diálogo**:
    * `alert()`: caixa de alerta.
    * `confirm()`: caixa de confirmação.
    * `prompt()`: caixa de prompt.

### Estruturas de Controle de Fluxo

* **`if`**:
    * Executa um bloco de código se a condição for verdadeira.
* **`if...else`**:
    * Executa um bloco de código se a condição for verdadeira e outro se for falsa.
* **`if...else if...else`**:
    * Permite verificar múltiplas condições em sequência.
* **`switch`**:
    * Executa um bloco de código com base no valor de uma expressão.
    * Utiliza `case` para cada valor possível e `break` para sair do bloco. O `default` é executado se nenhum `case` corresponder.

### Laços de Repetição

* **`for`**:
    * Usado quando se sabe o número de vezes que o loop deve ser executado.
* **`while`**:
    * Utilizado quando não se sabe exatamente quantas vezes repetir algo, mas se sabe quando parar.
* **`do...while`**:
    * A condição é verificada após cada iteração, garantindo que o bloco de código seja executado pelo menos uma vez.