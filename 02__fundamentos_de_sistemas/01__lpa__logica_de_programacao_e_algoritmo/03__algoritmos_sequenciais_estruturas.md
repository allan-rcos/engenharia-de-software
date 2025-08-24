# Algoritmos Sequenciais: Estruturas

## Conversa Inicial

O objetivo desta aula é dar continuidade aos estudos de programação com a linguagem **Python**, focando na construção de algoritmos com **estruturas de condição/decisão**. Você aprenderá a criar códigos que tomam decisões, ou seja, as instruções executadas poderão ser distintas dependendo de uma condição.

### Tipos de Condicionais Abordados

Serão investigados todos os tipos de condicionais existentes: a condicional **simples**, a **composta**, a **aninhada** e a de **múltipla escolha**.

### Aplicabilidade Universal

É importante notar que estas condicionais são existentes em todas as principais linguagens de programação modernas e podem ser adaptadas para fora do Python seguindo o mesmo raciocínio lógico aqui apresentado.

### Ambiente de Prática

Assim como em conteúdos anteriores, todos os exemplos apresentados neste material poderão ser praticados concomitantemente em um Jupyter Notebook, como o Google Colab, e não requerem a instalação de nenhum software de interpretação para a linguagem Python em sua máquina.

### Material Complementar

Ao longo do material você encontrará alguns exercícios resolvidos. Estes exercícios estão colocados em linguagem Python com seus respectivos fluxogramas.

## Algoritmos Sequenciais

Todos os algoritmos que você desenvolveu até aqui são chamados de **algoritmos sequenciais**. Ser sequencial significa que todas as instruções são executadas em uma ordem linear, uma após a outra. O fluxo de execução das instruções é da esquerda para a direita e deve ser respeitado.

### Exemplo Lúdico: O Lenhador

Para relembrar um algoritmo sequencial, imagine um lenhador que precisa cortar lenha na floresta antes que seu fogo se apague.

A execução das ações pode ser diferente dependendo do caminho tomado. A decisão de qual caminho tomar (ação na linha 2) é o que leva a ações distintas. Podemos reorganizar as ações usando uma **estrutura de decisão** ou **condicional "se"**.

#### Caminho Principal (Sem Condição):

  * Seguir até a entrada da floresta.
  * Seguir até as toras de madeira.
  * Cortar uma lenha.
  * Retornar ao seu acampamento.

Neste algoritmo, todos os passos são realizados um após o outro, sem exceção.

#### Quebrando o Fluxo de Execução (Caminhos Esquerda e Direita):

Agora, imagine que o lenhador pode optar por dois caminhos: esquerda ou direita.

##### Caminho da Esquerda:

  * Seguir até a entrada da floresta.
  * Tomar o caminho da **ESQUERDA**.
  * Enfrentar o lobo.
  * Seguir até as toras de madeira.
  * Cortar uma lenha.
  * Retornar ao seu acampamento.

Neste caminho, o lenhador encontra um lobo, exigindo um passo adicional.

##### Caminho da Direita:

  * Seguir até a entrada da floresta.
  * Escolher a **DIREITA**.
  * Seguir até as toras de madeira.
  * Cortar uma lenha.
  * Seguir até o acampamento.

Neste caminho, não há lobo para enfrentar.

### Otimização de Algoritmos com Condicionais

Muitas ações se repetem em ambos os caminhos. Em programação, não é uma boa prática repetir a mesma instrução diversas vezes; sempre que possível, deve-se evitar isso. Podemos otimizar o algoritmo para colocar instruções iguais fora da condicional.

### Pseudocódigo Otimizado do Lenhador:

Neste algoritmo otimizado, se o caminho for o da direita, nenhuma instrução dentro do `if` é executada, pois o lobo só aparece no caminho da esquerda.

```
Pseudocódigo otimizado do lenhador
Início
  Seguir até a entrada da floresta
  se (caminho = esquerda)
    Enfrentar o lobo
  fimse
  Seguir até as toras de madeira
  Cortar uma lenha
  Retornar ao seu acampamento
Fim
```

## Condicional Simples e Composta

### Condicional Simples (if)

A estrutura condicional simples decide se um conjunto de instruções deve ou não ser executado.

Se um teste lógico for verdadeiro, as instruções dentro da condição são executadas. Caso contrário (resultado falso), o fluxo de execução ignora esse bloco de código.

Em fluxogramas, o losango representa uma decisão, com dois caminhos: verdadeiro (V) e falso (F). Para o cenário verdadeiro, um bloco de instruções é executado; para o falso, o fluxo pula o bloco e segue adiante.

#### Estrutura em Python:

```python
if (condição): # Os parênteses são opcionais, mas são uma boa prática para clareza
    # Bloco de instruções a ser executado se a condição for verdadeira
    # (Este bloco DEVE estar indentado)
```

#### Exercício:

Desenvolver um programa que leia dois valores numéricos inteiros e compare se o primeiro é maior do que o segundo. Caso seja verdadeiro, imprime na tela a mensagem informando que o primeiro valor digitado é maior do que o segundo.

#### Solução do Exercício:

```python
num1 = int(input('Digite o primeiro número: '))
num2 = int(input('Digite o segundo número: '))
if num1 > num2:
    print(f'O primeiro número ({num1}) é maior do que o segundo ({num2}).')
```

### Condicional Composta (if-else)

A estrutura condicional composta oferece dois blocos de instruções: um para quando a condição é verdadeira (`if`) e outro para quando é falsa (`else`). Isso garante que um dos dois blocos sempre será executado.

#### Estrutura em Python:

```python
if (condição):
    # Bloco de instruções para condição verdadeira
else:
    # Bloco de instruções para condição falsa
```

#### Exercício:

Desenvolver um programa que leia um valor inteiro e descubra se ele é **par ou ímpar**.

### Solução do Exercício:

```python
num = int(input('Digite um número inteiro: '))
if num % 2 == 0:
    print(f'O número {num} é par.')
else:
    print(f'O número {num} é ímpar.')
```

## Expressões Lógicas e Álgebra Booleana

As expressões lógicas utilizam **operadores lógicos** para combinar ou modificar condições, resultando em um valor booleano (`True` ou `False`).

### Operadores Lógicos em Python:

1.  **`not` (Negação)**: Inverte o valor lógico da expressão.
      * `not True` resulta em `False`.
      * `not False` resulta em `True`.
2.  **`and` (Conjunção)**: Retorna `True` se **ambas** as expressões forem verdadeiras. Caso contrário, retorna `False`.
      * `True and True` resulta em `True`.
      * `True and False` resulta em `False`.
      * `False and True` resulta em `False`.
      * `False and False` resulta em `False`.
3.  **`or` (Disjunção)**: Retorna `True` se **pelo menos uma** das expressões for verdadeira. Retorna `False` apenas se ambas forem falsas.
      * `True or True` resulta em `True`.
      * `True or False` resulta em `True`.
      * `False or True` resulta em `True`.
      * `False or False` resulta em `False`.

### Precedência dos Operadores:

A ordem de avaliação das operações é crucial para garantir o resultado esperado de uma expressão. A precedência é a seguinte (do maior para o menor):

1.  **Parênteses**
2.  Operadores aritméticos de **potenciação** ou raiz
3.  Operadores aritméticos de **multiplicação, divisão e módulo**
4.  Operadores aritméticos de **adição e subtração**
5.  **Operadores relacionais** (`==`, `>`, `<`, `>=`, `<=`, `!=`)
6.  Operadores lógicos **`not`**
7.  Operadores lógicos **`and`**
8.  Operadores lógicos **`or`**
9.  **Atribuições** (`=`)

### Exercício:

Um aluno precisa ser aprovado em todas as 3 matérias (com média a partir de 7). Escreva um algoritmo que leia a nota final do aluno em cada matéria e informe se ele passou de ano ou não.

### Solução do Exercício:

```python
nota1 = float(input('Digite a nota da primeira matéria: '))
nota2 = float(input('Digite a nota da segunda matéria: '))
nota3 = float(input('Digite a nota da terceira matéria: '))

if (nota1 >= 7) and (nota2 >= 7) and (nota3 >= 7):
    print('Aluno aprovado!')
else:
    print('Aluno reprovado.')
```

## Condicionais Aninhadas

É possível inserir condicionais **dentro de outras condicionais**. Não há limite para a quantidade de aninhamentos, permitindo construir lógicas mais complexas e detalhadas. A **indentação** é fundamental para a clareza e correta execução do código com condicionais aninhadas.

### Exercício:

Desenvolver um programa que, dado um valor numérico inteiro, descubra se ele é par ou ímpar. Caso seja par, descubra se está entre 0 e 100 ou não. Caso seja ímpar, descubra se está entre 0 e 100 ou não.

## Solução do Exercício:

```python
num = int(input('Digite um número inteiro: '))

if num % 2 == 0: # É par
    print(f'O número {num} é par.')
    if (num >= 0) and (num <= 100):
        print(f'O número {num} está entre 0 e 100.')
    else:
        print(f'O número {num} não está entre 0 e 100.')
else: # É ímpar
    print(f'O número {num} é ímpar.')
    if (num >= 0) and (num <= 100):
        print(f'O número {num} está entre 0 e 100.')
    else:
        print(f'O número {num} não está entre 0 e 100.')
```

## Condicional de Múltipla Escolha (elif)

O `elif` simplifica o uso de **múltiplas condicionais** em um programa. Ele é usado quando há várias condições a serem testadas sequencialmente, e apenas um bloco de código deve ser executado. Isso torna o código mais legível e eficiente do que aninhar múltiplos `if-else`.

### Estrutura em Python:

```python
if (condição1):
    # Bloco de instruções se condição1 for verdadeira
elif (condição2):
    # Bloco de instruções se condição1 for falsa E condição2 for verdadeira
elif (condição3):
    # Bloco de instruções se condição1 e condição2 forem falsas E condição3 for verdadeira
else:
    # Bloco de instruções se nenhuma das condições anteriores for verdadeira
```

### Exercício:

Escrever um algoritmo em Python que apresente um menu para o usuário escolher entre maçãs (opção 1), laranjas (opção 2) ou bananas (opção 3). Após a escolha e a quantidade de unidades, o algoritmo deve calcular e mostrar o preço total a pagar. Considere: maçã R$ 2,30, laranja R$ 3,60 e banana R$ 1,85.

### Solução do Exercício:

```python
print('Bem-vindo ao mercado!')
print('Opções de frutas:')
print('1 - Maçã (R$ 2,30 por unidade)')
print('2 - Laranja (R$ 3,60 por unidade)')
print('3 - Banana (R$ 1,85 por unidade)')

opcao = int(input('Digite o número da fruta desejada: '))
quantidade = int(input('Digite a quantidade de unidades: '))

if opcao == 1:
    preco_total = quantidade * 2.30
    print(f'Você escolheu {quantidade} maçãs. Total a pagar: R$ {preco_total:.2f}.')
elif opcao == 2:
    preco_total = quantidade * 3.60
    print(f'Você escolheu {quantidade} laranjas. Total a pagar: R$ {preco_total:.2f}.')
elif opcao == 3:
    preco_total = quantidade * 1.85
    print(f'Você escolheu {quantidade} bananas. Total a pagar: R$ {preco_total:.2f}.')
else:
    print('Opção inválida. Por favor, escolha 1, 2 ou 3.')
```

### Exercício 2:

Escreva um algoritmo que leia um nome e uma idade. Se o nome for "Vinicius", imprima isso na tela. Caso contrário, verifique a idade: se for menor que 18 anos, informe que é de menor; se for maior que 100 anos, informe que a pessoa possivelmente não existe.

### Solução do Exercício 2:

```python
nome = input('Digite seu nome: ')
idade = int(input('Digite sua idade: '))

if nome == 'Vinicius':
    print('O nome digitado é Vinicius.')
elif idade < 18:
    print('Você é menor de idade.')
elif idade > 100:
    print('Você possivelmente não existe.')
else:
    print('Nome e idade não se encaixam nas condições específicas.')
```

## Finalizando:

Nesta abordagem, foram apresentados todos os tipos de estruturas condicionais existentes na literatura e sua aplicação em Python, incluindo condicionais simples, compostas, aninhadas e de múltipla escolha (`elif`). Reforçamos que tudo o que foi visto neste conteúdo continuará a ser utilizado de maneira extensiva ao longo das próximas aulas, portanto, pratique e resolva todos os exercícios do seu material.