Basic SQL commands:

1. **CREATE DATABASE**: Create a new database.
```mysql
CREATE DATABASE IF NOT EXISTS my_database;
```
This command creates a new database named `my_database`. The `IF NOT EXISTS` clause prevents an error if the database already exists.

2. **CREATE TABLE**: Create a new table within a database.
```sql
CREATE TABLE IF NOT EXISTS students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    grade VARCHAR(2)
);
```
This command creates a table named `students` with columns `id`, `name`, `age`, and `grade`. The `PRIMARY KEY` constraint ensures that the `id` column is unique and auto-incremented.

3. **INSERT INTO**: Add new rows of data into a table.
```sql
INSERT INTO students (name, age, grade) VALUES
('John', 18, 'A'),
('Alice', 17, 'B'),
('Bob', 19, 'C');
```
This command inserts three new rows into the `students` table with values for the `name`, `age`, and `grade` columns.

4. **SELECT**: Retrieve data from a table.
```sql
SELECT * FROM students;
```
This command retrieves all columns (`*`) from the `students` table.

5. **UPDATE**: Modify existing data in a table.
```sql
UPDATE students SET age = 20 WHERE name = 'Bob';
```
This command updates the `age` column of the row where the `name` is 'Bob' to 20.

6. **DELETE**: Remove data from a table.
```sql
DELETE FROM students WHERE age > 18;
```
This command deletes rows from the `students` table where the `age` is greater than 18.

