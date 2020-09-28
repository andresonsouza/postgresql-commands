# Resumo de comandos postgreSQL

## Sobre o PostgreSQL

PostgreSQL é um poderoso sistema de banco de dados relacional de objeto de código aberto que usa e estende a linguagem SQL combinada com muitos recursos que armazenam e escalam com segurança as cargas de trabalho de dados mais complicadas.

O PostgreSQL ganhou uma forte reputação por sua arquitetura comprovada, confiabilidade, integridade de dados, conjunto de recursos robustos, extensibilidade e dedicação da comunidade de código aberto por trás do software para fornecer soluções inovadoras e de alto desempenho de maneira consistente.

Para maiores informações consultar a [documentação oficial](https://www.postgresql.org/docs/).

**verificar se o banco está ativo**

```sql=
SELECT NOW();
```

**criar um novo database**

```sql=
CREATE DATABASE database_name;
```

**listar os databases criados**

```sql=
 \l
```

**apagar database**

```sql=
DROP DATABASE database_name;
```

**criar uma tabela**
O exemplo abaixo cria uma tabela aluno com vários atributos:

```sql=
CREATE TABLE aluno (
   id SERIAL, 
   nome VARCHAR(255),
   cpf CHAR(11),
   observacao TEXT,
   idade INTEGER,
   dinheiro NUMERIC(10,2),
   altura real,
   ativo BOOLEAN,
   data_nascimento DATE,
   hora_aula TIME,
   matriculado_em timestamp
);
```
exemplo de uso:
* SERIAL - se incrementa automaticamente;
* VARCHAR(255) - possue um range de 0 até 255 caracteres;
* CHAR(11) - define um tamanho exato para o atributo;
* TEXT - simula o valor do tipo TEXT com um texto gigantesco e não sabemos o limite dele;
* INTEGER - um número inteiro, sem casas decimais;
* NUMERIC(10,2) - representa dez caracteres e duas casas decimais;
* real - número com casa decimais;
* BOOLEAN - diz se está ativo ou não, atribuindo true ou false;
* DATE - define a data de nascimento ou algo do tipo;
* TIME - simula um horário de acesso para um usuário;
* timestamp - hora consiste na concatenação de uma data e hora, seguida por um fuso horário opcional.

**faz um select trazendo os dados da tabela criada aluno**
```sql=
SELECT * FROM aluno;
```
**inserir dados na tabela criada**

O comando INSERT - cria novas linhas em uma tabela
Abaixo segue um exemplo de inserção onde são passados os campos e seus respectivos valores a serem inseridos

```sql=
INSERT INTO aluno (
	nome,
	cpf,
	observacao,
	idade,
	dinheiro,
	altura,
	ativo,
	data_nascimento,
	hora_aula,
	matriculado_em

) VALUES (
	'Calopsita',
	'11111111101',
	'Aenean ac metus et augue blandit vehicula. Phasellus erat nulla, maximus ac turpis sit amet, lobortis viverra est. Etiam efficitur mollis lectus non ullamcorper. Praesent nec lacinia tortor. Ut a elementum arcu. Integer ac enim tellus. In vel purus tortor. Duis non imperdiet lectus. Nam eros erat, cursus a dapibus pretium, consectetur a turpis. Curabitur vel efficitur felis, at condimentum nunc.',
	35,
	100.50,
	1.81,
	TRUE,
	'1985-12-04',
	'18:30:00',
	'2020-09-28 10:59:28'
)
```