# Aula 5: Entendendo o Diagrama de Classes - Análise de Sistemas

### Conversa Inicial

* Projetar e construir um programa de computador envolve conhecer bem o problema que se quer resolver e traduzir a solução ideal em linhas de código.
* Entender bem os requisitos, ou o que o *software* precisa fazer para atender às necessidades do cliente, é a base de tudo.
* Se os requisitos não forem bem analisados e o *software* não for projetado de maneira adequada, fica mais difícil projetar uma solução que realmente resolva o problema do cliente.

### Diagrama de Classes

* Nesta aula, o foco é no diagrama de classes, muito importante para o projeto de *software*.
* Será compreendida sua estrutura e seu objetivo.

#### Organização da Aula (Grandes Temas)

1.  Entendendo o diagrama de classes.
2.  Classes, atributos e métodos.
3.  Relacionamentos.
4.  Técnicas de modelagem de diagrama de classes.
5.  Analisando um exemplo de diagrama de caso de uso.

### Entendendo o Diagrama de Classes

* Os diagramas de classes são fundamentais para o processo de modelagem de objetos e modelam a estrutura estática de um sistema.
* Dependendo da complexidade do sistema, é possível usar um único diagrama para modelar o sistema inteiro ou vários diagramas para modelar seus componentes.
* Ele modela quais classes estão relacionadas com o escopo do *software* e como elas se relacionam, mostrando como as informações se encaixam e se comunicam.

#### Orientação a Objetos

A modelagem das classes está totalmente relacionada com os conceitos de Orientação a Objetos:

* **Abstração:** Foco nos aspectos relevantes para um determinado propósito, abstraindo os elementos irrelevantes.
* **Encapsulamento:** Separação dos aspectos externos de um objeto (acessíveis) dos detalhes internos da implementação (ocultos).
* **Herança:** Compartilhamento de atributos e operações entre classes com base em um relacionamento hierárquico.

#### Exemplo de Diagrama de Classe (Estrutura Básica)

O diagrama exemplifica o relacionamento entre as classes **Turma**, **Aluno** e **Professor**:

* **Turma:**
    * *Atributos:* codigo:texto, sala:texto, horario:texto.
    * *Métodos:* incluirAluno (matricula), obterSala (codigo), definirProfessor (professor).
* **Aluno:**
    * *Relacionamento:* "Está matriculado em uma" Turma.
    * *Atributos:* nome:texto, matricula:inteiro.
    * *Métodos:* obterNome(), obterMatricula(), gerarMatricula().
* **Professor:**
    * *Relacionamento:* Turma "é conduzida por".
    * *Atributos:* nome:texto, titulação:texto.
    * *Métodos:* obterNome(), obterTitulação().

### Classes, Atributos e Métodos

#### Classe X Objeto

* **Classe:** É uma abstração de um conjunto de coisas que possuem características e operações em comum.
* **Objeto:** É uma instância da classe (exemplo: "José da Silva" é um objeto da classe ALUNO).
* **Instanciação:** Criar um novo objeto é criar uma nova instância da classe.

#### Atributos

* Representam o conjunto de características ou estados dos objetos de uma classe.
* Definem um intervalo de valores que as instâncias podem apresentar.
* Exemplo: Na classe ALUNO, os atributos são *nome* e *matrícula*.

#### Métodos (Operações)

* Representam o conjunto de operações ou comportamento que a classe fornece ou é responsável por executar.
* Exemplo: Na classe ALUNO, *consultar aluno* ou *alterar dados de aluno* são métodos.
* **Funcionamento do Método:** Pode ou não retornar um valor, pode ou não aceitar argumentos, e retorna o fluxo de controle após a execução.

#### Características dos Atributos e Métodos (Visibilidade)

* **`+` (público):** Visível em qualquer classe.
* **`#` (protegido):** Visível para classes do mesmo pacote.
* **`-` (privado):** Visível somente para a classe onde foi definido.

### Relacionamentos

* **Objetivo:** Garantir a comunicação e o compartilhamento de informações entre as classes, detalhando como ocorre a colaboração.
* **Características do relacionamento**:
    * **Nome:** Descrição dada ao relacionamento.
    * **Sentido de leitura:** Mostra a classe de origem e a de destino.
    * **Navegabilidade:** Indicada por uma seta no fim.
    * **Multiplicidade:** Indica como o relacionamento pode se verificar na classe (importante para regras de negócio).
    * **Tipo:** Representa o tipo do relacionamento modelado.
    * **Papéis:** Desempenhados pela classe no relacionamento.

#### Tipos de Relacionamentos

* **Associação:** Relacionamento estrutural que indica que objetos de uma classe estão vinculados a objetos de outra.
* **Generalização:** Utiliza o conceito de herança, permitindo que subclasses (*e.g.*, Terrestre, Aéreo) herdem características da superclasse (*e.g.*, Veículo). É lido como "é um" ou "é um tipo de".
* **Dependência:** Representa a dependência entre classes quando estas sofrem mudanças de estado, ajudando a entender o impacto de modificações.

### Técnicas de Modelagem de Diagrama de Classes

A modelagem é parte do processo de transformar as necessidades do cliente em um projeto objetivo.

#### Passos a Serem Seguidos

1.  Levantar os requisitos.
2.  Modelar o diagrama de caso de uso.
3.  Descrever os casos de uso.
4.  Identificar as classes.
5.  Identificar os atributos e métodos.
6.  Modelar o diagrama de classes.

### Estudo de Caso (Processo de Vendas Online de Livros)

O estudo de caso consiste em modelar o processo de vendas online de livros para uma livraria virtual.

* **Diferenciais da livraria:** Estoque próprio e aceita vários tipos de pagamento.
* **Programa de Fidelidade:** Oferece 10% de desconto aos clientes que comprarem R$ 500,00 ou mais em 1 ano.

#### Casos de Uso

* **UC01 - Utilizar programa de fidelidade:**
    * Chamado após o cliente selecionar produtos.
    * Mostra o valor de desconto aplicado no carrinho de compras, caso o cliente seja elegível (atingiu R$ 500,00 em compras no último ano), ou R$ 0,00 caso não seja.
* **UC02 - Atualizar programa de fidelidade:**
    * Caso de uso interno do sistema, sem interação com o usuário.
    * Objetivo: identificar se um cliente é elegível ao desconto por fidelidade na próxima compra.

#### Classes Identificadas

As classes principais identificadas são: **CLIENTE, FIDELIDADE, PEDIDO** e **PRODUTO DO PEDIDO**.

* **CLIENTE:**
    * Nome (texto)
    * CPF (inteiro)
    * Telefone (inteiro)
    * Endereço (texto)
* **FIDELIDADE:**
    * Status Fidelidade (boolean): diz se o cliente tem direito à fidelidade.
    * CPF (inteiro): para identificar o cliente.
* **PEDIDO:**
    * NÚMERO (inteiro): identifica o pedido.
    * CPF (inteiro): relaciona a qual cliente se refere.
    * DATA DO PEDIDO (data): dia, mês e ano da realização do pedido.
    * VALOR DO PEDIDO (real): valor total gasto no pedido.
* **PRODUTO DO PEDIDO:**
    * Criada para evitar repetir dados do cliente e do pedido em cada produto comprado.
    * NÚMERO (inteiro): identifica a qual pedido os produtos da classe estão relacionados.
    * PRODUTO (inteiro): identifica o produto adquirido no pedido.
    * QUANTIDADE PRODUTO (inteiro): quantidade do produto adquirida.
    * VALOR UNITÁRIO (real): valor unitário do produto.