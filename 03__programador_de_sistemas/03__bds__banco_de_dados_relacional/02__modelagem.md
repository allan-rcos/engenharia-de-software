# Modelagem de BDs

## Conversa Inicial

### Modelagem de Banco de Dados

#### Objetivos:

* Desenvolver o modelo lógico, aplicando a normalização.
* Gerar o modelo físico.
* Conhecer os modelos dimensionais.
* Introduzir os principais conceitos sobre o Structured Query Language (SQL).

#### Assuntos Abordados:

* Modelo lógico ou relacional.
* Normalização.
* Conversão para o modelo físico.
* Schemas.
* Structured Query Language (SQL).

Aqui, vamos abordar a **modelagem relacional**, também conhecida como **modelagem lógica**, convertendo o Modelo Entidade-Relacionamento (MER) para o modelo relacional e estudando os aspectos de refinamento no processo de **normalização** e conversão para o **modelo físico**. Vamos apresentar também outros modelos que podem ser aplicados em Bancos de Dados relacionais.

Daremos início ao estudo da linguagem **Structured Query Language (SQL)**, apresentando conceitos importantes para que você possa fortalecer o seu conhecimento teórico e aplicá-lo na prática. Também vamos dar prosseguimento ao nosso projeto de Bancos de Dados, que iniciamos na etapa anterior, desenvolvendo um passo a passo do modelo relacional e convertendo-o para o projeto físico.


## Modelo Lógico ou Relacional

* Baseado na teoria dos conjuntos (álgebra relacional).
* Dados são estruturados em tabelas (Sistema Gerenciador de Banco de Dados - SGBD específico).
* Refinado pelo processo de normalização.
* Base para a criação do modelo físico (banco de dados).

O **modelo relacional** é um modelo de dados adequado para um Sistema Gerenciador de Bancos de Dados (SGBD) específico, com base no princípio de que todos os dados estão armazenados em tabelas. Como já mencionado, o pesquisador Edgar Codd detectou que seria possível aplicar a teoria dos conjuntos (**álgebra relacional**) nas estruturas de dados, possibilitando a realização de operações de seleção, projeção, atribuição, entre outras. O modelo relacional foi aprimorado por Chris Date e Hugh Darwen como um modelo genérico.

### Elementos Básicos do Modelo Relacional

* **Entidade/Relação/Tabela:** Representa uma coleção de dados relacionados.
    * Exemplo: CLIENTE (com colunas como codigo, nome, nascimento, endereco).
* **Tupla/Linha/Registro:** Uma única entrada de dados em uma tabela.
    * Exemplo: 20001001 João da Silva 01/01/1986 Sete de setembro, 1000.
* **Atributo/Coluna/Campo:** Uma característica específica de uma entidade.
    * Exemplo: codigo, nome, nascimento, endereco.
* **Domínio:** O conjunto de valores permitidos para um atributo.
    * Exemplo: Para o atributo "nome", o domínio seria texto.
* **Grau:** O número de atributos em uma relação (tabela).
* **Cardinalidade:** O número de tuplas (linhas) em uma relação (tabela).
* **Chave Primária (PK - Primary Key):** Um atributo ou conjunto de atributos que identifica unicamente cada tupla em uma tabela.
* **Chave Estrangeira (FK - Foreign Key):** Um atributo ou conjunto de atributos em uma tabela que faz referência à chave primária de outra tabela, estabelecendo um relacionamento.

### Integridade

* **Integridade de Entidade:** Garante que toda chave primária seja única e não nula.
* **Integridade Referencial:** Garante que o valor de uma chave estrangeira seja nulo ou corresponda a um valor de chave primária existente na tabela referenciada.


## Normalização

* Um conjunto de regras para estruturar o esquema de um banco de dados relacional, eliminando anomalias de atualização, inserção e exclusão.
* Reduz a redundância de dados e melhora a integridade.

### Formas Normais

#### Primeira Forma Normal (1FN):

* Todos os atributos são atômicos (indivisíveis).
* Não há grupos de repetição.

#### Segunda Forma Normal (2FN):

* Já está na 1FN.
* Todos os atributos não-chave são funcionalmente dependentes da chave primária completa (não há dependências parciais).

#### Terceira Forma Normal (3FN):

* Já está na 2FN.
* Não possui dependências transitivas (atributos não-chave não dependem de outros atributos não-chave).

#### Forma Normal de Boyce-Codd (BCNF):

* Uma forma mais rigorosa da 3FN.
* Para cada dependência funcional X -> Y, X deve ser uma superchave.


## Conversão para o Modelo Físico

Representação da estrutura do banco de dados em um SGBD específico. Envolve a escolha de tipos de dados, índices, restrições e outros detalhes de implementação.

### Schemas

* **Schema Lógico:** Representação conceitual da estrutura do banco de dados, independente do SGBD.
* **Schema Físico:** Representação da estrutura do banco de dados como implementada em um SGBD específico.


## Structured Query Language (SQL)

* Responsável por toda e qualquer operação em um banco de dados.
* Por meio do SQL (criado pela IBM), diferentes aplicações acessam um banco de dados.
* Existem variações do SQL (dialetos) para diferentes SGBDs, como Oracle, Microsoft (Transact-SQL - T-SQL), MySQL (PL/SQL), IBM DB2 (SQL/PL), PostgreSQL (PL/pgSQL), Firebird (PSQL), entre outros.

### Atualizações (ao longo do tempo):

* Inclusão dos tipos booleanos (verdadeiro/falso).
* Savepoint para transações.
* Comando Merge.
* Campos autoincrementos.
* Suporte ao XML e extensões JSON.

### SQL Query/Script

* Linha ou bloco de instruções SQL que serão executados por um SGBD.

### Categorias do SQL

* **DQL (Data Query Language):** Comandos para consulta de dados (ex: SELECT).
* **DDL (Data Definition Language):** Comandos para definir a estrutura do banco de dados (ex: CREATE, ALTER, DROP, TRUNCATE).
* **DML (Data Manipulation Language):** Comandos para manipular dados (ex: INSERT, UPDATE, DELETE, MERGE).
* **DTL (Data Transaction Language):** Comandos para gerenciar transações (ex: COMMIT, ROLLBACK, SAVEPOINT).
* **DCL (Data Control Language):** Comandos para controle de acesso e permissões (ex: GRANT, REVOKE).

### Modelagem Dimensional (Conceitos Adicionais)

* Utilizada principalmente em Data Warehouses.
* **Fato:** Medida ou métrica numérica de um negócio.
* **Dimensão:** Contexto descritivo dos fatos.
* **Granularidade:** Nível de detalhe dos dados nos fatos e dimensões.

### Tipos de Modelos Dimensionais

#### Esquema Estrela (Star Schema):

* Uma tabela de fatos central conectada a várias tabelas de dimensão.
* Simples e otimizado para consultas.

#### Esquema Floco de Neve (Snowflake Schema):

* Extensão do esquema estrela, onde as tabelas de dimensão são normalizadas (divididas em subdimensões).
* Mais complexo, mas pode economizar espaço e reduzir redundância.

#### Esquema Constelação (Fact Constellation):

* Múltiplas tabelas de fatos que compartilham tabelas de dimensão.

## Conclusão da Aula

Nesta aula, aprofundamos os conceitos de banco de dados, passando do modelo conceitual para o **modelo lógico** e, em seguida, para o **modelo físico**. Compreendemos a importância da **normalização** para garantir a integridade e reduzir a redundância dos dados. Introduzimos os fundamentos do **SQL**, a linguagem essencial para interagir com bancos de dados, e exploramos os **modelos dimensionais**, cruciais para o desenvolvimento de Data Warehouses. A aplicação prática desses conceitos é fundamental para o desenvolvimento de sistemas robustos e eficientes.

Mais uma vez, propomos que você revise os assuntos tratados nesta etapa, pratique e crie os seus próprios exemplos de Bancos de Dados, refazendo todas as etapas do projeto (MER com cardinalidade, modelo relacional, sua normalização e, por fim, modelo físico). Assim, você estará preparado para outras discussões, durante as quais vamos trabalhar com SQL, compreendendo, na prática, os conceitos estudados até o momento.

Espero que ajude! Se precisar de mais alguma alteração ou tiver outra dúvida, é só me dizer.