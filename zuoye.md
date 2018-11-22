sudo mysql -u root -p
[sudo] password for huwang: 
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.13 MySQL Community Server - GPL

Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show tables;
ERROR 1046 (3D000): No database selected
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
5 rows in set (0.60 sec)

mysql> use database hello_mysql;
ERROR 1049 (42000): Unknown database 'database'
mysql> use database hello_mysql charset=utf8;
ERROR 1049 (42000): Unknown database 'database'
mysql> use database hello_mysql;
ERROR 1049 (42000): Unknown database 'database'
mysql> use hello_mysql;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables;
+-----------------------+
| Tables_in_hello_mysql |
+-----------------------+
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
+-----------------------+
11 rows in set (0.01 sec)

mysql> create table GWC(
​    -> favorite vachar(40) not null,
​    -> DR int not null,
​    -> 12desire vachar(60) not null,
​    -> id int not null Primary Key unique);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'vachar(40) not null,
DR int not null,
12desire vachar(60) not null,
id int not n' at line 2
mysql> create table GWC(favorite vachar(40) not null, DR int not null, 12desire vachar(60) not null, id int not null Primary Key unique);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'vachar(40) not null, DR int not null, 12desire vachar(60) not null, id int not n' at line 1
mysql> create table GWC(
​    -> id int not null primary key auto_increment,
​    -> favorite char(40) not null,
​    -> DR char(40) not null,
​    -> 12desire char(40) not null);
Query OK, 0 rows affected (0.18 sec)

mysql> show tables;
+-----------------------+
| Tables_in_hello_mysql |
+-----------------------+
| GWC                   |
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
+-----------------------+
12 rows in set (0.01 sec)

mysql> insert into GWC values(
​    -> 1,"Windbreaker","Yas","money");
Query OK, 1 row affected (0.09 sec)

mysql> select * from GWC;
+----+-------------+-----+----------+
| id | favorite    | DR  | 12desire |
+----+-------------+-----+----------+
|  1 | Windbreaker | Yas | money    |
+----+-------------+-----+----------+
1 row in set (0.00 sec)

mysql> insert into GWC values
​    -> (2,"shirt","Yes","money"),
​    -> (3,"Martin boots","Yes","money"),
​    -> (4,"hanfu","Yes","money"),
​    -> (5,"everything","No","money");
Query OK, 4 rows affected (0.08 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from GWC;
+----+-------------+-----+----------+
| id | favorite    | DR  | 12desire |
+----+-------------+-----+----------+
|  1 | Windbreaker | Yas | money    |
+----+-------------+-----+----------+
1 row in set (0.00 sec)

mysql> insert into GWC values
​    -> (2,"shirt","Yes","money"),
​    -> (3,"Martin boots","Yes","money"),
​    -> (4,"hanfu","Yes","money"),
​    -> (5,"everything","No","money");
Query OK, 4 rows affected (0.08 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from GWC;
+----+--------------+-----+----------+
| id | favorite     | DR  | 12desire |
+----+--------------+-----+----------+
|  1 | Windbreaker  | Yas | money    |
|  2 | shirt        | Yes | money    |
|  3 | Martin boots | Yes | money    |
|  4 | hanfu        | Yes | money    |
|  5 | everything   | No  | money    |
+----+--------------+-----+----------+
5 rows in set (0.00 sec)

update GWC set DR="No" where id=3;
Query OK, 1 row affected (0.07 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> update GWC set 
​    -> d;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 2
mysql> update GWC set DR="No" where id=3;
Query OK, 1 row affected (0.07 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> delete from GWC where id=5;
Query OK, 1 row affected (0.04 sec)

mysql> select * from GWC;
+----+--------------+-----+----------+
| id | favorite     | DR  | 12desire |
+----+--------------+-----+----------+
|  1 | Windbreaker  | Yas | money    |
|  2 | shirt        | Yes | money    |
|  3 | Martin boots | No  | money    |
|  4 | hanfu        | Yes | money    |
+----+--------------+-----+----------+
4 rows in set (0.01 sec)