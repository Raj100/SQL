# SQL
## Q1) Write a SQL Query to create a  table with specific columns and constraints?
### Sol:
```
CREATE DATABASES employees;
SHOW TABLES;
SHOW DATABASES;
USE employees;
```
Now Create 5 table
```
CREATE TABLE EMPLOYEES(
EMP_ID int primary key auto_increment ,
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
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.01 sec)
```
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
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)
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
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)
```
## Q6) Write a SQL Query to create a foreign key relationship between two tables?
### Sol:
```
ALTER TABLE EMPLOYEES ADD FACULTY_ID;
ALTER TABLE EMPLOYEES ADD CONSTRAINT fk FOREIGN KEY (FACULTY_ID) REFERENCES FACULTY(FACULTY_ID);
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
mysql> desc faculty;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| FACULTY_ID  | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> desc employees;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
| FACULTY_ID  | int          | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)
```
## Q7) Write a SQL Query to permanently delete a ?
### Sol:
```
ALTER TABLE EMPLOYEES ADD FACULTY_ID;
ALTER TABLE EMPLOYEES ADD CONSTRAINT fk FOREIGN KEY (FACULTY_ID) REFERENCES FACULTY(FACULTY_ID);
```
Now Check Description of the database
```
desc employees;
```
### Output:
```
mysql> desc faculty;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| FACULTY_ID  | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> desc employees;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| EMP_ID      | int          | NO   | PRI | NULL    | auto_increment |
| Name        | varchar(100) | YES  |     | NULL    |                |
| Department  | varchar(50)  | YES  |     | NULL    |                |
| Designation | varchar(100) | YES  |     | NULL    |                |
| MobNo       | int          | YES  | UNI | NULL    |                |
| FACULTY_ID  | int          | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.00 sec)
```
