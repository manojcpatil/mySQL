# View

{% hint style="info" %}
**Good to know:** Storybook canvas embeds don't just work great for live components, you can also embed things like icons, or your color palette or typography tokens just as easily!
{% endhint %}

Certainly, here's the description with the accompanying SQL code:

### **View Specific Rows**

When working with large datasets, it's often essential to focus on specific rows to gain insights or perform targeted analyses. In SQL, the `SELECT` statement empowers us to extract such subsets efficiently. Utilizing the `TOP` keyword, we can precisely define the number or percentage of rows to retrieve.

* **Limited Rows with `TOP`:** To exhibit only a specified number of rows, the `TOP` keyword followed by a numerical value can be employed. For instance, `SELECT TOP 2 * FROM customer` will display solely the first two rows from the 'customer' table.

```sql
-- Show only the first two rows
SELECT TOP 2 * FROM customer;
```

* **Percentage Display with `TOP`:** Similarly, when the need arises to showcase a certain percentage of rows, SQL facilitates this with the `TOP` keyword alongside a percentage value. For instance, `SELECT TOP 40 PERCENT * FROM customer` retrieves the first two rows, comprising 40 percent of the dataset.

```sql
-- Show the first 40 percent of rows
SELECT TOP 40 PERCENT * FROM customer;
```

### **View Specific Columns**

Often, we seek to streamline data analysis by focusing solely on pertinent columns. SQL offers robust mechanisms to retrieve specific columns from a dataset while providing options to customize the presentation order.

* **Ordered Results with `ORDER BY`:** To tailor the display sequence of results, the `ORDER BY` clause is employed. By default, sorting occurs in ascending order, but specifying `DESC` (descending) reverses this order. For instance, `SELECT customerfirstname, customerlastname FROM customer ORDER BY customerlastname DESC` arranges results based on the 'customerlastname' column in descending order.

```sql
-- Sort results by customerlastname in descending order
SELECT customerfirstname, customerlastname FROM customer 
ORDER BY customerlastname DESC;
```

* **Order by Column Number:** SQL introduces a convenient feature where columns can be ordered without explicitly typing their names. Instead, columns can be referenced by their position using numeric values. For instance, `SELECT customerfirstname, customerlastname FROM customer ORDER BY 4, 2, 3 DESC` sorts the results based on the fourth, second, and third columns respectively, in descending order.

```sql
-- Sort results by column position (4th, 2nd, 3rd) in descending order
SELECT customerfirstname, customerlastname FROM customer 
ORDER BY 4, 2, 3 DESC;
```

* **Eliminating Duplicates with `DISTINCT`:** In scenarios where unique values are preferred, the `DISTINCT` keyword proves invaluable. By incorporating `DISTINCT`, the results are streamlined to showcase only distinct values within the specified column. For example, `SELECT DISTINCT customerlastname FROM customer ORDER BY customerlastname` ensures that only unique values of 'customerlastname' are displayed, facilitating a clearer perspective on the data.

```sql
-- Show only unique values of customerlastname
SELECT DISTINCT customerlastname FROM customer 
ORDER BY customerlastname;
```

### **Save Table to Another Table**

In SQL, it's often necessary to preserve a subset of data for further analysis or processing. One common approach is to save the results of a query into another table. This allows for a more structured and organized way of handling data. The `SELECT INTO` statement facilitates this task, enabling the creation of a new table based on the results of a query.

* **Saving Results with `SELECT INTO`:** To save the results of a query into a new table, the `SELECT INTO` statement is utilized. In this scenario, the `INTO` keyword is followed by the name of the target table, and the `SELECT` statement specifies the data to be copied. For instance, `SELECT DISTINCT customerlastname INTO temp FROM customer ORDER BY customerlastname` creates a new table named 'temp' containing distinct values from the 'customerlastname' column, ordered alphabetically.

```sql
-- Save distinct customer last names into a new table named 'temp'
SELECT DISTINCT customerlastname INTO temp FROM customer 
ORDER BY customerlastname;
```

* **Viewing the New Table:** Once the data has been saved into the new table, it can be accessed and inspected like any other table. For example, `SELECT * FROM temp` retrieves all records from the 'temp' table, allowing users to examine the data structure and content. It's important to note that the data types of the columns in the new table will remain consistent with the original data.

```sql
-- View the contents of the newly created table 'temp'
SELECT * FROM temp;
```

By employing the `SELECT INTO` statement, SQL users can efficiently transfer data from one table to another, facilitating streamlined data management and analysis processes.
