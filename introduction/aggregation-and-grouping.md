# Aggregation and Grouping

{% hint style="info" %}
**Aggregation and Grouping:** GROUP BY groups together rows that have the same values in specified columns. It computes summaries (aggregates) for each unique combination of values.
{% endhint %}

{% tabs %}
{% tab title="Introduction" %}
**City Table:**

| id | name      | country\_id |
| -- | --------- | ----------- |
| 1  | Paris     | 101         |
| 2  | Marseille | 102         |
| 3  | Lyon      | 102         |
| 4  | Berlin    | 102         |
| 5  | Hamburg   | 103         |
| 6  | Munich    | 104         |
| 7  | Warsaw    | 104         |
| 8  | Cracow    | 104         |

**City Aggregate Table:**

| country\_id | count |
| ----------- | ----- |
| 101         | 1     |
| 102         | 3     |
| 103         | 1     |
| 104         | 3     |

**Aggregate Functions:**

* avg(expr): Average value for rows within the group.
* count(expr): Count of values for rows within the group.
* max(expr): Maximum value within the group.
* min(expr): Minimum value within the group.
* sum(expr): Sum of values within the group.

**Example Queries:**

1.  Find out the number of cities:

    ```sql
    SELECT COUNT(*) FROM city;
    ```

    Explanation: This query counts the total number of rows in the `city` table.
2.  Find out the number of cities with non-null ratings:

    ```sql
    SELECT COUNT(rating) FROM city;
    ```

    Explanation: This query counts the number of rows where the `rating` column is not null in the `city` table.
3.  Find out the number of distinctive country values:

    ```sql
    SELECT COUNT(DISTINCT country_id) FROM city;
    ```

    Explanation: This query counts the number of unique values in the `country_id` column of the `city` table.
4.  Find out the smallest and the greatest country populations:

    ```sql
    SELECT MIN(population), MAX(population) FROM country;
    ```

    Explanation: This query retrieves the smallest and largest values from the `population` column in the `country` table.
5.  Find out the total population of cities in respective countries:

    ```sql
    SELECT country_id, SUM(population) FROM city GROUP BY country_id;
    ```

    Explanation: This query calculates the total population of cities for each distinct `country_id` in the `city` table.
6.  Find out the average rating for cities in respective countries if the average is above 3.0:

    ```sql
    SELECT country_id, AVG(rating) FROM city
    GROUP BY country_id HAVING AVG(rating) > 3.0;
    ```

    Explanation: This query calculates the average rating for cities in each country and filters the results to include only those countries where the average rating is above 3.0, using the HAVING clause.
{% endtab %}
{% endtabs %}
