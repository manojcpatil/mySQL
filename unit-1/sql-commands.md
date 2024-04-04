# SQL commands

Let's elaborate on the SQL commands categorized into four categories: Data Definition Language (DDL), Data Manipulation Language (DML), Data Control Language (DCL), and Data Query Language (DQL), along with brief descriptions of their purposes.

## Data Definition Language (DDL):

DDL commands are used to define and manage the structure of database objects, such as tables, views, indexes, etc. They do not directly manipulate the data within the database but rather define its structure.

| Command | Description                                                                                                                                                                   |
| ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CREATE  | Creates a new table, view, index, or other database object. For example, `CREATE TABLE` is used to create a new table, and `CREATE VIEW` is used to create a view of a table. |
| ALTER   | Modifies an existing database object, such as adding, modifying, or dropping columns in a table, renaming tables, etc.                                                        |
| DROP    | Deletes an entire table, view, index, or other database object from the database. It permanently removes the object and its data.                                             |

## Data Manipulation Language (DML):

DML commands are used to manipulate the data within the database. They perform operations such as inserting, updating, deleting, and querying data in the database.

| Command | Description                                                                                                  |
| ------- | ------------------------------------------------------------------------------------------------------------ |
| INSERT  | Inserts new records into a table. It adds new rows to the table with specified values for each column.       |
| UPDATE  | Modifies existing records in a table. It allows changing the values of one or more columns in existing rows. |
| DELETE  | Deletes records from a table. It removes one or more rows from the table based on specified conditions.      |

## Data Control Language (DCL):

DCL commands are used to control access to the database. They grant or revoke privileges to users or roles, allowing or restricting their ability to perform certain actions within the database.

| Command | Description                                                                                                                                    |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| GRANT   | Grants specific privileges to users or roles. These privileges include the ability to perform DDL, DML, or DQL operations on database objects. |
| REVOKE  | Revokes previously granted privileges from users or roles. It removes specific privileges, restricting their access to database objects.       |

## Data Query Language (DQL):

DQL commands are used to retrieve data from the database. They perform queries on one or more tables and return the requested data based on specified conditions.

| Command | Description                                                                                                                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| SELECT  | Retrieves records from one or more tables. It allows querying data based on specified criteria and returning the result set meeting those criteria. |

These categories encompass the primary functions of SQL commands, each serving a distinct purpose in managing and interacting with databases.
