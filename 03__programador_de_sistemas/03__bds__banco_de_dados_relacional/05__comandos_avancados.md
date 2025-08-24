# Comandos Avançados

## Objetivos Principais:

  * Conhecer a utilização de **subconsultas**.
  * Realizar a adequação de dados por meio da **formatação**.
  * Discutir sobre o **controle e acesso de dados**.

### Preparando o Ambiente

```sql
-- Mod e div
select mod(4,2) as 'Resto divisão',
    mod(5,2) as 'Resto divisão', 
    4 div 2 as 'Quociente',
    5 div 2 as 'Quociente';

-- Round, truncate, mod e div
select salario,
    round(salario),
    round(salario,2),
    round(salario, 1),
    truncate(salario, 0),
    truncate(salario, 1),
    truncate(salario, 2)
    from funcionario;
```

## Subqueries (Subconsultas):

  * São comandos **SELECT** aninhados dentro de outros comandos (**SELECT**, **INSERT**, **UPDATE** ou **DELETE**).
  * Podem estar, inclusive, dentro de outras subqueries, criando um encadeamento de comandos onde o resultado de uma subquery impacta nas demais em um efeito em cadeia (de dentro para fora).
  * Em alguns casos, subconsultas podem ser substituídas por alternativas, como **JOIN**s, que são frequentemente mais performáticos, especialmente para grandes volumes de dados.
  * São úteis para resolver problemas complexos que seriam difíceis com uma única consulta.

<!-- end list -->

```sql
-- Mod e div
select mod(4,2) as 'Resto divisão',
    mod(5,2) as 'Resto divisão', 
    4 div 2 as 'Quociente',
    5 div 2 as 'Quociente';

-- Round, truncate, mod e div
select salario,
    round(salario),
    round(salario,2),
    round(salario, 1),
    truncate(salario, 0),
    truncate(salario, 1),
    truncate(salario, 2)
    from funcionario;
```

## Formatação de Dados:

  * **Textuais:** Funções para tratamento e manipulação de dados textuais armazenados. Envolvem operações de conversão, teste, localização, substituição, concatenação e remoção. Exemplos de funções mencionadas: `length()`, `upper()`, `lower()`, `ltrim()`, `rtrim()`, `trim()`, `substring()`, `replace()`, `cast()`.
  * **Numéricos:** Funções para arredondamento, truncamento e operações matemáticas com números. Exemplos: `round()`, `truncate()`, `mod()`, `div()`.
  * **Temporais (Datas e Horas):** Funções para manipulação de datas e horas, incluindo obtenção da data/hora atual, extração de partes de datas (ano, mês, dia), adição/subtração de tempo e formatação. Exemplos: `curdate()`, `curtime()`, `now()`, `date()`, `month()`, `monthname()`, `year()`, `day()`, `week()`, `weekday()`, `adddate()`, `datediff()`, `date_format()`, `timediff()`, `time()`, `addtime()`, `timestamp()`, `timestampadd()`, `time_format()`.

<!-- end list -->

```sql
-- Formatação de texto
select nome,
    upper(nome),
    lower(nome), 
    length(nome),
    ltrim(nome),
    rtrim(nome), 
    substring(nome, 5),
    substring(nome, 1, 3),
    dataNascimento,
    length(dataNascimento), 
    email,
    replace(email, '#', '@')
    from cliente;
```

## Agregação e Extração de Dados:

  * Funções de agregação que fornecem resumos, totalizadores e dados estatísticos.
  * Exemplos de funções: `count()`, `sum()`, `min()`, `max()`, `avg()`.
  * **GROUP BY:** Agrupa linhas que têm os mesmos valores em colunas especificadas em um conjunto de linhas de resumo.
  * **HAVING:** Filtra os resultados de funções de agregação, atuando de forma semelhante ao **WHERE**, mas sobre grupos.

<!-- end list -->

```sql
-- Funções de agregação
-- Count(*) e count null
select count(*),
    count(genero)
    from funcionario;

-- Conversão de valoes
select cast('2000-01-01' as date), 
    cast('1000.00' as decimal),
    cast('20:15' as time);

select curdate(),
    curtime(),
    now(), 
    date(curdate()),
    date(now());

-- Funções referentes ao dia
select curdate(), curtime(), now(), date(curdate()), date(now());
select curdate(), day(curdate()), dayname(curdate()), dayofweek(curdate()), dayofyear(curdate()), last_day(curdate());
select month(curdate()), monthname(curdate()), year(curdate());
select curdate(), now(), week(curdate()), weekday(now()), weekday(curdate());
select curdate(), adddate(curdate(), interval 31 day), adddate(curdate(), interval 1 month);
select curdate(), datediff('2022-01-01', curdate()), datediff(curdate(), '2022-01-01');
select curdate(), date_format(curdate(), '%w %m %y'), date_format('2022-01-01 20:15:00', '%h:%i:%s');

-- Funções de hora
select curtime(), time(curtime()), hour(curtime()), minute(curtime()), second(curtime()), microsecond(curtime());
select addtime('01:00:00.999999', '02:00:00.999998');
select timestamp('2003-12-31'), timestamp('2003-12-31 12:00:00', '12:00:00');
select curdate(), curtime(), timestampadd(minute, 30, curdate());
select timediff('2021-12-31 23:59:59.000001', '2021-12-31 01:01:01.000002');
select time_format('20:30:00', '%h %m');

-- Contando com filtro
select count(*) from funcionario
    where genero = 'M';

-- Sum salário
select sum(salario) from funcionario;

-- Min
select min(salario), min(nascimento) from funcionario;

-- Max
select max(salario), max(nascimento) from funcionario;

-- Média
select avg(salario) from funcionario;

-- Group by: Contando funcionários do departamento
select departamento, count(*) from funcionario 
group by departamento
order by departamento;

-- having
select departamento, count(*) from funcionario 
    group by departamento 
    having count(departamento) > 2;

-- Group by por gênero
select genero, avg(salario) from funcionario 
    group by genero;

-- Subconsultas
select nome, salario from funcionario
    where salario = (select max(salario) from funcionario);

select nome, cidadeId from cliente 
    where cidadeId = (select id from cidade where nomeCidade = 'Bagé');

-- Usando o in
select nome, cidadeId  from cliente 
    where cidadeId in (select id from cidade where nomeCidade = 'Curitiba' or nomeCidade = 'Imperatriz');

-- Não Curitiba e não Imperatriz
select nome, cidadeId  from cliente 
    where cidadeId not in (select id from cidade where nomeCidade = 'Curitiba' or nomeCidade = 'Imperatriz');

-- Exists
-- < 7000 > 11000
select nome, genero, salario from cliente 
    where salario < 7000
    and exists (select * from cliente where salario > 11000);

-- Any
-- id cliente > id cliente venda
select id, nome, genero from cliente 
    where id > any (select distinct clienteId from vendas);

-- All
select id, nome, genero from cliente
    where id > all (select distinct clienteId from vendas);

-- Subconsulta correlacionada
-- salario > any salario do mesmo gênero
select id, nome, genero, salario from cliente c
    where salario > any (select salario from cliente where genero = c.genero);
```

## Integridade e Segurança de Dados:

  * **Integridade dos Dados:** Assegurar a qualidade e a validade dos dados armazenados de forma lógica, utilizando regras e protocolos para garantir consistência e credibilidade. A implementação pode envolver integridade procedural (triggers, stored procedures).
  * **Segurança dos Dados:** Proteção dos dados (lógica e física) através de mecanismos de controle para prevenir o acesso não autorizado.
  * **Comandos de Controle de Dados (DCL):**
      * **GRANT:** Concede permissões a usuários sobre objetos do banco de dados (tabelas, visões, etc.).
      * **REVOKE:** Remove permissões concedidas anteriormente.
  * Outros mecanismos de segurança incluem *views*, *roles*, usuários e controle de acesso.

<!-- end list -->

```sql
-- Controle de acesso
-- Criando o usuário "aluno"
create user 'aluno'@'localhost' identified by '123';

-- Atualizando os privilégios
flush privileges;

-- Mostrando os usuários existentes
select user, host from mysql.user;

-- Mostrando os privilégios do usuário "aluno"
show grants for aluno@localhost;

revoke all, grant option from aluno@localhost;
flush privileges;
show grants for aluno@localhost;

-- Atribuindo algumas permissões
grant select, insert, delete on aula.* to aluno@localhost;
flush privileges;
show grants for aluno@localhost;
show grants for aluno;

-- Alterando os privilégios do usuário "aluno"
grant all privileges on *.* to aluno@localhost;
flush privileges;

-- Testando as permissões
use aula;
update funcionario set genero = 'M' where matricula = 7;
select * from funcionario where matricula = 7;

-- Retirando a permissão de update
revoke update on aula.* from aluno@localhost;
flush privileges;
show grants for aluno@localhost;

-- Tentando alterar a tabela "funcionario"
use aula;
update funcionario set genero = 'F' where matricula = 9;

-- Excluindo o usuário "aluno"
drop user aluno@localhost;
```

## Recomendações:

  * A prática constante, refazendo os exemplos e aplicando os conceitos em situações reais, é fundamental para assimilar o conteúdo.
  * A aplicação adequada dos recursos auxilia e facilita o trabalho do Administrador de Banco de Dados (**DBA**).

## Conclusão

Em resumo, os materiais fornecem uma visão aprofundada de comandos SQL mais complexos, capacitando o leitor a construir consultas mais eficientes, manipular e formatar dados de diversas naturezas, agregar informações e, crucialmente, entender e aplicar os princípios de integridade e segurança em um ambiente de Banco de Dados.

Espero que essa formatação ajude\! Se precisar de algo mais, me diga.