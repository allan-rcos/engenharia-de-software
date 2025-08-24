# Construção de Estruturas de Dados

## Conversa Inicial

Nesta etapa, continuaremos o estudo sobre **SQL**, abordando **tipos de dados**, aplicações e comandos. Trataremos também das **restrições (constraints)** e **declaração de chaves**. O controle de colunas **autoincremento** e o desenvolvimento prático de um Banco de Dados com exemplos serão foco.

### Construção de Estruturas de Dados

  * **Objetivo:** Aprofundar o estudo sobre SQL, tipos de dados, restrições, chaves e alterações em estruturas de dados.
  * **Assuntos Abordados:** SQL Data Types, SQL na prática, SQL PK, FK e UK, SQL Constraints, Alterações e Auto Increment.

## SQL Data Types

Todo objeto de armazenamento de dados tem um tipo associado, como colunas, variáveis e parâmetros. A escolha correta do tipo é crucial para otimizar o custo de armazenamento.

O MySQL, SGBD em foco, oferece diversos tipos de dados para armazenamento eficiente.

### SQL Data Types

O MySQL será o SGBD utilizado.

As categorias de tipos de dados são: **Numéricos**, **Cadeia de caracteres** e **Valores temporais**.

### SQL Data Types

A definição de uma coluna inclui o tipo e o comprimento do dado. Para números, o comprimento define a precisão (total de dígitos) e a escala (casas decimais).

### SQL Data Types - Numéricos

  * **Inteiros:** bit, tinyint, smallint, int, mediumint e bigint.
  * **Ponto-flutuante:** float e double (casa decimal ilimitada).
  * **Ponto-fixo:** Decimal (comprimento definido).

### SQL Data Types - Cadeia de Caracteres

  * **Char vs. varchar:** Char preenche todo o espaço; varchar usa apenas o necessário mais um caractere. Varchar é ideal para campos frequentemente vazios, enquanto char é melhor para campos geralmente preenchidos. Nchar e nvarchar suportam UNICODE.

### SQL Data Types - Temporais

  * **Data:** date e year.
  * **Hora:** time.
  * **Data e hora:** datetime e timestamp.

## SQL na Prática

Comandos essenciais do SQL para MySQL, usando MySQL Workbench.

```sql
-- Mostra os Bancos de Dados do servidor
show databases;

-- Cria um Banco de Dados 
create database aula;

-- Conecta um Banco de Dados
use aula;

-- Mostra qual Banco de Dados está conectado
select database();

-- Mostra as tabelas do Banco de Dados
show tables;

-- Cria uma tabela simples, sem nenhuma restrição 
create table produto (
    descricao varchar(100),
    preco decimal(10,2)    
);

-- Mostra a estrutura da tabela
describe produto;

insert into produto (descricao, preco) values ('Smartphone XPTO G5', 1500.60);
insert into produto (descricao, preco) values ('Notebook i7 4g ram', 3500.00);

-- Consulta dados na tabela
select * from produto;
select * from produto order by descricao asc;

-- Exclui uma tabela
drop table produto;

-- Exclui um Banco de Dados
drop database aula;

-- Verifica se o Banco de Dados existe antes de criá-lo
create database if not exists aula;
```

## SQL PK, FK e UK

  * **Declaração de chaves:** primária (PK, incluindo compostas), estrangeira (FK) e Unique Key (UK) para garantir a integridade dos dados.

## SQL Constraints

Restrições para limitar e padronizar dados:

  * **NOT NULL:** Garante valor não nulo.
  * **DEFAULT:** Define valor padrão.
  * **UNIQUE:** Garante valores únicos.
  * **PRIMARY KEY:** Combina NOT NULL e UNIQUE, identificando linhas.
  * **FOREIGN KEY:** Garante integridade referencial entre tabelas.
  * **CHECK:** Garante que valores atendam a uma condição.

<!-- end list -->

```sql
create table aluno (
    id int,
    nome varchar(100) not null,
    genero char(01),
    nascimento date,
    estadoCivil char(01) check (estadoCivil in ('C', 'S', 'V', 'O')),
    salario decimal(10,2) unsigned default 0,
    email varchar(120) unique
);

insert into aluno values (1, 'Helena Magalhães', 'F', '2000-01-01', 'C', 12500.99, 'helena.magalhaes@email.com'),
                         (2, 'Nicolas Oliveira', 'M', '2002-12-10', 'S', 8500, 'nicolas.oliveira@email.com'),
                         (3, 'Ana Rosa Silva', 'F', '1996-12-31', 'S', 8500, 'ana.rosa@email.com'),
                         (4, 'Tales Heitor Souza', 'M', '2000-10-01', 'O', 7689, 'tales.heitor@email.com'),
                         (5, 'Bia Meireles', 'F', '2002-03-14', 'O', 9450, 'bia.meireles@email.com'),
                         (6, 'Pedro Filho', 'M', null, 'V', 6800, 'pedro.filho@email.com'),
                         (7, 'Helena Soares', 'F', '1994-08-10', 'S', 8600, 'helena.soares@email.com');

describe aluno;

-- Realiza filtros na consulta
select * from aluno where genero = 'F';

-- Filtra e ordena
select * from aluno where genero = 'F' order by nascimento;

-- Filtra valores nulos: Não usar o sinal de = (igual)
select * from aluno where nascimento = null order by nascimento;

-- Filtra valores nulos: Usar o "is" ou "is not" 
select * from aluno where nascimento is null order by nascimento;
select * from aluno where salario is not null order by nascimento;

-- Restrição de unique
insert into aluno values (8, 'Helena Magalhães Bandeira', 'F', '1995-10-01', 'S', 12400, 'helena.magalhaes@email.com');

-- Not null
insert into aluno values (8, null, 'F', '1995-10-01', 'S', 12400, 'testes@email.com');
-- ou
insert into aluno (id, genero, nascimento, estadoCivil, salario, email) values (10, 'M', '2000-12-10', 'C', 9000, 'nicolas@email.com');

-- Check
insert into aluno values (8, 'Wilquison', 'M', '1995-10-01', 'X', 12400, 'testes@email.com');

-- Default
insert into aluno (id, nome, genero, nascimento, estadoCivil, email) values (8, 'Wilquison', 'M', '1995-10-01', 'C', 'testes@email.com');

-- Unsigned
insert into aluno (id, nome, genero, nascimento, estadoCivil, salario, email) values (8, 'Wilquison', 'M', '1995-10-01', 'C', -9000, 'testes@email.com');
```

## Alterações e Auto Increment

  * **Alterando tabelas:** Adicionar, excluir, alterar ou renomear colunas; renomear tabelas.
  * **Auto Increment:** Gera números únicos automaticamente para novos registros, comum em chaves primárias.

<!-- end list -->

```sql
-- Alter: Add, change, modify, rename, drop
-- Adiciona uma nova coluna
alter table aluno add telefone char(10);
alter table aluno add ddd int(03) zerofill after telefone;

describe aluno;

-- Modifica o nome de uma coluna
alter table aluno change telefone celular char(10);

describe aluno;

select * from aluno;

-- Modifica o tamanho de uma coluna
alter table aluno modify celular char(12);

-- Elimina uma coluna de uma tabela
alter table aluno drop celular;

describe aluno;

-- Altera o nome de uma tabela
alter table aluno rename to alunos;

show tables;

-- Altera o nome de uma tabela
alter table alunos rename to aluno;
 
show tables;

-- Adiciona as restrições: Chave primária
alter table aluno add constraint pkAluno primary key(id);
 
-- Remove uma restrição
alter table aluno drop primary key;
-- drop constraint pkaluno;

alter table aluno modify column id int not null primary key auto_increment;
 
insert into aluno (nome, genero, nascimento, estadoCivil, salario, email, ddd) values ('Zanana', 'F', '1995-10-01', 'C', 9000, 'zanana@email.com', 10);

-- Mostra o zerofill
select * from aluno;

-- Define um novo valor para o auto incremento
alter table aluno auto_increment = 100;

-- Exclui uma tabela
drop table aluno;
```

## Conclusão da Aula

Nesta aula, revisamos o **modelo relacional** e a **normalização**, importantes para um modelo de dados eficiente e sem redundâncias. Concluímos nosso projeto de Banco de Dados, transformando o MER para o modelo lógico e depois para o físico. Iniciamos o estudo de **SQL** para criar e manipular dados e objetos no Banco de Dados.

Recomendamos revisar os conceitos, praticar com exemplos e refazer as etapas do projeto (**MER**, **modelo relacional**, **normalização** e **modelo físico**). Isso o preparará para o uso prático do SQL.