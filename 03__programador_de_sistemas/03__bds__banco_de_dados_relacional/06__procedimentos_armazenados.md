# Procedimentos Armazenados

## Objetivos Principais:

  * Conhecer as estruturas auxiliares (**índices** e **views**) e **transações**.
  * Implementar códigos por meio de **triggers**, **stored procedures**, **funções** e **cursores**.

### Preparando o Ambiente

```sql
/* Index e view, trigger, stored procedure, function e cursor */

use aulaPratica;

create table funcionario (
    matricula int not null,
    nome varchar(100),
    genero char(01),
    nascimento date,
    salario decimal(10,2),
    departamento int,
    cargo int,
    email varchar(120),
    cidadeId int not null,
    constraint pkFuncionario primary key (matricula)
);

create table auditoria (
    acao char(10),  -- Será inclusão, exclusão ou alteração
    matricula int,
    salarioAntigo decimal(10,2),
    salarioNovo decimal(10,2),
    dataOperacao date
);

insert into funcionario values (1, 'Ana Rosa Silva', 'F', '1996-12-31', 8500, 1, 1, 'ana.rosa@email.com', 1),
                               (2, 'Tales Heitor Souza', 'M', '2000-10-01', 7689, 1, 2, 'tales.heitor@email.com', 1),
                               (3, 'Bia Meireles', 'F', '2002-03-14', 9450, 1, 2, 'bia.meireles@email.com', 2),
                               (4, 'Pedro Filho', 'M', '1998-05-22', 12340, 3, 3, 'pedro.filho@email.com', 2),
                               (5, 'Camila Fialho', 'F', '1989-03-15', 10450, 2, 3, 'camila.fialho@email.com', 4),
                               (6, 'Ulisses Frota', 'M', '1997-06-30', 12340, 1, 4, 'ulisses.frota@email.com', 7),
                               (7, 'Leonardo Timbo', null, '2001-07-02', 7850, 2, 3, 'leonardo.timbo@email.com', 2),
                               (8, 'Lucas Goes', 'M', '2002-03-02', 8834, 3, 4, 'lucas.goes@email.com', 5),
                               (9, 'Sofia Lima', null, '1999-12-23', 9578, 4, 4, 'sofia.lima@email.com', 5);

-- Criando a tabela "pessoa" sem chaves
create table pessoa (
    nome varchar(50),
    email varchar(50) 
);

-- Inserindo dados na tabela "pessoa"
insert into pessoa values ('Anabel', 'anabel@email.com');
insert into pessoa values ('Luis Afonso', 'luisafonso@email.com');
insert into pessoa values ('Alais', 'alais@email.com');
insert into pessoa values ('João Pedro', 'joaopedro@email.com');
insert into pessoa values ('Marcos', 'marcos@email.com');
insert into pessoa values ('Ulisses', 'ulisses@email.com');
insert into pessoa values ('Amadeu', 'amadeu@email.com');
insert into pessoa values ('Vitoria', 'vitoria@email.com');
insert into pessoa values ('Claudio', 'claudio@email.com');
insert into pessoa values ('Marcela', 'marcela@email.com');
insert into pessoa values ('Julia', 'julia@email.com');
insert into pessoa values ('Roberval', 'roberval@email.com');
insert into pessoa values ('Raiza', 'raiza@email.com');
insert into pessoa values ('Olavo', 'olavo@email.com');
insert into pessoa values ('Murilo', 'murilo@email.com');
insert into pessoa values ('Helena', 'melena@email.com');
insert into pessoa values ('Vitoria', 'vitoria@email.com');
insert into pessoa values ('Pedro', 'pedro@email.com');
insert into pessoa values ('Gabriela', 'gabriela@email.com');
insert into pessoa values ('Marilia', 'marilia@email.com');
insert into pessoa values ('Kevin', 'kevin@email.com');
```

## Índice e Visão (Index e View):

  * **Índice (Index):** Estruturas que auxiliam na organização e consulta de uma tabela, otimizando o desempenho das consultas e reduzindo o uso de operações de I/O. O tipo de índice mais comum é a B-Tree (Balanced Tree), com subtipos Clustered e Non-Clustered.
      * **Tabela Heap:** Uma tabela sem índice, onde o SGBD realiza um "table scan" (varredura completa) para encontrar dados, o que pode ser ineficiente.

<!-- end list -->

```sql
-- Mostra que os dados ficam na ordem de inclusão
select * from pessoa;

-- Executa a consulta dos dados da "Vitoria"
select * from pessoa where nome = 'Vitoria';

-- Cria um índice para o nome da pessoa
create index idxPessoaNome on pessoa(nome);

-- Mostra os índices na tabela
show index from pessoa;

-- Plano de execução
explain select * from pessoa where nome = 'Vitoria';
```

  * **Visão (View):** Também conhecida como tabela virtual, retorna um conjunto de dados baseado em uma consulta predefinida. É útil para:
      * Restringir acesso a dados.
      * Simplificar consultas complexas.
      * Garantir a independência de dados.
      * Realizar alterações em tabelas que a compõem (com restrições).

<!-- end list -->

```sql
-- Cria uma view
create view mostraFuncionario 
as 
    select nome as 'Nome', 
    genero as 'Gênero',  
    nascimento as 'Nascimento', 
    email as 'E-mail' 
    from funcionario;

select * from mostraFuncionario order by Nome;
```

## Transações:

  * Conjunto de operações que devem ser executadas como um bloco único (ou tudo ou nada) dentro de um Banco de Dados.
  * Utilizam o conceito **ACID** para garantir a consistência e confiabilidade:
      * **Atomicidade:** Todas as operações são executadas ou nenhuma é.
      * **Consistência:** A transação leva o banco de dados de um estado consistente para outro.
      * **Isolamento:** Múltiplas transações podem ocorrer simultaneamente sem interferir umas nas outras.
      * **Durabilidade:** Uma vez que a transação é confirmada (**commit**), seus efeitos são permanentes.
  * **Comandos de Transação:**
      * **START TRANSACTION** (ou BEGIN, BEGIN WORK): Inicia a transação.
      * **COMMIT:** Confirma as alterações da transação.
      * **ROLLBACK:** Desfaz as alterações da transação.

<!-- end list -->

```sql
-- Exemplo de função
delimiter $$
create function reajuste(salario decimal(10,2), percentual decimal(5,2))
returns decimal(10,2) deterministic
begin
    declare valorReajuste decimal(10,2) default 0;
    set valorReajuste = (salario * percentual) / 100;
    return (valorReajuste);
end $$
delimiter ;

-- Exemplo de uso de função
select salario, reajuste(salario, 10) from funcionario;
```

## Trigger (Gatilho):

  * Código SQL que é executado automaticamente em resposta a um evento específico (inserção, atualização ou exclusão) em uma tabela.
  * Pode ser **BEFORE** (antes do evento) ou **AFTER** (depois do evento).
  * São úteis para aplicar regras de negócio, manter a integridade referencial ou auditar alterações.

<!-- end list -->

```sql
-- Trigger disparada na inclusão
delimiter $$
create trigger funcionarioInclusao after insert 
on funcionario
for each row
begin
    insert into auditoria values ('inclusão', new.matricula, null, new.salario, curdate());
end$$
delimiter ;

-- Mostra as triggers do Banco de Dados "aula"
show triggers from aula; 

-- Inclui um funcionário
insert into funcionario values (1, 'Ana Rosa Silva', 'F', '1996-12-31', 8500, 1, 1, 'ana.rosa@email.com', 1);

-- Mostra os dados das tabelas "auditoria" e "funcionario"
select * from auditoria;
select * from funcionario;
```

## Stored Procedure (Procedimento Armazenado):

  * Um conjunto de instruções SQL compiladas e armazenadas no Banco de Dados.
  * Pode receber parâmetros de entrada e executar instruções de seleção, controle, repetição, declaração de variáveis e funções.
  * Não retorna valores diretamente, mas pode realizar alterações em dados de tabelas.
  * Aumenta o desempenho, melhora a segurança e facilita a manutenção.

<!-- end list -->

```sql
-- Exemplo de procedure
delimiter $$
create procedure incluiFuncionario(
    pmatricula int,
    pnome varchar(100),
    pgenero char(01),
    pnascimento date,
    psalario decimal(10,2),
    pdepartamento int,
    pcargo int,
    pemail varchar(120),
    pcidadeId int
)
begin
    declare mensagem varchar(100);
    set mensagem = 'OK';
    if exists (select * from funcionario where matricula = pmatricula) then
        set mensagem = 'Matrícula já existe';
    end if;
    if psalario < 0 then
        set mensagem = mensagem + ', salário inválido';
    end if;
    if length(trim(pnome)) = 0 then
        set mensagem = mensagem + ', nome está vazio';
    end if;
    if mensagem = 'OK' then
        insert into funcionario values (pmatricula, pnome, pgenero, pnascimento, psalario, pdepartamento, pcargo, pemail, pcidadeId);
    end if;
end $$

call incluiFuncionario (9, 'Sofia Lima', null, '1999-12-23', 9578, 4, 4, 'sofia.lima@email.com', 5);

show function status where db = 'aula';

-- Tabela para armazenar a simulação do reajuste de salário
create table simulacao (
    nome varchar(100), 
    salario decimal(10,2), 
    novoSalario decimal(10,2)
);
```

## Function (Função Definida pelo Usuário - UDF):

  * Sintaticamente semelhante a uma stored procedure, mas sempre retorna um valor (ou valores de um tipo válido) ao final da execução.
  * Tipos de UDF (MySQL): Escalares (retornam um único valor) e Compostas (retornam um conjunto de valores).

## Cursor:

  * Permite o acesso ao resultado de uma consulta linha a linha, ao contrário dos comandos SELECT, INSERT e DELETE que acessam várias linhas de uma vez.
  * Geralmente é utilizado para leitura de forma sequencial e na ordem definida pelo SELECT.
  * Possui um ciclo de vida: DECLARE (declaração), OPEN (abertura), FETCH (busca de linhas), CLOSE (fechamento) e DEALLOCATE (liberação).

<!-- end list -->

```sql
-- Cursor 
delimiter $$
create procedure simulaReajuste()
begin
    declare done boolean default false;  -- Variável para identificar o final do cursor
    declare vnome varchar(100); 
    declare vsalario decimal(10,2);
    declare vnovoSalario decimal(10,2);
    declare vdepartamento int;

    declare cursorFuncionario cursor 
        for select nome, departamento, salario
        from funcionario;

    declare continue handler 
        for not found set done = true; 
    
    open cursorFuncionario;
    
    leCursor: loop
        fetch cursorFuncionario 
            into vnome, vdepartamento, vsalario;
        if done then  -- Testa se o cursor chegou ao final
        leave leCursor;  -- Sai do loop ao chegar no final
        end if;
        if vdepartamento = 1 then
        set vnovoSalario = vsalario + reajuste(vsalario, 10);
        elseif vdepartamento = 2 then
        set vnovoSalario = vsalario + reajuste(vsalario, 12);
        else
        set vnovoSalario = vsalario + reajuste(vsalario, 8);
        end if;
        insert into simulacao values (vnome, vsalario, vnovoSalario);
    end loop;
close cursorFuncionario;
end $$
delimiter ;

-- Executa a procedure
call simulaReajuste();

select * from simulacao;
select * from funcionario;
```

## Recomendações:

  * A prática constante, simulando situações do cotidiano e refazendo os exemplos, é crucial para assimilar os conhecimentos.
  * A aplicação adequada desses recursos auxilia e facilita o trabalho do Administrador de Banco de Dados (DBA) na execução de suas tarefas diárias.

## Conclusão

Em resumo, os materiais fornecem uma exploração aprofundada de ferramentas avançadas em Banco de Dados, desde a otimização de consultas com **índices** e **views**, o controle transacional com **ACID**, até a automação de tarefas e a lógica de negócios com **triggers**, **stored procedures**, **funções** e **cursores**, capacitando o leitor a criar e gerenciar sistemas de banco de dados mais robustos, eficientes e seguros.