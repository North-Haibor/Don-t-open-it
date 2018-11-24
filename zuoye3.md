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
5 rows in set (0.13 sec)

mysql> use hello_mysql;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
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
| year                  |
+-----------------------+
13 rows in set (0.00 sec)

mysql> create table collection(
​    -> id int not null primary key auto_increment,
​    -> name varchar(60) not null,
​    -> Lncrease_collection varchar(80) not null,
​    -> Cancel_collection varchar(20) not null);
Query OK, 0 rows affected (0.35 sec)

mysql> select * from collection;
Empty set (0.01 sec)

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

mysql> insert into collection values
​    -> (1,"winderbreaker","Burberry","0"),
​    -> (2,"martin","Dr_Martens","0"),
​    -> (3,"shirt","Turnbull_Asser","0"),
​    -> (4,"watch","patek_phlllppe","1");                                        Query OK, 4 rows affected (0.04 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from collection;
+----+---------------+---------------------+-------------------+
| id | name          | Lncrease_collection | Cancel_collection |
+----+---------------+---------------------+-------------------+
|  1 | winderbreaker | Burberry            | 0                 |
|  2 | martin        | Dr_Martens          | 0                 |
|  3 | shirt         | Turnbull_Asser      | 0                 |
|  4 | watch         | patek_phlllppe      | 1                 |
+----+---------------+---------------------+-------------------+
4 rows in set (0.00 sec)

