# Tuplas, Listas, Dicionários e Strings

## Conversa Inicial

O objetivo desta aula é aprender a manipular **estruturas de dados** em Python, especificamente **variáveis compostas**. Serão abordados os três principais tipos de variáveis compostas:

  * **Tuplas**: representadas por `()`
  * **Listas**: representadas por `[]`
  * **Dicionários**: representados por `{}`

Também será estudado o **conceito de método** e **métodos para strings**.

### Variáveis

Variáveis podem ser:

  * **Simples**: armazenam somente um dado por vez na memória. Por exemplo, uma única mão carregando um item.
  * **Compostas**: armazenam um conjunto de dados em diversos espaços iguais na memória, todos atendendo pelo mesmo nome. A analogia da "mochila" é usada, onde vários itens (machado, camisa, bacon, abacate) podem ser armazenados e acessados por um índice (ex: `mochila[0]` para o machado).

Uma **estrutura de dados** é um conjunto de dados organizados de uma maneira específica na memória do programa. A forma como esses dados são organizados, buscados, manipulados e acessados define e diferencia as estruturas de dados.

## Tuplas

A **tupla** é a variável composta mais simples em Python. Sua característica primária é a **imutabilidade**, o que significa que, uma vez criada, **não pode ser alterada** ao longo da execução do programa. Também é uma **estrutura estática de dados**, pois seu endereçamento na memória não pode ser alterado.

### Características da Tupla

  * **Estrutura de dados estática**.
  * **Imutável**.
  * Representada em Python por **parênteses `()`**.
  * Os dados são colocados separados por vírgulas e dentro de parênteses.

### Manipulação e Fatiamento de Tuplas

Tuplas podem ser manipuladas e fatiadas de maneira similar às strings. É possível acessar elementos por **índice numérico** (ex: `mochila[0]`) e **fatiar subconjuntos** (ex: `mochila[0:2]`).

#### Exemplo de Fatiamento:

```python
mochila = ('Machado', 'Camisa', 'Bacon', 'Abacate')
print(mochila[0])    # Saída: Machado
print(mochila[2])    # Saída: Bacon
print(mochila[0:2])  # Saída: ('Machado', 'Camisa')
print(mochila[2:])   # Saída: ('Bacon', 'Abacate')
print(mochila[-1])   # Saída: Abacate
```

É importante lembrar que tentar substituir um valor em uma tupla (ex: `mochila[2] = 'Ovos'`) resultará em um erro de `TypeError`, confirmando sua imutabilidade.

### Varredura de Tuplas

É possível percorrer os elementos de uma tupla utilizando um laço `for`.

#### Exemplo com `for` direto:

```python
mochila = ('Machado', 'Camisa', 'Bacon', 'Abacate')
for item in mochila:
    print(f'Na minha mochila tem: {item}')
```

#### Exemplo com `for` e `range` (usando `len`):

```python
mochila = ('Machado', 'Camisa', 'Bacon', 'Abacate')
tam = len(mochila)
for i in range(0, tam, 1):
    print(f'Na minha mochila tem: {mochila[i]}')
```

### Concatenação de Tuplas

Embora tuplas sejam imutáveis, é possível criar uma nova tupla combinando duas ou mais tuplas através de concatenação, similar ao que se faz com strings. A ordem da concatenação faz diferença.

#### Exemplo de Concatenação:

```python
mochila = ('Machado', 'Camisa', 'Bacon', 'Abacate')
upgrade = ('Queijo', 'Canivete')
mochila_grande = mochila + upgrade
print(mochila_grande)
# Saída: ('Machado', 'Camisa', 'Bacon', 'Abacate', 'Queijo', 'Canivete')

mochila_grande_invertida = upgrade + mochila
print(mochila_grande_invertida)
# Saída: ('Queijo', 'Canivete', 'Machado', 'Camisa', 'Bacon', 'Abacate')
```

### Desempacotamento de Parâmetros em Funções

Tuplas podem ser usadas para desempacotar um número arbitrário de parâmetros em uma função, utilizando o asterisco `*` antes do nome da variável no parâmetro da função. Esses valores serão armazenados em uma tupla dentro da função.

#### Exemplo de Desempacotamento:

```python
def soma(*num):
    acumulador = 0
    print(f'Tupla: {num}')
    for i in num:
        acumulador += i
    return acumulador

# Programa principal
print(f'Resultado: {soma(1,2)}\n')
# Saída:
# Tupla: (1, 2)
# Resultado: 3

print(f'Resultado: {soma(1,2,3,4,5,6,7,8,9)}\n')
# Saída:
# Tupla: (1, 2, 3, 4, 5, 6, 7, 8, 9)
# Resultado: 45
```

### Exercícios de Tuplas

#### Exercício 1:

Crie um programa que contenha uma tupla com o nome de 10 linguagens de programação e mostre em qual posição está a linguagem Python.

```python
linguagens = ('Javascript', 'Rust', 'Swift', 'Python', 'Kotlin', 'Go', 'C#', 'Dart', 'Julia', 'Typescript')
i = 0
while (linguagens[i] != 'Python'):
    i += 1
print(f'Encontramos Python na {i+1} posição!')
```

#### Exercício 2:

Escreva uma função que receba uma string com uma mensagem e uma quantidade arbitrária de números empacotados. Dentro da função, encontre o maior número e imprima a mensagem junto com o maior valor.

```python
def func_maior(msg, *num):
    maior = 0
    for i in num:
        if i > maior:
            maior = i
    print(msg, maior)

# Programa principal
func_maior('Maior: ', 8, 6, 4, 78, 56, 12, 9)
```

## Listas

Diferentemente das tuplas, as **listas** são **variáveis compostas mutáveis**, permitindo alterar seus dados e tamanho. São indexadas por valores numéricos inteiros e representadas por **colchetes `[]`**.

### Características da Lista

  * Podemos **alterar dados e tamanho**.
  * São **indexadas por valores numéricos inteiros**.
  * Representadas em Python por **colchetes `[]`**.

### Exemplo de Lista vs. Tupla:

```python
mochila_tupla = ('Machado', 'Camisa', 'Bacon', 'Abacate')
print('Tupla:', mochila_tupla)
# Saída: Tupla: ('Machado', 'Camisa', 'Bacon', 'Abacate')

mochila_lista = ['Machado', 'Camisa', 'Bacon', 'Abacate']
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Camisa', 'Bacon', 'Abacate']
```

### Manipulando Listas

Listas oferecem diversas possibilidades de manipulação, incluindo inserção e remoção de elementos.

#### Alterar Elementos:

Ao contrário das tuplas, é possível substituir um elemento em uma lista usando seu índice.

```python
mochila_lista = ['Machado', 'Camisa', 'Bacon', 'Abacate']
mochila_lista[2] = 'Laranja'
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Camisa', 'Laranja', 'Abacate']
```

#### `append()`:

Adiciona um elemento ao final da lista, alocando memória extra se necessário.

```python
mochila_lista = ['Machado', 'Camisa', 'Laranja', 'Abacate']
mochila_lista.append('Ovos')
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
```

#### `insert()`:

Insere um elemento em qualquer posição da lista, deslocando os elementos existentes para a direita.

```python
mochila_lista = ['Machado', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
mochila_lista.insert(1, 'Canivete')
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Canivete', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
```

### Remover Elementos:

#### `del`:

Remove um elemento pelo seu índice.

```python
mochila_lista = ['Machado', 'Canivete', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
del mochila_lista[1]
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
```

#### `remove()`:

Remove a primeira ocorrência de um valor específico na lista.

```python
mochila_lista = ['Machado', 'Camisa', 'Laranja', 'Abacate', 'Ovos']
mochila_lista.remove('Ovos')
print('Lista:', mochila_lista)
# Saída: Lista: ['Machado', 'Camisa', 'Laranja', 'Abacate']
```

## O que são Métodos?

Em Python, uma lista é um **objeto** de uma classe chamada `list`. Os **métodos** são **funções associadas a objetos**, acessadas pela sintaxe `variável.funcao(parametro)` (ex: `mochila.append('Ovos')`). Este é um conceito de Programação Orientada a Objetos (POO), que, embora não seja o foco principal, explica por que chamamos `append`, `insert`, `remove` de métodos em vez de funções.

### Cópia de Listas

Ao atribuir uma lista a outra variável (`lista_referenciada = lista_original`), não se cria uma cópia independente, mas sim uma **referência** para o mesmo objeto na memória. Isso significa que alterar `lista_referenciada` também altera `lista_original`.

#### Exemplo de Referência (não é cópia):

```python
lista_original = [5, 7, 9, 11]
lista_referenciada = lista_original
print(lista_original)    # Saída: [5, 7, 9, 11]
print(lista_referenciada) # Saída: [5, 7, 9, 11]

lista_referenciada[0] = 2
print(lista_original)    # Saída: [2, 7, 9, 11] (lista_original também foi alterada!)
print(lista_referenciada) # Saída: [2, 7, 9, 11]
```

Para criar uma **cópia independente**, que não afete a lista original ao ser modificada, utiliza-se o fatiamento completo: `lista_referenciada = lista_original[:]`.

#### Exemplo de Cópia Verdadeira:

```python
lista_original = [5, 7, 9, 11]
lista_referenciada = lista_original[:] # Cria uma cópia
print(lista_original)    # Saída: [5, 7, 9, 11]
print(lista_referenciada) # Saída: [5, 7, 9, 11]

lista_referenciada[0] = 2
print(lista_original)    # Saída: [5, 7, 9, 11] (lista_original permanece inalterada)
print(lista_referenciada) # Saída: [2, 7, 9, 11]
```

### Strings e Listas dentro de Listas

É possível ter **dupla indexação** ao trabalhar com strings dentro de listas. O primeiro índice se refere ao item da lista, e o segundo, ao caractere dentro da string daquele item.

#### Exemplo de Dupla Indexação:

```python
mochila = ['Machado', 'Camisa', 'Bacon', 'Abacate']
print(mochila[0])    # Saída: Machado
print(mochila[0][0]) # Saída: M (primeiro caractere do primeiro item)
print(mochila[2][1]) # Saída: a (segundo caractere do terceiro item 'Bacon')
```

### Varredura Dupla de Índices (Laços Aninhados)

Para percorrer cada caractere de cada string dentro de uma lista, podem ser usados laços de repetição aninhados.

#### Exemplo com `for` direto:

```python
mochila = ['Machado', 'Camisa', 'Bacon', 'Abacate']
for item in mochila:
    for letra in item:
        print(letra, end='')
    print() # Quebra de linha após cada palavra
```

#### Exemplo com `for` e `range`:

```python
mochila = ['Machado', 'Camisa', 'Bacon', 'Abacate']
for i in range(0, len(mochila), 1):
    for j in range(0, len(mochila[i]), 1):
        print(mochila[i][j], end='')
    print() # Quebra de linha após cada palavra
```

## Dicionários

**Dicionários** são uma estrutura de dados dinâmica, indexada por **chaves (palavras-chave)**, e representadas por **chaves `{}`**. São ideais para registrar informações com identificadores descritivos, como em uma lista de compras onde cada produto tem nome, quantidade e valor.

### Características do Dicionário

  * É uma **estrutura de dados dinâmica**.
  * Podemos **alterar dados e tamanho**.
  * São **indexados por chaves**.
  * Representados em Python por **chaves `{}`**.

### Métodos para Dicionários

Dicionários possuem métodos específicos para acessar seus elementos:

  * **`values()`**: obtém somente os valores (dados).
  * **`keys()`**: obtém somente as chaves.
  * **`items()`**: obtém o par chave:valor.

### Listas com Dicionários e Dicionários com Listas

É possível aninhar estruturas de dados, tendo listas que contêm dicionários ou dicionários que contêm listas como valores.

## Trabalhando com Métodos em Strings

Apesar de uma string ser **imutável**, seus métodos permitem diversas manipulações úteis, muitas vezes facilitadas pelo conhecimento de listas.

| Função/Método | Objetivo |
| :------------ | :------- |
| **`startswith()`** | Verifica se caracteres existem no início da string. |
| **`endswith()`** | Verifica se caracteres existem no final da string. |
| **`lower()`** | Converte string para minúscula. |
| **`upper()`** | Converte string para maiúscula. |
| **`find()`** | Busca a primeira ocorrência de um padrão de caracteres em uma string. |
| **`rfind()`** | Idêntico a `find()`, mas inicia a busca da direita para a esquerda. |
| **`center()`** | Centraliza uma string. |
| **`ljust()`, `rjust()`** | Ajustam uma string com alinhamentos à esquerda ou à direita, respectivamente. |
| **`split()`** | Divide uma string em uma lista de substrings. |
| **`replace()`** | Substitui caracteres em uma string. |
| **`lstrip()`, `rstrip()`** | Removem espaços em branco à esquerda ou à direita, respectivamente. |
| **`strip()`** | Remove espaços em branco das extremidades. |

| Função/Método | Retorna `True` para uma string com... |
| :------------ | :------------------------------------ |
| **`isalnum()`** | Somente letras e números; acentos são aceitos. |
| **`isalpha()`** | Somente letras; acentos são aceitos. |
| **`isdigit()`** | Somente números. |
| **`isnumeric()`** | Somente números; aceita também caracteres matemáticos, como frações. |
| **`isupper()`** | Somente caracteres maiúsculos. |
| **`islower()`** | Somente caracteres minúsculos. |
| **`isspace()`** | Somente espaços (inclui TAB, quebra de linha, retorno, etc.). |
| **`isprintable()`** | Somente caracteres possíveis de serem impressos na tela. |