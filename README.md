# mysql-cheat-sheet
Mysql basics and quick shortcuts

# Mysql cheat sheet


## How to login into mysql from terminal
```
mysql -u root -p
```
Log in using the command line.

## How to SHOW USER
```
SELECT user FROM mysql.user;
```

## How to CREATE USERS
```
CREATE USER 'newuser'@'localhost’ IDENTIFIED BY 'password';
```
## How to GRANT PRIVILEGES, Show granted privileges and remove.
```
GRANT ALL PRIVILEGES ON *.* TO ‘newuser'@'localhost';
```

## How to SHOW, DELETE & CREATE DATABASES & SELECT DATABASES
```
CREATE DATABASE database_name;
```
```
SHOW DATABASES;
```
```
use DBNAME;
```
```
DROP DATABASE dbname;
```
## How to CREATE a TABLE with Columns and their data types
```
 CREATE TABLE table_name (
   column_name1 data_type constraints,
   column_name2 data_type constraints,
   column_name3 data_type constraints
  );

```

## How to SHOW, DELETE & DROP Tables

```
SHOW TABLES;
```

```
DROP TABLE table_name;
```

## How to Insert ROWS & RECORDS (single and multiple)
```
INSERT INTO table_name (column1_name, column1_name) 
VALUES (‘value1’, ‘value2’);
```

## How to SELECT with the WHERE Clause
### Syntax:
```
SELECT * FROM table WHERE column > number;
```

### Examples: 
```
	SELECT * FROM employees WHERE name LIKE ‘Ana%’;
```

```
	SELECT * FROM employees WHERE id = 2;
```
	

## How to SELECT with the WHERE Clause using a range
### Syntax:
```
SELECT * FROM table_name WHERE column_name BETWEEN number AND number;
```
### Example: 
```
 SELECT * FROM table_name WHERE wage BETWEEN 2000 AND 3000;
```
## How to DELETE an individual ROW
### Syntax:
```
DELETE FROM table WHERE column_name = row_name;
```
### Example: 
```
DELETE FROM employees WHERE id = 4;
```

## How to UPDATE a ROW   

### Syntax:
```
UPDATE table_name SET 
    column_name = 'update'
WHERE
    column_name = 'constraint';
 ```
    
### Example: 
```
UPDATE employees SET 
    email = 'John@gmail.com'
WHERE
    employee_id = 3;
```

## How to add a new column and modify it
### Syntax:
```
ALTER TABLE  table_name CHANGE current_column_name new_column_name data_type;
```
### Example: 
```
ALTER TABLE  employees CHANGE worker_new new-workers VARCHAR(50) NOT NULL;
```



## How to Order by and use Distinct
```
SELECT DISTINCT length FROM table 
```
```
SELECT column FROM film ORDER BY length
```
## How to Concatenate Columns
```
SELECT CONCAT(Address, " ", PostalCode, " ", City) AS Address
FROM Customers;
```
## How to Select Distinct Rows
```
SELECT DISTINCT column-name  FROM table-name
```

## How to use LIKE to Search
```
SELECT customer_name
FROM customers
WHERE last_name LIKE 'Sm%';
```

## How Select using IN
### Syntax:
```
SELECT 
    columns
FROM
    Table
WHERE
    column IN (‘row’ , ‘row’);
```
### Example:
```
SELECT 
    officeCode, 
    city, 
    phone, 
    country
FROM
    offices
WHERE
    country IN ('USA' , 'France');
```

## How to Create & Remove Index
### Syntax:
```
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```
```
ALTER TABLE table_name
DROP INDEX index_name;
```

### Example:
```
CREATE INDEX idx_lastname
ON Persons (LastName);
```


## How to Create a New Table with Foreign Key (Posts)
```
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```
## How to use Inner Join
```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```
## How to JOIN Multiple Tables
```
select *
from student s, bridge b, course c
where b.id = s.id and b.id = c.id 
```
