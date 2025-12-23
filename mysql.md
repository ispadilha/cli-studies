# Comandos de terminal MySQL

_Alguns comandos podem ser substituídos pelo uso de outras tecnologias de gestão de bancos de dados, como por exemplo Prisma. Mas é importante conhecer._

---

# Comandos "seguros" de servidor SQL

_Estes comandos não fazem alterações no banco de dados, e são bons para treino na linguagem._

---

## `DESCRIBE`
descreve a tabela especificada, suas colunas e seus campos  
tecnicamente, é um alias do MySQL para `SHOW COLUMNS FROM <table>;`

```DESCRIBE <table>;```

---

## `EXPLAIN`
explica o "plano de execução" de um comando `SELECT`, `UPDATE`, `DELETE` ou `INSERT` (menos comum)

```EXPLAIN SELECT * FROM users WHERE email = 'teste@email.com';```

---

## `SELECT`
“seleciona para visualização” as linhas da tabela  
opcionalmente, pode-se passar um número como limite  
se o limite for omitido, serão mostradas todas as linhas

```SELECT * FROM <table> LIMIT <number>;```  
```SELECT name, email FROM users WHERE active = 1 LIMIT 5;```

---

## `SHOW`
exibe informações sobre bancos de dados, tabelas, servidor, etc

### `SHOW DATABASES`
exibe todos os bancos de dados

### `SHOW TABLES`
exibe todas as tabelas contidas no banco de dados atualmente em uso

### `SHOW COLUMNS FROM <table>`
exibe as colunas da tabela especificada

### `SHOW CREATE TABLE <table>`
exibe como foi criada a tabela em comandos SQL  
mostra uma descrição semelhante ao comando acima e ao `DESCRIBE`, mas muito mais detalhada  
os comandos mostrados são parecidos com os vistos nos arquivos .sql gerados nas migrações do prisma

---

## `USE`

“seleciona para uso” o banco de dados especificado

---

# Comandos "não-seguros" de servidor SQL

_Estes comandos fazem alterações no banco de dados, e devem ser usados com cuidado._

---

## `ALTER TABLE`
modifica a estrutura de uma tabela  
permite adicionar ou remover colunas, por exemplo

```ALTER TABLE users ADD COLUMN age INT;```

---

## `COMMIT`
confirma uma transação  
só funciona em determinadas condições  
logicamente, tem que haver uma transação em curso  
o engine tem que ser InnoDB  
o autocommit tem que estar desligado

```START TRANSACTION;```  
```UPDATE users SET active = 0 WHERE last_login < '2023-01-01';```  
```COMMIT;```

---

## `CREATE`
cria banco de dados, tabela, index (estrutura de dados usada para acelerar buscas em uma tabela), view (uma consulta SQL salva, como se fosse uma "tabela virtual")

```CREATE DATABASE loja;```  
```CREATE TABLE users (id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(100), email VARCHAR(100));```  
```CREATE INDEX idx_users_email ON users(email);```  
```CREATE VIEW active_users AS SELECT name, email FROM users WHERE active = 1;```

---

## `DELETE`
deleta linhas ("entradas") de uma tabela  
tomar cuidado: caso "where" seja omitido, deleta todas as linhas

```DELETE from User WHERE id = 1;```  
```DELETE FROM users;```

---

## `DROP`
"derrubar"  
apaga todo um banco de dados ou uma tabela, com todo o conteúdo  
é necessário especificar o tipo

```DROP DATABASE loja;```  
```DROP TABLE users;```

---

## `INSERT`
insere novas linhas (ou "entradas") de dados em uma tabela

```INSERT INTO users (name, email) VALUES ('Ana', 'ana@email.com');```  
```INSERT INTO users VALUES (NULL, 'João', 'joao@email.com');```

---

## `ROLLBACK`
cancela uma transação em curso

```START TRANSACTION;```  
```DELETE FROM users;```  
```ROLLBACK;```

---

## `SET`
especifica variáveis de sessão ou modos SQL

```SET autocommit = 0;```  
```SET sql_safe_updates = 0;```

---

## `TRUNCATE`
apaga os dados de uma tabela, mas mantém sua estrutura  
é um alias do MySQL para `TRUNCATE TABLE`, que é a forma padrão e recomendada  
não é transacional, ou seja, não pode ser desfeito com `ROLLBACK`, portanto exige muito cuidado  
reseta `AUTO_INCREMENT`

---

## `UPDATE`
atualiza (modifica) os dados em uma tabela  
tomar cuidado: caso "where" seja omitido, atualiza todas as linhas  

```UPDATE users SET active = 1 WHERE id = 3;```  
```UPDATE users SET active = 0;```

---

# Comandos de cliente SQL
_Estes comandos, por serem interpretados diretamente pelo cliente, não são SQL e não precisam do delimitador (;)_

---

## `help`
exibe ajuda e outros comandos disponíveis

---

## `quit`
encerra e sai da sessão  
é igual a `exit`

---

## `status`
exibe informações sobre a conexão, usuário, banco de dados atual, etc