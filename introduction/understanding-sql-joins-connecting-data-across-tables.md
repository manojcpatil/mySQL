# Understanding SQL Joins: Connecting Data Across Tables

{% hint style="info" %}
**Joins** in SQL allow combining data from two or more tables based on related columns, enabling users to retrieve comprehensive datasets. They provide flexibility in data analysis by facilitating the extraction of relevant information from interconnected tables through various types of join operations.
{% endhint %}

Here are the SQL codes along with explanations for querying multiple tables using different types of joins:

1.  **Inner Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    INNER JOIN country ON city.country_id = country.id;
    ```

    Explanation: Inner join returns only the rows from both tables that have matching values in the specified column (`country_id` in this case). Rows from either table that do not have a match in the other table are excluded from the result set.
2.  **Full Outer Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    FULL OUTER JOIN country ON city.country_id = country.id;
    ```

    Explanation: Full outer join returns all rows from both tables, including rows that have no match in the other table. If there is no matching row in the other table, NULL values are returned.
3.  **Left Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    LEFT JOIN country ON city.country_id = country.id;
    ```

    Explanation: Left join returns all rows from the left table (`city`), along with matching rows from the right table (`country`). If there is no matching row in the right table, NULL values are returned for the columns of the right table.
4.  **Cross Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    CROSS JOIN country;
    ```

    Explanation: Cross join returns all possible combinations of rows from both tables. It does not require any specific condition to match rows between tables.
5.  **Right Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    RIGHT JOIN country ON city.country_id = country.id;
    ```

    Explanation: Right join returns all rows from the right table (`country`), along with matching rows from the left table (`city`). If there is no matching row in the left table, NULL values are returned for the columns of the left table.
6.  **Natural Join:**

    ```sql
    SELECT city.name, country.name 
    FROM city 
    NATURAL JOIN country;
    ```

    Explanation: Natural join automatically joins tables based on columns with the same name. It matches rows where the values in all columns with the same name are equal. However, it's rarely used in practice due to its potential for unexpected results.
