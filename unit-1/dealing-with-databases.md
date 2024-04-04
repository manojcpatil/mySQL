# Dealing with Databases

## Creating a Database

The SQL `CREATE DATABASE` statement facilitates the creation of a new SQL database.

#### Syntax

The basic syntax for creating a database is as follows:

```sql
CREATE DATABASE DatabaseName;
```

* It is imperative to ensure that the chosen database name is unique within the RDBMS.

#### Example

To illustrate, consider the creation of a database named `testDB`:

```sql
CREATE DATABASE testDB;
```

* Prior to executing this command, ensure appropriate administrative privileges are granted.
* Upon successful creation, you can verify the presence of the new database by executing:

```sql
SHOW DATABASES;
```

### Deleting a Database

The SQL `DROP DATABASE` statement is utilized to remove an existing database from the SQL schema.

```sql
DROP DATABASE DatabaseName;
```

* Caution must be exercised before executing this operation as it results in the permanent loss of all data stored within the database.
* Administrative privileges are required to execute this command.

#### Example

Consider the scenario where we wish to delete the database named `testDB`:

```sql
DROP DATABASE testDB;
```

* Following the execution of this command, you can confirm the deletion by listing the databases:

```sql
SHOW DATABASES;
```
