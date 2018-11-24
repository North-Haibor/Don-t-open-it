 sudo mysql -u root -p
[sudo] password for huwang: 
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
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
| movie                 |
| regions               |
| salgrade              |
| weixin                |
| year                  |
+-----------------------+
15 rows in set (0.01 sec)

mysql> create table MRZH(ID int auto_increment primary key not null);
Query OK, 0 rows affected (0.08 sec)

mysql> alter table MRZH add name varchar(10);
Query OK, 0 rows affected (0.12 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table MRZH add method varchar(20);
Query OK, 0 rows affected (0.12 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table MRZH add logindate int;
Query OK, 0 rows affected (0.13 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> insert into MRZH values
​    -> (1,"aa","app",1996),
​    -> (2,"bb","ipad",2003),
​    -> (3,"cc","pc",2006);
Query OK, 3 rows affected (0.02 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from MRZH;
+----+------+--------+-----------+
| ID | name | method | logindate |
+----+------+--------+-----------+
|  1 | aa   | app    |      1996 |
|  2 | bb   | ipad   |      2003 |
|  3 | cc   | pc     |      2006 |
+----+------+--------+-----------+
3 rows in set (0.00 sec)

mysql> select case                                                                 

 -> when abs(UNIX_TIMESTAMP(now()))>30 then "你去死吧"                          

 -> when abs(UNIX_TIMESTAMP(now()))>9 then "你特么的回不回来"
​    -> when abs(UNIX_TIMESTAMP(now()))>7 then "快回来小天才"
​    -> end from MRZH;
+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| case
when abs(UNIX_TIMESTAMP(now()))>30 then "你去死吧"
when abs(UNIX_TIMESTAMP(now()))>9 then "你特么的回不回来"
when abs(UNIX_TIMESTAMP(now()))>7 then "快回来小天才"
end                   |
+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 你去死吧                                                                                                                                                                                      |
| 你去死吧                                                                                                                                                                                      |
| 你去死吧                                                                                                                                                                                      |
+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
3 rows in set (0.00 sec)