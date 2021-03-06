# Ravature SQL - LABS

## Instructions: One-To-Many Relationships
* [x] Creat two tables supporting a one-to-many relationship.
* [x] Create tables to represent a link between Students and their Pets. We can set that up with two tables as such
* [x] Students Table

## One-To-Many Relationships
```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS students;
CREATE TABLE students(
	studentId INT AUTO_INCREMENT,
	studentFirstName VARCHAR(50),
	studentLastName VARCHAR(50),
	PRIMARY KEY(studentId)
); 

DROP TABLE IF EXISTS pets;
CREATE TABLE pets(
	petId INT NOT NULL,
	petName VARCHAR(50),
	petType VARCHAR(50),
	studentId INT,
	PRIMARY KEY(petId)
); 

INSERT INTO students (studentFirstName, studentLastName) 
values ('jack', 'stone'),
('brittany', 'jones'),
('Talia', 'morrison'),
('STEVEN', 'smith'),
('kourtney', 'klein');

INSERT INTO pets (petId, petName, petType, studentId) 
values (101, 'fluffy', 'hamster',1),
(102, 'fido', 'dog',2),
(103, 'spot', 'dog',2),
(104, 'princess', 'cat',3),
(105, 'goldie', 'dog',2),
(106, 'roy', 'fish',4),
(107, 'susie', 'cat',3);
```
---
## Instructions: Many-To-Many Relationships
* [x] Creating two tables that will support a many-to-many relationship.
* [x] Create tables to represent a link between Students and their Classes.

## Many-To-Many Relationships

```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS students;
CREATE TABLE students(
	studentId INT AUTO_INCREMENT,
	studentFirstName VARCHAR(50),
	studentLastName VARCHAR(50),
	PRIMARY KEY(studentId)
); 

DROP TABLE IF EXISTS classes;
CREATE TABLE classes(
	classId	INT,
	className VARCHAR(50),
	shortName VARCHAR(50),
	PRIMARY KEY(classId)
); 

INSERT INTO students (studentFirstName, studentLastName) 
values ('jack', 'stone'),
('brittany', 'jones'),
('Talia', 'morrison'),
('STEVEN', 'smith'),
('kourtney', 'klein');

INSERT INTO classes (classId, className, shortName) 
values (101, 'Chemistry 101', 'CHEM101'),
(102, 'Calculus 101', 'MATH101'),
(103, 'Biology 101', 'BIO101'),
(104, 'English 102', 'ENG102');

```
## Instructions: DDL - Data Definition Language
* [x] Create, alter and drop a table in a database.
* [x] Practice using DDL commands to manage data structures within our database..

## DDL - Data Definition Language

```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS Students;
CREATE TABLE Students(
  firstname varchar(30),
  lastname varchar(30),
  age integer
);

alter table Students add column middlename varchar(30);

drop table Students;
```
---
## Instructions: CRUD Methods
* [x] CRUD = Create-Read-Update-Delete
* [x] CRUD is for referring to Data Manipulation Language commands (SELECT, INSERT, UPDATE, AND DELETE).

* [x] Oractice using DDL and DML statements against a database.
* [x] Create a students table. 
* [x] Primary key (StudentID)
* [x] firstname (varchar; length 30) lastname (varchar; length 30) age (int)

## CRUD Methods
```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS students;
CREATE TABLE students(
	StudentID INT AUTO_INCREMENT,
	firstname VARCHAR(30),
	lastname VARCHAR(30),
	age int,
	PRIMARY KEY(StudentID)
); 

INSERT INTO students (firstname, lastname, age) 
values('Cindy', 'Davidson', 41);


SELECT * FROM students;
-- SELECT * FROM Revature_DB.students;

SELECT lastname, age FROM students;
-- UPDATE some_table SET email = 'newmail@gmail.com' WHERE id = 1;
UPDATE students SET age = 30 WHERE StudentID=1;

INSERT INTO students (firstname, age) 
values('Mandy', 32);
INSERT INTO students (firstname, age) 
values('Dandy', 22);
INSERT INTO students (firstname, age) 
values('Sandy', 24);

SELECT * FROM students;


INSERT INTO students (studentFirstName, studentLastName) 
values ('jack', 'stone'),
('brittany', 'jones'),
('Talia', 'morrison'),
('STEVEN', 'smith'),
('kourtney', 'klein');

INSERT INTO pets (petId, petName, petType, studentId) 
values (101, 'fluffy', 'hamster',1),
(102, 'fido', 'dog',2),
(103, 'spot', 'dog',2),
(104, 'princess', 'cat',3),
(105, 'goldie', 'dog',2),
(106, 'roy', 'fish',4),
(107, 'susie', 'cat',3);
```
---
## Instructions: WHERE Clauses
* [x] A WHERE is always used in conjunction with another command.
* [x] Practice using a WHERE clause with comparison operators to limit the records affected by a command.

## WHERE Clauses
```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

CREATE TABLE Students(
  firstname varchar(30),
  lastname varchar(30),
  age integer
);

INSERT INTO Students VALUES ('Mandy', 'Davidson', 32);
INSERT INTO Students VALUES ('Dandy', 'Davidson', 22);
INSERT INTO Students VALUES ('Sandy', 'Davidson', 24);

SELECT * FROM Students;
SELECT * FROM Students where age > 23;
SELECT * FROM Students;

UPDATE Students SET lastname = 'David' WHERE age = 32;
DELETE FROM Students WHERE firstname = 'Sandy';
SELECT * FROM Students;
```
---
## Instructions: GROUP BY vs. ORDER BY
* [x] GROUP BY: used to containerize results returned from an aggregate function.
* [x] ORDER BY: used to order results according to a column.
* [x] Explore how to use GROUP BY and ORDER BY

 - create a Cities table. It'll need columns with the following attributes:
 - id(int) PRIMARY KEY
 - name (varchar; length 30), NOT NULL
 - state varchar(20), NOT NULL
 - population integer

## GROUP BY vs. ORDER BY
```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS Students;
CREATE TABLE cities(
  id INTEGER PRIMARY KEY,
  name VARCHAR(30) NOT NULL,
  state VARCHAR(20),
  population INTEGER
);
insert into cities values (1, 'New York', 'New York', 8175133);
insert into cities values (2, 'Los Angeles', 'California', 3792621);
insert into cities values (3, 'Chicago', 'Illinois', 2695598);
insert into cities values (4, 'Houston', 'Texas', 2099451);
insert into cities values (5, 'Philadelphia', 'Pennsylvania', 1526006);
insert into cities values (6, 'Phoenix', 'Arizona', 1445632);
insert into cities values (7, 'San Antonio', 'Texas', 1327407);
insert into cities values (8, 'San Diego', 'California', 1307402);
insert into cities values (9, 'Dallas', 'Texas', 1197816);
insert into cities values (10, 'San Jose', 'California', 945942);

select * from cities;
/* Total cities by state */
-- select state, count(name)             from cities group by state;
 select state, count(population) as pop0 from cities group by state;

/* Total cities by state in order */
select state, count(population) as pop1 from cities group by state order by pop1;

/* Total cities by state in descending order */
select state, count(population) as pop2 from cities group by state order by pop2 desc;

/* Total population by state in descending order */
select state, sum(population) as pop3 from cities group by state order by pop3 desc;

/* ORDER BY */
select * from cities order by population;

/* ORDER BY */
select * from cities order by population desc;

```
---
## Instructions: Subqueries
* [x] Subquery: a query within a query. 
* [x] AKA: a nested query or inner query.
* [x] USE: SELECT column1, column2 from (select column1, column2 from table);
* [x] The subquery will execute first, store its results in a temporary table and then the outer query will execute its function against that temporary table.
* [x] The parenthesis is necessary to create the subquery.
 
 - Create a table (Cities)
 - Create a Cities table. 
 - Columns with the following attributes:
 - id(int) PRIMARY KEY
 - name (varchar; length 30), NOT NULL
 - state varchar(20), NOT NULL
 - population integer

## Subqueries
```sql
DROP DATABASE IF EXISTS `Revature_DB`;
CREATE DATABASE `Revature_DB`;
USE `Revature_DB`;

DROP TABLE IF EXISTS Students;
CREATE TABLE cities(
  id integer primary key,
  name varchar(30) not null,
  state varchar(20),
  population integer
);

insert into cities values (1, 'New York', 'New York', 8175133);
insert into cities values (2, 'Los Angeles', 'California', 3792621);
insert into cities values (3, 'Chicago', 'Illinois', 2695598);
insert into cities values (4, 'Houston', 'Texa', 2099451);
insert into cities values (5, 'Philadelphia', 'Pennsylvania', 1526006);
insert into cities values (6, 'Phoenix', 'Arizona', 1445632);
insert into cities values (7, 'San Antonio', 'Texas', 1327407);
insert into cities values (8, 'San Diego', 'California', 1307402);
insert into cities values (9, 'Dallas', 'Texas', 1197816);
insert into cities values (10, 'San Jose', 'California', 945942);

/* A subquery */
select * from cities WHERE population = (select min(population) from cities);

insert into cities values (11, 'San Jose Copy', 'California', 945942);

select  * FROM cities WHERE population = (select min(population) from cities);

/* A subquery within a subquery */
select * from cities WHERE id = (select min(id) from cities WHERE population = (select min(population) from cities));
```
