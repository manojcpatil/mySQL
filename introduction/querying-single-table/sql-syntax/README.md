---
description: >-
  Explore essential SQL syntax for effective database management. From SELECT
  queries to table creation and manipulation, master the fundamentals with our
  concise guide.
---

# SQL Syntax

***

Structured Query Language (SQL) follows a defined set of rules and conventions known as syntax. This guide provides a comprehensive overview of fundamental SQL syntax elements:

**1. SQL Statements:** SQL statements begin with keywords such as SELECT, INSERT, UPDATE, DELETE, ALTER, DROP, CREATE, USE, and SHOW, and conclude with a semicolon (;).

**2. SQL SELECT Statement:** Retrieves data from a database table.

```
SELECT column1, column2, ..., columnN
FROM table_name;
```

**3. SQL DISTINCT Clause:** Filters out duplicate values from the result set.

```
SELECT DISTINCT column1, column2, ..., columnN
FROM table_name;
```

**4. SQL WHERE Clause:** Filters rows based on specified conditions.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE CONDITION;
```

**5. SQL AND/OR Clause:** Combines multiple conditions in a WHERE clause.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE CONDITION-1 {AND|OR} CONDITION-2;
```

**6. SQL IN Clause:** Filters rows based on a specified list of values.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE column_name IN (val-1, val-2, ..., val-N);
```

**7. SQL BETWEEN Clause:** Filters rows based on a range of values.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE column_name BETWEEN val-1 AND val-2;
```

**8. SQL LIKE Clause:** Filters rows based on a pattern.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE column_name LIKE { PATTERN };
```

**9. SQL ORDER BY Clause:** Sorts the result set in ascending or descending order.

```
SELECT column1, column2, ..., columnN
FROM table_name
WHERE CONDITION
ORDER BY column_name {ASC|DESC};
```

**10. SQL GROUP BY Clause:** Groups rows sharing a common value into summary rows.

```
SELECT SUM(column_name)
FROM table_name
WHERE CONDITION
GROUP BY column_name;
```

**11. SQL COUNT Clause:** Counts the number of rows in a table.

```
SELECT COUNT(column_name)
FROM table_name
WHERE CONDITION;
```

**12. SQL HAVING Clause:** Filters rows after the GROUP BY clause has been applied.

```
SELECT SUM(column_name)
FROM table_name
WHERE CONDITION
GROUP BY column_name
HAVING (arithmetical function condition);
```

**13. SQL CREATE TABLE Statement:** Creates a new table in the database.

```
CREATE TABLE table_name(
column1 datatype,
column2 datatype,
column3 datatype,
...,
columnN datatype,
PRIMARY KEY(one or more columns)
);
```

**14. SQL DROP TABLE Statement:** Deletes a table from the database.

```
DROP TABLE table_name;
```

**15. SQL CREATE INDEX Statement:** Creates an index on a table.

```
CREATE UNIQUE INDEX index_name
ON table_name(column1, column2, ..., columnN);
```

**16. SQL DROP INDEX Statement:** Deletes an index from a table.

```
ALTER TABLE table_name
DROP INDEX index_name;
```

**17. SQL DESC Statement:** Describes the structure of a table.

```
DESC table_name;
```

**18. SQL TRUNCATE TABLE Statement:** Deletes all rows from a table.

```
TRUNCATE TABLE table_name;
```

**19. SQL ALTER TABLE Statement:** Modifies a table structure.

```
ALTER TABLE table_name {ADD|DROP|MODIFY} column_name {data_type};
```

**20. SQL ALTER TABLE Statement (Rename):** Renames a table.

```
ALTER TABLE table_name RENAME TO new_table_name;
```

**21. SQL INSERT INTO Statement:** Inserts new rows into a table.

```
INSERT INTO table_name(column1, column2, ..., columnN)
VALUES(value1, value2, ..., valueN);
```

**22. SQL UPDATE Statement:** Modifies existing rows in a table.

```
UPDATE table_name
SET column1 = value1, column2 = value2, ..., columnN = valueN
[WHERE CONDITION];
```

**23. SQL DELETE Statement:** Deletes rows from a table based on specified conditions.

```
DELETE FROM table_name
WHERE {CONDITION};
```

**24. SQL CREATE DATABASE Statement:** Creates a new database.

```
CREATE DATABASE database_name;
```

**25. SQL DROP DATABASE Statement:** Deletes a database.

```
DROP DATABASE database_name;
```

**26. SQL USE Statement:** Specifies the database to be used for subsequent operations.

```
USE DATABASE database_name;
```

**27. SQL COMMIT Statement:** Saves the changes made in the current transaction.

```
COMMIT;
```

**28. SQL ROLLBACK Statement:** Reverts the changes made in the current transaction.

```
ROLLBACK;
```

***

## Code Example

```sql
-- Create a database named "employees_database"
CREATE DATABASE employees_database;

-- Use the "employees_database" database
USE employees_database;

-- Create the "employees" table
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    salary DECIMAL(10, 2),
    department VARCHAR(50)
);

-- Insert sample data into the "employees" table
INSERT INTO employees (id, name, salary, department)
VALUES 
    (101, 'John Doe', 60000, 'Finance'),
    (102, 'Jane Smith', 75000, 'Marketing'),
    (103, 'Mike Johnson', 55000, 'IT'),
    (104, 'Emily Brown', 65000, 'HR');

-- Create the "students" table
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);

-- Create the "products" table
CREATE TABLE products (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    price DECIMAL(10, 2)
);

-- Create the "customers" table
CREATE TABLE customers (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);
```

```
```

Now, assuming you have set up the required tables, let's proceed to execute the provided SQL commands:

```sql
-- Insert a new employee record into the "employees" table
INSERT INTO employees (id, name, salary)
VALUES (105, 'Alice Johnson', 62000);

-- Update the salary of employee with ID 101
UPDATE employees
SET salary = 65000
WHERE id = 101;

-- Delete the employee with ID 101 from the "employees" table
DELETE FROM employees
WHERE id = 101;

-- Create a unique index on the "email" column in the "users" table
-- Note: Assuming "users" table exists
CREATE UNIQUE INDEX idx_email ON users(email);

-- Calculate the total salary for each department
SELECT department, SUM(salary)
FROM employees
GROUP BY department;

-- Count the number of employees in the "sales" department
SELECT COUNT(*)
FROM employees
WHERE department = 'sales';

-- Retrieve employees sorted by salary in descending order
SELECT * FROM employees
ORDER BY salary DESC;

-- Retrieve students whose names start with "A"
SELECT * FROM students
WHERE name LIKE 'A%';

-- Retrieve products with prices between $10 and $20
SELECT * FROM products
WHERE price BETWEEN 10 AND 20;

-- Retrieve unique department names from the employees table
SELECT DISTINCT department FROM employees;

-- Remove all records from the "customers" table
TRUNCATE TABLE customers;

-- Drop the table "orders" from the database
DROP TABLE orders;

-- Add a new column "email" to the "customers" table
ALTER TABLE customers
ADD COLUMN email VARCHAR(100);

-- Rename the table "old_table" to "new_table"
ALTER TABLE old_table
RENAME TO new_table;

-- Describe the structure of the "products" table
DESC products;

```
