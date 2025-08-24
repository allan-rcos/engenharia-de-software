# Algoritmos Iterativos. Estruturas de Repetições

## Conversa Inicial

O principal objetivo desta aula é construir algoritmos utilizando **estruturas de repetição**. Serão abordados os seguintes tópicos:

  * **`while` (enquanto)**
  * **`for` (para)**
  * **Laços de repetição aninhados**

### Exemplo Lúdico

Um exemplo é apresentado onde um boneco precisa se "mover" cinco vezes para alcançar um tronco. O objetivo é ilustrar a repetição de uma ação.

### Motivação

Escrever a instrução "Mover" cinco vezes pode não parecer trabalhoso, mas a dificuldade aumenta consideravelmente ao repetir a ação 100 ou 1000 vezes. Para resolver problemas como este, as linguagens de programação empregam estruturas de repetição.

-----

## Estrutura de Repetição

Uma **estrutura de repetição** é um segmento do programa onde todas as instruções contidas nele são repetidas indefinidamente, até que uma condição específica seja satisfeita.

  * **Sinônimos**: estrutura iterativa, laço de repetição ou loop de repetição.

-----

## Estrutura de Repetição While

A estrutura `while` (enquanto) repete um bloco de instruções enquanto uma determinada condição permanecer verdadeira. Caso a condição se torne falsa, o fluxo do programa é desviado para a primeira linha de código após o bloco de repetição.

### Python

Em Python, a estrutura `while` é definida pela palavra-chave `while`, seguida por uma condição lógica (opcionalmente entre parênteses) e dois pontos (`:`).

### Prática em Python

É importante praticar o uso do `while` em Python, prestando atenção especial à **indentação**, que é crucial para a execução correta do código.

#### Exemplo de Código com `while`

```python
# Contagem regressiva simples
contador = 5
while contador > 0:
    print(contador)
    contador -= 1
print("Decolagem!")
```

-----

## Tópicos Importantes com Laços em Python

### Variáveis Contadoras e Acumuladoras

A **variável de controle**, também chamada de iterador, é a responsável por definir a condição de parada do laço e por contar o número de execuções do laço.

  * **Contadoras**: Variáveis que incrementam valores constantes.
  * **Acumuladoras**: Variáveis que acumulam totais, funcionando como um somatório.

### Exemplo de Código com Variável Contadora

```python
i = 0
while i < 5:
    print(f"O valor de i é: {i}")
    i += 1 # Incrementa i em 1
```

### Exemplo de Código com Variável Acumuladora

```python
soma = 0
numero = 1
while numero <= 10:
    soma += numero # Acumula a soma dos números
    numero += 1
print(f"A soma dos números de 1 a 10 é: {soma}")
```

### Exercício com Contador

Escreva um algoritmo que imprima na tela apenas os valores pares dentro de um intervalo especificado pelo usuário.

#### Exemplo de Código: Números Pares em Intervalo

```python
inicio = int(input("Digite o valor inicial do intervalo: "))
fim = int(input("Digite o valor final do intervalo: "))

numero_atual = inicio
while numero_atual <= fim:
    if numero_atual % 2 == 0:
        print(numero_atual)
    numero_atual += 1
```

### Exercício com Acumulador

Crie um algoritmo que calcule a média das notas em uma disciplina, considerando que a média final é a média aritmética de cinco notas digitadas.

#### Exemplo de Código: Média de Notas

```python
total_notas = 0
contador_notas = 0
while contador_notas < 5:
    nota = float(input(f"Digite a nota {contador_notas + 1}: "))
    total_notas += nota
    contador_notas += 1

media = total_notas / 5
print(f"A média das notas é: {media:.2f}")
```

### Operadores Especiais de Atribuição

Python oferece operadores de atribuição que são atalhos para operações comuns:

  * `x += 1` é equivalente a `x = x + 1`
  * `x -= 1` é equivalente a `x = x - 1`
  * `x *= 2` é equivalente a `x = x * 2`
  * `x /= 2` é equivalente a `x = x / 2`
  * `x **= 2` é equivalente a `x = x ** 2`
  * `x //= 4` é equivalente a `x = x // 4`

#### Exemplo de Código: Uso de Operadores de Atribuição

```python
x = 10
x += 5  # x agora é 15
print(f"x depois de x += 5: {x}")

y = 20
y -= 3  # y agora é 17
print(f"y depois de y -= 3: {y}")

z = 2
z *= 4  # z agora é 8
print(f"z depois de z *= 4: {z}")
```

### Validando Dados de Entrada

Crie um algoritmo que receba um valor inteiro via teclado. O programa deve aceitar apenas valores inteiros e positivos, rejeitando qualquer valor negativo ou igual a zero e solicitando um novo valor.

#### Exemplo de Código: Validação de Entrada

```python
numero = -1 # Inicializa com um valor inválido para entrar no loop
while numero <= 0:
    try:
        numero = int(input("Digite um número inteiro e positivo: "))
        if numero <= 0:
            print("Número inválido. Digite um valor positivo.")
    except ValueError:
        print("Entrada inválida. Por favor, digite um número inteiro.")
print(f"Número válido digitado: {numero}")
```

### Instrução Break

A instrução `break` é usada para encerrar um laço de repetição abruptamente, independentemente do estado da variável de controle do laço.

#### Exemplo de Código: Uso de `break`

```python
while True:
    comando = input("Digite um comando (ou 'sair' para encerrar): ")
    if comando == "sair":
        print("Encerrando o programa.")
        break
    print(f"Você digitou: {comando}")
```

### Instrução Continue

O comando `continue` serve para retornar o laço ao início a qualquer momento, independentemente do estado da variável de controle condicional do laço.

#### Exemplo de Código: Uso de `continue`

```python
for i in range(1, 11):
    if i % 2 != 0: # Se o número for ímpar
        continue   # Pula para a próxima iteração
    print(i) # Só imprime números pares
```

### Exercício de Login

Escreva um algoritmo que realize um login em um sistema, onde o usuário deve informar seu nome e senha.

#### Exemplo de Código: Simulação de Login

```python
usuario_correto = "admin"
senha_correta = "12345"

while True:
    usuario = input("Usuário: ")
    senha = input("Senha: ")

    if usuario == usuario_correto and senha == senha_correta:
        print("Login bem-sucedido!")
        break
    else:
        print("Usuário ou senha incorretos. Tente novamente.")
```

-----

## Estrutura de Repetição For

Assim como o `while`, a estrutura `for` repete um bloco de instruções enquanto uma condição se mantiver verdadeira. A principal diferença é que o `for` é geralmente empregado em situações onde o número de vezes que o laço será executado é finito e bem definido.

### Python

Em Python, a estrutura `for` é usada com a palavra-chave `for`, uma variável de iteração, a palavra-chave `in`, e uma função `range()` que define o valor final do iterador (entre parênteses obrigatórios), seguido por dois pontos (`:`). Por exemplo: `for i in range(6):`

### Valores Truthy e Falsey

Em Python, dados não booleanos também podem ser tratados como `True` ou `False` em condições.

  * **Falsey/False**: Número zero (inteiro ou float) e string vazia.
  * **Truthy/True**: Qualquer outro dado.

#### Exemplo de Código: Truthy e Falsey

```python
if 0:
    print("0 é Truthy")
else:
    print("0 é Falsey")

if "":
    print("String vazia é Truthy")
else:
    print("String vazia é Falsey")

if "olá":
    print("String 'olá' é Truthy")
else:
    print("String 'olá' é Falsey")

if 10:
    print("10 é Truthy")
else:
    print("10 é Falsey")
```

### Parâmetros do `for`

  * É possível definir o valor inicial do iterador.
  * É possível definir o passo do iterador.

#### Python: Com Três Parâmetros

A função `range()` em Python pode receber três parâmetros: `range(valor_inicial, valor_final, passo)`.

  * **Valor inicial do iterador**: Onde a contagem começa.
  * **Valor final do iterador**: Onde a contagem termina (não inclusivo).
  * **Passo do iterador**: O incremento a cada repetição.

#### Exemplo de Código: `range()` com 3 Parâmetros

```python
# Contagem de 0 a 5 (exclusivo)
for i in range(6):
    print(i) # Saída: 0, 1, 2, 3, 4, 5

print("-" * 20)

# Contagem de 2 a 8 (exclusivo)
for i in range(2, 9):
    print(i) # Saída: 2, 3, 4, 5, 6, 7, 8

print("-" * 20)

# Contagem de 1 a 10 com passo de 2
for i in range(1, 11, 2):
    print(i) # Saída: 1, 3, 5, 7, 9
```

### Varredura de String

É possível percorrer todos os caracteres de uma string utilizando um laço `for`.

#### Exemplo de Código: Iterando sobre uma String

```python
minha_string = "Python"
for caractere in minha_string:
    print(caractere)
```

### Comparativo `while` e `for`

Um comparativo visual mostra como as estruturas `while` e `for` podem ser usadas para propósitos semelhantes, destacando como o `for` encapsula o valor inicial, valor final e passo do iterador.

#### Exemplo de Código: Equivalência `while` e `for`

```python
# Usando while
x = 1
while x <= 5:
    print(x)
    x += 1

print("-" * 20)

# Usando for (equivalente)
for i in range(1, 6):
    print(i)
```

### Exercício de Média de Pares

Escreva um algoritmo que calcule a média dos números pares de 1 até 100 (inclusive 1 e 100), implementando o laço usando `for`.

#### Exemplo de Código: Média de Pares com `for`

```python
soma_pares = 0
contador_pares = 0

for numero in range(1, 101):
    if numero % 2 == 0:
        soma_pares += numero
        contador_pares += 1

if contador_pares > 0:
    media_pares = soma_pares / contador_pares
    print(f"A média dos números pares de 1 a 100 é: {media_pares:.2f}")
else:
    print("Não foram encontrados números pares no intervalo.")
```

-----

## Estruturas de Repetição Aninhadas

É possível inserir laços de repetição dentro de outros laços. Não há limite para quantos laços podem ser aninhados, e é permitido misturar `while` e `for` em estruturas aninhadas.

### Exercício de Tabuada

Escreva um algoritmo em Python que calcule a tabuada de todos os números de 1 até 10. Para cada número, a tabuada deve ser calculada multiplicando-o pelo intervalo de 1 até 10.

#### Exemplo de Código: Tabuada com Laços Aninhados

```python
# Usando for aninhado
for i in range(1, 11): # Tabuada do número i
    print(f"\nTabuada do {i}:")
    for j in range(1, 11): # Multiplicador j
        resultado = i * j
        print(f"{i} x {j} = {resultado}")
```

### Implementações

Serão resolvidas diferentes implementações em Python, incluindo:

  * Duas estruturas `while` aninhadas.
  * Duas estruturas `for` aninhadas.
  * Uma combinação de `while` e `for` aninhados.

#### Exemplo de Código: `while` Aninhado

```python
linha = 1
while linha <= 3:
    coluna = 1
    while coluna <= 3:
        print(f"({linha}, {coluna})", end=" ")
        coluna += 1
    print() # Nova linha após cada linha de colunas
    linha += 1
```

#### Exemplo de Código: `for` Aninhado

```python
for linha in range(1, 4):
    for coluna in range(1, 4):
        print(f"({linha}, {coluna})", end=" ")
    print()
```

#### Exemplo de Código: `while` com `for` Aninhado

```python
linha_while = 1
while linha_while <= 3:
    for coluna_for in range(1, 4):
        print(f"({linha_while}, {coluna_for})", end=" ")
    print()
    linha_while += 1
```