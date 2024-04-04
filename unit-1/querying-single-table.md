# Querying Single Table

MySQL is one of the most popular relational database management systems (RDBMS) used for storing and managing structured data. It is widely used in web development, data analysis, and various other applications due to its reliability, performance, and ease of use. In these study notes, we will explore the basics of MySQL, starting with querying single tables.

### **Querying Single Table:**

1.  **Fetch all columns from a table:** To retrieve all columns from a table, you can use the `SELECT * FROM table_name;` syntax. For example:

    ```sql
    SELECT * FROM country;
    ```
2.  **Fetch specific columns:** If you only need certain columns from a table, you can specify them in the `SELECT` statement. For example:

    ```sql
    SELECT id, name FROM city;
    ```
3.  **Sorting data:** You can sort the results of a query using the `ORDER BY` clause. By default, sorting is done in ascending order. For example:

    ```sql
    SELECT name FROM city ORDER BY rating;
    ```

    To sort in descending order, you can use the `DESC` keyword after the column name:

    ```sql
    SELECT name FROM city ORDER BY rating DESC;
    ```

These are some basic SQL queries for querying a single table in MySQL. Understanding these fundamentals is crucial for further exploration of relational databases and more complex queries involving multiple tables. Let's move on to exploring more advanced SQL concepts.

### Aliases

1.  **Using Aliases for Columns:**

    ```sql
    SELECT name AS city_name FROM city;
    ```

    Explanation: In this query, we're selecting the `name` column from the `city` table and using the `AS` keyword to alias it as `city_name`. Aliases provide a way to rename columns in the result set, making them more descriptive and easier to understand.
2.  **Using Aliases for Tables:**

    ```sql
    SELECT c.name AS city_name, co.name AS country_name
    FROM city AS c
    JOIN country AS co ON c.country_id = co.id;
    ```

    Explanation: Here, we're using aliases for tables (`c` for `city` and `co` for `country`) to simplify the query and make it more readable. The `AS` keyword is used to assign aliases to the tables. We then join the `city` table (`c`) with the `country` table (`co`) based on the `country_id` column in the `city` table and the `id` column in the `country` table. By using aliases, we can refer to the tables with shorter and more meaningful names throughout the query.

