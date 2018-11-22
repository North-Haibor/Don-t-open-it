huwang@ubuntu:~ $ ls
Desktop    Downloads         Music     Public     Videos
Documents  examples.desktop  Pictures  Templates
huwang@ubuntu:~$ cd Desktop
huwang@ubuntu:~/Desktop$ pwd
/home/huwang/Desktop
huwang@ubuntu:~/Desktop$ 



source /home/huwang/Desktop/hr.sql;





huwang@ubuntu:~$ sudo mysql -u root -p
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
5 rows in set (0.01 sec)

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
+-----------------------+
12 rows in set (0.00 sec)

mysql> select * from emp;
+-------+--------+-----------+------+------------+------+---------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM    | DEPTNO |
+-------+--------+-----------+------+------------+------+---------+--------+
|  7369 | SMITH  | CLERK     | 7902 | 1980/12/17 |  800 |         | 20     |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981/2/20  | 1600 | 300.00  | 30     |
|  7521 | WARD   | SALESMAN  | 7698 | 1981/2/22  | 1250 | 500.00  | 30     |
|  7566 | JONES  | MANAGER   | 7839 | 1981/4/2   | 2975 |         | 20     |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981/9/28  | 1250 | 1400.00 | 30     |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981/5/1   | 2850 |         | 30     |
|  7782 | CLARK  | MANAGER   | 7839 | 1981/6/9   | 2450 |         | 10     |
|  7788 | SCOTT  | ANALYST   | 7566 | 1987/4/19  | 3000 |         | 20     |
|  7839 | KING   | PRESIDENT |      | 1981/11/17 | 5000 |         | 10     |
|  7844 | TURNER | SALESMAN  | 7698 | 1981/9/8   | 1500 | 0.00    | 30     |
|  7876 | ADAMS  | CLERK     | 7788 | 1987/5/23  | 1100 |         | 20     |
|  7900 | JAMES  | CLERK     | 7698 | 1981/12/3  |  950 |         | 30     |
|  7902 | FORD   | ANALYST   | 7566 | 1981/12/3  | 3000 |         | 20     |
|  7934 | MILLER | CLERK     | 7782 | 1982/1/23  | 1300 |         | 10     |
+-------+--------+-----------+------+------------+------+---------+--------+
14 rows in set (0.01 sec)

mysql> select * from dept;
+--------+------------+----------+
| DEPTNO | DNAME      | LOC      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | DALLAS   |
|     30 | SALES      | CHICAGO  |
|     40 | OPERATIONS | BOSTON   |
+--------+------------+----------+
4 rows in set (0.00 sec)

mysql> select distinct(sal) from emp;
+------+
| sal  |
+------+
|  800 |
| 1600 |
| 1250 |
| 2975 |
| 2850 |
| 2450 |
| 3000 |
| 5000 |
| 1500 |
| 1100 |
|  950 |
| 1300 |
+------+
12 rows in set (0.00 sec)

mysql> select * from emp order by sal desc;
+-------+--------+-----------+------+------------+------+---------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM    | DEPTNO |
+-------+--------+-----------+------+------------+------+---------+--------+
|  7839 | KING   | PRESIDENT |      | 1981/11/17 | 5000 |         | 10     |
|  7788 | SCOTT  | ANALYST   | 7566 | 1987/4/19  | 3000 |         | 20     |
|  7902 | FORD   | ANALYST   | 7566 | 1981/12/3  | 3000 |         | 20     |
|  7566 | JONES  | MANAGER   | 7839 | 1981/4/2   | 2975 |         | 20     |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981/5/1   | 2850 |         | 30     |
|  7782 | CLARK  | MANAGER   | 7839 | 1981/6/9   | 2450 |         | 10     |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981/2/20  | 1600 | 300.00  | 30     |
|  7844 | TURNER | SALESMAN  | 7698 | 1981/9/8   | 1500 | 0.00    | 30     |
|  7934 | MILLER | CLERK     | 7782 | 1982/1/23  | 1300 |         | 10     |
|  7521 | WARD   | SALESMAN  | 7698 | 1981/2/22  | 1250 | 500.00  | 30     |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981/9/28  | 1250 | 1400.00 | 30     |
|  7876 | ADAMS  | CLERK     | 7788 | 1987/5/23  | 1100 |         | 20     |
|  7900 | JAMES  | CLERK     | 7698 | 1981/12/3  |  950 |         | 30     |
|  7369 | SMITH  | CLERK     | 7902 | 1980/12/17 |  800 |         | 20     |
+-------+--------+-----------+------+------------+------+---------+--------+
14 rows in set (0.01 sec)



mysql> select distinct(sal) from emp order by sal desc limit 5;
+------+
| sal  |
+------+
| 5000 |
| 3000 |
| 2975 |
| 2850 |
| 2450 |
+------+
5 rows in set (0.01 sec)

mysql> select distinct(sal) from emp order by sal desc limit 5;
+------+
| sal  |
+------+
| 5000 |
| 3000 |
| 2975 |
| 2850 |
| 2450 |
+------+
5 rows in set (0.01 sec)

mysql> select sum(sal) from emp;
+----------+
| sum(sal) |
+----------+
|    29025 |
+----------+
1 row in set (0.01 sec)

mysql> select max(sal) from emp;
+----------+
| max(sal) |
+----------+
|     5000 |
+----------+
1 row in set (0.00 sec)

mysql> select max(sal),min(sal) from emp;
+----------+----------+
| max(sal) | min(sal) |
+----------+----------+
|     5000 |      800 |
+----------+----------+
1 row in set (0.01 sec)

mysql> select * from emp;
+-------+--------+-----------+------+------------+------+---------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM    | DEPTNO |
+-------+--------+-----------+------+------------+------+---------+--------+
|  7369 | SMITH  | CLERK     | 7902 | 1980/12/17 |  800 |         | 20     |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981/2/20  | 1600 | 300.00  | 30     |
|  7521 | WARD   | SALESMAN  | 7698 | 1981/2/22  | 1250 | 500.00  | 30     |
|  7566 | JONES  | MANAGER   | 7839 | 1981/4/2   | 2975 |         | 20     |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981/9/28  | 1250 | 1400.00 | 30     |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981/5/1   | 2850 |         | 30     |
|  7782 | CLARK  | MANAGER   | 7839 | 1981/6/9   | 2450 |         | 10     |
|  7788 | SCOTT  | ANALYST   | 7566 | 1987/4/19  | 3000 |         | 20     |
|  7839 | KING   | PRESIDENT |      | 1981/11/17 | 5000 |         | 10     |
|  7844 | TURNER | SALESMAN  | 7698 | 1981/9/8   | 1500 | 0.00    | 30     |
|  7876 | ADAMS  | CLERK     | 7788 | 1987/5/23  | 1100 |         | 20     |
|  7900 | JAMES  | CLERK     | 7698 | 1981/12/3  |  950 |         | 30     |
|  7902 | FORD   | ANALYST   | 7566 | 1981/12/3  | 3000 |         | 20     |
|  7934 | MILLER | CLERK     | 7782 | 1982/1/23  | 1300 |         | 10     |
+-------+--------+-----------+------+------------+------+---------+--------+
14 rows in set (0.01 sec)

mysql> select * from dept;
+--------+------------+----------+
| DEPTNO | DNAME      | LOC      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | DALLAS   |
|     30 | SALES      | CHICAGO  |
|     40 | OPERATIONS | BOSTON   |
+--------+------------+----------+
4 rows in set (0.00 sec)

mysql> select sal,dname from emp,dept where emp.deptno=dept.deptno;
+------+------------+
| sal  | dname      |
+------+------------+
|  800 | RESEARCH   |
| 1600 | SALES      |
| 1250 | SALES      |
| 2975 | RESEARCH   |
| 1250 | SALES      |
| 2850 | SALES      |
| 2450 | ACCOUNTING |
| 3000 | RESEARCH   |
| 5000 | ACCOUNTING |
| 1500 | SALES      |
| 1100 | RESEARCH   |
|  950 | SALES      |
| 3000 | RESEARCH   |
| 1300 | ACCOUNTING |
+------+------------+
14 rows in set (0.01 sec)

mysql> select emp.sal,emp.deptno,dept.deptno from emp,dept where emp.sal>1250 and emp.deptno=dept.deptno;
+------+--------+--------+
| sal  | deptno | deptno |
+------+--------+--------+
| 1600 | 30     |     30 |
| 2975 | 20     |     20 |
| 2850 | 30     |     30 |
| 2450 | 10     |     10 |
| 3000 | 20     |     20 |
| 5000 | 10     |     10 |
| 1500 | 30     |     30 |
| 3000 | 20     |     20 |
| 1300 | 10     |     10 |
+------+--------+--------+
9 rows in set (0.00 sec)



mysql> select * from emp where emp.empno not in(select min(empno) from emp group by sal having count(sal)>1);
+-------+--------+-----------+------+------------+------+---------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM    | DEPTNO |
+-------+--------+-----------+------+------------+------+---------+--------+
|  7369 | SMITH  | CLERK     | 7902 | 1980/12/17 |  800 |         | 20     |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981/2/20  | 1600 | 300.00  | 30     |
|  7566 | JONES  | MANAGER   | 7839 | 1981/4/2   | 2975 |         | 20     |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981/9/28  | 1250 | 1400.00 | 30     |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981/5/1   | 2850 |         | 30     |
|  7782 | CLARK  | MANAGER   | 7839 | 1981/6/9   | 2450 |         | 10     |
|  7839 | KING   | PRESIDENT |      | 1981/11/17 | 5000 |         | 10     |
|  7844 | TURNER | SALESMAN  | 7698 | 1981/9/8   | 1500 | 0.00    | 30     |
|  7876 | ADAMS  | CLERK     | 7788 | 1987/5/23  | 1100 |         | 20     |
|  7900 | JAMES  | CLERK     | 7698 | 1981/12/3  |  950 |         | 30     |
|  7902 | FORD   | ANALYST   | 7566 | 1981/12/3  | 3000 |         | 20     |
|  7934 | MILLER | CLERK     | 7782 | 1982/1/23  | 1300 |         | 10     |
+-------+--------+-----------+------+------------+------+---------+--------+
12 rows in set (0.00 sec)



