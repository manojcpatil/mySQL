# Ranking

<pre class="language-sql"><code class="lang-sql">-- Create a sample table EmployeeSalary
<strong>CREATE TABLE EmployeeSalary (
</strong>    EmployeeID INT primary key,
    EmployeeName VARCHAR(50),
    JobTitle VARCHAR(50),
    Salary DECIMAL(10, 2)
);
</code></pre>

This SQL statement creates a table named `EmployeeSalary` with columns for `EmployeeID`, `EmployeeName`, `JobTitle`, and `Salary`. `EmployeeID` is an integer identifier for each employee, `EmployeeName` stores the names of the employees (using Indian names in this case), `JobTitle` represents the job title of each employee, and `Salary` stores the salary information for each employee.

```sql
-- Insert sample data into the EmployeeSalary table
INSERT INTO EmployeeSalary (EmployeeID, EmployeeName, JobTitle, Salary) VALUES
(1, 'Amit Kumar', 'Manager', 50000),
(2, 'Priya Sharma', 'Manager', 65000),
(3, 'Rahul Gupta', 'Manager', 55000),
(4, 'Sneha Patel', 'Developer', 98000),
(5, 'Neha Singh', 'Developer', 95000),
(6, 'Ananya Mehta', 'Developer', 62000),
(7, 'Rajesh Verma', 'Analyst', 80000),
(8, 'Kunal Singh', 'Analyst', 88000),
(9, 'Divya Jain', 'Intern', 80000);
```

Here's the `EmployeeSalary` table:

<table><thead><tr><th width="142">EmployeeID</th><th width="155">EmployeeName</th><th width="113">JobTitle</th><th>Salary</th></tr></thead><tbody><tr><td>1</td><td>Amit Kumar</td><td>Manager</td><td>50000</td></tr><tr><td>2</td><td>Priya Sharma</td><td>Manager</td><td>65000</td></tr><tr><td>3</td><td>Rahul Gupta</td><td>Manager</td><td>55000</td></tr><tr><td>4</td><td>Sneha Patel</td><td>Developer</td><td>98000</td></tr><tr><td>5</td><td>Neha Singh</td><td>Developer</td><td>95000</td></tr><tr><td>6</td><td>Ananya Mehta</td><td>Developer</td><td>62000</td></tr><tr><td>7</td><td>Rajesh Verma</td><td>Analyst</td><td>80000</td></tr><tr><td>8</td><td>Kunal Singh</td><td>Analyst</td><td>88000</td></tr><tr><td>9</td><td>Divya Jain</td><td>Intern</td><td>80000</td></tr></tbody></table>

This table represents the `EmployeeID, EmployeeName, JobTitle`, and `Salary` for each employee provided in the data.

### Row\_Number()

This SQL statement inserts sample data into the `EmployeeSalary` table. Each row represents an employee with their respective `EmployeeID`, `EmployeeName`, `JobTitle`, and `Salary`.

```sql
-- ROW_NUMBER(): Assign a unique sequential number for each row
SELECT *,
       ROW_NUMBER() OVER(ORDER BY Salary DESC) AS SalaryRowNumber
FROM EmployeeSalary;
```

This query uses the `ROW_NUMBER()` window function to assign a unique sequential number to each row in the result set, ordered by `Salary` in descending order. The assigned sequential number is aliased as `SalaryRowNumber`.

### Rank()

```sql
-- RANK(): Specify rank for each row in the result set using PARTITION BY
-- Each subset gets rank as per Salary in descending order
SELECT *,
       RANK() OVER(PARTITION BY JobTitle ORDER BY Salary DESC) AS SalaryRankByJob
FROM EmployeeSalary;
```

This query utilizes the `RANK()` window function to assign a rank to each row in the result set based on `Salary`, within each partition defined by `JobTitle`. The rank is calculated in descending order of salary within each job title group and is aliased as `SalaryRankByJob`.

```sql
-- RANK(): Get same ranks for rows having similar values
SELECT *,
       RANK() OVER(ORDER BY Salary DESC) AS SalaryRank
FROM EmployeeSalary;
```

This query uses the `RANK()` window function without `PARTITION BY`, resulting in the same rank being assigned to rows with identical `Salary` values. The rank is determined based on the `Salary` column in descending order, and it is aliased as `SalaryRank`.

```sql
-- DENSE_RANK(): Assign ranks to rows, ensuring no gaps in ranking
SELECT *,
       DENSE_RANK() OVER(ORDER BY Salary DESC) AS DenseSalaryRank
FROM EmployeeSalary;
```

This query employs the `DENSE_RANK()` window function to assign ranks to rows based on `Salary` in descending order, ensuring there are no gaps in the ranking sequence. The rank is aliased as `DenseSalaryRank`.

### NTILE()

```sql
-- NTILE(): Divide the result set into specified number of groups and assign a rank accordingly
-- In this example, divide the employees into 3 groups based on their salary
SELECT *,
       NTILE(3) OVER(ORDER BY Salary DESC) AS SalaryRank
FROM EmployeeSalary;
```

Description:

* In this part of the code, a sample table named `EmployeeSalary` is created with columns for `EmployeeID`, `EmployeeName`, `JobTitle`, and `Salary`.
* Sample data is inserted into the `EmployeeSalary` table, representing various employees with different job titles and salaries.

```sql
-- NTILE() using PARTITION BY: Divide the employees within each job title into specified number of groups and assign a rank accordingly
-- In this example, divide the employees within each job title into 3 groups based on their salary
SELECT *,
       NTILE(3) OVER(PARTITION BY JobTitle ORDER BY Salary DESC) AS SalaryRank
FROM EmployeeSalary;
```

Description:

* This part of the code demonstrates the usage of NTILE() function with PARTITION BY clause.
* NTILE() function divides the employees within each job title into a specified number of groups (in this case, 3) based on their salary.
* The result set is partitioned by the `JobTitle` column, and within each partition, the employees are ranked based on their salary in descending order.
* The assigned rank for each group is provided in the `SalaryRank` column.

```sql
-- Partitioning with PARTITION BY clause
-- Apply RANK() function within each partition defined by JobTitle
SELECT *,
       RANK() OVER(PARTITION BY JobTitle ORDER BY Salary DESC) AS SalaryRankWithinJobTitle
FROM EmployeeSalary;
```

In this code:

* A table named `EmployeeSalary` is created with columns for `EmployeeID`, `EmployeeName`, `JobTitle`, and `Salary`.
* Sample data representing employees with different job titles and salaries is inserted into the `EmployeeSalary` table.
* The `RANK()` window function is applied with the `PARTITION BY` clause. This partitions the result set into separate groups based on the `JobTitle` column, and within each partition, the employees are ranked based on their salary in descending order.
* The result set includes the original columns from the `EmployeeSalary` table along with the calculated `SalaryRankWithinJobTitle` column, indicating the rank of each employee's salary within their respective job title group.
