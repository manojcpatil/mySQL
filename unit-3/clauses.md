# Clauses

{% hint style="info" %}
**Good to know:** you can embed a Storybook canvas by simple pasting the canvas link and hitting enter.
{% endhint %}

* Let's delve deeper into each query to understand its purpose and functionality:



### HAVING Clause

```sql
SELECT JobTitle, COUNT(JobTitle)  
FROM EmployeeDemographics ED 
JOIN EmployeeSalary ES ON ED.EmployeeID = ES.EmployeeID 
GROUP BY JobTitle 
HAVING COUNT(JobTitle) > 1;
```

Explanation:

* This query retrieves the count of employees for each job title from the tables `EmployeeDemographics` and `EmployeeSalary`.
* It utilizes a join operation to link employee data across both tables based on the `EmployeeID` column.
* The `GROUP BY` clause groups the results by job title, allowing for aggregation.
* The `HAVING` clause filters the results to only include job titles with a count greater than 1, indicating that there are multiple employees with the same job title.

```sql
SELECT JobTitle, AVG(Salary)  
FROM EmployeeDemographics ED 
JOIN EmployeeSalary ES ON ED.EmployeeID = ES.EmployeeID 
GROUP BY JobTitle 
HAVING AVG(Salary) > 45000 
ORDER BY AVG(Salary);
```

* Explanation:
  1. This query calculates the average salary for each job title from the tables `EmployeeDemographics` and `EmployeeSalary`.
  2. Similar to the previous query, it performs a join operation to combine employee data from both tables based on the `EmployeeID` column.
  3. The results are grouped by job title using the `GROUP BY` clause.
  4. The `HAVING` clause filters the results to only include job titles with an average salary greater than $45,000.
  5. The results are ordered by the average salary in ascending order.

### PARTITION BY Clause

```sql
SELECT FirstName, LastName, Gender, Salary, 
       COUNT(Gender) OVER (PARTITION BY Gender) AS TotalGender  
FROM EmployeeDemographics ED 
JOIN EmployeeSalary ES ON ED.EmployeeID = ES.EmployeeID;
```

Explanation:

1. This query retrieves employee data including first name, last name, gender, and salary from the tables `EmployeeDemographics` and `EmployeeSalary`.
2. It uses a join operation to combine employee data across both tables based on the `EmployeeID` column.
3. The `COUNT(Gender) OVER (PARTITION BY Gender)` is a window function that counts the occurrences of each gender within its partition.
4. The `PARTITION BY Gender` clause divides the result set into partitions based on the gender column.
5. For each row, the `TotalGender` column displays the total count of employees with the same gender.

These queries demonstrate the versatility of SQL in performing complex data analysis tasks, including aggregation, filtering, and partitioning.
