# mysql
I learned how to create a database using `CREATE` and delete a database using `DROP`. Inside the database, you can create a table and insert column values into it. The syntax to create a table is:

```sql
USE db_name;
CREATE TABLE table_name (
    column_name_1 datatype constraint,
    column_name_2 datatype constraint
);
I learned how to create a database using `CREATE` and delete a database using `DROP`. Inside the database, you can create a table and insert column values into it. The syntax to create a table is:

```sql
USE db_name;
CREATE TABLE table_name (
    column_name_1 datatype constraint,
    column_name_2 datatype constraint
);
Create a table with a primary key:
CREATE TABLE temp1 (
    id INT,
    name VARCHAR(50),
    age INT,
    city VARCHAR(20),
    PRIMARY KEY (id, name)
);
Create a table with a foreign key:
CREATE TABLE temp (
    cust_id INT,
    FOREIGN KEY (cust_id) REFERENCES customer(id)
);
Default Value: By default, a column can store a fixed value if no input is given.
CREATE TABLE emp (
    id INT,
    salary INT DEFAULT 250000
);
INSERT INTO emp(id) VALUES (101);
SELECT * FROM emp;
CREATE TABLE emp (
    id INT,
    salary INT DEFAULT 250000
);
INSERT INTO emp(id) VALUES (101);
SELECT * FROM emp;
Create and insert values into a student table:
CREATE TABLE student (
    rollno INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    grade CHAR(2),
    salary DECIMAL(10, 2)
);

INSERT INTO student (rollno, name, age, grade, salary)
VALUES 
    (1, 'John Doe', 21, 'A+', 1500.00),
    (2, 'Jane Smith', 22, 'B', 1200.50),
    (3, 'Mike Brown', 20, 'A', 1800.75),
    (4, 'Emily Davis', 23, 'C+', 900.25),
    (5, 'Chris Evans', 19, 'B-', 1100.00);
Select students with a salary less than 1200.50:
SELECT rollno, name FROM student WHERE salary < 1200.50;
Output:4  Emily Davis
5  Chris Evans
Select top 2 students with a salary greater than 900.25:
SELECT * FROM student WHERE salary > 900.25 LIMIT 2;
1  John Doe     21  A+   1500.00
2  Jane Smith   22  B    1200.50
Order students by age in ascending order:
SELECT * FROM student ORDER BY age ASC;
o/p:
5  Chris Evans   19  B-   1100.00
3  Mike Brown    20  A    1800.75
1  John Doe      21  A+   1500.00
2  Jane Smith    22  B    1200.50
4  Emily Davis   23  C+   900.25
General Order of Commands:
SELECT column1, column2, ...
FROM table_name
WHERE condition
GROUP BY column
HAVING condition
ORDER BY column [ASC|DESC];
Safe Updates Mode:
SET SQL_SAFE_UPDATES = 0;
SET SQL_SAFE_UPDATES = 1;
update eg:
UPDATE student
SET grade = 'A'
WHERE grade = 'B';
SELECT * FROM student;
o/p:
1  John Doe     21  A+   1500.00
2  Jane Smith   22  A    1200.50
3  Mike Brown    20  A    1800.75
4  Emily Davis   23  C+   900.25
5  Chris Evans   19  B-   1100.00
delete eg:
DELETE FROM student WHERE age < 21;
SELECT * FROM student;
o/p:
1  John Doe     21  A+   1500.00
2  Jane Smith   22  A    1200.50
4  Emily Davis  23  C+   900.25
Additional Concepts:

ALTER: Changes table structure.
TRUNCATE: Removes all data from a table without logging each delete.
JOINS: Combines rows from multiple tables based on a condition.
