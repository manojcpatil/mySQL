# SUBQUERIES

{% hint style="info" %}
**Good to know:** A subquery in SQL is a query nested inside another query, or inside another subquery. It allows for more complex and flexible querying of data by providing a way to perform operations on subsets of data within the main query.
{% endhint %}

**SINGLE VALUE**

A single-value subquery returns exactly one column and one row. It can be used with comparison operators such as =, <, <=, >, or >=. This type of subquery is typically used when you need to compare a single value against a result set.

_Example_:

```sql
SELECT name 
FROM city
WHERE rating = (
    SELECT rating
    FROM city
    WHERE name = 'Paris'
);
```

Explanation: This query finds cities with the same rating as Paris. The subquery retrieves the rating of Paris, and then the outer query selects cities with that rating.

**MULTIPLE VALUES**

A multiple-values subquery returns multiple columns or multiple rows. It is often used with operators like IN, EXISTS, ALL, or ANY to filter data based on conditions involving sets of values.

_Example_:

```sql
SELECT name
FROM city
WHERE country_id IN (
    SELECT country_id
    FROM country
    WHERE population > 20000000
);
```

Explanation: This query finds cities in countries with a population above 20 million. The subquery retrieves the country IDs of countries with a population above 20 million, and then the outer query selects cities in those countries.

**CORRELATED**

A correlated subquery refers to tables introduced in the outer query and depends on the outer query for its execution. It cannot be run independently from the outer query.

_Example_:

```sql
SELECT *
FROM city main_city
WHERE population > (
    SELECT AVG(population)
    FROM city average_city
    WHERE average_city.country_id = main_city.country_id
);
```

Explanation: This query finds cities with a population greater than the average population in their respective countries. The subquery calculates the average population for each country, and then the outer query selects cities with a population greater than this average.

_Another Example_:

```sql
SELECT name
FROM country
WHERE EXISTS (
    SELECT *
    FROM city
    WHERE country_id = country.id
);
```

Explanation: This query finds countries that have at least one city. The subquery checks if there exists any city with the same country ID as the country in the outer query, and then the outer query selects countries that satisfy this condition.
