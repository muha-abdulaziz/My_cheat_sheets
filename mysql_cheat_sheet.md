# Mysql/Mariadb cheat sheet

I write this cheat sheet thanks to Abdelrahman Ghareeb (@BooDy), Jeffrey Way () and Shady Samir (@shadysamir).

- Abdelrahman Ghareeb: almost all of this
- Shady Samir: character sets
- Jeffrey Way: DESCRIBE statement

## create database and give privileges to a new user

change db_name with your data-base name

```SQL
CREATE DATABASE db_name;
```

change **db_name** with your data-base name, **username** with the user name of this data-base
and **password** with the user's name password

```SQL
GRANT ALL PRIVILEGES ON db_name.* TO 'username'@'localhost' IDENTIFIED BY 'password';
```

execute the privileges;

```SQL
FLUSH PRIVILEGES;
```

## Character Sets

Defualt character set is "latin1".
If you want to sapport language like Arabic use **utf8**.
If you want to support **emojis** use **utf16**.
[More about Character encoding](https://en.wikipedia.org/wiki/Character_encoding), 
[More about Unicode](https://en.wikipedia.org/wiki/Unicode)

If you want to create a new database with a specific character set

```SQL
CREATE DATABASE czech_slovak_names 
  CHARACTER SET = 'charset_name'
  [COLLATE = 'collation_name'];
```

- charset_name (like utf8)
- COLLATE is optional

If you want to change the caracter set of a database write

```SQL
ALTER TABLE table_name
 CONVERT TO CHARACTER SET charset_name [COLLATE collation_name];
```

- charset_name (like utf8)
- COLLATE is optional

[For more see](https://mariadb.com/kb/en/library/setting-character-sets-and-collations/)

## common commands

show all data bases

```SQL
SHOW DATABASES;
```
move to a database to perform actions

```SQL
USE {database name};
```
show all the tables inside the database

```SQL
SHOW TABLES;
```
show the schema for a database

```SQL
DESCRIBE {table name};
```
