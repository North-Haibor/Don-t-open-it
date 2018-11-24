sudo mysql -u root -p
[sudo] password for huwang: 
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.13 MySQL Community Server - GPL

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| hello_mysql        |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> use hello_mysql;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables;
+-----------------------+
| Tables_in_hello_mysql |
+-----------------------+
| GWC                   |
| collection            |
| countries             |
| departments           |
| dept                  |
| emp                   |
| employees             |
| job_history           |
| jobs                  |
| locations             |
| regions               |
| salgrade              |
| weixin                |
| year                  |
+-----------------------+
14 rows in set (0.00 sec)

mysql> create table movie(
​    -> id int not null auto_increment primary key,                          
​    -> name varchar(20) not null,                                           
​    -> time int not null,                                           
​    -> director varchar(20) not null,                                              

 -> score int not null);                                                   

  Query OK, 0 rows affected (0.12 sec)

mysql> insert into movie values(
​    -> 1,"Anonymous",20181124,"raoxiaozhi",9),
​    -> (2,"danaohulianwang",20181124,"ruiqi",9),
​    -> (3,"Bean_Bean_Agent",20181124,"dawei",8),
​    -> (4,"duye",20181124,"tangmu",9);
Query OK, 4 rows affected (0.04 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from movie;
+----+-----------------+----------+------------+-------+
| id | name            | time     | director   | score |
+----+-----------------+----------+------------+-------+
|  1 | Anonymous       | 20181124 | raoxiaozhi |     9 |
|  2 | danaohulianwang | 20181124 | ruiqi      |     9 |
|  3 | Bean_Bean_Agent | 20181124 | dawei      |     8 |
|  4 | duye            | 20181124 | tangmu     |     9 |
+----+-----------------+----------+------------+-------+
4 rows in set (0.00 sec)

mysql> select * from movie where name like "Ano%";
+----+-----------+----------+------------+-------+
| id | name      | time     | director   | score |
+----+-----------+----------+------------+-------+
|  1 | Anonymous | 20181124 | raoxiaozhi |     9 |
+----+-----------+----------+------------+-------+
1 row in set (0.00 sec)

mysql> select * from movie where director like "%aw%";
+----+-----------------+----------+----------+-------+
| id | name            | time     | director | score |
+----+-----------------+----------+----------+-------+
|  3 | Bean_Bean_Agent | 20181124 | dawei    |     8 |
+----+-----------------+----------+----------+-------+
1 row in set (0.00 sec)

mysql> select * from movie where time like "2018%";
+----+-----------------+----------+------------+-------+
| id | name            | time     | director   | score |
+----+-----------------+----------+------------+-------+
|  1 | Anonymous       | 20181124 | raoxiaozhi |     9 |
|  2 | danaohulianwang | 20181124 | ruiqi      |     9 |
|  3 | Bean_Bean_Agent | 20181124 | dawei      |     8 |
|  4 | duye            | 20181124 | tangmu     |     9 |
+----+-----------------+----------+------------+-------+
4 rows in set (0.00 sec)

mysql> select max(score) from movie;
+------------+
| max(score) |
+------------+
|          9 |
+------------+
1 row in set (0.01 sec)

mysql> select * from movie where movie.score in(select max(score) from movie);
+----+-----------------+----------+------------+-------+
| id | name            | time     | director   | score |
+----+-----------------+----------+------------+-------+
|  1 | Anonymous       | 20181124 | raoxiaozhi |     9 |
|  2 | danaohulianwang | 20181124 | ruiqi      |     9 |
|  4 | duye            | 20181124 | tangmu     |     9 |
+----+-----------------+----------+------------+-------+
3 rows in set (0.02 sec)