---
description: >-
  Filtering is a fundamental operation in SQL that allows you to retrieve
  specific subsets of data from a database based on specified conditions. It is
  used to narrow down the results of a query.
---

# Introduction to Filtering

### Key Points:

1. **WHERE Clause:** Filtering in SQL is typically done using the WHERE clause in a SELECT statement. The WHERE clause specifies the conditions that rows must meet to be included in the query results.
2. **Comparison Operators:** SQL provides a variety of comparison operators that can be used in the WHERE clause to specify conditions, such as:
   * Equals: `=`
   * Not equal to: `<>` or `!=`
   * Greater than: `>`
   * Less than: `<`
   * Greater than or equal to: `>=`
   * Less than or equal to: `<=`
3. **Logical Operators:** In addition to comparison operators, SQL also supports logical operators such as AND, OR, and NOT, which can be used to combine multiple conditions in a WHERE clause.
4. **Text Matching:** SQL offers the LIKE operator for pattern matching in text data. It allows you to search for patterns within strings using wildcard characters such as `%` (matches any sequence of characters) and `_` (matches any single character).
5. **Range Conditions:** You can use the BETWEEN operator to specify a range of values for filtering. It allows you to select rows with values within a specified range, inclusive of both endpoints.
6. **IN Operator:** The IN operator allows you to specify multiple values for filtering. It is useful when you want to filter rows based on a list of predefined values.

By using filtering in SQL, you can tailor your queries to retrieve only the data that is relevant to your specific requirements, making it a powerful tool for data analysis and manipulation.

1. **Using Comparison Operators:**
   *   Fetch names of cities that have a rating above 3:

       ```sql
       SELECT name FROM city WHERE rating > 3;
       ```

       Explanation: In this query, we're selecting the `name` column from the `city` table where the `rating` column is greater than 3. This retrieves the names of cities with a rating above 3.
   *   Fetch names of cities that are neither Berlin nor Madrid:

       ```sql
       SELECT name FROM city WHERE name NOT IN ('Berlin', 'Madrid');
       ```

       Explanation: Here, we're selecting the `name` column from the `city` table where the `name` is not 'Berlin' or 'Madrid'. This retrieves the names of cities that are neither Berlin nor Madrid.
2. **Using Text Operators:**
   *   Fetch names of cities that start with a 'P' or end with an 's':

       ```sql
       SELECT name FROM city WHERE name LIKE 'P%' OR name LIKE '%s';
       ```

       Explanation: This query uses the `LIKE` operator to match city names that start with 'P' (`'P%'`) or end with 's' (`'%s'`). The `%` wildcard matches any sequence of characters.
   *   Fetch names of cities that start with any letter followed by 'ublin':

       ```sql
       SELECT name FROM city WHERE name LIKE '_ublin';
       ```

       Explanation: Here, the `_` wildcard matches any single character. So, `'_ublin'` will match city names that start with any single character followed by 'ublin', such as 'Dublin' or 'Lublin'.
3. **Using Other Operators:**
   *   Fetch names of cities that have a population between 500K and 5M:

       ```sql
       SELECT name FROM city WHERE population BETWEEN 500000 AND 5000000;
       ```

       Explanation: This query selects the `name` column from the `city` table where the `population` column is between 500,000 and 5,000,000. The `BETWEEN` operator is used to specify a range.
   *   Fetch names of cities that don't miss a rating value:

       ```sql
       SELECT name FROM city WHERE rating IS NOT NULL;
       ```

       Explanation: Here, we're selecting the `name` column from the `city` table where the `rating` column is not NULL. This retrieves the names of cities where the rating value is present.
   *   Fetch names of cities that are in countries with IDs 1, 4, 7, or 8:

       ```sql
       SELECT name FROM city WHERE country_id IN (1, 4, 7, 8);
       ```

       Explanation: This query selects the `name` column from the `city` table where the `country_id` is in the list `(1, 4, 7, 8)`. It retrieves the names of cities that belong to countries with IDs 1, 4, 7, or 8.
