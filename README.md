# SQL
## Q1) Write a SQL Query to create a  table with specific columns and constraints?
### Sol:
```
CREATE DATABASE employees;
SHOW TABLES;
SHOW DATABASES;
USE employees;
```
Now Create 5 table
```
CREATE TABLE EMPLOYEES(
EMP_ID int primary key not null auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
CREATE TABLE STUDENTS(
STUDENT_ID int primary key auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
CREATE TABLE STAFF(
STAFF_ID int primary key auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
CREATE TABLE FACULTY(
FACULTY_ID int primary key auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
CREATE TABLE PARENTS(
PARENTS_ID int primary key auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
CREATE TABLE GAMERS(
GAMERS_ID int primary key auto_increment ,
Name varchar(100),
Department varchar(50),
Designation varchar(100)
);
```
## Q2) Write a SQL Query to add a new column to an existing table?
### Sol:
```
ALTER TABLE EMPLOYEES ADD MobNo int unique;
ALTER TABLE STUDENTS ADD MobNo int unique;
ALTER TABLE STAFF ADD MobNo int unique;
ALTER TABLE FACULTY ADD MobNo int unique;
ALTER TABLE PARENTS ADD MobNo int unique;
ALTER TABLE GAMERS ADD MobNo int unique;
ALTER TABLE EMPLOYEES ADD Salary int ;
ALTER TABLE STUDENTS ADD Salary int ;
ALTER TABLE STAFF ADD Salary int ;
ALTER TABLE FACULTY ADD Salary int ;
ALTER TABLE PARENTS ADD Salary int ;
ALTER TABLE GAMERS ADD Salary int ;
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)
```
Now we can see that two new columns is added to all the tables Salary and MobNo.

## Q3) Write a SQL Query to change data type of an existing column in a table?
### Sol:
```
ALTER TABLE EMPLOYEES MODIFY MobNo varchar(10) unique;
```
Now Check Description of the database datatype of MobNo was changed from int to varchar(10)
```
desc employees;
```
### Output:
```
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | varchar(10)  | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)
```

## Q4) Write a SQL Query to remove a column from an existing table?
### Sol:
```
ALTER TABLE EMPLOYEES DROP COLUMN MobNo;
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
mysql> ALTER TABLE EMPLOYEES DROP COLUMN MobNo;
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc employees;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.01 sec)
```
## Q5) Write a SQL Query to add a unique constrain to a column in existing table?
### Sol:
```
ALTER TABLE EMPLOYEES ADD MobNo int;
ALTER TABLE EMPLOYEES MODIFY COLUMN MobNo int unique;
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
mysql> ALTER TABLE EMPLOYEES ADD MobNo int;
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> alter table employees modify MobNo int unique;
Query OK, 0 rows affected (0.01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc employees;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.01 sec)

```
## Q6) Write a SQL Query to create a foreign key relationship between two tables?
### Sol:
```
ALTER TABLE EMPLOYEES ADD FACULTY_ID INT;
ALTER TABLE EMPLOYEES ADD CONSTRAINT fk FOREIGN KEY (FACULTY_ID) REFERENCES FACULTY(FACULTY_ID);
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
| FACULTY_ID  | int          | YES  | MUL | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
7 rows in set (0.04 sec)
```
## Q7) Write a SQL Query to permanently delete a table and all its data?
#### Sol:
```
DROP TABLE GAMERS;
```
Now Check Description of the database
```
show tables;
```
### Output:
```
mysql> show tables;
+---------------------+
| Tables_in_employees |
+---------------------+
| EMPLOYEES           |
| FACULTY             |
| PARENTS             |
| STAFF               |
| STUDENTS            |
+---------------------+
5 rows in set (0.03 sec)
```
## Q8) Remove all rows from a table but retain its structure?
#### Sol:
```
 TRUNCATE TABLE employees;
```
Now Check Description of the database
```
desc employees;
Select * from employees;
```
### Output:
```
mysql> show tables;
+---------------------+
| Tables_in_employees |
+---------------------+
| EMPLOYEES           |
| FACULTY             |
| PARENTS             |
| STAFF               |
| STUDENTS            |
+---------------------+
5 rows in set (0.03 sec)

mysql> Select * from employees;
Empty set (0.00 sec)
```

## Q9) Create an index on a column for better query performance?
#### Sol:
```
create index EMP_ID_INDEXING on EMPLOYEES(EMP_ID, NAME);

```
### Output:
```
mysql> create index EMP_ID_INDEXING on EMPLOYEES(EMP_ID, NAME);
Query OK, 0 rows affected (0.13 sec)
Records: 0  Duplicates: 0  Warnings: 0
```
## Q10) Remove an index from a table?
#### Solution:
```
drop index EMP_ID_INDEXING on EMPLOYEES;
```
#### Output:
```
mysql> drop index EMP_ID_INDEXING on EMPLOYEES;
Query OK, 0 rows affected (0.12 sec)
Records: 0  Duplicates: 0  Warnings: 0
```
## Q11) Rename an existing table
#### Solution:
```
ALTER TABLE STAFF RENAME NON_TEACHING_STAFF;
```
#### Output:
```
mysql> ALTER TABLE STAFF RENAME NON_TEACHING_STAFF;
Query OK, 0 rows affected (0.03 sec)
```
## Q12)Assign a default value to a column
#### Solution:
```
 ALTER TABLE EMPLOYEES
    -> MODIFY Salary int 
    -> DEFAULT 0;
```
#### Output:
```
mysql> ALTER TABLE EMPLOYEES
    -> MODIFY Salary int 
    -> DEFAULT 0;
Query OK, 0 rows affected (0.11 sec)
Records: 0  Duplicates: 0  Warnings: 0
mysql> desc employees
    -> ;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | 0       |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
| FACULTY_ID  | int          | YES  | MUL | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
7 rows in set (0.04 sec)
```
## Q13) Remove a constraint from an existing table
#### Solution:
```
ALTER TABLE EMPLOYEES DROP INDEX MobNo;
```
#### Output:
```
mysql> ALTER TABLE EMPLOYEES DROP INDEX MobNo;
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc employees;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Salary      | int          | YES  |     | 0       |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  |     | NULL    |                |
| FACULTY_ID  | int          | YES  | MUL | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
7 rows in set (0.02 sec)
```
## Q14) Create a new schema in the database
#### Solution:
```
CREATE SCHEMA EMP_SCH;
```
#### Output:
```
mysql> CREATE SCHEMA EMP_SCH;
Query OK, 1 row affected (0.12 sec)
```

## Q15) Move a table from one schema to another
```
ALTER SCHEMA EMP_SCH TRANSFER EMPLOYEES;
```
#### Output:
```
mysql>ALTER SCHEMA EMP_SCH TRANSFER EMPLOYEES;
Query OK, 1 row affected (0.15 sec)
```


