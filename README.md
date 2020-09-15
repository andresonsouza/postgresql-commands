# Comandos postgreSQL

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
