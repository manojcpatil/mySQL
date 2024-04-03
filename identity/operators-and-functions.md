# Operators and Functions

### **Like (Search Something)**

The `LIKE` operator in SQL is instrumental for searching patterns within textual data. It enables the use of wildcard characters to represent single or multiple characters. The underscore sign `_` signifies a single character, while the percent sign `%` represents zero, one, or multiple characters.

```sql
-- Search for customer last names starting with any single character, followed by 'r'
SELECT * FROM customer
WHERE customerlastname LIKE '_r%';
```

### **In (Search Something)**

The `IN` operator is employed to match values against a specified list. It allows for the search of multiple items simultaneously, providing a convenient way to filter results based on predefined criteria.

```sql
-- Retrieve records for customers with last names 'Brown', 'Michael', or 'Jim'
SELECT * FROM customer
WHERE customerlastname IN ('Brown', 'Michael', 'Jim');
```

### **> (Search Something)**

The `>` operator in SQL is used to retrieve records where a specified value is greater than the provided condition.

```sql
-- Retrieve records for customers with last names greater than 'Brown' or 'Cross'
SELECT * FROM customer
WHERE customerlastname > 'Brown' OR customerlastname > 'Cross';
```

### **<> (Not Equal)**

The `<>` operator, also known as the not equal operator, is employed to retrieve records where a specified value is not equal to the given condition.

```sql
-- Retrieve records for customers with last names not equal to 'Brown'
SELECT * FROM customer
WHERE customerlastname <> 'Brown';
```

### **IS NULL**

The `IS NULL` operator is used to check for null values within a column.

```sql
-- Retrieve records where customer last names are NULL
SELECT * FROM customer
WHERE customerlastname IS NULL;
```

### **IS NOT NULL**

Conversely, the `IS NOT NULL` operator is employed to retrieve records where a column is not null.

```sql
-- Retrieve records where customer last names are not NULL
SELECT * FROM customer
WHERE customerlastname IS NOT NULL;
```

### **Between**

The `BETWEEN` operator is used to filter results within a specified range, inclusive of the endpoints.

```sql
-- Retrieve sales with unit prices between 5 and 10 (excluding 5 and 10)
SELECT * FROM sale
WHERE saleunitprice BETWEEN 5 AND 10;
```

### **Count**

The `COUNT` function returns the number of rows in a table, optionally allowing for conditional filtering. The `AS` keyword is utilized for aliasing, temporarily assigning a name to a column or table.

```sql
-- Count the number of records for customers with first names starting with 'B'
SELECT COUNT(*) AS [Number of Records] FROM customer
WHERE customerfirstname LIKE 'B%';
```

### **Sum**

The `SUM` function calculates the total sum of a specified column.

```sql
-- Calculate the total quantity of sales and the number of orders for each employee
SELECT sale.employeeid, EmployeeFirstName, EmployeeLastName, COUNT(*) AS [Number of Orders], SUM(salequantity) AS [Total Quantity]
FROM sale, employee
WHERE sale.employeeid = employee.employeeid
GROUP BY sale.employeeid, EmployeeFirstName, EmployeeLastName;
```

### **Count Month**

The `MONTH` function extracts the month component from a date. This example demonstrates how to count the number of sales and calculate the total amount per month.

```sql
-- Count the number of sales and calculate the total amount for each month
SELECT MONTH(saledate) AS [Month], COUNT(*) AS [Number of Sales], SUM(salequantity * saleunitprice) AS [Total Amount]
FROM sale
GROUP BY MONTH(saledate);
```

### **Max**

The `MAX` function returns the maximum value from a specified column.

```sql
-- Retrieve the maximum salary from the EmployeeSalary table
SELECT MAX(Salary) FROM EmployeeSalary;
```

### **Min**

Conversely, the `MIN` function returns the minimum value from a specified column.

```sql
-- Retrieve the minimum salary from the EmployeeSalary table
SELECT MIN(Salary) FROM EmployeeSalary;
```

### **Average**

The `AVG` function calculates the average value of a specified column.

```sql
-- Calculate the average salary from the EmployeeSalary table
SELECT AVG(Salary) FROM EmployeeSalary;
```
