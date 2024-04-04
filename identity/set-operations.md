# Set Operations

{% hint style="info" %}
**Good to know:** Set operations in SQL are used to combine the results of two or more queries into a single result set. These operations are useful for manipulating and analyzing data from multiple sources or tables. It's important to note that the combined queries must return the same number of columns and compatible data types, although the names of the corresponding columns can be different.
{% endhint %}

## Before Studying set operations lets generate some tables

```sql
-- Create the database
CREATE DATABASE company_database;

-- Use the newly created database
USE company_database;

-- Create tables and insert data
CREATE TABLE hr_department (
    employee_name VARCHAR(50)
);

INSERT INTO hr_department (employee_name) VALUES
('Rahul Sharma'),
('Priya Patel'),
('Amit Singh'),
('Neha Gupta');

CREATE TABLE finance_department (
    employee_name VARCHAR(50)
);

INSERT INTO finance_department (employee_name) VALUES
('Ananya Desai'),
('Rajesh Shah'),
('Sneha Verma'),
('Kunal Mehta');

CREATE TABLE managers (
    employee_name VARCHAR(50)
);

INSERT INTO managers (employee_name) VALUES
('Rahul Sharma'),
('Ananya Desai'),
('Kunal Mehta');

CREATE TABLE team_leaders (
    employee_name VARCHAR(50)
);

INSERT INTO team_leaders (employee_name) VALUES
('Priya Patel'),
('Amit Singh');

CREATE TABLE all_employees (
    employee_name VARCHAR(50)
);

INSERT INTO all_employees (employee_name) VALUES
('Rahul Sharma'),
('Priya Patel'),
('Amit Singh'),
('Ananya Desai'),
('Rajesh Shah'),
('Sneha Verma'),
('Kunal Mehta');

CREATE TABLE sales_team (
    employee_name VARCHAR(50)
);

INSERT INTO sales_team (employee_name) VALUES
('Rajesh Shah'),
('Sneha Verma');

```

**UNION**

The UNION operator is used to combine the results of two queries and remove duplicate rows from the result set. It selects distinct values from both queries and returns a single result set containing those values.

_Example:_

```sql
-- Combine the names of employees from two departments
SELECT employee_name
FROM hr_department
UNION
SELECT employee_name
FROM finance_department;
```

Explanation: This query retrieves the names of employees from both HR and Finance departments, ensuring that each employee name appears only once in the combined result set.

**INTERSECT**

```sql
-- Find employees who are both managers and team leaders
SELECT employee_name
FROM managers
INTERSECT
SELECT employee_name
FROM team_leaders;
```

Explanation: This query retrieves the names of employees who hold both managerial and team leadership positions, showing only those who fulfill both roles.

**EXCEPT**

```sql
-- Identify employees who are not part of the sales team
SELECT employee_name
FROM all_employees
EXCEPT
SELECT employee_name
FROM sales_team;
```

Explanation: This query retrieves the names of employees who are not part of the sales team, showing only those who work in other departments or roles.
