# Introdução

## Conversa Inicial

### Fundamentos de Banco de Dados

#### Objetivos:

* Apresentar os principais conceitos de banco de dados.
* Construir um projeto de banco de dados com o desenvolvimento do modelo conceitual.

#### Assuntos Abordados:

* Conceitos, definições e modelos.
* Sistema Gerenciador de Banco de Dados (SGBD) e aplicações de banco de dados.
* Modelagem de dados:
    * Modelo Entidade-Relacionamento (MER).
    * Cardinalidade.

### Conceitos, Definições e Modelos

#### A Importância da Informação nas Organizações

* Tomada de decisão.
* Informação deve ser precisa, ágil e instantânea.
* Dado x Informação.

#### Dado x Informação

A reunião de dados relacionados ao mesmo assunto transforma-se em informação.

* **Exemplo:** 2 + 5 (Dados) = 7 (Informação).

#### Banco de Dados

Sistema computadorizado de armazenamento de registros, cujo objetivo é armazenar informações e permitir ao usuário buscá-las e atualizá-las quando necessário.

* **Exemplos:**
    * Sistema de delivery.
    * Sistema acadêmico.

##### Modelos de Banco de Dados

É a forma como os bancos de dados são construídos conceitualmente.

###### Modelos:

* Modelo hierárquico.
* Modelo de rede.
* Modelo orientado a objetos.
* Modelo NoSQL (não relacional).
* Modelo relacional.

## Sistema Gerenciador de Banco de Dados (SGBD)

Um SGBD é a interface entre os dados de baixo nível, armazenados em um banco de dados, e os usuários e aplicações que desejam acessar e manipular esses dados.

### Objetivos:

* Abstração de dados.
* Independência de dados em relação às aplicações.
* **Exemplos:**
    * DB2, Microsoft SQL Server, Oracle, MySQL, PostgreSQL, entre outros.

### Sistema de Banco de Dados

#### Características de um SGBD

* Controle de redundância.
* Compartilhamento dos dados e concorrência.
* Controle de acesso.
* Controle de transações.
* Possibilidade de múltiplas interfaces.
* Restrições de integridade.
* Backup e recuperação de dados.
* Independência de dados.
* Eliminação de inconsistências.
* Padronização dos dados.

#### Pontos de Atenção em um SGBD

* Dispositivos de controle adequados.
* Integridade das informações.
* Levantamento de dados.
* Administração do banco de dados.

#### Administrador de Banco de Dados (DBA)

* Definição do banco de dados.
* Estrutura de armazenamento e definição de acesso aos dados.
* Esquema físico e organização dos dados.
* Controle de acesso dos usuários.
* Cuidar da integridade dos dados.
* Acompanhar o desempenho do banco de dados.
* Atividades de manutenção e backup.

## Modelagem de Dados

Consiste no levantamento e análise de dados sobre as informações e como se relacionam entre si, desenvolvendo um modelo que representa a realidade de um cenário.

* **Modelos básicos:** conceitual, lógico e físico.
* A análise, juntamente com os modelos, produz o projeto de banco de dados.

### Projeto de Banco de Dados

#### Modelo de Dados Conceitual

Esse modelo abrange:

* Visão geral do negócio (regras).
* Comunicação entre usuários e desenvolvedores.
* Definição das entidades e principais campos.
* Independente da implementação e do SGBD.
* Descrição mais abstrata do banco de dados.
* Aplicação da técnica do MER.

## Modelo Entidade-Relacionamento (MER)

Abstração de alto nível - visão do usuário.
É desenvolvido com base em três elementos:

* **Entidade:** objeto do mundo real.
* **Campo:** características particulares de cada objeto.
* **Relacionamento:** relação entre entidades.

### Entidade

Baseada na estrutura da chave primária e no grau de dependência.
Pode ser representada como:

* **Entidade fundamental:** presença de uma chave primária simples.
* **Entidade associativa:** baseia-se em relações n:n envolvendo várias entidades.
* **Entidade fraca:** depende de outra entidade para existir (dependência existencial).

### Instância de uma Entidade

Informações armazenadas nos campos de uma entidade.

* **Exemplo: PESSOA**
    * nome: Zanana Silva, Wilquison Souza
    * cpf: 123.456.789.00, 789.123.456.11
    * endereco: Rua das Flores, 999; Avenida 7 de setembro, 1

### Campo

Características de uma entidade.

#### Tipos de campos:

* Obrigatório.
* Opcional ou nulo.
* Simples ou atômico.
* Composto.
* Monovalorado.
* Multivalorado.
* Derivado.

#### Domínio:

possível valor definido para determinado campo.

* **Exemplo:** salário, valor numérico positivo com duas casas decimais.

### Chaves de um Campo

* Identificam cada instância separadamente em um banco de dados.
* Garantem o relacionamento entre as entidades.

#### Tipos:

* Chave primária (PK - Primary Key).
* Chave primária não natural.
* Chave estrangeira (FK - Foreign Key).

##### Chave Estrangeira (FK) - Exemplo

* A tabela CLIENTE possui as colunas: codigo, nome, nascimento, endereco e cidade. O campo "cidade" nesta tabela faz referência a outra tabela.
* A tabela CIDADE possui as colunas: codigo, descricao e UF.

##### Relacionamento ou Associação

Comunicação entre as entidades.

###### Tipos especiais:

* Recursivo ou autorrelacionamento.
* Especialização e generalização.

## Cardinalidade

* Determina a relação entre as entidades.
* Com base nas instâncias do objeto.

### Formas:

* Um para um (1:1).
* Um para muitos / muitos para um (1:n) / (n:1).
* Muitos para muitos (n:n) / (n:m).
* Máxima e mínima.

#### Cardinalidade Um para Um (1:1)

* Relacionamento exclusivo.
* Uma instância está associada a uma instância de outra entidade.

#### Cardinalidade (1:1) - Chave Estrangeira

* A entidade que recebe a chave estrangeira fica a critério do projetista.
* Existência opcional.

#### Cardinalidade Um para Muitos (1:n)

* Uma entidade associada a várias instâncias de outra entidade.
* O inverso não ocorre, em que uma entidade pode estar associada a uma instância.

#### Cardinalidade (1:n) - Chave Estrangeira

* A chave estrangeira é sempre declarada no lado da entidade que recebe muitos (n).

#### Cardinalidade Muitos para Muitos (n:n)

* Várias instâncias de uma entidade associada a várias instâncias de outra entidade.

#### Cardinalidade (n:n) - Chave Estrangeira

* Surgimento de uma nova entidade.
* Representação 1
* Representação 2

### Cardinalidade Mínima e Máxima

(0,n)

* **CARDINALIDADE MÁXIMA:** Representando uma associação obrigatória com, no mínimo 1 ou no máximo n (muitos).
* **CARDINALIDADE MÍNIMA:** Pode representar uma associação opcional (0) ou uma associação obrigatória (mínimo 1).