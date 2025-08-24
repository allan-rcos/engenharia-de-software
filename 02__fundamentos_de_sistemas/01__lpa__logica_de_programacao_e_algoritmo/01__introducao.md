# Introdução

## Conversa Inicial

O objetivo é introduzir os principais conceitos inerentes à disciplina de **programação**. Estes conceitos serão recorrentes.

### Estrutura de Conteúdos:

  * O que é lógica?
  * O que são algoritmos?
  * Como representamos algoritmos?
  * Que sistema computacional usamos para executar programas?
  * O que são linguagens de programação?
  * Qual linguagem será adotada?

## Introdução à Lógica e aos Algoritmos

### O que é lógica?

  * Aristóteles (384 a 322 a.C.) conceituou lógica (logos) como linguagem racional.
  * É a parte da filosofia que se ocupa das formas do pensamento e das operações intelectuais.
  * **Origem do Termo:** A palavra "**lógica**" deriva do grego "logos", que foi conceitualizada por Aristóteles como linguagem racional.
  * **Definição Filosófica:** No contexto da filosofia, a lógica é o ramo que estuda as formas do pensamento e as operações intelectuais.

### O que são algoritmos?

  * É o raciocínio lógico do nosso dia a dia para realizar atividades.
  * Na computação: maneira pela qual instruções, assertivas e pressupostos são organizados num algoritmo para viabilizar a implantação de um programa.
  * Um algoritmo é uma sequência de passos a serem realizados para que determinada tarefa seja concluída, ou um objetivo atingido.
  * **Definição no Dia a Dia:** Algoritmos são o raciocínio lógico que usamos cotidianamente para realizar diversas atividades.
  * **Definição na Computação:** Na área da computação, um **algoritmo** é a maneira como instruções, assertivas e pressupostos são estruturados para viabilizar a implementação de um programa. Essencialmente, é uma sequência de passos para concluir uma tarefa ou atingir um objetivo.
  * **Exemplo de algoritmo (Sanduíche):** Pegar uma fatia de pão, raspar manteiga, espalhar, colocar queijo e presunto, colocar outro pão.
  * **Exemplo de algoritmo (Equação):** Para resolver $(a+b) \\cdot c+d$, primeiro realizar a soma dentro dos parênteses, depois multiplicar por c, e por fim, somar com d.

## Sistemas de Computação

  * Percebeu-se a necessidade de mudar a maneira como computadores eram projetados, da aritmética decimal para a binária.
  * **John von Neumann:** Matemático húngaro que propôs o primeiro computador de programa armazenado.

### Contexto Histórico

  * Durante a Segunda Guerra Mundial, computadores foram usados para cálculo de mísseis e mensagens codificadas. Eram máquinas construídas com milhares de válvulas e relés, pesando toneladas e consumindo muita energia.
  * **Tecnologia Antiga:** As primeiras máquinas eram compostas por milhares de válvulas e relés, possuíam um tamanho enorme (pesando toneladas) e um consumo energético muito elevado.
  * **Inovação de Von Neumann:** A necessidade de otimização levou à proposta de John von Neumann, um matemático húngaro, que introduziu o conceito do primeiro **computador de programa armazenado**, fundamental para a arquitetura computacional moderna. Sua ideia de arquitetura mudou a forma como os computadores foram projetados, passando da aritmética decimal para a binária.

### A Máquina de Von Neumann

  * Equivalência de armazenamento:
      * 8 bits = 1 Byte
      * 1024 Bytes = 1 KiloByte (KB)
      * 1024 KB = 1 MegaByte (MB)
      * 1024 MB = 1 GigaByte (GB)
      * 1024 GB = 1 TeraByte (TB)
      * 1024 TB = 1 PetaByte (PB)

### O Bit

  * Base decimal: dígitos de 0 a 9.
  * Base binária: dígitos 0 e 1.
  * Todo e qualquer computador é binário.
  * **Binary digit:** a menor unidade de armazenamento de dados.

### A Palavra (Word)

  * **Binary digit:** a menor unidade de armazenamento de dados.
  * **Palavra (word):** a menor unidade útil de manipulação do dado.

### O Sistema Operacional

  * Define quais softwares e quando serão executados.
  * Gerencia o uso de memória.
  * Abstrai o hardware para o usuário e para o desenvolvedor.

## Representação de Algoritmos

### Descrição Narrativa

  * Linguagem natural.
  * Não utilizada em algoritmos computacionais.
  * **Exemplo:** Ler dois valores (x e y), verificar se são iguais. Se forem iguais, mostrar "Valores iguais\!". Se forem diferentes, mostrar "Valores diferentes\!". Fim.

### Pseudocódigo

  * Português estruturado.
  * Representação mais próxima de um programa computacional, mas sem se preocupar com a linguagem de programação adotada.
  * Possui regras definidas e é uma linguagem genérica.

#### Exemplo:

```
Algoritmo VerificaValores
Var
  x, y: inteiro
Início
  Ler (x, y)
  Se (x = y) então
    Mostrar ("Valores iguais!")
  Senão
    Mostrar ("Valores diferentes!")
  Fimse
Fim
```

### Fluxograma

  * Representação gráfica de um algoritmo.
  * Usado para passar a ideia do seu código e organizar o raciocínio lógico.
  * Simbologia gráfica padrão ISO 5807:1985.
  * **Exemplo:** Um fluxograma para o pseudocódigo anterior iniciaria com um símbolo de terminal para "Início", seguido por um símbolo de entrada para "Ler (x, y)". A próxima etapa seria um símbolo de decisão para "x = y?". Se verdadeiro, um símbolo de processo para "Mostrar ('Valores iguais\!')"; se falso, um símbolo de processo para "Mostrar ('Valores diferentes\!')". Ambos os caminhos convergiriam para um símbolo de terminal "Fim".

## Linguagens de Programação e Compiladores

  * Um computador só compreende bits.
  * É muito difícil escrever um programa somente usando bits.

### Linguagens de Programação

  * É um conjunto de regras, com palavras-chaves, verbos, símbolos e sequências específicas, que chamamos de **sintaxe da linguagem**.
  * Resultam em instruções compreendidas pelo computador e não geram ambiguidades.

### Software de Compilação

  * Transforma o código escrito em alto nível (pelo programador) em uma linguagem de máquina (baixo nível) compreendida pelo hardware.
  * **Compilador:** transforma um código-fonte em um arquivo binário.
  * **Interpretador:** o código não é convertido de uma só vez, mas é executado instrução por instrução à medida que o programa vai requisitando.

## Linguagem de Programação Python

  * **Sites oficiais:** [https://www.python.org/](https://www.python.org/) e [https://python.org.br/](https://python.org.br/).

### Popularidade:

  * Linguagem de propósito geral.
  * Vasta quantidade de bibliotecas existentes.
  * Linguagem simples, intuitiva, ótima para iniciantes.
  * Multiplataforma.
  * Comunidade ativa e atualizações constantes (Python Software Foundation, 2001).

### Histórico da Linguagem

  * Criada em 1982 por Guido van Rossum no Centrum Wiskunde & Informatica (CWI), Amsterdam.
  * Inspiração: linguagem ABC.
  * Nome inspirado em "Monty Python Flying Circus", programa de televisão britânico (1969-1974).

### Exemplos de Aplicações Python

  * Sistemas operacionais (Linux, macOS, RaspBerry Pi).
  * Análise de dados e inteligência artificial.
  * Industrial Light and Magical (ILM) - usado em filmes como Star Wars.
  * Jogos (Civilization, Battlefield).

### O Zen do Python, por Tim Peters

  * Bonito é melhor que feio.
  * Explícito é melhor que implícito.
  * Simples é melhor que complexo.
  * Complexo é melhor que complicado.
  * Plano é melhor que aglomerado.
  * Legibilidade faz diferença.
  * Agora é melhor que nunca.