# Algoritmos Sequenciais. Dados, Variáveis e Comandos

## Conversa Inicial

Esta aula tem como objetivo dar os primeiros passos em programação, com foco na construção dos primeiros algoritmos. Os conteúdos abordados incluem: onde programar em Python, quais partes compõem um algoritmo computacional, como exibir mensagens na tela, como manipular dados e variáveis, como realizar operações aritméticas e como ler informações do teclado.

## Ambientes de Desenvolvimento

### Google Colab (Jupyter Notebook)

É possível programar em Python utilizando o **Google Colab**, que é um Jupyter Notebook, acessível através do link [Google Colab](https://colab.research.google.com/).

### Programação Offline

Para programar offline, o Python pode ser instalado na máquina.

  * Em **ambientes Windows**, a instalação é necessária e pode ser feita através do link [Python Downloads](https://www.python.org/downloads/).
  * Em **ambientes Linux**, o Python já vem instalado nativamente.

### IDEs (Ambientes de Desenvolvimento Integrado)

Junto com o Python, é instalado o **IDLE** (Integrated Development Environment - IDE), que é um ambiente de desenvolvimento integrado. Outras opções de IDEs incluem:

  * **PyCharm Community Edition** ([PyCharm](https://www.jetbrains.com/pt-br/pycharm/))
  * **Visual Studio Code**, mantido pela Microsoft ([Visual Studio Code](https://code.visualstudio.com/))

### Boas Práticas de Programação

Ao programar, é fundamental verificar cada caractere digitado, pois caracteres maiúsculos e minúsculos são distintos. É importante também sempre fechar aspas e parênteses que forem abertos, e ter cuidado com os espaços.

## Comandos Básicos em Python

### Comando de Saída (print)

O comando de saída em Python é `print`, que funciona como um comando, instrução ou função. Ele pode ser usado para exibir mensagens como "Olá, mundo\!" ou para realizar cálculos aritméticos como `2+3`.

#### Exemplo:

```python
print("Olá, mundo!")
```

### Operadores e Operações Matemáticas

Os operadores e operações matemáticas em Python são:

  * `+`: **Adição**
  * `-`: **Subtração**
  * `*`: **Multiplicação**
  * `/`: **Divisão** (com casas decimais)
  * `//`: **Divisão** (somente a parte inteira)
  * `%`: **Módulo** / resto da divisão
  * `**`: **Exponenciação** ou potenciação

É importante prestar atenção à **ordem de precedência dos operadores**.

#### Exemplo:

```python
print(2 + 3)
```

## Ciclo de Processamento de Dados

Um algoritmo computacional geralmente segue um ciclo de processamento de dados que consiste em três partes: **Entrada**, **Processamento** e **Saída**. Por exemplo, para somar dois números, o algoritmo leria (x, y) na Entrada, faria o processamento `res = x + y`, e escreveria (res) na Saída.

## Variáveis, Dados e Seus Tipos

**Dados** são sequências de símbolos quantificados ou quantificáveis, ou seja, valores fornecidos via entrada e manipulados ao longo do programa.

Uma **variável** é um nome dado a uma região da memória do programa. Sempre que o nome de uma variável é invocado, seu bloco de memória é automaticamente carregado da RAM.

A **atribuição** é o ato de uma variável receber um dado. Por exemplo, "nota = 8.5" significa que a variável "nota" recebe o dado 8,5, sendo `=` o símbolo de atribuição.

### Regras para nomes de variáveis:

O PEP 8 (Python Enhancement Proposals) é o conjunto oficial de regras e boas práticas do Python. Ele recomenda `preco_total` em vez de `precoTotal`.

  * Nunca inicie o nome de uma variável com um número.
  * Inicie o nome de uma variável com uma letra ou sublinha (underline).
  * Números, letras e sublinhas podem ser usados livremente no meio do nome.
  * Embora Python permita o uso de letras com acentuação, não é recomendado.

### Tipos primitivos de dados:

#### Numéricos:

  * **Inteiro (int):** números sem casas decimais, usados para operações aritméticas.
  * **Ponto flutuante (float):** números com casas decimais, também usados para operações aritméticas.

#### Variáveis lógicas/booleanas:

Armazenam um bit, com dois estados: `True` (Verdadeiro) e `False` (falso), ou nível lógico alto (1) ou baixo (0).

Operadores lógicos em Python e pseudocódigo:

  * `==`: Igualdade
  * `>`: Maior que
  * `<`: Menor que
  * `>=`: Maior ou igual a
  * `<=`: Menor ou igual a
  * `!=`: Diferente

#### Variáveis de cadeias de caracteres (strings):

Armazenam conjuntos de símbolos encadeados, incluindo acentuação, pontuação etc. As strings são representadas em ASCII (7 bits) ou UNICODE (UTF-8, UTF-16, UTF-32).

  * **Índice do caractere:** Um número inteiro que indica a posição do caractere dentro da string. A contagem do índice sempre começa em zero.

## Manipulações com Strings

A **concatenação** serve para juntar ou somar strings.

A **composição com marcadores de posição** permite juntar diferentes variáveis e strings. Exemplos incluem:

  * `'Você tirou %d na disciplina de %s'` e o uso de `%(nota, disciplina)`. Os marcadores são `%d` ou `%i` para números inteiros, `%f` para números de ponto flutuante e `%s` para strings.
  * `'Você tirou {} na disciplina de {}'` e o uso de `.format(nota, disciplina)`.
  * O uso de f-strings, como `f'Você tirou {nota} na disciplina de {disciplina}'`.

O **tamanho (length)** de uma cadeia de caracteres pode ser descoberto com a função `len()`.

O **fatiamento** permite recortar ou fatiar um pedaço da string.

### Código de exemplo:

```python
# Composição de strings com marcadores de posição (método antigo):
'Você tirou %d na disciplina de %s' % (nota, disciplina)

# Composição de strings com o método .format():
'Você tirou {} na disciplina de {}'.format(nota, disciplina)

# Composição de strings com f-string:
f'Você tirou {nota} na disciplina de {disciplina}'
```

## Função de Entrada e Fluxo de Execução

O comando de entrada em Python é `input`, que funciona como um comando, instrução ou função. No pseudocódigo, seria "Ler". A sintaxe é:

```python
input('Mensagem')
```

### Conversão de Dados (Casting)

O `input` sempre retorna um dado do tipo string. Se for necessário um dado numérico, utiliza-se a função `int()` ou `float()` antes do input. Isso ocorre quando uma variável é convertida de um tipo de dado para outro, desde que a conversão seja lógica.

#### Exemplo:

```python
# Convertendo dados de entrada para inteiro (casting):
numero_inteiro = int(input('Digite um número inteiro: '))

# Convertendo dados de entrada para ponto flutuante (casting):
numero_float = float(input('Digite um número com casas decimais: '))
```

O fluxo de execução do programa e o **teste de mesa** são importantes para entender como um programa Python funciona.

## Exercício:

Desenvolver um algoritmo que solicite ao usuário dois números inteiros e imprima a soma desses dois números na tela.

```python
# Solicita o primeiro número inteiro
num1 = int(input("Digite o primeiro número inteiro: "))

# Solicita o segundo número inteiro
num2 = int(input("Digite o segundo número inteiro: "))

# Calcula a soma
soma = num1 + num2

# Imprime a soma na tela
print("A soma dos dois números é:", soma)
```