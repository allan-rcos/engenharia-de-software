# Funções

## Conversa Inicial

Esta seção aborda a **modularização de códigos** em programação. Em Python, isso significa criar **funções** para organizar rotinas, tornando o código mais **legível, simples e útil**. Todo o conteúdo e exemplos podem ser praticados em ambientes como Jupyter Notebook ou Google Colab.

### Funções Pré-definidas em Python

Desde o início dos estudos em Python, funções como `input()`, `print()`, `int()`, `float()` e `range()` já são utilizadas. Embora chamadas de instruções ou comandos, para Python, são **funções**. Elas são rotinas de código que, ao serem invocadas, executam uma tarefa específica. Funções fundamentais como `print()` são escritas em linguagens de baixo nível como C para maior controle.

### Vantagens da Modularização

Evitar a repetição de código é crucial. Funções agrupam instruções para reutilização, simplificando o desenvolvimento e tornando os programas mais portáveis. Como nem todos os problemas têm funções pré-definidas, aprender a **criar suas próprias rotinas** é essencial para a **modularização de código**.

## Funções

### Definição

Uma **função** é um bloco de código reutilizável. Usamos funções quando um conjunto de instruções precisa ser executado várias vezes ou para modularizar o código, melhorando legibilidade e manutenção.

### Motivação para Uso

Repetir instruções torna o código extenso e difícil de manter. Funções evitam essa repetição, agrupando as instruções para serem chamadas conforme a necessidade.

### Sintaxe Básica

Para definir uma função em Python, usa-se a palavra-chave `def`, seguida pelo nome da função, parênteses `()` (que podem conter parâmetros) e dois pontos `:`.

```python
def nome_da_funcao():
    # Bloco de instruções
```

### Corpo da Função

O código dentro de uma função é chamado de **corpo da função**.

```python
def realce():
    print('|', ' ' * 10, '|')
    print('|', '_' * 10, '|')
```

### Chamada de Função

Para executar o código de uma função, basta invocar seu nome seguido de parênteses.

```python
# Programa principal
realce()
print('   MENU')
realce()
```

### Fluxo de Execução

A execução de um programa Python ocorre linha por linha. A execução **sempre começa pelo programa principal**. Ao chamar uma função, o programa principal é interrompido, as linhas da função são executadas e, ao final dela, o programa principal é retomado na linha seguinte à chamada.

#### Erro de Função Não Definida

Uma função deve ser **definida antes de ser invocada** pela primeira vez para evitar erros de compilação.

## Parâmetros em Funções

### O que são Parâmetros

**Parâmetros** são dados que uma função recebe, permitindo que ela opere com informações diferentes a cada execução, aumentando sua flexibilidade.

### Passagem de Parâmetros

Funções podem receber dados de variáveis do programa principal, manipulando-os em sua rotina. As informações passadas na chamada da função são os **argumentos** (ou parâmetros no contexto da chamada).

```python
def realce(s1):
    print('|', ' ' * 10, '|')
    print('|', '_' * 10, '|')
    print(s1)
    print('|', '_' * 10, '|')
    print('|', ' ' * 10, '|')

# Programa principal
realce('   MENU')
```

### Parâmetros por Posição

Ao chamar uma função, os argumentos são associados aos parâmetros na ordem em que são definidos. A ordem é crucial.

```python
def sub2(x, y):
    res = x - y
    print(res)

sub2(5, 7) # x=5, y=7
sub2(7, 5) # x=7, y=5
```

### Parâmetros por Chave (Nomeados)

Python permite passar parâmetros fora de ordem, explicitando qual variável receberá qual valor. No entanto, é recomendável manter a ordem para legibilidade.

```python
def sub2(x, y):
    res = x - y
    print(res)

sub2(y=7, x=5)
```

### Parâmetros Opcionais

É possível tornar parâmetros opcionais definindo um **valor padrão** na criação da função. Se o parâmetro for omitido na chamada, o valor padrão é utilizado.

#### Valores Padrão

```python
def soma3(x=0, y=0, z=0):
    res = x + y + z
    print(res)

soma3(1, 2, 3) # Saída: 6
soma3(1, 2)    # Saída: 3
soma3(1)       # Saída: 1
soma3()        # Saída: 0
```

#### Flexibilidade no Uso

Parâmetros opcionais são úteis para **habilitar ou desabilitar recursos** dentro de uma função.

```python
def soma3(x=0, y=0, z=0, imprime=False):
    res = x + y + z
    if imprime:
        print(res)

soma3(1, 2, 3, True)
```

#### Cuidado ao Omitir Argumentos

Ao usar parâmetros opcionais, se você omitir um valor e passar um argumento posicional que deveria ser para um parâmetro posterior, pode ocorrer um erro lógico. Use parâmetros nomeados para evitar isso.

```python
# Para somar 1 e 2 e imprimir, o correto é:
# soma3(1, 2, imprime=True) # Exemplo de chamada correta com parâmetro nomeado
```

## Exercícios Práticos

### Exercício 1: Borda Personalizada

Crie uma rotina que gera uma borda ao redor de uma palavra, adaptando o tamanho da caixa de texto à palavra.

```python
def borda(s1):
    tam = len(s1)
    if tam:
        print('+', '-' * tam, '+')
        print('|', s1, '|')
        print('+', '-' * tam, '+')

borda('Olá, Mundo!')
borda('Lógica de Programação e Algoritmos')
```

### Exercício 2: Contador Flexível

Escreva uma rotina para contagem em laço de repetição, imprimindo em uma única linha. A função deve receber valor inicial, final e passo, com inicial e passo opcionais.

```python
def contador(fim, inicio=0, passo=1):
    for i in range(inicio, fim + 1, passo):
        print(f'{i}', end=' ')
    print('\n')

contador(20, 10, 2)
contador(12)
```

### Exercício 3: Ordenar Três Valores

Escreva uma rotina que recebe três valores e os organiza em ordem crescente, imprimindo-os.

```python
def maior3(v1=0, v2=0, v3=0):
    if (v1 is not None and v2 is not None and v3 is not None): # Garante que os valores foram fornecidos
        valores = [v1, v2, v3]
        valores.sort() # Usa o método sort() para ordenar a lista
        print(f'Ordem crescente: {valores[0]}, {valores[1]}, {valores[2]}')

x = int(input('Digite o valor 1: '))
y = int(input('Digite o valor 2: '))
z = int(input('Digite o valor 3: '))
maior3(x, y, z)
```

## Escopo de Variáveis

### Definição de Escopo

**Escopo** é a área do programa onde uma variável pode ser acessada. Existem escopos **global** e **local**.

### Variáveis Locais

Variáveis criadas como parâmetro ou dentro do corpo de uma função são **locais** a essa função. Elas existem **apenas dentro da própria função** e são destruídas ao seu término. Se a função for chamada novamente, as variáveis locais são reiniciadas.

#### Exemplo de Erro `NameError`

```python
def omelete():
    ovos = 12 # variável local

# Programa principal
omelete()
# print(ovos) # Causa NameError: 'ovos' não está definida
```

### Variáveis Globais

Variáveis **globais** são criadas no programa principal e podem ser acessadas por todas as funções. O uso de escopos locais ajuda a minimizar bugs, pois problemas ficam confinados à função.

#### Exemplo de Múltiplos Escopos

```python
def omelete():
    ovos = 12 # Variável local de omelete
    bacon()
    print('Ovos (omelete):', ovos) # Imprime ovos local de omelete

def bacon():
    ovos = 6 # Variável local de bacon
    print('Ovos (bacon):', ovos)

# Programa principal
ovos = 2 # Variável global
bacon()
print('Ovos (global):', ovos)

# Saída:
# Ovos (bacon): 6
# Ovos (global): 2

# Neste exemplo, bacon() cria sua própria ovos local. A ovos global permanece inalterada.
```

### Instrução `global`

Para modificar uma **variável global** dentro de uma função sem criar uma variável local de mesmo nome, usa-se a palavra-chave `global`.

#### Exemplo de Uso de `global`

```python
salario = 1000 # Variável global

def aumento():
    global salario # Declara que salario é a variável global
    salario += 500
    print('Salário na função:', salario)

print('Salário antes:', salario)
aumento()
print('Salário depois:', salario)

# Saída:
# Salário antes: 1000
# Salário na função: 1500
# Salário depois: 1500

# Aqui, aumento() modifica diretamente a variável salario global.
```

## Retorno de Valores em Funções

### Propósito do Retorno

Funções podem enviar valores de volta para o ponto onde foram chamadas. Isso é feito com a instrução `return`.

### A Instrução `return`

`return` especifica o valor que a função deve retornar. Uma função pode retornar qualquer tipo de dado.

```python
def somar(a, b):
    resultado = a + b
    return resultado

soma = somar(5, 3)
print(soma) # Saída: 8
```

### Retornando Múltiplos Valores

Uma função pode retornar múltiplos valores como uma tupla.

```python
def operacoes(a, b):
    soma = a + b
    subtracao = a - b
    return soma, subtracao

res_soma, res_subtracao = operacoes(10, 4)
print(f"Soma: {res_soma}, Subtração: {res_subtracao}") # Saída: Soma: 14, Subtração: 6
```

### Exemplo Prático: Média Aritmética

```python
def calcular_media(n1, n2, n3):
    media = (n1 + n2 + n3) / 3
    return media

nota_final = calcular_media(7.0, 8.5, 6.0)
print(f"A média final é: {nota_final:.2f}") # Saída: A média final é: 7.17
```

## Recursos Avançados com Funções

### Docstrings

**Docstrings** são strings de documentação que explicam o que uma função faz. São definidas logo abaixo da assinatura da função.

#### Documentação de Funções

Docstrings melhoram a legibilidade do código, servindo como uma mini-documentação.

#### Acesso à Docstring

Podem ser acessadas usando `help()` ou o atributo `.__doc__`.

```python
def minha_funcao(param):
    """
    Esta é uma função de exemplo.
    :param param: Um parâmetro qualquer.
    :return: Retorna o valor do parâmetro.
    """
    return param

print(help(minha_funcao))
```

### Funções Anônimas (Lambda)

Funções **lambda** são pequenas funções sem nome, com qualquer número de argumentos, mas apenas uma expressão. Úteis para operações simples e uso temporário.

#### Sintaxe e Uso

```python
multiplicar = lambda x, y: x * y
print(multiplicar(5, 3)) # Saída: 15
```

#### Casos de Uso

São frequentemente usadas em conjunto com funções como `map()`, `filter()` e `sorted()`.

### Recursividade

**Recursividade** é quando uma função chama a si mesma para resolver um problema.

#### Definição

Problemas complexos podem ser divididos em subproblemas menores, semelhantes ao problema original, resolvidos pela própria função.

### Condição de Parada

É essencial ter uma **condição de parada** para evitar loops infinitos.

#### Exemplo: Cálculo de Fatorial

```python
def fatorial(n):
    if n == 0:
        return 1
    else:
        return n * fatorial(n - 1)

print(fatorial(5)) # Saída: 120 (5 * 4 * 3 * 2 * 1)
```

## Tratamento de Exceções

**Exceções** são erros que ocorrem durante a execução do programa, mesmo com a sintaxe correta. O tratamento de exceções evita que o programa pare abruptamente.

### Propósito

Permite que o programa lide com situações inesperadas de forma controlada.

### `try-except`

O código que pode gerar um erro é colocado no bloco `try`. Se um erro ocorrer, o programa salta para o bloco `except`, que lida com a exceção.

```python
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(resultado)
except ValueError:
    print("Entrada inválida. Digite um número inteiro.")
except ZeroDivisionError:
    print("Não é possível dividir por zero.")
```

#### Tipos Comuns de Exceções

  * **`ZeroDivisionError`**: Divisão por zero.
  * **`ValueError`**: Tipo de dado inesperado (ex: `int('abc')`).
  * **`IndexError`**: Acesso a índice inexistente em lista/tupla.

### Bloco `finally`

Opcionalmente, pode-se usar um bloco `finally`, cujo código é executado sempre, independentemente de ter ocorrido uma exceção ou não.

## Exercícios Propostos

### Validação de Entrada

Reimplemente o exercício de validação de entrada, utilizando uma função para encapsular a lógica de validação.

#### Solução:

```python
# Exercício: Validação de Entrada com Função
def validar_inteiro_positivo():
    """
    Solicita ao usuário um número inteiro e positivo,
    repetindo a solicitação até que uma entrada válida seja fornecida.
    """
    numero = -1
    while numero <= 0:
        try:
            numero = int(input("Digite um número inteiro e positivo: "))
            if numero <= 0:
                print("Número inválido. Digite um valor positivo.")
        except ValueError:
            print("Entrada inválida. Por favor, digite um número inteiro.")
    return numero

# Exemplo de uso:
# valor_validado = validar_inteiro_positivo()
# print(f"Você digitou um valor válido: {valor_validado}")
```

### Cálculo de Média

Reimplemente o cálculo da média utilizando uma função para separar a lógica de cálculo.

#### Solução:

```python
# Exercício: Cálculo da Média com Função
def calcular_media_n_notas(num_notas):
    """
    Calcula a média aritmética de 'num_notas' digitadas pelo usuário.

    Args:
        num_notas (int): O número de notas a serem inseridas.

    Returns:
        float: A média das notas.
    """
    total_notas = 0
    for i in range(num_notas):
        while True:
            try:
                nota = float(input(f"Digite a nota {i + 1}: "))
                if 0 <= nota <= 10: # Supondo notas de 0 a 10
                    total_notas += nota
                    break
                else:
                    print("Nota inválida. Digite um valor entre 0 e 10.")
            except ValueError:
                print("Entrada inválida. Por favor, digite um número.")
    
    if num_notas > 0:
        media = total_notas / num_notas
        return media
    else:
        return 0.0 # Retorna 0 se não houver notas

# Exemplo de uso:
# numero_de_notas = int(input("Quantas notas você deseja calcular a média? "))
# media_calculada = calcular_media_n_notas(numero_de_notas)
# print(f"A média das {numero_de_notas} notas é: {media_calculada:.2f}")
```