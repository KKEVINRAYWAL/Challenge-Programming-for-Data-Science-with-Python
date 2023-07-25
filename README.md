## Bertelsmann Next Generation Tech Booster Challenge Program
| Week Number | Content |
|-------------|---------|
| 1           | Basic SQL |
| 2           | SQL Joins |
| 3           | SQL Aggregations |
| 4           | SQL Subqueries & Temporary Tables |
| 5           | SQL Data Cleaning |
| 6           | SQL Window Functions |
| 7           | SQL Advanced JOINS & Performance Tuning |
| 8           | Attempt the Final Assessment - Finish and Graduate |


![Bmann Challenge Completed](assets/Bmann_Challenge-Completed.png)

To load a .sql file into a local PostgreSQL database using the command line, you can use the psql command. The general syntax for this command is
```cmd  
psql -U [username] -d [database_name] -f [file_path]
```
 Here is an explanation of each part of the command:

psql: This is the command to run the PostgreSQL interactive terminal.
-U [username]: This specifies the username to connect to the database. Replace [username] with the username you want to use.

-d [database_name]: This specifies the name of the database you want to connect to. Replace [database_name] with the name of your database.

-f [file_path]: This specifies the path to the .sql file you want to load into the database. Replace [file_path] with the path to your .sql file.

For example, if your username is postgres, your database name is Udacitydb, and your .sql file is located at C:\Users\user\Downloads\UdacitySQL\Challenge-Programming-for-Data-Science-with-Python\assets, you can use the following command:

```cmd
psql -U postgres -d Udacitydb -f C:\Users\user\Downloads\UdacitySQL\Challenge-Programming-for-Data-Science-with-Python\assets

```
This command will load the .sql file into the specified database. 
when loading data into a PostgreSQL database using the psql command, you may be prompted to enter the password for the specified user. If you are using the -U [username] option to specify a username, you will be prompted to enter the password for that user.

If you want to avoid being prompted for a password, you can set the PGPASSWORD environment variable to the password for the specified user before running the psql command. For example, on Windows, you can use the following command to set the PGPASSWORD environment variable:
```cmd

set PGPASSWORD=[password]
```

Replace [password] with the password for the specified user. After setting the PGPASSWORD environment variable, you can run the psql command without being prompted for a password.

When loading data into a PostgreSQL database using the psql command, here are some additional things to keep in mind:


-Make sure that the PostgreSQL server is running and that you have the necessary permissions to connect to the database and execute the commands in the .sql file.
Ensure that the .sql file is properly formatted and contains valid SQL commands. Any errors in the file may cause the import to fail or produce unexpected results.


-If you are loading large amounts of data, it may take some time for the import to complete. Be patient and wait for the process to finish before attempting to access the data in the database.


-If you encounter any errors or issues during the import process, check the PostgreSQL documentation or seek help from online resources or forums.


































## SQL Notes


### Some Quick Vocabulary
- Structured Query Language (SQL) – Structured Query Language is a language that allows us to access information in a database. A typical query might look like this: 
```sql
SELECT account_id, standard_qty, gloss_qty 
FROM orders 
WHERE (standard_qty = 0 OR gloss_qty = 0) AND occurred_at = ‘2016-1-01’;
  ```
- NoSQL – NoSQL stands for Not Only SQL. NoSQL databases are a different type of database sometimes used to store web data. An example of a NoSQL database is MongoDB.
- Entity Relationship Diagram (ERD) – A diagrammatic representation of tables and their relationships to one another. Each box shows the name of the table and has two columns below. The first column shows whether a particular field listed to the right is a primary key (PK) or a Foreign Key (FK); the second shows a list of the attributes in the table. Each attribute has a corresponding column in the actual table. The key point here is that the ERD shows us relationships between tables. The “crows feet” arrows show us how the tables connect to one another by connecting primary keys to foreign keys. The three little prongs show that the foreign key can appear in many rows in a table. In other words, the foreign key is not unique in table.To further expand on the explanation, an Entity-Relationship Diagram (ERD) is a graphical representation of entities and their relationships to each other, and it's commonly used in database design. It shows the different entities in a database, their attributes or properties, and the relationships between them.

In an ERD, an entity is a thing or concept about which data is stored, such as a customer, order, or product. The attributes of an entity are the properties or characteristics that describe the entity, such as a customer's name, address, or email.
Relationships between entities show how they are related to each other. For example, a customer can place many orders, but an order can only be placed by one customer. This is represented by a one-to-many relationship between the customer entity and the order entity.
The ERD for a database typically shows all the tables in the database, the attributes of each table, and the relationships between the tables. This helps users understand the database structure and how the different tables are related to each other.

### Primary Key (PK)
– Every table has a primary key. The primary key is a unique value for each row. Now two rows can have the same primary key. The primary key is often the first column in a table.
- A column (or a set of columns) whose value exists and is unique for every record in a table is called a primary key.  It is a fundamental concept in database design and is used to enforce data integrity and ensure that each row in a table can be uniquely identified.

In order to qualify as a primary key, the value(s) in the column or columns must be unique and non-null for each row in the table. This ensures that each record can be identified by its primary key value, and that no two records can have the same primary key value.

Primary keys are also used to establish relationships between tables. In a relational database, a primary key in one table can be used as a foreign key in another table to link the two tables together. This enables the database to maintain consistency and avoid duplication of data, which helps ensure data accuracy and reliability.

Typically, a primary key is defined when a table is created, and it is usually implemented using an index on the column or columns that make up the key. This allows for efficient searching and sorting of data based on the primary key values.
### Foreign Key (FK) 
– A foreign key is a column in one table that is the primary key in a different table.In a relational database, each table must have a unique way of identifying each record, which is done using a primary key. A table can have only one primary key, which is typically a single column or a combination of columns that uniquely identify each record in the table.

Having multiple primary keys in a single table would create ambiguity in identifying individual records, as each record could have multiple unique identifiers. It would also complicate relationships between tables, as foreign keys typically reference a single primary key in another table. Therefore, a table should have only one primary key to maintain data integrity and ensure consistency in the database.

### Why is SQL important?
1.	Easy to understand
2.	Can access data directly
3.	Can audit data
4.	Can replicate data
5.	Can analyze multiple tables at once
6.	Can do complex analysis

### Why do businesses like DBs? 
1.	Data integrity is ensured
2.	Data can be accessed quickly
3.	Data is easily shared

### Key points about DBs:
- A few key points about data stored in SQL databases, as follows:

Data is stored in tables: In a SQL database, data is stored in tables which are similar to Excel spreadsheets. Each table has rows and columns, where each row represents a record or an instance of an entity (such as a person, a transaction, a company, etc.), and each column represents an attribute or a characteristic of the entity.

Consistency of data types: All the data in the same column of a table must have the same data type. This means that if a column holds numerical values, all the values in that column must be of numerical data type, and if a column holds text values, all the values in that column must be of text data type. If a column has mixed data types, such as numerical values and text values, it can cause issues with performing calculations or filtering data.

Consistent column types improve performance: Having consistent column types is important for efficient data retrieval from the database. SQL databases can hold a large amount of data, and having consistent column types means that data can be retrieved faster. Additionally, it helps to optimize queries and improve performance.

In summary, SQL databases store data in tables, where each table has rows and columns, and data in each column must have the same data type. Having consistent column types is important for efficient data retrieval and better performance.

### What are some examples of SQL DBs?
1.	MySQL
2.	Access
3.	Oracle
4.	MS SQL Server
5.	Postgres

### What is a statement in SQL?
A statement in SQL is a command that allows you to perform a certain function.  Examples include:
 - CREATE TABLE is a statement that creates a new table in a database.
 - DROP TABLE is a statement that removes a table in a database.
 - SELECT allows you to read data and display it. This is called a query.
## Creating a Database
The SQL statement "CREATE DATABASE" is used to create a new database. The general syntax for creating a database is as follows:
```sql
CREATE DATABASE [IF NOT EXISTS] database_name;
```
The IF NOT EXISTS clause is optional and can be used to check if a database with the specified name already exists. If the database exists, the CREATE DATABASE statement will not be executed.

database_name is the name of the new database you want to create.

Here's an example of how to use the CREATE DATABASE statement:
```sql
CREATE DATABASE IF NOT EXISTS my_new_database;
```
This statement will create a new database called my_new_database if it does not already exist. If it does exist, the statement will not have any effect.
The semicolon (;) is used as a statement terminator in SQL to mark the end of a statement. It tells the database engine where one statement ends and the next one begins. In some cases, the semicolon is optional, especially in single statement queries. However, using it is considered good practice because it can help prevent errors and make the code easier to read and maintain. When executing multiple statements in a single query, using the semicolon is mandatory to separate the statements.
        #### ; (the semicolon character) it functions as a statement terminator
        -when your code contains more than a single statement, ; is indispensable
        -will help you avoid errors sometimes
        -will improve the readability of your code
 ### Introduction to Data Types
 #### String Data types
 In SQL, a string is a data type that is used to store textual data. A string can contain a sequence of characters, including letters, numbers, and special characters.
Common string data types in SQL include:

CHAR - a fixed-length string that can contain up to 255 characters. It is used for storing short strings of a known length.

VARCHAR - a variable-length string that can contain up to 255 characters. It is used for storing longer strings of varying lengths.

TEXT - a data type that can hold up to 2 GB of text data. It is used for storing large amounts of text, such as long paragraphs or entire documents.

String data types are important in SQL because they allow you to store and manipulate textual data in your database. You can use SQL functions to search, extract, and manipulate string data, making it a powerful tool for data analysis and manipulation.
#### Integers
In SQL, integers are a numeric data type that represent whole numbers without any decimal point. The specific integer data types available in SQL may vary depending on the database system being used, but some common ones include:

TINYINT: a 1-byte integer that can hold values from -128 to 127 (or 0 to 255, if unsigned)
SMALLINT: a 2-byte integer that can hold values from -32768 to 32767 (or 0 to 65535, if unsigned)
MEDIUMINT: a 3-byte integer that can hold values from -8388608 to 8388607 (or 0 to 16777215, if unsigned)
INT: a 4-byte integer that can hold values from -2147483648 to 2147483647 (or 0 to 4294967295, if unsigned)
BIGINT: an 8-byte integer that can hold values from -9223372036854775808 to 9223372036854775807 (or 0 to 18446744073709551615, if unsigned)

Integers are typically used to represent whole numbers in a database, such as IDs, quantities, or counts. The choice of integer data type will depend on the expected range of values for a particular column and the storage space available in the database
In SQL, integer data types are signed by default, meaning that they can represent both positive and negative values.
However, you can specify that a particular integer data type should only contain non-negative values (i.e., be unsigned) by adding the keyword UNSIGNED after the data type. For example, INT UNSIGNED would create an integer column that can only store non-negative values.

It's worth noting that using an unsigned integer can effectively double the maximum value that can be stored in that column, since you're not using one bit to represent the sign of the value.
###### Why not use BIGINT all the time?
Using a smaller integer type can indeed increase processing speed and require less storage space per data point. However, it is important to choose the appropriate data type for the specific needs of the database.

For example, if the range of values for a column is likely to exceed the maximum value of a TINYINT data type, using that data type could result in errors or data loss. On the other hand, if a larger data type like BIGINT is used when it is not needed, it can result in wasted storage space and slower processing times.

It's important to consider the range of possible values for a column, as well as any potential future needs, when choosing a data type. Additionally, some database management systems have different limitations or performance characteristics for certain data types, so it's important to consider those factors as well.
### Fixed and Floating Point Data Types
Fixed point data types are used to represent exact numeric values that are not floating point numbers. In fixed point data types, the decimal point is fixed at a specific location, which means the number of decimal places is predetermined and cannot be changed. The most common fixed point data types in SQL are DECIMAL and NUMERIC.

Floating point data types, on the other hand, represent approximate numeric values. They are used to store values that have decimal places and can be of variable precision. The most common floating point data types in SQL are FLOAT and DOUBLE. Floating point data types are useful when you need to store very large or very small numbers, or when you need to perform complex mathematical calculations.

The choice between fixed and floating point data types depends on the specific requirements of your application. If you need to store exact values, then fixed point data types are the way to go. If you need to store very large or very small numbers, or if you need to perform complex mathematical calculations, then floating point data types are the better choice.

THe main difference between the fixed and the floating point type is in the way the value is represented in the memory of the computer.Fixed point numbers are represented as a set number of bits for the whole number part and a set number of bits for the fractional part, with the decimal point fixed in place. Floating point numbers, on the other hand, use a scientific notation-like representation, where the number is expressed as a mantissa (or significand) and an exponent. This allows for a wider range of values to be represented, but at the cost of some precision.
### Other Useful Data Types
DATETIME: represents the date shown on the calendar and the time shown on the clock. The DATETIME data type in SQL is used to represent a specific point in time, including both a date and a time. It is typically used for recording and manipulating temporal data in a database.

The format of the DATETIME value is 'YYYY-MM-DD HH:MM:SS', where YYYY is the four-digit year, MM is the two-digit month, DD is the two-digit day, HH is the two-digit hour, MM is the two-digit minute, and SS is the two-digit second.

The range of values that can be stored in a DATETIME data type depends on the specific implementation of SQL. In some systems, the range may be limited to the years 1901 through 2099, while in others it may extend to earlier or later dates.
TIMESTAMP: The TIMESTAMP data type in SQL represents a specific point in time, typically including both a date and time component. It is often used to store information about when a record was last updated or when a certain event occurred.
Representing a moment in time as a number (such as the Unix timestamp) allows for easy comparison and calculation of the difference between two timestamps. For example, if you have two timestamps representing the start and end of an event, you can easily calculate the duration of the event by subtracting the start timestamp from the end timestamp.

One of the advantages of using TIMESTAMP is that it automatically updates itself to the current date and time whenever a row is inserted or updated. This can be useful for tracking changes to a database over time, and for ensuring that records are kept up-to-date.

However, it's worth noting that the precise behavior of TIMESTAMP can vary depending on the database management system you are using, so it's important to consult the documentation for your particular system to ensure that you are using the data type correctly.
### BLOB: Binary Large OB ject
-refers to a file of binary data data with 1s and 0s
- involves saving files in a record
- BLOB (Binary Large Object) is a data type that allows you to store large binary data in a database table, such as image files, audio files, or video files. 
- It can be used to save any kind of binary data, including executable programs or compressed archives.
- BLOBs are commonly used to store files in a database as a way of keeping related data together in one place, rather than in separate files on a file system. 
- This can make it easier to manage and back up the data, and can also help with data consistency and integrity.
- BLOBs can be a useful data type for certain types of applications, but they can also make databases much larger and slower to search than they need to be.
-  In general, it is recommended to use BLOBs sparingly and only when they are really necessary, and to use other types of data for storing text and other smaller data.
## Creating A table
To create a table in SQL, you can use the CREATE TABLE statement followed by the table name and a set of parentheses that list the columns and their data types. Here's an example:
```sql
CREATE TABLE customers (
  id INT,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  email VARCHAR(100)
);
```
This creates a table called customers with four columns: id, first_name, last_name, and email. The id column has a data type of INT, which stands for integer. The first_name, last_name, and email columns are all of data type VARCHAR, which stands for variable-length character string, and they have different maximum lengths specified in parentheses.
Note that, When creating a table in SQL, you must add at least one column to define the structure of the table. Here's an example of creating a table called "customers" with three columns: "customer_id", "customer_name", and "customer_email":
```sql
CREATE TABLE customers (
    customer_id INT,
    customer_name VARCHAR(50),
    customer_email VARCHAR(100)
);
```
#### AUTO_INCREMENT
-frees you from having to insert all purchase numbers manually through the INSERT command at a later stage
-assigns 1 to the first record of the table and automatically increments by 1 for every subsequent row
AUTO_INCREMENT is a feature in SQL that is commonly used for generating a unique and sequential ID number for a primary key column in a table. It is often used for tables where new records are frequently added, such as transactional tables, to ensure that each record has a unique identifier.

When a column is defined as AUTO_INCREMENT, it is automatically assigned the next available number starting from 1, and increments by 1 for each new row added to the table. This helps to ensure that each record has a unique identifier, and also makes it easy to reference a specific record in a table by its ID number.

AUTO_INCREMENT is often used in combination with the PRIMARY KEY constraint, which ensures that the ID number column is unique and not null. This helps to ensure that each record in the table has a unique identifier, which is useful for querying and updating the data in the table.
## Using Databases and Tables
### Queries
Queries are used to retrieve, manipulate, and analyze data stored in a database. SQL, the language used to manage databases, provides a variety of commands for working with data, such as SELECT, INSERT, UPDATE, and DELETE. These commands allow you to retrieve specific data based on certain conditions, insert new data into tables, update existing data, or delete data from tables. By using these commands, you can create complex queries to retrieve the information you need from a database.

### SELECT * FROM orders;
This statement is composed of clauses. Clauses always appear in the same order. Some clauses are required and others are optional. The SELECT clause tells the database which columns you want to read from the database. The * is called a wildcard. There are various types of wildcards. This one represents “all columns.” The FROM clause tells the database which table to you want to select columns from. Both SELECT and FROM are mandatory clauses in any SELECT statement. You can write statements in lower case, but traditionally, SQL commands are written all uppercase. So, “select * from orders;” works just fine, but “SELECT * FROM orders;” is more conventional. Sometimes you’ll be required to end a statement in a semicolon, but it depends on the environment. It’s a good habit to include the semicolon at the end.

### The LIMIT Clause
The LIMIT clause limits the number of rows returned from a query. For example:

```sql
SELECT *
FROM orders
LIMIT 10
```

### The ORDER BY clause
The ORDER BY clause allows you specify which column you want to use as the basis for your query results ordering and whether you would like your query results to be put in ascending order (that’s the default) or DESCending order. For example:
```sql
SELECT *
FROM orders
ORDER BY occurred_at DESC
LIMIT 10
```
```sql
-- This query selects the first 10 rows from the orders table
SELECT * FROM orders
LIMIT 10;
```
The double hyphens indicate a single-line comment, which is ignored by the SQL engine when it executes the code. The comment is simply there to provide a human-readable explanation of what the code does.

The SELECT statement in this code selects all columns from the orders table. The * symbol is a shorthand way of saying "select all columns". The FROM clause specifies the table from which the data is selected.

The LIMIT clause is used to restrict the number of rows that are returned by the query. In this case, the LIMIT clause is set to 10, so the query will return the first 10 rows from the orders table. This is useful when working with large datasets, as it allows you to preview a small subset of the data before running more complex queries or processing the entire dataset.

Just like in Excel, you can order by multiple columns. Just list the columns you want to use as a comma separated list. For example:
```sql
-- This query selects all columns from the "orders" table
SELECT *
-- Orders the results in descending order by the "occurred_at" column
FROM orders
ORDER BY occurred_at DESC
-- Limits the number of results to 10
LIMIT 10
```
Notice that we specified that “occurred_at” should be descending order, but total_amt_usd should be in the default ascending order.

### The WHERE Clause
The WHERE clause goes between FROM and ORDER BY. WHERE allows you narrow your search to results where one column has a particular value or range of values. For example:
```sql
SELECT *
FROM orders
WHERE account_id >= 1000 and account_id <= 1041 and standard_qty > 150
ORDER BY occurred_at
LIMIT 1000;
```
Here, you’ll get results only for the records with account_id in the range greater than or equal to 1,000 and less than or equal to 1041 and with standard_qty greater than 150. You can use a combination of mathematical and logical operators to create complex WHERE clauses. The example above uses columns that have numerical values, but you could also use columns with text values. For example,
```sql
SELECT name, website, primary_poc
FROM accounts
WHERE name = 'Exxon Mobil';
```

### Derived Columns
A derived column is a column you create by using mathematical operations on already existing columns. For example:
```sql
SELECT id, (standard_amt_usd/total_amt_usd)*100 AS std_percent, total_amt_usd
FROM orders
LIMIT 10;
```
Here, we select the “id” column and a second derived column that we create by dividing standard_amt_usd by total_amt_usd and multiplying that by 100. We use the AS clause to name this new derived column “std_percent.” Then we add a third column – “total_amt_usd”.

### Logical Operators
Logical operators allow you to create longer more complex statements. Here’s a summary of the logical operators:
- LIKE - This allows you to perform operations similar to using WHERE and =, but for cases when you might not know exactly what you are looking for.
- IN - This allows you to perform operations similar to using WHERE and =, but for more than one condition.
- NOT - This is used with IN and LIKE to select all of the rows NOT LIKE or NOT IN a certain condition.
- AND & BETWEEN - These allow you to combine operations where all combined conditions must be true.
- OR - This allows you to combine operations where at least one of the combined conditions must be true.

### LIKE Example
```sql
SELECT *
FROM accounts
WHERE website LIKE '%google%';
```
Here we’re selecting all columns from the “accounts” table where the “website” column is like the word “google,” but preceded by 0 or more characters of any type and/or followed by 0 or more characters of any type.  Not that LIKE is always used in the WHERE clause.

### IN Example
 The IN operator is useful for working with both numeric and text columns. This operator allows you to use an =, but for more than one item of that particular column. We can check one, two, or many column values for which we want to pull data, but all within the same query.
```sql
SELECT *
FROM orders
WHERE account_id IN (1001,1021);
```
Here’s we’re selecting all columns from the “orders” table but only where the “account_id” is in the group 1001 or 1021. 

### NOT Example
You can add the NOT operator before IN or LIKE to get the inverse of the results those queries would otherwise produce. For example:
```sql
SELECT sales_rep_id, 
       name
FROM accounts
WHERE sales_rep_id NOT IN (321500,321570)
ORDER BY sales_rep_id;
```
Here, we’re getting the “sales_rep_id” and “name” columns from the “accounts” table, but only where the “sales_rep_id” is not in the group 321500 or 321570. 
Here’s another example:
```sql
 SELECT *
FROM accounts
WHERE website NOT LIKE '%com%';
```
Here, we’re getting all of the columns from the “accounts” table, but only where the “website” column does not contain a value with the string “com” within it.

### AND, BETWEEN, and OR Examples
```sql
SELECT *
FROM orders
WHERE occurred_at >= '2016-04-01' AND occurred_at <= '2016-10-01'
ORDER BY occurred_at
```
Here, we select all columns from the “orders” table, but only where the “occurred_at” column contains values greater than or equal to ‘2016-04-01’ and less than or equal to ‘2016-10-01’. Not that you must repeat the “occurred_at” column name for each arithmetic operator. The results are then ordered by “occurred_at”.
The BETWEEN operator works similarly to AND, but look like this:
```sql
SELECT *
FROM orders
WHERE occurred_at BETWEEN '2016-04-01' AND '2016-10-01'
ORDER BY occurred_at
```
Whereas the AND operator makes a statement more exclusive of some records, the OR operator makes a statement more inclusive.
```sql
SELECT *
FROM orders
WHERE standard_qty = 0 OR gloss_qty = 0 OR poster_qty = 0
```
Here, we are selecting all columns from the “orders” table, but only where the “standard_qty” is 0, or where the “gloss_qty” is 0, or where the “poster_qty” is 0.
### .––“dot operator"

The "dot operator" is also known as the period or full stop symbol "." in SQL. It is used to indicate the existence of a relationship or connection between two object types, usually between tables and their respective columns.

In a query, the dot operator is used to reference a column in a specific table. For example, if you have two tables named "orders" and "customers" that are related by a "customer_id" column, you could use the dot operator to join the two tables on that column like this:
```sql
SELECT * FROM sales.customers;
```

This SQL query selects all columns from the "customers" table in the "sales" database. The asterisk indicates that all columns should be included in the results. The "sales.customers" notation specifies the table name and its location within the "sales" database. This query would return all of the rows and columns in the "customers" table.

In this example, the dot operator is used to specify the column names and their associated tables in the SELECT statement. It is also used to specify the column used in the join condition between the two tables.

## Introduction to Joins
The whole purpose of JOIN statements is to allow us to pull data from more than one table at a time.
Again - JOINs are useful for allowing us to pull data from multiple tables. This is both simple and powerful all at the same time.
With the addition of the JOIN statement to our toolkit, we will also be adding the ON statement.
We use ON clause to specify a JOIN condition which is a logical statement to combine the table in FROM and JOIN statements.

The ON statement is used to specify the condition for the JOIN to be executed. The JOIN statement is used to combine rows from two or more tables based on a related column between them. The ON statement is where you specify the column(s) on which to join the tables.

For example, consider two tables: customers and orders. The customers table has columns customer_id, name, and email, while the orders table has columns order_id, customer_id, product_name, and price. If you want to retrieve data from both tables, you can use a JOIN statement with the ON condition specifying that the customer_id column in the customers table matches the customer_id column in the orders table:
```sql
SELECT *
FROM customers
JOIN orders ON customers.customer_id = orders.customer_id;
```
This query will return a result set with all the columns from both tables where the customer_id column matches between the two tables.
Let's say you have two tables in your database, a "customers" table and an "orders" table. The customers table contains information about your customers, such as their name and address, while the orders table contains information about each order they have made, such as the order date and the total cost.

If you want to know which orders were made by a particular customer, you would need to join these two tables together. You can do this using a JOIN statement, like so:
```sql
SELECT *
FROM customers
JOIN orders ON customers.customer_id = orders.customer_id
WHERE customers.name = 'John Smith';
```
In this example, we are selecting all columns from both the customers and orders tables where the customer name is "John Smith". The JOIN statement is used to combine the two tables, with the ON statement specifying the condition for the join. In this case, we are joining the tables on the customer_id column, which is present in both tables.
Using JOIN statements allows you to combine data from multiple tables into a single result set, enabling you to answer more complex questions about your data.
### other examples 

```

```sql
SELECT orders.*,
       accounts.*
FROM orders 
JOIN accounts
ON orders.account_id = accounts.id;
```
In this example, we're selecting every column from both the orders table and the accounts table, and we're joining these two tables ON the account_id column from orders and the id column from accounts.

This SQL statement is an example of a JOIN query that combines data from two tables: "orders" and "accounts".

The SELECT statement is used to specify the columns we want to retrieve data from. In this case, we are using the wildcard character "*" to indicate that we want to retrieve all columns from both tables.

The JOIN statement is used to combine data from the "orders" and "accounts" tables. We are using the INNER JOIN clause, which will only return rows where there is a match in both tables based on the ON condition.

The ON statement specifies the condition for the join operation, which in this case is that the "account_id" column in the "orders" table matches the "id" column in the "accounts" table.
By combining the data from these two tables in the query results, we can gain insights into relationships between the data and better understand the data as a whole.

Joins are used in SQL to combine data from multiple tables. They allow us to pull data from more than one table at a time. The inner join will only return records that appear in both tables (or all of the tables) that you're working with. It will not return records that appear in one table but not the other(s). In contrast, the left and right joins allow us to display records in our results that only appear in one of the tables we're working with.

Aliases are used to provide short or temporary names for database objects, including tables and columns. You can use an optional AS clause between the name and the alias if you want to. The general form of aliases is SELECT t1.column1 aliasname, t2.column2 aliasname2 FROM tablename AS t1 JOIN tablename2 AS t2.
###vJoining more than two tables example:
```sql

SELECT *
FROM web_events
JOIN accounts
ON web_events.account_id = accounts.id
JOIN orders
ON accounts.id = orders.account_id
```
In this example, we're selecting all columns from all tables, starting FROM the web_events table and JOINing the accounts table ON web_events.account_id and accounts.id. Then we JOIN the orders table ON accounts.id and orders.account_id.
### Alias example:
```sql
SELECT t1.column1 aliasname, t2.column2 aliasname2
FROM tablename AS t1
JOIN tablename2 AS t2
```
In this example, we're giving the short alias "t1" to "tablename" and the short alias "t2" to "tablename2". Those aliases are then used in the SELECT clause to rename "t1.column1" to "aliasname" and "t2.column2" as "aliasname2".
### Using an alias when two tables have the same column name:
```sql
SELECT o.*, a.*
FROM orders o
JOIN accounts a
ON o.account_id = a.id
```
In this example, we're getting all columns from both orders and accounts, starting FROM orders, which we alias as "o" and JOINing accounts, which we alias as "a", and joining those two tables ON orders.account_id and accounts.id.
### Left and Right Joins

An inner join will only return records that appear in both tables (or all of the tables) that you're working with. It will not return records that appear in one table, but not the other(s). But sometimes you want to be able to display records in your results that only appear in one of the tables you're working with. That's where LEFT and RIGHT joins come in. Note that these joins are sometimes referred to as the LEFT OUTER JOIN and RIGHT OUTER JOIN. 

Here's an example:
```sql
SELECT a.id, a.name, o.total
FROM orders o
LEFT JOIN accounts a
ON o.account_id = a.id
```
In this example, we're selecting the id and name columns from the accounts table and the total column from the orders table. We're starting with the orders table (which we alias to o), and then LEFT JOIN the accounts table (which we alias to a). We join these tables ON the order table's account_id column (a foreign key in orders) and the accounts table's id column (the primary key in accounts). The left join in this case will return all records from the orders table, and only the matching records from the accounts table.
However, the results will be different if we use a RIGHT JOIN, like this:
```sql
SELECT a.id, a.name, o.total
FROM orders o
RIGHT JOIN accounts a
ON o.account_id = a.id
```
Here, again, we're selecting the id and name columns from the accounts table and the total column from the orders table. We're starting with the orders table (which we alias to o), and then RIGHT JOIN the accounts table (which we alias to a). We join these tables ON the order table's account_id column (a foreign key in orders) and the accounts table's id column (the primary key in accounts). Now the results that we get back from the query have changed. If you evaluate the query in the classroom's IDE and then scroll all the way to the bottom of the results, you will now see one account id, 1731, and name, Goldman Sachs Group, that does not have a corresponding total. 

```sql

SELECT a.id, a.name, o.total
FROM orders o
RIGHT JOIN accounts a
ON o.account_id = a.id

```
In this example, we're selecting the id and name columns from the accounts table and the total column from the orders table. We're starting with the accounts table (which we alias to a), 
### What makes the orders table the left table in a Venn diagram of the two tables?
The orders table is the left hand part of the diagram because it is the table that appears in the FROM clause. You can switch things around and use accounts in the FROM clause, and in that case, accounts will now be the left hand part of the diagram and orders will be the right hand part. 

Here's an example code to demonstrate how the left table in a Venn diagram of two tables is determined by the FROM clause:
```sql
SELECT *
FROM orders
LEFT JOIN accounts
    ON orders.account_id = accounts.id;

```
In this example, the FROM clause specifies orders as the left table in the Venn diagram because it appears first. The LEFT JOIN clause specifies accounts as the right table.

If we were to switch the tables in the FROM clause like this:
```sql
SELECT *
FROM accounts
LEFT JOIN orders
    ON accounts.id = orders.account_id;
```
Then accounts would be the left table in the Venn diagram and orders would be the right table.

In either case, the LEFT JOIN or RIGHT JOIN clause determines how the tables are joined and how the data is combined.
### Outer Joins
An OUTER JOIN, also called a FULL OUTER JOIN, is a join that will return rows from the inner join result, and also rows from either of the tables being joined. This join is used rarely.

### Sample problems from section 19

Problem 1. Provide a table that provides the region for each sales_rep along with their associated accounts. This time only for the Midwest region. Your final table should include three columns: the region name, the sales rep name, and the account name. Sort the accounts alphabetically (A-Z) according to the account name.
```sql
select r.name as rname, sr.name as srname, a.name as aname
from region r
join sales_reps sr
on sr.region_id = r.id
and r.name = 'Midwest'
join accounts a
on a.sales_rep_id = sr.id
```
Explanation: This query joins the orders and accounts tables using the account_id column. It then selects the name column from the accounts table and the occurred_at column from the orders table. The result set is sorted by occurred_at in ascending order and limited to the first row, which will have the earliest order.

Problem 2. Provide a table that provides the region for each sales_rep along with their associated accounts. This time only for accounts where the sales rep has a first name starting with S and in the Midwest region. Your final table should include three columns: the region name, the sales rep name, and the account name. Sort the accounts alphabetically (A-Z) according to the account name.
```sql
select r.name as rname, sr.name as srname, a.name as aname
from region r
join sales_reps sr
on sr.region_id = r.id
and r.name = 'Midwest'
join accounts a
on a.sales_rep_id = sr.id
and sr.name like 'S%'
order by a.name
```
Explanation: This query joins the accounts and orders tables using the id and account_id columns respectively. It then selects the name column from the accounts table and the sum of total from the orders table, aliased as total. The result set is grouped by name and sorted by name in ascending order.

Problem 3. Provide a table that provides the region for each sales_rep along with their associated accounts. This time only for accounts where the sales rep has a last name starting with K and in the Midwest region. Your final table should include three columns: the region name, the sales rep name, and the account name. Sort the accounts alphabetically (A-Z) according to the account name.
```sql
select r.name as rname, sr.name as srname, a.name as aname
from region r
join sales_reps sr
on sr.region_id = r.id
and r.name = 'Midwest'
join accounts a
on a.sales_rep_id = sr.id
and sr.name like '% K%'
order by a.name
```
Explanation: This query joins the accounts and web_events tables using the id and account_id columns respectively. It then selects the name column from the accounts table, the channel column from the web_events table, and the maximum occurred_at value from the web_events table, aliased as occurred_at. The result set is grouped by name and channel and sorted by occurred_at in descending order. The LIMIT clause limits the result set to the first row.

Note that the second solution provided in the prompt is more efficient as it does not require the MAX() function. It simply selects the occurred_at, channel, and name columns from the web_events and accounts tables, joined using the account_id and id columns respectively. The result set is sorted by occurred_at in descending order and limited to the first row.

Problem 4. Provide the name for each region for every order, as well as the account name and the unit price they paid (total_amt_usd/total) for the order. However, you should only provide the results if the standard order quantity exceeds 100. Your final table should have 3 columns: region name, account name, and unit price. In order to avoid a division by zero error, adding .01 to the denominator here is helpful total_amt_usd/(total+0.01).
```sql
select r.name, a.name, o.total_amt_usd/(o.total + 0.01) as unit_price
from region r
join sales_reps sr
on sr.region_id = r.id
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id 
and o.standard_qty > 100
```
Explanation: This query selects the channel column from the web_events table and counts the number of occurrences of each channel using the COUNT() function, aliased as channel_count. The result set is grouped by channel.

Problem 5. Provide the name for each region for every order, as well as the account name and the unit price they paid (total_amt_usd/total) for the order. However, you should only provide the results if the standard order quantity exceeds 100 and the poster order quantity exceeds 50. Your final table should have 3 columns: region name, account name, and unit price. Sort for the smallest unit price first. In order to avoid a division by zero error, adding .01 to the denominator here is helpful (total_amt_usd/(total+0.01).
```sql
select r.name as rname, a.name as aname, o.total_amt_usd/(o.total + 0.01) as unit_price
from region r
join sales_reps sr
on sr.region_id = r.id
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id
and o.standard_qty > 100
and poster_qty > 50
```

Problem 6. Provide the name for each region for every order, as well as the account name and the unit price they paid (total_amt_usd/total) for the order. However, you should only provide the results if the standard order quantity exceeds 100 and the poster order quantity exceeds 50. Your final table should have 3 columns: region name, account name, and unit price. Sort for the largest unit price first. In order to avoid a division by zero error, adding .01 to the denominator here is helpful (total_amt_usd/(total+0.01).
```sql
select r.name as rname, a.name as aname, o.total_amt_usd/(o.total + 0.01) as unit_price
from region r
join sales_reps sr
on sr.region_id = r.id
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id
and o.standard_qty > 100
and poster_qty > 50
order by unit_price desc
```

Problem 7. What are the different channels used by account id 1001? Your final table should have only 2 columns: account name and the different channels. You can try SELECT DISTINCT to narrow down the results to only the unique values.
```sql
select distinct we.channel, a.name
from web_events we
join accounts a
on we.account_id = a.id
and a.id = '1001'
```

Problem 8. Find all the orders that occurred in 2015. Your final table should have 4 columns: occurred_at, account name, order total, and order total_amt_usd.
```sql
select o.occurred_at, a.name, o.total, o.total_amt_usd
from accounts a
join orders o
on o.account_id = a.id
where o.occurred_at between '01-01-2015' and '01-01-2016'
order by o.occurred_at desc
```

## Aggregations:

Aggregations in SQL are functions used to summarize and group data. They are particularly useful for understanding large data sets and identifying patterns in them. In this note, we'll discuss several aggregation functions in SQL, including COUNT, SUM, MIN, and MAX.

### NULL:
In SQL, NULL is a datatype that represents the absence of data. It is not the same as zero or an empty string, and it is often ignored in aggregation functions. To identify NULLs in a WHERE clause, we use IS NULL or IS NOT NULL instead of the = operator, as NULL is not considered a value in SQL.

COUNT:
COUNT is an aggregation function in SQL that returns the total number of records in a table or the number of non-null records in a specific column. COUNT works with columns that have numerical values, as well as non-numerical columns. To use COUNT, we simply specify the column we want to count or use * to count all records in a table.

Example:

```sql
SELECT COUNT(*) AS order_count
FROM orders
WHERE occurred_at >= '2016-12-01'
AND occurred_at < '2017-01-01'

```
This query returns the number of orders that occurred between December 1st, 2016 and January 1st, 2017.
### SUM:
SUM is an aggregation function in SQL that adds up all of the numerical values in a column, ignoring NULL values. To use SUM, we specify the column we want to sum.

Example:
```sql
SELECT SUM(standard_qty) AS standard,
       SUM(gloss_qty) AS gloss,
       SUM(poster_qty) AS poster
FROM orders
```
This query returns the total number of standard, gloss, and poster items sold.
### MIN and MAX:
MIN and MAX are aggregation functions in SQL that return the minimum and maximum values in a column, respectively. They can be used on both numerical and non-numerical columns. Depending on the column type, MIN returns the lowest number or earliest date, or the non-numerical value that appears earliest in the alphabet. MAX does the opposite, returning the highest number or latest date, or the non-numerical value that appears closest to "Z" in the alphabet.

Example:
```sql
SELECT MIN(standard_qty) AS standard_min,
       MIN(gloss_qty) AS gloss_min,
       MIN(poster_qty) AS poster_min,
       MAX(standard_qty) AS standard_max,
       MAX(gloss_qty) AS gloss_max,
       MAX(poster_qty) AS poster_max
FROM orders
```
### GROUP BY
GROUP BY is a clause that is used with aggregate functions to group the result-set by one or more columns. When GROUP BY is used, the result-set is divided into groups based on the values in the specified column(s), and aggregate functions like COUNT, SUM, AVG, MIN, and MAX are applied to each group.
### Where does GROUP BY go?
GROUP BY goes between the WHERE clause and the ORDER BY clause. 

### How do you use GROUP BY?
Any column included the SELECT clause that is not being aggregated, must be included in the GROUP BY clause. For example:

```sql
SELECT state, COUNT(*) AS num_customers
FROM customers
GROUP BY state
```
Here, we SELECT the state and COUNT of all records, which we'll call num_customers, FROM the customers table. We then GROUP BY state, which means that we'll get the count of customers by state.

```sql
SELECT account_id,
       SUM(standard_qty) AS standard,
       SUM(gloss_qty) AS gloss,
       SUM(poster_qty) AS poster
FROM orders
GROUP BY account_id
ORDER BY account_id
```
Here, we select orders.account_id and the sums of quantities of each type of paper. We get those FROM the orders table. However, we must GROUP BY account_id if what we want to see is the sums per account. It also helps to ORDER BY the account_id.

### GROUP BY Practice Problems from section 14

1. Which account (by name) placed the earliest order? Your solution should have the account name and the date of the order.
```sql
select accounts.name, orders.occurred_at
from orders
join accounts
on orders.account_id = accounts.id
order by orders.occurred_at
limit 1
```

2. Find the total sales in usd for each account. You should include two columns - the total sales for each company's orders in usd and the company name.
```sql
select a.name, sum(o.total) as total
from accounts a
join orders o
on o.account_id = a.id
group by a.name
order by a.name
```

3. Via what channel did the most recent (latest) web_event occur, which account was associated with this web_event? Your query should return only three values - the date, channel, and account name.
```sql
select a.name, we.channel, max(we.occurred_at) as occurred_at
from accounts a
join web_events we
on we.account_id = a.id
group by a.name, we.channel
order by occurred_at desc
limit 1
```
Note that this solution works, but it turns out that the max function is unnecessary and probably slows the query down a bit. You get the exact same answer with this solution:
```sql
SELECT w.occurred_at, w.channel, a.name
FROM web_events w
JOIN accounts a
ON w.account_id = a.id 
ORDER BY w.occurred_at DESC
LIMIT 1;
```

4. Find the total number of times each type of channel from the web_events was used. Your final table should have two columns - the channel and the number of times the channel was used.
```sql
select we.channel, count(we.channel) as channel_count
from web_events we
group by we.channel
```

5. Who was the primary contact associated with the earliest web_event?
```sql
select a.primary_poc, min(we.occurred_at) as occurred_at
from accounts a
join web_events we
on we.account_id = a.id
group by a.primary_poc
order by occurred_at
limit 1
```
This is another error. The solution returns the correct result, but the function isn't necessary, and it probably slows things down. The solution given in section 15 is:
```sql
SELECT a.primary_poc
FROM web_events w
JOIN accounts a
ON a.id = w.account_id
ORDER BY w.occurred_at
LIMIT 1;
```

6. What was the smallest order placed by each account in terms of total usd. Provide only two columns - the account name and the total usd. Order from smallest dollar amounts to largest.
```sql
select a.name, min(o.total_amt_usd) as total
from orders o
join accounts a
on o.account_id = a.id
group by a.name
order by total
```

7. Find the number of sales reps in each region. Your final table should have two columns - the region and the number of sales_reps. Order from the fewest reps to most reps.
```sql
select r.name, count(sr.name) as number_of_reps
from region r
join sales_reps sr
on sr.region_id = r.id
group by r.name
order by number_of_reps
```

### Grouping by Multiple Columns
You can GROUP BY and ORDER BY multiple columns in the same query. For example, say you want to get the number of events per channel per account id. Because we're only after the account_id, we can confine our query to the web_events table without needing to join any other table. And because each id in the web_events table represents an event, we can just count the ids to get the number of events. Because we're counting the ids, we know we'll need at least one group by value. But we don't just want to events per channel or events per account id. Instead, we want events per channel *per account id*. To get that, we need both of those columns in our GROUP BY clause.
```sql
SELECT account_id,
       channel,
       COUNT(id) as events
FROM web_events
GROUP BY account_id, channel
ORDER BY account_id, channel DESC
```
Here, we're getting the account id, channel and count of id from web_events, and we're grouping by both account_id and channel. We're also ordering by account_id first, then channel. Note that the order that you list the columns in the GROUP BY clause doesn't matter, but the order that list columns in the ORDER BY clause does.

### DISTINCT
DISTINCT is always used in SELECT statements, and it provides the unique rows for all columns written in the SELECT statement. Therefore, you only use DISTINCT once in any particular SELECT statement. Note that DISTINCT, especially in aggregations, can slow your queries.

### Problems

1. Are there any accounts associated with more than one region?

This is the solution that makes the most sense to me:
```sql
select a.name as account_name, count(r.name) as region_count
from region r
join sales_reps sr on sr.region_id = r.id
join accounts a    on a.sales_rep_id = sr.id
group by account_name
order by region_count, account_name
```
This solution shows us the account names and the number of regions associated with each account. However, it turns out that this is a very roundabout way to answer the question being asked.

This is the most succinct (and probably fastest) solution, using DISTINCT:
```sql
SELECT DISTINCT id, name
FROM accounts;
```
I think the reasoning is that if there were any accounts that had more than one region, then there would have to be duplicate account ids and names in the accounts table to allow for a single account having two or more regions. There are no such duplicate accounts, therefore there are no accounts associated with more than one region.

2. Have any sales reps worked in more than one account?

This is what makes sense to me:
```sql
select distinct sr.id as sr_id, sr.name as sr_name, a.id as a_id, a.name as a_name
from sales_reps sr
join accounts a
on a.sales_rep_id = sr.id
order by sr.id, a.id
```
The result we get here shows us the sales reps' names and account names, making it obvious that all sales reps are associated with more than just one account.

This is the actual answer:
```sql
SELECT DISTINCT id, name
FROM sales_reps;
```
What this query returns is a list of 50 names, but if you know that there are more than 50 accounts (there are), then you quickly realize that at least one sales rep has more than one account. As it turns out, all of the sales reps have more than one account. 

It's pretty annoying that there isn't more explanation offered in the course material. This stuff may seem quite obvious to the course designers, but I don't think it will be obvious to everyone.

### HAVING
Say you want to get a list of accounts with total sales greater than $250,000. This isn't something that you can do with a WHERE clause, because you can not include aggregations in a WHERE clause. Instead, you need to use the HAVING clause. The HAVING clause must appear after the GROUP BY clause, because it is executed after any aggregate functions have been performed. Note that the HAVING clause really only works when you're group by 1 or 2 columns.

So, this will NOT work:
```sql
SELECT account_id,
       SUM(total_amt_usd) AS sum_total_amt_usd
FROM orders
/* This will NOT work! */
WHERE SUM(total_amt_usd) >= 250000
GROUP BY 1
ORDER BY 2 DESC
```

However, you can successfully do this:
```sql
SELECT account_id,
       SUM(total_amt_usd) AS sum_total_amt_usd
FROM orders
GROUP BY 1
HAVING SUM(total_amt_usd) >= 250000
ORDER BY 2 DESC
```
As you can see the WHERE clause has been replaced by a HAVING clause that appears after the GROUP BY clause.

### Problems 

1. How many of the sales reps have more than 5 accounts that they manage?
```sql
select sr.name, count(a.id) as acc_count
from sales_reps sr
join accounts a
on a.sales_rep_id = sr.id
group by sr.name
having count(a.id) > 5
```
You can also get this result using a subquery, like this:
```sql
SELECT COUNT(*) num_reps_above5
FROM(SELECT s.id, s.name, COUNT(*) num_accounts
     FROM accounts a
     JOIN sales_reps s
     ON s.id = a.sales_rep_id
     GROUP BY s.id, s.name
     HAVING COUNT(*) > 5
     ORDER BY num_accounts) AS Table1;
```

2. How many accounts have more than 20 orders?
```sql
select accounts.id, count(orders.id) 
from accounts
join orders 
on orders.account_id = accounts.id
group by accounts.id
having count(orders.id) > 20
order by count(orders.id) desc
```
In the solution provided by Udacity, they use count(*) in both the select clause and the having clause, rather than count(orders.id). I guess that works, because we're looking at the inner join of the two tables, which means that every orders.account_id is associated with an account.id.

3. Which account has the most orders?
```sql
select accounts.name, count(orders.id)
from accounts
join orders 
on orders.account_id = accounts.id
group by accounts.name
order by count(orders.id) desc
limit 1
```

4. Which accounts spent more than 30,000 usd total across all orders?
```sql
select a.name, sum(o.total_amt_usd)
from accounts a
join orders o
on o.account_id = a.id
group by a.name
having sum(o.total_amt_usd) > 30000
order by sum(o.total_amt_usd) desc
```
Note that you can alias the sum of the totals and use that alias in the order by clause, but you can't use the alias in the having clause.

5. Which accounts spent less than 1,000 usd total across all orders?
```sql
select a.name, sum(o.total_amt_usd)
from accounts a
join orders o
on o.account_id = a.id
group by a.name
having sum(o.total_amt_usd) < 1000
order by sum(o.total_amt_usd) desc
```

6. Which account has spent the most with us?
```sql
select a.name, sum(o.total_amt_usd)
from accounts a
join orders o
on o.account_id = a.id
group by a.name
order by sum(o.total_amt_usd) desc
limit 1
```

7. Which account has spent the least with us?
```sql
select a.name, sum(o.total_amt_usd)
from accounts a
join orders o
on o.account_id = a.id
group by a.name
order by sum(o.total_amt_usd)
limit 1
```

8. Which accounts used facebook as a channel to contact customers more than 6 times?
```sql
select a.name
from accounts a
join web_events we
on we.account_id = a.id
where we.channel = 'facebook'
group by a.name
having count(a.id) > 6
order by a.name
```
Udacity solved this differently, choosing not to use the where clause and to put the "we.channel = 'facebook'" expression into the having clause. 

9. Which account used facebook most as a channel?
```sql
select a.name, count(a.id) as num_uses
from accounts a
join web_events we
on we.account_id = a.id
where we.channel = 'facebook'
group by a.name
order by num_uses desc
limit 1
```
Udacity notes that using limit like this only works if there are no ties. It's a good idea to check that by trying limit 5 first.

10. Which channel was most frequently used by most accounts?

This question is badly worded. It sounds like they want a result with one channel name and that's it, i.e. the one channel that was used more frequently than any other channel for at least half the accounts. But what they wanted was a list of account names, the most frequently used channel for that account name, and the number of times the channel was used.
```sql
SELECT a.id, a.name, w.channel, COUNT(*) use_of_channel
FROM accounts a
JOIN web_events w
ON a.id = w.account_id
GROUP BY a.id, a.name, w.channel
ORDER BY use_of_channel DESC
LIMIT 10;
```

### Dates
Storing dates as YY-MM-DD is useful because it means that dates will be in the correct chronological order even when sorted as text, i.e. 10-01-23 will appear before 10-01-24, etc.

DATE_TRUNC is a function that allows you to truncate your date to a particular part of your date-time column. Common truncations are *day*, *month*, and *year*.

DATE_PART can be useful for pulling a specific portion of a date, but notice pulling month or day of the week (dow) means that you are no longer keeping the years in order. Rather you are grouping for certain components regardless of which year they belonged in.

Note: 'dow' stands for day of week and returns a number from 0-6 where 0 is Sunday and 6 is Saturday.

Example 1. How much standard paper was sold on April 1st, 2016?
```sql
select date_trunc('day', o.occurred_at) as the_date, 
	sum(o.standard_qty) as total_standard_sold
from orders o
group by 1
having date_trunc('day', o.occurred_at) = '2016-04-01:00:00:00'
```
Here we're truncating the occurred_at column to just the day and calling it the_date. We're also getting the sum of standard_qty and calling it total_standard_qty. We're selecting these aggregates from the orders table. We're also group by the_date, which we can refer to as just "1". And we're setting the truncated date to April, 1st 2016. 

Example 2. Which day of the week does Parch and Posey sell the most paper?
```sql
select date_part('dow', occurred_at) as day_of_week,
   sum(total) as total_qty
from orders
group by 1
order by 2 desc
```
Here, we're selecting the occurred_at column and aggregating by day of the week using the date_trunc function. We're also selecting the total column and aggregating by the sum of total. We've aliased both of those aggregations. We're selecting from the orders table and grouping by day_of_week, which we refer to here as "1". Finally, we're ordering by total_qty, which we refer to here as "2" with the totals in descending order.

### Using numbers in the GROUP BY and ORDER BY clause to refer to previously identified columns
You can use numbers in the GROUP BY and ORDER BY clause to refer to columns previously identified in the SELECT clause. For example,
```sql
SELECT standard_qty, COUNT(*)
FROM orders
GROUP BY 1 /*this 1 refers to standard_qty since it is the first of the columns included in the select statement*/
ORDER BY 1 /*this 1 refers to standard_qty since it is the first of the columns included in the select statement*/
```

### Date and Time Problems
1. Find the sales in terms of total dollars for all orders in each year, ordered from greatest to least. Do you notice any trends in the yearly sales totals?
```sql
select date_trunc('year', o.occurred_at) as year, sum(o.total_amt_usd) as sum
from orders o
group by 1
order by 2 desc
```
Here, we're selecting the occurred_at and total_amt_usd columns from the orders table, but we're truncating the date by year and summing the orders. We're grouping by the truncated occurred_at column, and ordering in descending order by the sum of total_amt_usd.

2. Which month did Parch & Posey have the greatest sales in terms of total dollars? Are all months evenly represented by the dataset?

I used date_trunc, not date_part here. It's tough to tell what the course designers are asking for. I thought they were asking for the single month that had the highest sales, starting back in 2013 and moving right up through 2017 inclusive. But it turns out that that's not what they were asking. Instead, they wanted to know, if you group all of the months together by name, which "month type" has the highest sales. The answer is still December, but the totals are obviously different. They also excluded 
```sql
select date_trunc('month', o.occurred_at) as month, sum(o.total_amt_usd) as sum
from orders o
group by date_trunc('month', o.occurred_at)
order by sum desc
limit 1
```

3. Which year did Parch & Posey have the greatest sales in terms of the total number of orders? Are all years evenly represented by the dataset?

In this case, it makes no difference whether you use date_trunc or date_part, except that the table just looks nice if you use date_part.
```sql
select date_trunc('year', o.occurred_at) as year, count(*) as orders_count
from orders o
group by date_trunc('year', o.occurred_at)
order by orders_count desc
```

4. Which month did Parch & Posey have the greatest sales in terms of the total number of orders? Are all months evenly represented by the dataset?

I made the same mistake here that I did in quesiton 2.
```sql
select date_trunc('month', o.occurred_at) as year, count(*) as orders_count
from orders o
group by date_trunc('month', o.occurred_at)
order by orders_count desc
```

5. In which month of which year did Walmart spend the most on gloss paper in terms of dollars?
```sql
select a.name, date_trunc('month', o.occurred_at) as month, sum(gloss_amt_usd) as gloss_sales
from orders o
join accounts a
on o.account_id = a.id
where a.name = 'Walmart'
group by a.name, date_trunc('month', o.occurred_at)
order by gloss_sales desc
limit 1
```

### CASE Statement
The CASE statement is SQL's way of handling if...then logic. 

- The CASE statement always goes in the SELECT clause.
- CASE must include the following components: WHEN, THEN, and END. ELSE is an optional component to catch cases that didn’t meet any of the other previous CASE conditions.
- You can make any conditional statement using any conditional operator (like WHERE) between WHEN and THEN. This includes stringing together multiple conditional statements using AND and OR.
- You can include multiple WHEN statements, as well as an ELSE statement again, to deal with any unaddressed conditions.

Here's an example. Say you want to find the unit price for standard paper for each order by dividing standard_amt_usd by standard_qty. The answer below will cause an error due to divison by 0.
```sql
SELECT id, account_id, standard_amt_usd/standard_qty AS unit_price
FROM orders
```

However, we can avoid this error by using a case clause.
```sql
SELECT id, account_id,
   case when standard_qty = 0  or standard_qty is null then 0 
         else standard_amt_usd/standard_qty end AS unit_price
FROM orders
LIMIT 10;
```

Here's another example. Say you want to create a column to identify whether a record is within a certain total quantity range. 
```sql
SELECT account_id,
       occurred_at,
       total,
       CASE WHEN total > 500 THEN 'Over 500'
            WHEN total > 300 AND total <= 500 THEN '301 - 500'
            WHEN total > 100 AND total <=300 THEN '101 - 300'
            ELSE '100 or under' END AS total_group
FROM orders
```

### CASE and Aggregations
How do you aggregate based on derived columns created with CASE statements? Here's an example. Say you want to know how many orders have a total quantity under 500 and how many have a total quantity over 500. The query looks like this:
```sql
select case when total < 500 then 'Less than 500'
            else 'Greater than or equal to 500' end as category,
   count(*) as order_count
from orders
/* We use 1 in the group by statement to avoid repeating the entire case statement */
group by 1 
```

Can you do this with a WHERE clause? Yes:
```sql
SELECT COUNT(1) AS orders_over_500_units
FROM orders
WHERE total > 500
```
The limitation is that this kind of query can only handle 1 condition. The results will display only the orders over 500. For more complicated conditions, you need to use case with aggregations.

### Problems with CASE and Aggregations
1. Write a query to display for each order, the account ID, the total amount of the order, and the level of the order - ‘Large’ or ’Small’ - depending on if the order is $3000 or more, or smaller than $3000.
```sql
select o.account_id, o.total_amt_usd, 
   case when o.total_amt_usd > 3000 then 'Large' 
        else 'Small' end
from orders o
```

2. Write a query to display the number of orders in each of three categories, based on the total number of items in each order. The three categories are: 'At Least 2000', 'Between 1000 and 2000' and 'Less than 1000'.

Remember what you're trying to display: a number of orders column, and a category column that has 3 possible categories. The number of orders column is going to be a count of the orders within each category. How do you know that the count will be correctly divided into our 3 possible categories? In the group by clause we group by the case statement, and that ensures that the count will be divided according to the conditions we set up in the case statement.
```sql
select case when total >= 2000 then 'At least 2000'
            when total < 2000 and total >= 1000 then 'Between 1000 and 2000'
            else 'Less than 1000' end as category,
      count(*) as count 
from orders
group by 1
```

3. We would like to understand 3 different levels of customers based on the amount associated with their purchases. 

The top-level includes anyone with a Lifetime Value (total sales of all orders) greater than 200,000 usd. The second level is between 200,000 and 100,000 usd. The lowest level is anyone under 100,000 usd. 

Provide a table that includes the level associated with each account. You should provide the account name, the total sales of all orders for the customer, and the level. Order with the top spending customers listed first.

Again, what do we want to display? Three columns. Column 1 will show the account name. Column 2 will show their total purchase amount per account. Column 3 will show our categories, which we set up with our case statement. 

How do we get the total amount spent per account? We need to sum the total_amt_usd for each order associated with that account. There may be several orders associated with each account. We can use sum(total_amt_usd) to do this and then group by account to make sure the sum is broken up by account.

How do we get the conditions for the case statement? We need to use the same sum(total_amt_usd) function in the first two conditions of the case statement. The group by clause will ensure that we're only dealing with the total_lifetime for this account name.

### For me, the big takeaway is that you can use aggregations inside the conditions of a case statement and your group by clause will make sure that they're grouped appropriately.
```sql
select 
   a.name, 
   sum(o.total_amt_usd) as total_lifetime,
   case when sum(o.total_amt_usd) > 200000 then 'top'
      when sum(o.total_amt_usd) <= 200000 and sum(o.total_amt_usd) > 100000 then 'mid'
      else 'low' end as Lifetime_Value
from accounts a
join orders o
on o.account_id = a.id
group by 1
order by 2 desc
```

4. We would now like to perform a similar calculation to that in question 3, but we want to obtain the total amount spent by customers only in 2016 and 2017. Keep the same levels as in the previous question. Order with the top spending customers listed first.
```sql
select 
   a.name, 
   sum(o.total_amt_usd) as total_lifetime,
   case when sum(o.total_amt_usd) > 200000 then 'top'
      when sum(o.total_amt_usd) <= 200000 and sum(o.total_amt_usd) > 100000 then 'mid'
      else 'low' end as Lifetime_Value
from accounts a
join orders o
on o.account_id = a.id
where o.occurred_at > '2015-12-31'
group by 1
order by 2 desc
```

5. We would like to identify top-performing sales reps, which are sales reps associated with more than 200 orders. Create a table with the sales rep name, the total number of orders, and a column with top or not depending on if they have more than 200 orders. Place the top salespeople first in your final table.
```sql
select sr.name, count(o.id),
   case when count(o.id) > 200 then 'top'
        else 'bottom' end
from sales_reps sr
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id
group by 1
order by 2 desc
```

6. Question 5 didn't account for the middle, nor the dollar amount associated with the sales. Management decides they want to see these characteristics represented as well. We would like to identify top-performing sales reps, which are sales reps associated with more than 200 orders or more than 750000 in total sales. The middle group has any rep with more than 150 orders or 500000 in sales. Create a table with the sales rep name, the total number of orders, total sales across all orders, and a column with top, middle, or low depending on these criteria. Place the top salespeople based on the dollar amount of sales first in your final table. You might see a few upset salespeople by this criteria!
```sql
select sr.name, count(o.id), sum(o.total_amt_usd),
   case when count(o.id) > 200 or sum(o.total_amt_usd) > 200000 then 'top'
        when count(o.id) > 150 or sum(o.total_amt_usd) > 150000 then 'middle'
        else 'bottom' end
from sales_reps sr
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id
group by 1
order by 3 desc
```



## Subqueries and Temporary Tables

### Goals for Lesson 4:
- Create subqueries to solve real-world problems
- Differentiate between Subqueries and Joins
- Implement the best type of Subqueries
- Consider the tradeoffs to using subqueries
- Implement the best subquery strategy

### Why do we need subqueries?
We need subqueries, because somtimes, the question you are trying to answer can't be solved with the set of tables in your database. Instead, there's a need to manipulate existing tables and join them to solve the problem at hand. Subqueries can do that.

### What exactly are subqueries?
A subquery is a query within a query. As far as I can tell "subquery" and "inner query" are interchangable. 

Here's an example:
```sql
SELECT product_id,
       name,
       price
FROM db.product
/* Note that subqueries always appear in parentheses) */
Where price > (SELECT AVG(price)
              FROM db.product)
```
Here we want to show a table including product ids, names, and prices, but only where the price is greater than the average price of products. To get the average price of products, we run a separate subquery with its own SELECT and FROM clauses. The lesson doesn't make it clear whether there is any way to construct this query without using a subquery.

### When do you use a subquery?
In the example above, you have to use a subquery, because you can't use just an aggregation in a WHERE clause. In this case, the whole subquery is executed first and the only thing the outer query sees in a number representing whatever that average is, e.g. WHERE price > 40.23.

Here are some examples of situations in which you would need to use a subquery:
| Problem                                                                           | Existing Table                            | Subquery              |
|-----------------------------------------------------------------------------------|-------------------------------------------|-----------------------|
| ID the top-selling Amazon products in months where sales have exceeded $1m        | Amazon daily sales                        | Daily to month        |
| Examine the average price of a brand’s products for the highest-grossing brands   | Product pricing data across all retailers | Individual to average |
| Order the annual salary of employees that are working less than 150 hours a month | Daily time-table of employees             | Daily to Monthly      |

### What the difference between joins and subqueries?
Both joins and subqueries combine data from one or more tables into a single result. They also work similarly under the hood. However, the strength of joins is that they allow you to display any number of columns or derived columns from both tables. Whereas the strength of subqueries is that they allow you to build an output that will be used in an outer query. There are some tradeoffs regarding performance and readability when trying to decide whether to use a join or subquery to solve a problem.

### Differences between joins and subqueries.
(If you're just looking at the markdown file, the table below will look really strange. You need to view the file in a markdown viewer.)

|              | Subquery                                                                                                                                                                          | Join                                                                                                                                 |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Use Cases    | When an existing table needs to be manipulated or aggregated to then be joined to a larger table.                                                                                 | A fully flexible and discretionary use case where a user wants to bring two or more tables together and select and filter as needed. |
| Syntax       | A subquery is query within a query. The syntax has multiple SELECT and FROM clauses.                                                                                              | A join stitches together multiple tales with a common key or column. A join clause cannot stand and be run independently.            |
| Dependencies | A subquery clause can be run completely independently. Why trying to debug code, subqueries are often run independently to pressure test results before running the larger query. | A join clause cannot stand and be run independently.                                                                                 |

### Similarities between joins and subqueries.
- Output: Both bring together multiple tables to generate a single output. 
- Deep-Dive: They're similar under the hood.

### More similarities and differences

Subqueries:
- Output: Either a scalar (a single value) or rows that have met a condition. 
- Use Case: Calculate a scalar value to use in a later part of the query (e.g., average price as a filter). 
- Dependencies: Stand independently and be run as complete queries themselves.

Joins:
- Output: A joint view of multiple tables stitched together using a common “key”. 
- Use Case: Fully stitch tables together and have full flexibility on what to “select” and “filter from”. 
- Dependencies: Cannot stand independently. (There's an exception for correlated nested or inline queries.)

### Placement and Dependencies
Placement:
There are four places where subqueries can be inserted within a larger query:
- With - This subquery is used when you’d like to “pseudo-create” a table from an existing table and visually scope the temporary table at the top of the larger query. For example,
```sql
WITH subquery_name (column_name1, ...) AS
 (SELECT ...)
SELECT ...
```

- Nested - This subquery is used when you’d like the temporary table to act as a filter within the larger query, which implies that it often sits within the where clause. For example,
```sql
SELECT s.s_id, s.s_name, g.final_grade
FROM student s, grades g
WHERE s.s_id = g.s_id
IN (SELECT final_grade FROM grades g WHERE final_grade > 3.7);
```

- Inline - Similar to the with case, but instead of the temporary table sitting on top of the larger query, it’s embedded within the from clause. For example,
```sql
SELECT student_name
FROM
  (SELECT student_id, student_name, grade
   FROM student
   WHERE teacher =10)
WHERE grade >80;
```

- Scalar - This subquery is used when you’d like to generate a scalar value to be used as a benchmark of some sort.
```sql
SELECT s.student_name
  (SELECT AVG(final_score)
   FROM grades g
   WHERE g.student_id = s.student_id) AS
     avg_score
FROM student s;
```

With and Nested subqueries are most advantageous for readability.

Scalar subqueries are advantageous for performance and are often used on smaller datasets.

Dependencies:
A subquery can be dependent on the outer query or independent of the outer query.

(This is the article that the instructor recommends: [Microsoft's Article on Subqueries](https://learn.microsoft.com/en-us/sql/relational-databases/performance/subqueries?view=sql-server-ver15) Note: I'm not sure how applicaable material from this MS article is to standard SQL or PostgreSQL.)

### Our First Subquery

Problem:  On an average day, which channels send the most traffic to Parch and Posey?

So, we already know how to see how much total web traffic each channel sends. 
```sql
select channel, count(*) as event_count
from web_events
group by 1
```

We can also break this down a little further to the total traffic sent to each channel per day.
```sql
select channel, count(*) as event_count, date_trunc('day', occurred_at) as the_day
from web_events
group by 1, 3
order by 1, 3
```

But if we want to see the average number of events per channel per day, then we have to use a subquery, specifically an inline query, which means that the subquery will appear in the FROM clause.

We want something like this:
```sql
select channel, avg(event_count) as avg_event_count
from ...
group by channel
order by avg_event_count desc
```

But how do we get event_count? That's where the subquery comes in.
```sql
select channel, avg(event_count) as avg_event_count
from (select 
        channel,
        count(*) as event_count, /* Here it is */
        date_trunc('day', occurred_at) as day
      from web_events
      group by 1, 3) as my_subquery
group by 1
order by 2 desc
```
As you can see, the second query we tried is now the subquery in the solution. That subquery gave us the correct number of total events per day for each channel.

Put another way, in order to get our average, we needed a table that looked like this:

| "channel"  | "event_count" | "day"                 |
|------------|---------------|-----------------------|
| "twitter"  | 1             | "2016-05-30 00:00:00" |
| "adwords"  | 1             | "2016-05-28 00:00:00" |
| "banner"   | 3             | "2016-05-04 00:00:00" |
| "twitter"  | 1             | "2016-08-26 00:00:00" |
| "adwords"  | 1             | "2016-10-25 00:00:00" |
| "organic"  | 1             | "2016-08-24 00:00:00" |
| "facebook" | 2             | "2016-09-04 00:00:00" |

And that's what the subquery gave us. With this query, we can now get an average for the event_count column per channel.

### Steps when building a subquery:
1. Build the Subquery: The aggregation of an existing table that you’d like to leverage as a part of the larger query.
2. Run the Subquery: Because a subquery can stand independently, it’s important to run its content first to get a sense of whether this aggregation is the interim output you are expecting.
3. Encapsulate and Name: Close this subquery off with parentheses and call it something. In this case, we called the subquery table ‘sub.’
4. Test Again: Run a SELECT * within the larger query to determine if all syntax of the subquery is good to go.
5. Build Outer Query: Develop the SELECT * clause as you see fit to solve the problem at hand, leveraging the subquery appropriately.

### Subquery Formatting
A subquery can appear in several different places within a query. In the above example, we saw a subquery in the FROM clause. That's called an **inline** query. But subqueries can appear in many other places. Another place a subquery can appear is in a WHERE clause. When it does, that's called a **nested** subquery.

NOTE: Do not include an alias for your subquery when you write a subquery in a conditional statement. This is because the subquery is treated as an individual value (or set of values in the IN case) rather than as a table. Nested and Scalar subqueries often do not require aliases the way With and Inline subqueries do.

### Problem: Return orders that occurred in the same month as Parch and Posey's first ever order.

To solve this problem we need a query that looks like this:
```sql
select * 
from orders
where date_trunc('month', occurred_at) = /*month of first ever order order*/
```
However, there's no way to get the month of the first ever order without using a subquery.

To get the month of the first ever order we need this:
```sql
select date_trunc('month', min(occurred_at)) as min_month
from orders
```
When you put it together, it looks like this:
```sql
select * 
from orders
where date_trunc('month', occurred_at) = (select date_trunc('month', min(occurred_at)) as min_month
from orders)
order by occurred_at
```
Why do we have to use a subquery here rather than just inserting the min function into the WHERE clause? Because we can't use aggregations in a WHERE clause. Well, then why can't we use a HAVING clause? I have no idea, but I tried it and it various ways and it doesn't work.

### Problem: Return the average quantities of each type of paper sold in the same month identified in the previous problem.

```sql
SELECT AVG(standard_qty) avg_std, AVG(gloss_qty) avg_gls, AVG(poster_qty) avg_pst
FROM orders
WHERE DATE_TRUNC('month', occurred_at) = 
     (SELECT DATE_TRUNC('month', MIN(occurred_at)) FROM orders);
```
The FROM and WHERE clauses are identical to the ones in the previous problem. What's changed is the SELECT clause. We just need to get the average for each of the paper quantities.

### Problem: Return the total amount spent on all orders in the same month identified in the previous problem.

```sql
select sum(total_amt_usd)
from orders
where date_trunc('month', occurred_at) = (select date_trunc('month', min(occurred_at)) as min_month
from orders)
```
Again, the FROM and WHERE clauses are identical to the previous problem. What's changed is the SELECT clause. We just need to get the sum of the total amount of money spent.

### Dependencies: Simple versus Correlated Subqueries
**Simple Subquery**: The inner subquery is completely independent of the larger query.

**Correlated Subquery**: The inner subquery is dependent on the larger query. 

Correlated subqueries are used for row-by-row processing. Each subquery is executed once for every row of the outer query. 

With a normal nested subquery, the inner SELECT query runs first and executes once, returning values to be used by the main query. A correlated subquery, however, executes once for each candidate row considered by the outer query. In other words, the inner query is driven by the outer query. 

A correlated subquery is one way of reading every row in a table and comparing values in each row against related data.  It is used whenever a subquery must return a different result or set of results for each candidate row considered by the main query.

Here's the general form of a correlated subquery:
```sql
SELECT column1, column2, ....
FROM table1 outer
WHERE column1 operator
                    (SELECT column1, column2
                     FROM table2
                     WHERE expr1 = outer.expr2);
```

Simple subqueries are easier to read. However, some problems require that you use a correlated subquery. 

Other subqueries could be written either way: as a simple subquery or as a correlated subquery. The lesson provides an example using an employee database.

First, here's the simple subquery version:
```sql
WITH dept_average AS 
  (SELECT dept, AVG(salary) AS avg_dept_salary
   FROM employee
   GROUP BY employee.dept
  )
SELECT E.eid, E.ename, D.avg_dept_salary
FROM employee E
JOIN dept.average D
ON E.dept = D.dept
WHERE E.salary > D.avg_dept_salary
```
And here's the correlated subquery version:
```sql
SELECT employee_id, name
FROM employees_db emp
WHERE salary > (SELECT AVG(salary)
                FROM employees_db
                WHERE department = emp.department);
```

Here's another example. Imagine that you want to get the first and last name of each student, their GPA, and the university that they attend from a database. However, you only want students whose GPA is higher than the average GPA of all students at that particular university. In other words, if you're looking at a student from Ohio State University, you want to know that this student has a higher GPA than the average OSU student.

To do this, you'll need a subquery in which you calculate the average GPA
```sql
SELECT first_name, last_name, GPA, university
FROM student_db outer_db
WHERE GPA > (SELECT AVG(GPA) 
            FROM student_db 
            WHERE university = outer_db.university);
```

### Views
Assume you run a complex query to fetch data from multiple tables. Now, you’d like to query again on the top of the result set. And later, you’d like to query more on the same result set returned earlier. So, there arises a need to store the result set of the original query, so that you can re-query it multiple times. This necessity can be fulfilled with the help of views.

Views are virtual tables that are derived from the tables in the db.

The general form is:
```sql
CREATE VIEW <VIEW_NAME>
AS
SELECT …
FROM …
WHERE …
```
### Problem: Suppose you are managing sales representatives who are looking after the accounts in the Northeast region only. The details of such a subset of sales representatives can be fetched from two tables, and stored as a view:
```sql
create view v1
as
select S.id, S.name as Rep_Name, R.name as Region_Name
from sales_reps S
join region R
/*FYI to myself - I completely forgot that you can do this */
on S.region_id = R.id and R.name = 'Northeast';
```
### Problem: Provide the name for each region for every order, as well as the account name and the unit price they paid (total_amt_usd/total) for the order. Your final result should have 3 columns: region name, account name, and unit price. Store this as a view.
```sql
CREATE VIEW V2
AS
SELECT r.name region, a.name account, 
       o.total_amt_usd/(o.total + 0.01) unit_price
FROM region r
JOIN sales_reps s
ON s.region_id = r.id
JOIN accounts a
ON a.sales_rep_id = s.id
JOIN orders o
ON o.account_id = a.id;
```
Points to Remember

Can we update the base tables by updating a view?

Since views do not exist physically in the database, it is may or may not be possible to execute UPDATE operations on views. It depends on the SELECT query used in the view definition. Generally, if the SELECT statement contains either an AGGREGATE function, GROUPING, or JOIN, then the view may not update the underlying base tables.

Can we insert or delete a tuple in the base table by inserting or deleting a tuple in a view?

Again, it depends on the view definition. If a view is created from a single base table, then yes, you can insert/delete tuples by doing so in the view.

Can we alter the view definition?

Most of the databases allow you to alter a view. For example, Oracle and IBM DB2 allows us to alter views and provides CREATE OR REPLACE VIEW option to redefine a view.

### Problem: What is the top channel used by each account to market products?
First, I get all channels per account name with a count of the channel, like this:
```sql
select a.name as name, channel as channel, count(channel) as channel_count
from web_events we
join accounts a
on we.account_id = a.id
group by 1, 2
order by 1, 3
```
But what I need is not all of the channels for each account, but just the top channel - the channel with the largest count. So, I sort of want this max(count(channel)). You can't do that. You can't aggregate on an aggregation.

Do I need to isolate this part?
```sql
select count(channel) as channel_count from web_events
```
So that I can do this:
```sql
select a.name, we.channel, max(sub.channel_count)
```
It turns out, no. I actually want almost the entire query to be in the subquery, so that the outer query just grabs a couple of things from the subquery, and most importantly, applies max(sub.channel_count). It looks like this:
```sql
select sub.name, max(sub.channel_count)
from (
  select a.name as name, channel as channel, count(channel) as channel_count
  from web_events we
  join accounts a
  on we.account_id = a.id
  group by 1
  order by 1, 3
) as sub
group by 1

```
One of the things that tripped me up is that I wanted the channel name to be in the query. You can't do that without adding another subquery, because if you add sub.channel to the SELECT clause in the outer query, then you have to add it to the GROUP BY clause, which messes things up and just ends up giving you as a result the subquery again. I don't really get why that is, but that's what happened when I tried it.

Problem: How often was the same channel used?
So now we have the MAX usage number for a channel for each account. Now we can use this to filter the original table to find channels for each account that match the MAX amount for their account.

This is what it looks like:
```sql
/* In the end we want to end up with a table of id, name, the most frequently used channel, and the count of that channel */
SELECT t3.id, t3.name, t3.channel, t3.ct
/* This subquery provides a table with the id, name, all channels, and the count for each channel, aliased as ct */
FROM (SELECT a.id, a.name, we.channel, COUNT(*) ct
     FROM accounts a
     /* To get account names, we need to join the accounts table with the web_events table. The order doesn't matter. You can select from web_events and then join accounts or select from accounts and then join web_events. */
     JOIN web_events we
     On a.id = we.account_id
     /* To group by name and channel type, we need to GROUP BY right here. This tells the db how we want to split up the channel count. */
     GROUP BY a.id, a.name, we.channel) t3
/* Now we have to JOIN another subquery that provides a table of the id, name, and the MAX count as max_chan. This subquery doesn't provide the channel name.  */
JOIN (
  SELECT t1.id, t1.name, MAX(ct) max_chan
  /* The query above is created using the same subquery that we earlier aliased as t3. But we have to repeat it here and alias it as t1. */
  FROM (
    SELECT a.id, a.name, we.channel, COUNT(*) ct
    FROM accounts a
    JOIN web_events we
    ON a.id = we.account_id
    GROUP BY a.id, a.name, we.channel
    ) t1
  /* This time we just group by id and name */
  GROUP BY t1.id, t1.name
) t2
/* We join our two queries on the id key and also on the condition that max_chan from t2 is equal to ct from t3. That condition is what allows us to see the channel name and the max count.*/
ON t2.id = t3.id AND t2.max_chan = t3.ct
ORDER BY t3.id;
```
This is pretty long. I'm sure there's a way to reuse t3/t1, maybe with a with clause or a view.

One more time, but factoring out the t3/t1 subquery
```sql
SELECT t3.id, t3.name, t3.channel, t3.ct
FROM t3
JOIN (SELECT t1.id, t1.name, MAX(ct) max_chan
      FROM t1
      GROUP BY t1.id, t1.name) t2
ON t2.id = t3.id AND t2.max_chan = t3.ct
ORDER BY t3.id;
```
This makes it a little bit clearer to me. 

### Problems from section 4.17 and their solutions

1. Provide the name of the sales_rep in each region with the largest amount of total_amt_usd sales.

Rephrase: There's one sales rep in each region who has the largest total sales in that region, beating all other sales reps in that region. Get the name of that person for each region.
```sql
/* First, get sales reps names and regions and total sales per sales rep. Order it by region and total sales (desc) to see who in each region has the best sales. */

/*
select sr.id as sr_id, sr.name as sr_name, r.name as reg_name, sum(o.total_amt_usd) as total_sales
from sales_reps sr
join region r
on sr.region_id = r.id
join accounts a
on a.sales_rep_id = sr.id
join orders o
on o.account_id = a.id
group by 1,2,3
order by reg_name, total_sales desc
*/

/* Next, get the max total sales per region */
/*
select sub.reg_name, max(sub.total_sales) as max_sales
from (select sr.id as sr_id, sr.name as sr_name, r.name as reg_name, sum(o.total_amt_usd) as total_sales
	from sales_reps sr
	join region r
	on sr.region_id = r.id
	join accounts a
	on a.sales_rep_id = sr.id
	join orders o
	on o.account_id = a.id
	group by 1,2,3
	order by reg_name, total_sales desc) as sub
group by 1
order by 1
*/

/* Finally, join the above to queries to get the sales rep name from the first query and the region and max total sales from the second query. I'm joining on the region name from each query, because that's the only thing they have in common, but maybe I should have used region id. */
select sub1.sr_name, sub2.reg_name, sub2.max_sales
from (
      select sr.id as sr_id, 
              sr.name as sr_name, 
              r.name as reg_name, 
              sum(o.total_amt_usd) as total_sales
      from sales_reps sr
      join region r
      on sr.region_id = r.id
      join accounts a
      on a.sales_rep_id = sr.id
      join orders o
      on o.account_id = a.id
      group by 1,2,3
      ) as sub1
join (
      select sub.reg_name, 
             max(sub.total_sales) as max_sales
      from (
            select sr.id as sr_id, 
                  sr.name as sr_name, 
                  r.name as reg_name, 
                  sum(o.total_amt_usd) as total_sales
            from sales_reps sr
            join region r
            on sr.region_id = r.id
            join accounts a
            on a.sales_rep_id = sr.id
            join orders o
            on o.account_id = a.id
            group by 1,2,3
            ) as sub
      group by 1
    ) as sub2
on sub1.reg_name = sub2.reg_name
and sub1.total_sales = sub2.max_sales

```

2. For the region with the largest (sum) of sales total_amt_usd, how many total (count) orders were placed?

Rephrase: How many orders have been placed in the top selling region? Sounds like they just want a number.
- Which is the top selling region?
- How many orders have been placed in that region?

You can see the top performing Northeast in the table resulting from this query:
```sql
select r.name as region_name, count(*) as total_orders, sum(total_amt_usd) as total_sales
from orders o
join accounts a
on o.account_id = a.id
join sales_reps sr
on a.sales_rep_id = sr.id
join region r
on sr.region_id = r.id
group by 1
```
But how do we return just the number of orders for the Northeast? The simple solution is to use ORDER BY and LIMIT to return just the Northeast from the query above. However, that's not in the spirit of practicing our subquery skills.

This was very difficult for me. I thought we could do something similar to what we did in problem 1 and join the above query with a second query shown below that returns the max(sub.total_sales):
```sql
select max(sub.total_sales) as max_sales
from (
  select r.name as region_name, 
         sum(total_amt_usd) as total_sales
  from orders o
  join accounts a
  on o.account_id = a.id
  join sales_reps sr
  on a.sales_rep_id = sr.id
  join region r
  on sr.region_id = r.id
  group by 1
) as sub
group by 1
```
The join would look like this:
```sql
select sub1.region_name, sub1.total_orders
from (
  select r.name as region_name, 
         count(*) as total_orders, 
         sum(total_amt_usd) as total_sales
  from orders o
  join accounts a
  on o.account_id = a.id
  join sales_reps sr
  on a.sales_rep_id = sr.id
  join region r
  on sr.region_id = r.id
  group by 1
  ) as sub1
join (
    select max(sub.total_sales) as max_sales
    from (
        select r.name as region_name,  
               sum(total_amt_usd) as total_sales
        from orders o
        join accounts a
        on o.account_id = a.id
        join sales_reps sr
        on a.sales_rep_id = sr.id
        join region r
        on sr.region_id = r.id
        group by 1
    ) as sub
) as sub2
on sub1.total_sales = sub2.max_sales
```
It works! The thing that threw me was that in the ON clause you need to specify that you only want to join on the condition that the total_sales from "sub1" is equal to the max_sales from "sub2" even though you're not displaying total or max sales. 

The suggested solution is different. That solution uses a HAVING clause:
```sql
SELECT r.name as region_name, COUNT(o.total) total_orders
FROM sales_reps sr
JOIN accounts a
ON a.sales_rep_id = sr.id
JOIN orders o
ON o.account_id = a.id
JOIN region r
ON r.id = sr.region_id
GROUP BY 1
HAVING SUM(o.total_amt_usd) = (
      SELECT MAX(total_amt)
      FROM (SELECT r.name region_name, 
                   SUM(o.total_amt_usd) total_amt
              FROM sales_reps s
              JOIN accounts a
              ON a.sales_rep_id = s.id
              JOIN orders o
              ON o.account_id = a.id
              JOIN region r
              ON r.id = s.region_id
              GROUP BY r.name) sub);
```
Here, we're getting the total_orders by region, but then we're using the HAVING clause to filter that down to just the region with the highest total sales. We need a subquery to do that.

3. How many accounts had more total purchases than the account name which has bought the most standard_qty paper throughout their lifetime as a customer?

Rephrase: How many accounts has total purchases that were greater than the account with the most standard paper purchased? 
- Which account purchased the most standard paper
- Which accounts purchased more paper (of all types) than the answer to the previous question

We can write a query to get account names and the sum of the total quantities of all types of paper purchased, grouped by account. When I was working on this, I also threw in the sum of standard paper bought. That way, I can check my work. That's the outer query.

Then, in the HAVING clause, we need to filter down to accounts that have bought more total paper of all types than the the quantity of standard paper bought by the account that bought the most standard paper out of all accounts. This is confusing. What we're ultimately looking for is a list of accounts, but what we're comparing here is two quantities. On the left-hand side of the comparison operator we need the sum quantity of all types of paper. On the right-hand side we need the quantity of standard paper purchased by the account that purchased the most standard paper by quantity. That requires a subquery. That subquery forms the right-hand side of the equality in the HAVING clause below. It took me a moment to realize that we can just select max(sub.total_standard). We don't have to worry about including account names. Account names are included in the sub-subquery (called "sub"), and in "sub" we group by those account names. So, when the MAX function does its work, it's getting us the right thing.
```sql
select a.name, 
       sum(o.total) as total_all_types, 
       sum(o.standard_qty) as total_standard
from accounts a
join orders o
on o.account_id = a.id
group by 1
having sum(o.total) > (select max(sub.total_standard) 
					   from (select a.name, sum(o.standard_qty) as total_standard 
							 from orders o
							 join accounts a
							 on o.account_id = a.id
							 group by 1
							) as sub
					  )
order by 3 desc
```

4. For the customer that spent the most (in total over their lifetime as a customer) total_amt_usd, how many web_events did they have for each channel?

Rephrase: How many web events per channel did the customer who spent the most money over their customer lifetime have?

After a lot of messing around and trying out different things, I eventually figured out that I needed to use a subquery to get just the name of the company that spent the most on paper and use that subquery on the right-hand side of a HAVING clause with an equality operator. On the left-hand side is the name of the company. The outer query just need to get the events per channel per company.
```sql
/* web events per channel per company */
select 
  a.name as account_name,
  we.channel as channel,
  count(*) as count
from web_events we
join accounts a
on we.account_id = a.id
/* I had an extra join here at first and it messes everything up */
-- join orders o
-- on o.account_id = a.id
group by 1, 2
having a.name = (
	select 
		sub.account_name 
    from (
      select 
        a.name as account_name, 
		    sum(o.total_amt_usd) as total_spent
      from accounts a
	  join orders o
	  on o.account_id = a.id
	  group by 1
	  order by 2 desc
	  limit 1) as sub
);
```
Except that this is not the answer given in the lesson. The answer given in the lesson is a bit different.
```sql
SELECT 
  a.name, 
  w.channel, 
  COUNT(*)
FROM accounts a
JOIN web_events w
ON a.id = w.account_id 
AND a.id =  (
  SELECT id
  FROM (
    SELECT 
      a.id, 
      a.name, 
      SUM(o.total_amt_usd) tot_spent
    FROM orders o
    JOIN accounts a
    ON a.id = o.account_id
    GROUP BY a.id, a.name
    ORDER BY 3 DESC
    LIMIT 1) inner_table)
GROUP BY 1, 2
ORDER BY 3 DESC;
```
Let's annotate that to see if I can figure out what they did.
```sql
/* Begin by getting the customer name, channels, and count of web events for each channel */
SELECT 
  a.name, 
  w.channel, 
  COUNT(*)
FROM accounts a
JOIN web_events w
/* The accounts and web_events tables have to be joined on a.id and w.account_id */
ON a.id = w.account_id 
/* And also on a.id and ... */
AND a.id =  (
  /* ...the account id ... */
  SELECT id
  /* ...pulled from the inner_table. That inner_table gets...  */
  FROM (
    /* ... account id and name and total spent */
    SELECT 
      a.id, 
      a.name, 
      SUM(o.total_amt_usd) tot_spent
    FROM orders o
    JOIN accounts a
    ON a.id = o.account_id
    /* grouped by account id and name. This ensures that the spending is broken out by account */
    GROUP BY a.id, a.name
    /* ordered by tot_spent descending */
    ORDER BY 3 DESC
    /* and get just the top spender */
    LIMIT 1) inner_table)
/* The outer query is grouped by account name and web channel */
GROUP BY 1, 2
ORDER BY 3 DESC;
```

5. What is the lifetime average amount spent in terms of total_amt_usd for the top 10 total spending accounts?

Rephrase: Get the average amount spent by the top 10 accounts in terms of lifetime spending.

I know I'll need a subquery for the top 10 accounts in terms of total spending, so here it is:
```sql
select a.name as account_name, sum(o.total_amt_usd) as total_spending
from accounts a
join orders o
on o.account_id = a.id
group by 1
order by 2 desc
limit 10
```
Then the outer query would just be the select statement and the subquery would go in the FROM clause:
```sql
select avg(sub.total_spending)
from (
	select 
		a.name as account_name, 
		sum(o.total_amt_usd) as total_spending
	from accounts a
	join orders o
	on o.account_id = a.id
	group by 1
	order by 2 desc
	limit 10
) as sub;
```

6. What is the lifetime average amount spent in terms of total_amt_usd, including only the companies that spent more per order, on average, than the average of all orders?

Rephrase: On average, what did the customers who spent more than the average spending of all customers spend?
- What was the average spending among all customers?
- What was the average spending of customers who spent more than that?

Start with the subquery about the average spending of all customers
```sql
select avg(o.total_amt_usd)
from orders o
```
Now use that subquery in an outer query that gets all of the accounts that spent more than the average and what that average is.
```sql
SELECT o.account_id, AVG(o.total_amt_usd)
FROM orders o
GROUP BY 1
HAVING AVG(o.total_amt_usd) > 
  /* average spending per customer over lifetime */
  (
    SELECT AVG(o.total_amt_usd) avg_all
    FROM orders o
  );
```
Now average the spending by just those accounts.
```sql
-- Get average spending of the average spending of a subset of accounts 
SELECT AVG(avg_amt)
/* Get account ids and average spending per account id, but filtering down to just those account ids HAVING average spending greater than the overall average spending by all accounts */
FROM (
  SELECT 
    o.account_id, 
    AVG(o.total_amt_usd) avg_amt
  FROM orders o
  -- We want average spending per account
  GROUP BY 1
  -- We want to filter down to...
  HAVING 
    -- Average spending greater than...
    AVG(o.total_amt_usd) > (
      /* Overall, average spending, i.e. sum of all spending divided by the total number of accounts */
      SELECT 
        AVG(o.total_amt_usd) avg_all
      FROM orders o
    )
) sub;
```

### Subquery Tradeoffs

Most queries can be solved in a wide variety of ways, so, when writing a query, it's important to consider:
- Readability: How easy is it for someone else to understand
- Performance: How quickly is it executed
    - Example: Correlated subqueries (which are interdependent on outer query) are often slower than "with" subqueries (which create a temporary view)
- What the DB is actually doing: 
- DRYness: Where you might need to use a subquery multiple times

See Chapter 8 of the MySQL Reference Manual for more information on optimization: https://dev.mysql.com/doc/refman/8.0/en/optimization.html

(Sure. I'll get on that right away. Let me just run an read all of the books written about SQL instead of you explaining it to me. /endcomplaint)

### Subquery Strategy

1. Do I really a subquery or might a join or aggregation suffice?
2. If a subquery is necessary, what's the best placement: "with", nested, inline, or scalar?

### With Subqueries

When should you use it:
- When you want to create a version of a table to be used in the larger query (e.g. aggregated daily prices to an average price table)

Advantages:
- Scoped
- Easy to read

Here's an example:
```sql
WITH average_price as
( 
  SELECT 
    brand_id, 
    AVG(product_price) as brand_avg_price
  FROM 
    product_records
  /* Why is there no group by statement here? Should we see GROUP BY brand_id? */
),
SELECT 
  a.brand_id, 
  a.total_brand_sales, 
  b.brand_avg_price
FROM brand_table a
JOIN average_price b
ON b.brand_id = a.brand_id
ORDER BY a.total_brand_sales desc;
```

**CTE** stands for Common Table Expression. A Common Table Expression in SQL allows you to define a temporary result, such as a table, to then be referenced in a later part of the query.

Problem: Get average events per channel per day.

Solution with nested query:
```sql
SELECT 
  channel, 
  AVG(events) AS average_events
FROM (
  SELECT 
    DATE_TRUNC('day',occurred_at) AS day,
    channel, 
    COUNT(*) as events
  FROM web_events 
  GROUP BY 1,2
) sub
GROUP BY channel
ORDER BY 2 DESC;
```
Solution with WITH clause:
```sql
WITH events AS (
  SELECT 
    DATE_TRUNC('day',occurred_at) AS day, 
    channel,
    /* In the outer query, we use events to get avg(events) */ 
    COUNT(*) as events
  FROM web_events 
  GROUP BY 1,2
)
SELECT 
  channel, 
  AVG(events) AS average_events
/* Notice that the CTE "events" has the same name as the column "events" and it doesn't seem to matter. */
/* Also, you don't refer in the SELECT statement to events.events, because there aren't any other tables. Just "events" is enough. */
/* Also notice that you aren't JOINing your subquery with web_events. You're just using the subquery as the FROM table*/
FROM events
GROUP BY channel
ORDER BY 2 DESC;
```

It's also possible to create multiple tables with WITH:
```sql
WITH table1 AS (
          SELECT *
          FROM web_events),

     table2 AS (
          SELECT *
          FROM accounts)


SELECT *
FROM table1
JOIN table2
ON table1.account_id = table2.id;
```

### WITH Problems

1. Provide the name of the sales_rep in each region with the largest amount of total_amt_usd sales.

Rephrase: Who in each region got the most sales for all time?
  - Each region has a sales rep who performed better than other sales reps in terms of total sales in that region
  - In each region
    - A sales rep performed better 
      - than other reps
        - In that region

```sql
WITH 
  t1 AS (
    /* Get total sales by reps by region */
    SELECT 
      s.name rep_name, 
      r.name region_name, 
      SUM(o.total_amt_usd) total_amt
    FROM sales_reps s
    JOIN accounts a
    ON a.sales_rep_id = s.id
    JOIN orders o
    ON o.account_id = a.id
    JOIN region r
    ON r.id = s.region_id
    GROUP BY 1,2
    ORDER BY 3 DESC), 
  t2 AS (
    /* Get max sales by region */
    SELECT 
      region_name, 
      MAX(total_amt) total_amt
    FROM t1
    GROUP BY 1)
/* Get rep, region, and total sales */
SELECT t1.rep_name, t1.region_name, t1.total_amt
FROM t1
JOIN t2
/* Join the two tables only when the region matches and */
ON t1.region_name = t2.region_name 
  /* the total sales is equal to the max sales (which will only be true for one sales rep in each region */
  AND t1.total_amt = t2.total_amt;

```
2. For the region with the largest sales total_amt_usd, how many total orders were placed?

My solution is slightly different from the suggested solution. I'm only joining on the total sales equaling the max total sales. I think this might create a problem when 2 or more regions are tied for total or max total sales. I'm basically using the ON clause as though it was a HAVING clause. It's a bit simpler to read, because the outer query is very straightforward.
```sql
with 
  t1 as (
    -- Get the total sales and total orders by region
    select 
      r.name region_name, 
      sum(o.total_amt_usd) total_amt,
      count(o.id) as order_count
    from region r
    join sales_reps sr
    on sr.region_id = r.id
    join accounts a
    on a.sales_rep_id = sr.id
    join orders o
    on o.account_id = a.id
    group by 1
  ),
  t2 as ( 
    -- Get the highest total sales figure
    select max(total_amt) max_total
    from t1
  )
-- Get the total sales by region
select 
  region_name,
  order_count
from t1
join t2
-- Filter to the one region that has the highest total sales
on t1.total_amt = t2.max_total
```

This is the suggested solution below. 
```sql
WITH t1 AS (
   SELECT r.name region_name, SUM(o.total_amt_usd) total_amt
   FROM sales_reps s
   JOIN accounts a
   ON a.sales_rep_id = s.id
   JOIN orders o
   ON o.account_id = a.id
   JOIN region r
   ON r.id = s.region_id
   GROUP BY r.name), 
t2 AS (
   SELECT MAX(total_amt)
   FROM t1)
SELECT r.name, COUNT(o.total) total_orders
FROM sales_reps s
JOIN accounts a
ON a.sales_rep_id = s.id
JOIN orders o
ON o.account_id = a.id
JOIN region r
ON r.id = s.region_id
GROUP BY r.name
HAVING SUM(o.total_amt_usd) = (SELECT * FROM t2);
```
In this solution, t1 only gets region name and total sales. It doesn't get a count of orders. T2 is identical to my t2. Then, in the outer query, this solution gets the region name and the count of orders. That means we have to go through the sequence of joins again, but we never join tables t1 or t2. Instead, we get total orders by region name and then use a HAVING clause to tell the query to filter down sum(total_amt_usd) = (select * from t2). This is interesting, because the outer query is no dependent on t1 directly at any point, only on t2 in the HAVING clause.

3. How many accounts had more total purchases than the account name which has bought the most standard_qty paper throughout their lifetime as a customer?

Rephrase: In the end we just want a number - the number of accounts that meet a certain condition. The condition is having total purchases of any type of paper (in terms I think of quantity, not spending) greater than another account. That other account is the account that has bought the most standard paper over its lifetime. So, the way I read it is that we'll have to compare how much (of any type of paper) was purchased by a bunch of accounts to how much (just standard paper) was purchased by this other account, and filter out the ones that bought less. At least two people have told me that I'm misreading this and that the comparison should be between total quantities.

```sql
with 
  t1 as (
    select
      a.id a_id,
      a.name account_name,
      sum(o.standard_qty) total_qty_standard,
      sum(o.standard_qty) + sum(o.gloss_qty) + sum(o.poster_qty) as total_qty_all
    from accounts a
    join orders o
    on o.account_id = a.id
    group by 1,2
  ),
  t2 as (
    select max(total_qty_standard) max_total
    from t1
  )
-- What they want is a number here, but I'm going to list out the accounts and the quantities of paper. It would be easy to just do a count of the names.
select
  account_name,
  total_qty_all
from t1
join t2
on t1.total_qty_all > t2.max_total
```
Once again, the suggested answer is a bit different. In my solution, I create two subqueries and JOIN them in the outer query with an ON clause that contains the condition. Event though it provides the correct answer, I think mine is probably wrong, but it's very readable to me, which is why I like it. 

Anyway, the suggested solution uses t1 to get the account with the greatest purchase quantity of standard paper, along with that figure and also the figure for total purchases. It uses t2 to get the account names of the accounts HAVING sum(o.total) > (select total from t1). Then in the outer query, it gets the count of those accounts to give the answer.

```sql
WITH 
  t1 AS (
	-- this query gets the one account with the greatest quantity of standard paper purchased, and also the total paper it purchased
    SELECT 
      a.name account_name, 
      SUM(o.standard_qty) total_std, 
      SUM(o.total) total -- woops, forgot this existed
    FROM accounts a
    JOIN orders o
    ON o.account_id = a.id
    GROUP BY 1
    -- get rid of the whole max() part
    ORDER BY 2 DESC
    LIMIT 1
  ), 
  t2 AS (
	-- this query gets accounts for which total quantity of all paper types purchased is greater than t1.total_std
    SELECT a.name
    FROM orders o
    JOIN accounts a
    ON a.id = o.account_id
    GROUP BY 1
    HAVING SUM(o.total) > (SELECT total_std FROM t1)
  )
-- Finally, the outer query gets a count of accounts in t2
SELECT COUNT(*)
FROM t2;
```

**PLEASE NOTE**: The suggested solution compares total quantites of all types of paper, thus inn the course materials the HAVING clause uses "total" instead of "total_std". This results in an answer of 3. I interpreted the question to be asking us to compare total quantity to only standard quantity. The correct answer in that case is 6.

4. For the customer that spent the most (in total over their lifetime as a customer) total_amt_usd, how many web_events did they have for each channel?
```sql
WITH t1 AS (
   -- Get the id and name for the top spending account
   SELECT 
    a.id, 
    a.name, 
    SUM(o.total_amt_usd) tot_spent
   FROM orders o
   JOIN accounts a
   ON a.id = o.account_id
   GROUP BY 1, 2
   ORDER BY 3 DESC
   LIMIT 1
   )
-- Get the name, channels, and event count for all accounts
SELECT 
  a.name, 
  w.channel, 
  COUNT(*)
FROM accounts a
JOIN web_events w
-- I was so close! Join on id and to filter down also join on id from t1
ON a.id = w.account_id AND a.id =  (SELECT id FROM t1)
GROUP BY 1, 2
ORDER BY 3 DESC;
```
5. What is the lifetime average amount spent in terms of total_amt_usd for the top 10 total spending accounts?

I think the course materials had the wrong answer for this one. Their answer just returns a single average. Mine returns the top 10.
```sql
with 
  t1 as (
    select
      a.name account_name,
      sum(o.total_amt_usd) total_spent
    from accounts a
    join orders o
    on o.account_id = a.id
    group by 1
)
select 
  account_name, 
  avg(total_spent)
from t1
group by 1
order by 2 desc
limit 10
```
6. What is the lifetime average amount spent in terms of total_amt_usd, including only the companies that spent more per order, on average, than the average of all orders.

Rephase: What was the average amount spend by companies that spent more per order than the average spending on an order overall
  - Need average cost of orders

```sql
WITH 
  t1 AS (
    -- Get the average spending per order, overall
    SELECT 
      AVG(total_amt_usd) avg_all
    FROM orders),
  t2 AS (
    -- Get the average spending per order, grouped by account
    SELECT 
      account_id, 
      AVG(total_amt_usd) avg_amt
    FROM orders
    GROUP BY 1
    -- only include accounts for which their average spending per order is greater than overall spending per order
    HAVING AVG(total_amt_usd) > (SELECT * FROM t1))
-- Get the average of the averages but only for the accounts that passed the condition in t2
SELECT AVG(avg_amt)
FROM t2;
```

### Nested Subqueries

A nested subquery is a subquery placed in the WHERE clause of another query. They're useful when a user wants to filter output using a condition met from another table.

Here's an example:
```sql
SELECT *
FROM students
WHERE student_id
IN (
    SELECT DISTINCT student_id
    FROM gpa_table
    WHERE gpa>3.5
   );
```

### Inline Subqueries

An inline subquery is a subquery placed in the FROM clause of another query. They're useful when a user needs a pseduo table to aggregate or manipulate an existing table within a larger query. They're similar to WITH clauses, but not as helpful for readability.

Here's an example:
```sql
SELECT 
  dept_name,
  max_gpa
FROM 
  department_db x,
  (
    SELECT 
      dept_id
      MAX(gpa) as max_gpa
    FROM students
    GROUP BY dept_id
  ) y
WHERE x.dept_id = y.dept_id
ORDER BY 1;
```

### Scalar Subqueries

A scalar subquery is placed in the SELECT clause of another query. They're useful when you want to return on column and one row from a query. They're performant and also useful when the data set is small. If a scalar subquery does not find a match, it returns NULL. If a scalar subquery finds multiple matches, it returns an error.

Here's an example:
```sql
SELECT 
  (SELECT MAX(salary) FROM employees_db) AS top_salary,
  employee_name
FROM employees_db;
```

### Conclusion

Subquery Facts to Know:
- Commonly used as a filter/aggregation tool
- Commonly used to create a “temporary” view that can be queried off
- Commonly used to increase readability
- Can stand independently

### Lesson 4 Key Terms

- Correlated - Subquery	The inner subquery is dependent on the larger query.
- CTE	- Common Table Expression in SQL allows you to define a temporary result, such as a table, to then be referenced in a later part of the query.
- Inline	- This subquery is used in the same fashion as the WITH use case above. However, instead of the temporary table sitting on top of the larger query, it’s embedded within the from clause.
- Joins Dependencies - Cannot stand independently.
Joins Output	A joint view of multiple tables stitched together using a common “key”.
- Joins Use Case	- Fully stitch tables together and have full flexibility on what to “select” and “filter from”.
- Nested	This subquery is used when you’d like the temporary table to act as a filter within the larger query, which implies that it often sits within the where clause.
- Scalar	- This subquery is used when you’d like to generate a scalar value to be used as a benchmark of some sort.
- Simple Subquery	The inner subquery is completely independent of the larger query.
- SQL Views	- Virtual tables that are derived from one or more base tables. The term virtual means that the views do not exist physically in a database, instead, they reside in the memory (not database), just like the result of any query is stored in the memory.
- Subquery	- A SQL query where one SQL query is nested within another query
- Subquery Dependencies	- Stand independently and be run as complete queries themselves.
- Subquery Output	- Either a scalar (a single value) or rows that have met a condition.
- Subquery Use Case	- Calculate a scalar value to use in a later part of the query (e.g., average price as a filter).
- With	- This subquery is used when you’d like to “pseudo-create” a table from an existing table and visually scope the temporary table at the top of the larger query



##  SQL Data Cleaning

**Data Cleaning** is massaging or manipulating data to make to more suitable for analysis.

By definition, data cleaning is the task of cleaning up raw data to make it usable and ready for analysis. Almost always, your data will not be ready for you to run an analysis.

- Your data could all be lumped together in a single column, and you need to parse it to extract useful information.
- Your data could all default to string data types, and you need to cast each column appropriately to run computations.
- Your data could have un-standardized units of currency, and you need to normalize the column to ensure you are comparing equally across records.

**Normalization**: Standardizing or “cleaning up a column” by transforming it in some way to make it ready for analysis. A few normalization techniques are below:

- Adjusting a column that includes multiple currencies to one common currency
- Adjusting the varied distribution of a column value by transforming it into a z-score
- Converting all price into a common metric (e.g., price per ounce)

### Key Steps in Data Cleaning

1. What data do you need?: Review what data you need to run an analysis and solve the problem at hand.
2. What data do you have?: Take stock of not only the information you have in your dataset today but what data types those fields are. Do these align with your data needs?
3. How will you clean your data?: Build a game plan of how you’ll convert the data you currently have to the data you need. What types of actions and data cleaning techniques will you have to apply? Do you have the skills you need to go from the current to future state?
4. How will you analyze your data?: Now, it’s game time! How do you run an effective analysis? Build an approach for analysis, as well. And visualize your plan to solve the problem. Finally, remember to question “so what?” at the end of your results, which will help drive recommendations for your organization.

### Methods for Data Cleaning

The following set of methods cover three types of data cleaning techniques: 
- parsing information, 
- returning where information lives, and 
- changing the data type of the information.

Here are the methods:
- Left: Extracts a number of characters from a string starting from the left
- Right: Extracts a number of characters from a string starting from the right
- Substr: Extracts a substring from a string (starting at any position)
- Position: Returns the position of the first occurrence of a substring in a string, e.g. POSITION("$" IN student_information) as salary_starting_position
- Strpos: Returns the position of a substring within a string
- Concat: Adds two or more expressions together, e.g. CONCAT(month, '-', day, '-', year) AS date
- Cast: Converts a value of any type into a specific, different data type, e.g. CAST(salary AS int)
- Coalesce: Returns the first non-null value in a list

### Common Methods

#### Use Case: When data in a single column holds multiple pieces of information. 

Methods:
- LEFT(string, number_of_characters)
- RIGHT(string, number_of_characters)
- SUBSTR(string, start, number_of_characters)
- POSITION(substring IN string)
- STRPOS(string, substring)

#### Use Case: When two or more columns serve as a unique identifier

Methods:
- Concat(string1, string2, string3, ...)

#### Use Case: Converting data into specific data types

Methods:
- Cast(expression AS datatype)

#### Use Case: If there are multiple columns that have a combination of null and non-null values and the user needs to extract the first non-null value, you can use the coalesce function.

Methods:
- Coalesce(value1, value2, value3, ...)

### Table of Functions

| Function | Description                                                             | Syntax                                  | Returns                                                                                                                                    | Example                                    |
|----------|-------------------------------------------------------------------------|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| left     | Extracts a number of characters from a string starting from the left    | left(string, num_characters)            | A new string starting at the first character and continuing to num_characters to the left, inclusive                                       |                                            |
| right    | Extracts a number of characters from a string starting from the right   | right(string, num_characters)           | A new string starting at the last character and continuing to num_characters to the right, inclusive                                       |                                            |
| substr   | Extracts a substring from a string (starting at any position)           | substr(string, start, num_characters)   | A new string starting from start and continuing to num_characters, inclusive.                                                              |                                            |
| position | Returns the position of the first occurrence of a substring in a string | position(substring IN string)           | A new string if substring is found or 0, unless the value is NULL, in which case NULL.                                                     | POSITION("$" IN student_info) AS salary    |
| strpos   | Returns the position of a substring within a string                     | strpos(string, substring)             | A new string if substring is found or 0, unless the value is NULL, in which case NULL.                                                     |                                            |
| concat   | Adds two or more expressions together                                   | concat(string1, string2, ...)           | A new string. NULL values are ignored, unless using \|\| operator in which case anything concatenated with a NULL value will return NULL.  | CONCAT(month, '-', day, '-', year) AS date |
| cast     | Converts a value of any type into a specific, different data type       | cast(expression AS datatype)            | An expression of the new type. If the expression cannot be converted to the target type, PostgreSQL will raise an error.                   | CAST(salary AS int)                        |
| coalesce | Returns the first non-null value in a list                              | coalesce(expression1, expression2, ...) | The first argument that is not null. If all arguments are null, returns null.                                                              | COALESCE(hourly_wage * 40 * 52, salary, commission * sales) AS annual_income                                           | 

### LEFT and RIGHT Quiz

1. In the accounts table, there is a column holding the website for each company. The last three digits specify what type of web address they are using. A list of extensions (and pricing) is provided here. Pull these extensions and provide how many of each website type exist in the accounts table.
```sql
with 
    t1 as (
        select
  	        right(website, 3) as domain
        from accounts
    )
select 
	distinct domain,
	count(domain) as count
from t1
group by 1
```

2. There is much debate about how much the name (or even the first letter of a company name) matters. Use the accounts table to pull the first letter of each company name to see the distribution of company names that begin with each letter (or number).

```sql
with t1 as (
  	select 
        left(name, 1) as initial 
	from accounts
  )
select 
	initial,
    count(*) as count
from t1
group by 1
order by 1
```

3. Use the accounts table and a CASE statement to create two groups: one group of company names that start with a number and the second group of those company names that start with a letter. What proportion of company names start with a letter?

```sql
SELECT SUM(num) nums, SUM(letter) letters
FROM (
        SELECT 
            name, 
            CASE 
                WHEN LEFT(UPPER(name), 1) IN ('0','1','2','3','4','5','6','7','8','9') 
                THEN 1 
                ELSE 0 
            END AS num, 
            CASE 
                WHEN LEFT(UPPER(name), 1) IN ('0','1','2','3','4','5','6','7','8','9') 
                THEN 0 
                ELSE 1 
            END AS letter
        FROM accounts
) t1;
```

4. Consider vowels as a, e, i, o, and u. What proportion of company names start with a vowel, and what percent start with anything else?

```sql
select
    sum(vowel) as vowels,
    sum(other) as others
from (
    select 
        case
            when left(name, 1) in ('A','E','I','O','U', 'a', 'e', 'i', 'o', 'u')
            then 1
            else 0
        end as vowel,
        case
            when left(name, 1) in ('A','E','I','O','U', 'a', 'e', 'i', 'o', 'u')
            then 0
            else 1
        end as other
    from accounts
    ) t1
```

### BONUS CONCEPT
This is an advanced example:
```sql
WITH table AS(
SELECT  student_information,
        value,
        ROW _NUMBER() OVER(PARTITION BY student_information ORDER BY (SELECT NULL)) AS row_number
FROM    student_db
        CROSS APPLY STRING_SPLIT(student_information, ',') AS back_values
)
SELECT  student_information,
        [1] AS STUDENT_ID,
        [2] AS GENDER,
        [3] AS CITY,
        [4] AS GPA,
        [5] AS SALARY
FROM    table
PIVOT(
        MAX(VALUE)
        FOR row_number IN([1],[2],[3],[4],[5])
) AS PVT
```
What this query does is create a pivot table from the student_db table. It uses some concepts that haven't been covered yet.

### Quiz: CONCAT, LEFT, RIGHT, and SUBSTR

1. Suppose the company wants to assess the performance of all the sales representatives. Each sales representative is assigned to work in a particular region. To make it easier to understand for the HR team, display the concatenated sales_reps.id, ‘_’ (underscore), and region.name as EMP_ID_REGION for each sales representative.

```sql
select concat(sr.id, '_', r.name) as EMP_ID_REGION
from region r
join sales_reps sr
on sr.region_id = r.id
```

2. From the accounts table, display the name of the client, the coordinate as concatenated (latitude, longitude), email id of the primary point of contact as <first letter of the primary_poc><last letter of the primary_poc>@<extracted name and domain from the website>.

```sql
select 
    a.name as account_name, 
    concat(lat, long) as coordinate, 
    concat(
            left(primary_poc, 1), 
            right(primary_poc, 1), 
            '@', 
            -- surprised this worked!
            substr(website, (position('.' in website)+1))
            ) as poc_email_id
from accounts a
```

3. From the web_events table, display the concatenated value of account_id, '_' , channel, '_', count of web events of the particular channel.

```sql
with t1 as (
    select 
        account_id, 
        channel, 
        count(*) as channel_count
    from web_events
    group by 1,2
)
select
    concat(account_id, '_', channel, '_', channel_count) as account_channel_count
from t1
```
### Using CAST 

Take a column formatted like this "01/31/2014 08:00:00 AM +0000" and return a properly formatted DATE.

```sql
select 
	date,
	cast(
      	concat(
      		substr(date, 7, 4),
      		'-',
      		substr(date, 1, 2),
      		'-',
      		substr(date, 4, 2)--,
            -- I tried to add in the time, but it doesn't seem to work
      		--'T',
      		--substr(date, 12, 9)
    		) 
     	AS DATE)
from sf_crime_data
```

### POSITION and STRPOS

1. Use the accounts table to create first and last name columns that hold the first and last names for the primary_poc.

```SQL
select 
	substr(primary_poc, 1, (position(' ' in primary_poc)-1)) as first,
    substr(primary_poc, (position(' ' in primary_poc)+1)) as last
from accounts a
```

2. Now see if you can do the same thing for every rep name in the sales_reps table. Again provide first and last name columns.

```sql
select 
	substr(name, 1, (position(' ' in name)-1)) as first,
    substr(name, (position(' ' in name)+1)) as last
from sales_reps sr
```

The suggested solutions are a little different. Both use LENGTH, which we have not covered:
```sql
SELECT 
    LEFT(primary_poc, STRPOS(primary_poc, ' ') -1 ) first_name, 
    RIGHT(primary_poc, LENGTH(primary_poc) - STRPOS(primary_poc, ' ')) last_name
FROM accounts;


SELECT 
    LEFT(name, STRPOS(name, ' ') -1 ) first_name, 
    RIGHT(name, LENGTH(name) - STRPOS(name, ' ')) last_name
FROM sales_reps;
```
### Problems for CONCAT and STRPOS

1. Each company in the accounts table wants to create an email address for each primary_poc. The email address should be the first name of the primary_poc . last name primary_poc @ company name .com.

```sql
select
	primary_poc,
    -- could do this quickly with REPLACE()
    -- replace(name, ' ', '.')
	concat(
      	left(primary_poc, (strpos(primary_poc, ' ')-1)),
      	'.',
      	substr(primary_poc, (strpos(primary_poc, ' ')+1)), 
        '@', 
        replace(name, ' ', ''), 
        '.com'
      ) as email
from accounts
```

2. You may have noticed that in the previous solution some of the company names include spaces, which will certainly not work in an email address. See if you can create an email address that will work by removing all of the spaces in the account name, but otherwise, your solution should be just as in question 1. Some helpful documentation is here.

See answer to 1 above.

3. We would also like to create an initial password, which they will change after their first log in. The first password will be the first letter of the primary_poc's first name (lowercase), then the last letter of their first name (lowercase), the first letter of their last name (lowercase), the last letter of their last name (lowercase), the number of letters in their first name, the number of letters in their last name, and then the name of the company they are working with, all capitalized with no spaces.

```sql
select
	primary_poc,
	concat(
		-- first letter of the primary_poc's first name (lowercase),
		lower(left(primary_poc, 1)),
		-- then the last letter of their first name (lowercase), 
		substr(primary_poc, strpos(primary_poc, ' ')-1, 1),
		-- the first letter of their last name (lowercase),
		lower(substr(primary_poc, strpos(primary_poc, ' ')+1, 1)),
		-- the last letter of their last name (lowercase), 
		right(primary_poc, 1),
		-- the number of letters in their first name, 
		length(substr(primary_poc, 1, strpos(primary_poc, ' ')-1)),
		-- the number of letters in their last name, 
		length(substr(primary_poc, strpos(primary_poc, ' ')+1)),
		-- and then the name of the company they are working with, all capitalized with no spaces
		replace(upper(name), ' ', '')
	) as temp_password
from accounts
```

### Dealing with NULL values

The three methods below are the most common ways to deal with null values in SQL:

1. Coalesce: Allows you to return the first non-null value across a set of columns in a slick, single command. This is a good approach only if a single column’s value needs to be extracted whilst the rest are null.

2. Drop records: Sometimes, if there are null values in records at all, analysts can decide to drop the row entirely. This is not favorable, as it removes data. Data is precious. Think about the reason those values are null. Does it make sense to use COALESCE, drop records, and conduct an imputation.

3. Imputation: Outside of the COALESCE use case, you may want to impute missing values. If so, think about the problem you are trying to solve, and impute accordingly. Perhaps you’d like to be conversative so you take the MIN of that column or the 25th percentile value. Classic imputation values are often the median or mean value of the column.

### COALESCE problems

1. Use COALESCE to fill in the accounts.id column with the account.id for the NULL value for the table created by this query:

```sql
SELECT *
FROM accounts a
LEFT JOIN orders o
ON a.id = o.account_id
WHERE o.total IS NULL;
```

Solution:
```sql
SELECT 
    -- you don't need 2 a.id arguments here
    -- you only need 1. i think using 2 here
    -- just makes it more confusing
    COALESCE(a.id, a.id) filled_id, 
    a.name, 
    a.website, 
    a.lat, 
    a.long, 
    a.primary_poc, 
    a.sales_rep_id, 
    o.*
FROM accounts a
LEFT JOIN orders o
ON a.id = o.account_id
WHERE o.total IS NULL;
```

2. Use COALESCE to fill in the orders.account_id column with the account.id for the NULL value for the table created by the query in question 1.

```sql
select 
    a.*
    coalesce(o.account_id, a.id) as filled_account_id
    -- other orders columns go here
from accounts a
left join orders o
on a.id = o.account_id
where o.total is null;
```

3. Still referring to the table creatred by the query in question 1, fill in the order table's columns with either data from the order, if it exists, or with a 0.

```sql
SELECT 
    COALESCE(a.id, a.id) filled_id, 
    -- other accounts columns go here
    COALESCE(o.account_id, a.id) account_id, 
    o.occurred_at, 
    COALESCE(o.standard_qty, 0) standard_qty, 
    COALESCE(o.gloss_qty,0) gloss_qty, 
    COALESCE(o.poster_qty,0) poster_qty, 
    COALESCE(o.total,0) total, 
    COALESCE(o.standard_amt_usd,0) standard_amt_usd, 
    COALESCE(o.gloss_amt_usd,0) gloss_amt_usd, 
    COALESCE(o.poster_amt_usd,0) poster_amt_usd, 
    COALESCE(o.total_amt_usd,0) total_amt_usd
FROM accounts a
LEFT JOIN orders o
ON a.id = o.account_id
WHERE o.total IS NULL;
```




## Window Functions

### Two Use Cases for Window Functions

- When you want to measure trends or changes over rows or records in your data.
- When you want to rank a column for outreach or prioritization.

A few cases where you’d have these needs are described below:

#### Measuring change over time:
- Has the average price of airline tickets gone up this year?
  - Calculate a running average of ticker prices partitioned by the month and ordered by time
- What’s the best way to keep the running total orders of customers?
  - Calculate a running total of orders and maintain as a separate row within the table
#### The ranking used for outreach prioritization:
- Use a combination of factors to rank companies most likely to need a loan.
  - Include a rank column to be used by a BD rep to reach out to potential customers

### What is a Window Function?

A window function is a calculation across a set of rows within a table that is related to the current row. Window functions are similar to aggregate functions, but they retain the total number of rows between the input table and the output table (or result).

Window functions are permitted only in the SELECT list and the ORDER BY clause of the query.

They are forbidden elsewhere, such as in GROUP BY, HAVING and WHERE clauses. This is because they logically execute after the processing of those clauses. Also, window functions execute after regular aggregate functions. This means it is valid to include an aggregate function call in the arguments of a window function, but not vice versa.

This is from the Postgres documentation:

"A window function performs a calculation across a set of table rows that are somehow related to the current row. This is comparable to the type of calculation that can be done with an aggregate function. But unlike regular aggregate functions, use of a window function does not cause rows to become grouped into a single output row — the rows retain their separate identities. Behind the scenes, the window function is able to access more than just the current row of the query result."

More here: https://www.postgresql.org/docs/9.1/tutorial-window.html

Here is the general form of a window function:
```sql
AGGREGATE_FUNCTION (column_1) OVER
  (
    PARTITION BY column_2 
    ORDER BY column_3
  ) AS new_column_name;
```

For example:

- Calculating running totals that incorporate the current row
- Ranking records across rows, inclusive of the current one

A detailed example:

#### Problem: Compare each employee's salary with the average salary in his or her department:

```sql
SELECT 
  depname, 
  empno, 
  salary, 
  avg(salary) OVER 
    (
      PARTITION BY depname
    ) as average
FROM empsalary;
```

The resulting table:

  depname  | empno | salary |          average          
-----------|-------|--------|-----------------------
 develop   |    11 |   5200 | 5020.0000000000000000
 develop   |     7 |   4200 | 5020.0000000000000000
 develop   |     9 |   4500 | 5020.0000000000000000
 develop   |     8 |   6000 | 5020.0000000000000000
 develop   |    10 |   5200 | 5020.0000000000000000
 personnel |     5 |   3500 | 3700.0000000000000000
 personnel |     2 |   3900 | 3700.0000000000000000
 sales     |     3 |   4800 | 4866.6666666666666667
 sales     |     1 |   5000 | 4866.6666666666666667
 sales     |     4 |   4800 | 4866.6666666666666667
(10 rows)

In this example, the fourth column represents an average taken across all the table rows that have the same depname value as the current row.

Another example:

#### Problem: Rank employee's by salary in descending order within department.
```sql
SELECT 
  depname, 
  empno, 
  salary, 
  rank() OVER 
    (
      PARTITION BY depname 
      -- You can order the ranking differently than you order the result table
      ORDER BY salary DESC
    ) 
FROM empsalary;
```

The resulting table:
  depname  | empno | salary | rank 
-----------|-------|--------|------
 develop   |     8 |   6000 |    1
 develop   |    10 |   5200 |    2
 develop   |    11 |   5200 |    2
 develop   |     9 |   4500 |    4
 develop   |     7 |   4200 |    5
 personnel |     2 |   3900 |    1
 personnel |     5 |   3500 |    2
 sales     |     1 |   5000 |    1
 sales     |     4 |   4800 |    2
 sales     |     3 |   4800 |    2
(10 rows)

As shown here, the rank function produces a numerical rank within the current row's partition for each distinct ORDER BY value, in the order defined by the ORDER BY clause. rank needs no explicit parameter, because its behavior is entirely determined by the OVER clause.

The rows considered by a window function are those of the "virtual table" produced by the query's FROM clause as filtered by its WHERE, GROUP BY, and HAVING clauses if any. For example, **a row removed because it does not meet the WHERE condition is not seen by any window function.** A query can contain multiple window functions that slice up the data in different ways by means of different OVER clauses, but they all act on the same collection of rows defined by this virtual table.

We already saw that ORDER BY can be omitted if the ordering of rows is not important. It is also possible to omit PARTITION BY, in which case there is just one partition containing all the rows.

Another example illustrating the **window frame** concept:

#### Problem: Get salary and the sum of all salaries from empsalaray.

```sql
SELECT 
  salary, 
  -- Leaving out the partition means you're considering all rows
  sum(salary) OVER () 
FROM empsalary;
```

The resulting table:

 salary |  sum  
--------|-------
   5200 | 47100
   5000 | 47100
   3500 | 47100
   4800 | 47100
   3900 | 47100
   4200 | 47100
   4500 | 47100
   4800 | 47100
   6000 | 47100
   5200 | 47100
(10 rows)

#### Problem: What would happen if we added an order by clause to the above problem?

```sql
SELECT 
  salary, 
  sum(salary) OVER 
    (
      ORDER BY salary
    ) 
FROM empsalary;
```
The resulting table:

 salary |  sum  
--------|-------
   3500 |  3500
   3900 |  7400
   4200 | 11600
   4500 | 16100
   4800 | 25700
   4800 | 25700
   5000 | 30700
   5200 | 41100
   5200 | 41100
   6000 | 47100
(10 rows)

#### Can you filter or group rows after a window function is performed?

If there is a need to filter or group rows after the window calculations are performed, you can use a sub-select.

```sql
SELECT 
  depname, 
  empno, 
  salary, 
  enroll_date
FROM
  (
    SELECT 
      depname, 
      empno, 
      salary, 
      enroll_date,
      -- The window function is in the inner query
      rank() OVER 
        (
          PARTITION BY depname 
          ORDER BY salary DESC, empno
        ) AS pos
    FROM empsalary
  ) AS ss
-- The outer query filters the results of the inner query, showing only those with a pos over 3
WHERE pos < 3;
```

#### What if your query has multiple window functions with the same partition?

You can group them like this:

```sql
SELECT 
  sum(salary) OVER w, 
  avg(salary) OVER w
FROM empsalary
WINDOW w AS (
  PARTITION BY depname 
  ORDER BY salary DESC
);
```

Back to the Udacity material.

Term | Definition
-----| ----------
**Basic**
Partition by | A subclause of the OVER clause. Similar to GROUP BY.
Over | Typically precedes the partition by that signals what to “GROUP BY”.
Aggregates | Aggregate functions that are used in window functions, too (e.g., sum, count, avg).
**Ranking**
Row_number() | Ranking function where each row gets a different number.
Rank() | Ranking function where a row could get the same rank if they have the same value.
Dense_rank() | Ranking function similar to rank() but ranks are not skipped with ties.
**Advanced**
Aliases | Shorthand that can be used if there are several window functions in one query.
Percentiles | Defines what percentile a value falls into over the entire table.
Lag/Lead | Calculating differences between rows’ values.

### Problems

1. Create a running total of standard_amt_usd (in the orders table) over order time with no date truncation. Your final table should have two columns: one with the amount being added for each new row, and a second with the running total.

This is actually a little bit tricky, because there is no partition, just an order by clause.
```sql
select 
	standard_amt_usd,
    sum(standard_amt_usd) over (
      -- Notice that there's no partition clause, only an order by clause
    	order by occurred_at
     ) running_total
from orders
```

2. Create a running total of standard_amt_usd (in the orders table) over order time, but this time, date truncate occurred_at by year and partition by that same year-truncated occurred_at variable.

```sql
select
  date_trunc('year', occurred_at)
  standard_amt_usd,
  sum(standard_amt_usd) over (
    partition by date_trunc('year', occurred_at)
    order by occurred_at
  ) running_total
from orders o
```

### The Difference between GROUP BY and PARTITION BY

GROUP BY will condense the rows in the "partition" to one row of data per GROUP BY clause. PARTITION BY retains all of the rows in the data and shows the aggregation in a new column.

#### Similarities
Both groups by/aggregation queries and window functions serve the same use case. Synthesizing information over time and often grouped by a column (e.g., a region, month, customer group, etc.)

#### Differences
The difference between group by/aggregation queries and window functions is simple. The output of window functions retains all individual records whereas the group by/aggregation queries condense or collapse information.

![Click to see example](assets/group-by-and-partition-by.png)

The results table on the right-hand side in that image was created with this query:

```sql
SELECT order_id,
       order_total,
       order_price,
       SUM(order_total) OVER
           (PARTITION BY month(order_date) ORDER BY order_date) AS running_monthly_sales,
       COUNT(order_id) OVER
           (PARTITION BY month(order_date) ORDER BY order_date) AS running_monthly orders,
       AVG(order_price) OVER
           (PARTITION BY month(order_date) ORDER BY order_date) AS average_monthly_price
FROM  amazon_sales_db
WHERE order_date < '2017-01-01';
```

Here's another query, this time from Parch and Posey, that shows us 6 different aggregate functions over a partition by account_id with order by date trunc of month. To phrase this as a problem:

Show the ranking, total quantity purchased, order count, average order quantity, smallest order quantity, and largest order quantity all of standard paper by customer by month.

```sql
SELECT id,
       account_id,
       standard_qty,
       DATE_TRUNC('month', occurred_at) AS month,
       DENSE_RANK() 		    OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS dense_rank,
       SUM(standard_qty) 	  OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS sum_standard_qty,
       COUNT(standard_qty) 	OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS count_standard_qty,
       AVG(standard_qty) 	  OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS avg_standard_qty,
       MIN(standard_qty) 	  OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS min_standard_qty,
       MAX(standard_qty) 	  OVER (PARTITION BY account_id ORDER BY DATE_TRUNC('month', occurred_at)) AS max_standard_qty
FROM orders
```

And here's the result table shown in pgAdmin:

![the result table](assets/wind-func-example.png)

So, for example, looking at row 28, we can see that account 1001 has 
- 15 months to consider
- the running total got up to 7,896 units of standard paper
- there were 28 orders placed in those 15 months
- the average order size was 282 units per order
- the smallest order was 85 units
- the largest order was 566 units.

### The Three Types of Ranking Functions

- Row_number(): Ranking is distinct amongst records even with ties in what the table is ranked against.
- Rank(): Ranking is the same amongst tied values and ranks skip for subsequent values.
- Dense_rank(): Ranking is the same amongst tied values and ranks do not skip for subsequent values.

### Examples of Ranking

row_number()
```sql
SELECT ROW_NUMBER() OVER(ORDER BY date_time) AS rank,
       date_time
FROM   db;
```
rank()
```sql
SELECT RANK() OVER(ORDER BY date_time) AS rank,
       date_time
FROM   db;
```
dense_rank()
```sql
SELECT DENSE_RANK() OVER(ORDER BY date_time) AS rank,
       date_time
FROM   db;
```

#### Problems for rank()

1. Select the id, account_id, and total variable from the orders table, then create a column called total_rank that ranks this total amount of paper ordered (from highest to lowest) for each account using a partition. Your final table should have these four columns.

```sql
select
	id,
    account_id,
    total,
    row_number() over (
      partition by account_id
      order by total desc 
    ) as total_rank
from orders o
```

### Aliases

Aliases allow you to use the same OVER, PARTITION BY  and   ORDER BY clauses multiple times. For example:
```sql
SELECT 
  order_id,
  order_total,
  order_price,
  SUM(order_total) OVER monthly_window AS running_monthly_sales,
  COUNT(order_id) OVER monthly_window AS running_monthly orders,
  AVG(order_price) OVER monthly_window AS average_monthly_price
FROM   amazon_sales_db
WHERE  order_date < '2017-01-01'
WINDOW monthly_window AS
  (
    PARTITION BY month(order_date) 
    ORDER BY order_date
  );
```

An example from our Parch and Posey database:
```sql
SELECT id,
       account_id,
       DATE_TRUNC('year',occurred_at) AS year,
       DENSE_RANK() OVER account_year_window AS dense_rank,
       total_amt_usd,
       SUM(total_amt_usd) OVER account_year_window AS sum_total_amt_usd,
       COUNT(total_amt_usd) OVER account_year_window AS count_total_amt_usd,
       AVG(total_amt_usd) OVER account_year_window AS avg_total_amt_usd,
       MIN(total_amt_usd) OVER account_year_window AS min_total_amt_usd,
       MAX(total_amt_usd) OVER account_year_window AS max_total_amt_usd
FROM orders
window account_year_window as
  (
    PARTITION BY account_id 
    ORDER BY DATE_TRUNC('year',occurred_at)
  );
```

### LAG and LEAD Window Functions

The LAG and LEAD functions are positional window functions. They allow you to compare a current row with values from a previous row (LAG) or a subsequent row (LEAD). 

In their simplest form, these functions get the adjacent row above or below the current row. You can specify an optional offset for which previous or subsequent row you want. For example, you can get a value from a row that was 3 rows previous or 2 rows subsequent to the current row.

An ORDER BY clause is required when working with LEAD and LAG functions, but a PARTITION BY clause is optional.

Here's the general form for both LAG and LEAD:

```sql
LAG(expression [,offset [,default_value]]) 
OVER (
    [PARTITION BY partition_expression, ... ]
    ORDER BY sort_expression [ASC | DESC], ...
)
```

Here's an example using LAG:

```sql
SELECT 
  account_id,
  standard_sum,
  LAG(standard_sum) OVER (ORDER BY standard_sum) AS lag,
  standard_sum - LAG(standard_sum) OVER (ORDER BY standard_sum) AS lag_difference
FROM (
  SELECT account_id,
  SUM(standard_qty) AS standard_sum
  FROM orders 
  GROUP BY 1
) sub
```

In this example, we use a derived table (aka a common table expression or CTE) in the FROM clause and give it an alias of sub. The derived table gets the sum of all standard quantity paper orders from the order table, grouped by account_id. Note that we could also get just a partition of the total sum, e.g. the annual sum or the sum for specified date range.

Then in the outer query, we get the account_id, standard_sum, and our lag and lag difference derived columns.

In lag, we specify that we want standard_sum, and that we want it ordered by standard_sum.

In lag_difference, we specify that we want the difference between standard_sum and lag. We can't use the alias, however. We have to use the full expression.

The result looks like this:

![lag query result](/assets/lag-query-example.png)

### Problem for LAG/LEAD

Compare how the current order's total revenue ("total" meaning from sales of all types of paper) compares to the next order's total revenue.

If there were only one total_amt_usd per order date, we could solve this problem without a subquery like this:

```sql
select  
	occurred_at,
    total_amt_usd,
    lead(total_amt_usd) over (order by occurred_at) as lead,
	lead(total_amt_usd) over (order by occurred_at) - total_amt_usd as lead_difference
from orders
group by 1,2
order by occurred_at
```

However, there are dates on which there is more than one order, and that means that we will need to aggregate or sum up those total order amounts, like this:

```sql
SELECT occurred_at,
       total_amt_usd,
       -- We're intesrested in the sum of totals spent, but 
       -- we want to order by date
       LEAD(total_amt_usd) OVER (ORDER BY occurred_at) AS lead,
       LEAD(total_amt_usd) OVER (ORDER BY occurred_at) - total_amt_usd AS lead_difference
FROM (
SELECT occurred_at,
      -- sum up the total order amounts from multiple orders on the same day
       SUM(total_amt_usd) AS total_amt_usd
  FROM orders 
 GROUP BY 1
) sub
```

### Percentiles

When there are a large number of records that need to be ranked, individual ranks (e.g., 1, 2, 3, 4…) are ineffective in helping teams determine the best of the distribution from the rest. Percentiles help better describe large datasets. For example, a team might want to reach out to the Top 5% of customers.

You can use window functions to identify what percentile (or quartile, or any other subdivision) a given row falls into. The syntax is NTILE(# of buckets). In this case, ORDER BY determines which column to use to determine the quartiles (or whatever number of ‘tiles you specify).

Here's the general form:
```sql
NTILE(# of buckets) OVER (
  ORDER BY ranking_column
  ) AS new_column_name
```

The following components are important to consider when building a query with percentiles:

- NTILE + the number of buckets you’d like to create within a column (e.g., 100 buckets would create traditional percentiles, 4 buckets would create quartiles, etc.)
- OVER
- ORDER BY (optional, typically a date column) 
- AS + the new column name

Expert Tip: 
In cases with relatively few rows in a window, the NTILE function doesn’t calculate exactly as you might expect. For example, If you only had two records and you were measuring percentiles, you’d expect one record to define the 1st percentile, and the other record to define the 100th percentile. Using the NTILE function, what you’d actually see is one record in the 1st percentile, and one in the 2nd percentile.

In other words, when you use an NTILE function but the number of rows in the partition is less than the NTILE(number of groups), then NTILE will divide the rows into as many groups as there are members (rows) in the set but then stop short of the requested number of groups. If you’re working with very small windows, keep this in mind and consider using quartiles or similarly small bands.

Here's an example:

```sql
SELECT  customer_id,
        composite_score,
        NTILE(100) OVER(ORDER BY composite_score) AS percentile
FROM    customer_lead_score;
```

### Percentile Problems

You can use partitions with percentiles to determine the percentile of a specific subset of all rows. Imagine you're an analyst at Parch & Posey and you want to determine the largest orders (in terms of quantity) a specific customer has made to encourage them to order more similarly sized large orders. You only want to consider the NTILE for that customer's account_id.

1. Use the NTILE functionality to divide the accounts into 4 levels in terms of the amount of standard_qty for their orders. Your resulting table should have the account_id, the occurred_at time for each order, the total amount of standard_qty paper purchased, and one of four levels in a standard_quartile column.

You might think that the questions is asking for a quartile that shows you whether a certain order was in a certain quartile for all order of standard paper. But don't forget that first pararaph in the section. We want quartiles within in a company (not overall), so that we can encourage them to make orders that are larger relative to their orders only! 

I added a subquery so that I could account for any case where a company place more than one order for standard paper on the same day.

```sql
select
	account_id,
    occurred_at,
    sum_standard,
	ntile(4) over (
    -- partition by company so that quartiles are within a company
      partition by account_id
      order by sum_standard
      ) as standard_quartile
from (
	select 
  		account_id,
  		occurred_at,
  		sum(standard_qty) as sum_standard
  	from orders
  	group by 1,2
) as sub
group by 1,2,3
order by 1 desc
```

2. Use the NTILE functionality to divide the accounts into two levels in terms of the amount of gloss_qty for their orders. Your resulting table should have the account_id, the occurred_at time for each order, the total amount of gloss_qty paper purchased, and one of two levels in a gloss_half column.

```sql
select
	account_id,
  occurred_at,
  sum_gloss,
	ntile(2) over (
    -- partition by company so that percentiles are within a company
      partition by account_id
      order by sum_gloss
      ) as two_tier
from (
	select 
  		account_id,
  		occurred_at,
  		sum(gloss_qty) as sum_gloss
  	from orders
  	group by 1,2
) as sub
group by 1,2,3
-- In the solution they order by account_id DESC for this one
order by 1 desc
```

3. Use the NTILE functionality to divide the orders for each account into 100 levels in terms of the amount of total_amt_usd for their orders. Your resulting table should have the account_id, the occurred_at time for each order, the total amount of total_amt_usd paper purchased, and one of 100 levels in a total_percentile column.

No subquery this time.

```sql
select
	account_id,
  occurred_at,
  total_amt_usd,
	ntile(100) over (
    -- partition by company so that percentiles are within a company
      partition by account_id
      order by total_amt_usd
      ) as percentiles
from orders
group by 1,2,3
-- In the solution they order by account_id DESC for this one
order by 1 desc
```


# Lesson 7: SQL Advanced Joins and Performance Tuning

### Join Types and the Full Outer Join

For all of these, the table on the left side of the diagram is Table A and the one on the right is Table B.

#### Inner Join

This is the most common and also the default join type.
```sql
SELECT column_name(s)
FROM Table_A
INNER JOIN Table_B ON Table_A.column_name = Table_B.column_name;
```

![Inner Join](/assets/inner-join.png)

#### Left Join General Form

When you want include unmatched records from the left table.
```sql
SELECT column_name(s)
FROM Table_A
LEFT JOIN Table_B ON Table_A.column_name = Table_B.column_name;
```

![Left Join](/assets/left-join.png)

#### Right Join General Form

When you want to include unmatched records from the right table.
```sql
SELECT column_name(s)
FROM Table_A
RIGHT JOIN Table_B ON Table_A.column_name = Table_B.column_name;
```

![Right Join](/assets/right-join.png)

#### Full Outer Join

When you want to include unmatched records from both tables.
```sql
SELECT column_name(s)
FROM Table_A
FULL OUTER JOIN Table_B ON Table_A.column_name = Table_B.column_name;
```

![Full Outer](/assets/full-outer-join.png)

FULL JOIN is commonly used in conjunction with aggregations to understand the amount of overlap between two tables.

#### Full Outer Join If Null

Find only the unmatched rows in your tables.
```sql
SELECT column_name(s)
FROM Table_A
FULL OUTER JOIN Table_B ON Table_A.column_name = Table_B.column_name;
WHERE Table_A.column_name IS NULL OR Table_B.column_name IS NULL
```

![Full outer join with nulls only](/assets/full-outer-join-if-null.png)

#### Problems for Full Outer Join

Say you're an analyst at Parch & Posey and you want to see:

- Each account who has a sales rep and each sales rep that has an account (all of the columns in these returned rows will be full)
- But also each account that does not have a sales rep and each sales rep that does not have an account (some of the columns in these returned rows will be empty)

```sql
select
    a.*,
    sr.*
from accounts a
full outer join sales_reps sr
on a.sales_rep_id = sr.id
```

### Joins with Inequalities

First, lets find all of the orders that occurred during the first month that there were orders. We can do this with a subquery in the WHERE clause. 

```sql
select *
from orders
where date_trunc('month', occurred_at) = (
    -- Use a subquery and MIN() to get the earliest date of any order
    select date_trunc('month' min(occurred_at)) from orders
)
order by occurred_at;
```

Then, let's add the left join from web_events to orders to get all of the web_events that occurred before there any orders. We join them on account_id and also on the date inequality. Then we just need to disambiguate the id and occurred_at references in the SELECT, WHERE and ORDER BY clauses. 

```sql
select 
    -- We can narrow down what we want and add the table prefix to disambiguate
	o.id as order_id,
    o.occurred_at as order_date,
	we.*
from orders o
-- Left join to include any null entries in web_events
left join web_events we
-- We join on account_id
on we.account_id = o.account_id
-- ...and also on events. Here's the inequality. We want events that occurred before any orders were made. 
-- Note that the join will be processed before the WHERE clause
and we.occurred_at < o.occurred_at
where date_trunc('month', o.occurred_at) = (
    select date_trunc('month', min(occurred_at)) from orders
)
order by o.occurred_at, we.occurred_at;
```

NOTE: The join clause is evaluated before the where clause -- filtering in the join clause will eliminate rows before they are joined, while filtering in the WHERE clause will leave those rows in and produce some nulls.

#### Joins and Inequalities Problem

Write a query that left joins the accounts table and the sales_reps tables on each sale rep's ID number and joins it using the < comparison operator on accounts.primary_poc and sales_reps.name.

The query results should be a table with three columns: the account name (e.g. Johnson Controls), the primary contact name (e.g. Cammy Sosnowski), and the sales representative's name (e.g. Samuel Racine).

```sql
select
    a.name account_name,
    a.primary_poc,
    sr.name sales_rep_name
from accounts a
left join sales_reps sr
on sr.id = a.sales_rep_id
    -- Using an inequality on a string value. The effect is that the poc's name comes before the rep's name alphabetically
    and a.primary_poc < sr.name 
```

Remember that there are 351 accounts and every account has a primary point of contact. There are only 50 sales reps, which means that each sales rep will have many accounts assigned to them. 

You can see how many accounts are assigned to each sales rep with:

```sql
select sr.name rep_name, count(*) accounts_assigned
from sales_reps sr
-- It so happens that every account has a rep and every rep has at least 1 account
join accounts a 
	/* 
    For each row in the sales rep table, there are
    x corresponding rows in the accounts table. That is,
    x rows that have that sales rep's id in 'sales_rep_id'.
    For example, for Akilah Drinkard x = 3. She has 3 accounts.
    */
	on a.sales_rep_id = sr.id
group by 1
order by 1
```

Back to the problem. What is a our filting condition? In this case, our filtering condition appears in the ON clause. It's the requirement that in addtion to joining only records that match on sales rep id, we also only match records for which the point of contact's name appears earlier in the alphabet than the sales rep's name.

Because we're doing a left join in the solution query and because we're not doing any filtering on accounts, we'll see all 351 accounts. However, we may not see all 50 sales reps. Some sales reps may be filtered out by our filting condtions. And, in fact, that is the case. If we had done a right join, rather than a left join, we would see that there are sales reps who do not have any accounts that meet the filtering conditions we imposed. Akila Drinkard, for example, has 3 accounts, but she doesn't have any accounts that meet our filtering conditions. All of her points of contact have names that appear later in the alphabet than her name.

### Self Joins

A "self join" is a join between a table and itself.

One of the most common use cases for self JOINs is in cases where two events occurred, one after another.

Using inequalities in conjunction with self JOINs is common.

#### Problem: Find the accounts that have ever made multiple orders within a 30 day period. Also show all of the occassions on which this occurred. Use a left join of the orders table to itself so that we can also see occassions on which an order does not have a matching order within 30 days. Show order id, account id, and occurred at for both tables o1 and o2.

```sql
SELECT o1.id AS o1_id,
       o1.account_id AS o1_account_id,
       o1.occurred_at AS o1_occurred_at,
       o2.id AS o2_id,
       o2.account_id AS o2_account_id,
       o2.occurred_at AS o2_occurred_at
FROM   orders o1
LEFT JOIN orders o2
ON     o1.account_id = o2.account_id
-- The second order occurred later than the first order
AND    o2.occurred_at > o1.occurred_at
-- But also occurred earlier than 28 days after the first order
AND    o2.occurred_at <= o1.occurred_at + INTERVAL '28 days'
ORDER BY o1.account_id, o1.occurred_at
```

There are only 2,550 orders out of the total 6,912 orders that were ordered by the same account within 30 days of an earlier order. But we see all of the orders, due to the left join from orders o1 to orders o2. The orders that do not have a matching subsequent order within 30 days really stand out if you re-order by o1_id, because you'll see nulls in the o2 id, o2 account id, and o2 occurred at columns.

#### Problem: You could turn this into a slightly different challenge: How many accounts have ever placed more than one order for paper in the same 30 day period?

```sql
SELECT COUNT(DISTINCT o1_account_id)
FROM (
	SELECT o1.account_id AS o1_account_id
	FROM orders o1
	JOIN orders o2
	ON   o1.account_id = o2.account_id
	AND  o2.occurred_at > o1.occurred_at
	AND  o2.occurred_at <= o1.occurred_at + INTERVAL '28 days'
) AS sub
```

We get a count of distinct occurrences of o1_account_id and put the previous solution into a derived table in the FROM clause. In the derived table, we don't need to select anything other than the o1_account_id. But we do need that one, because we're counting distinct instances of it in the outer query.

#### Problem: Find all of the web events that occurred after, but not more than 1 day after, another web event. Add a column for the channel variable in both instances of the table in your query.

```sql
select
    we1.channel as we1_channel,
    we1.occurred_at as earlier,
    we2.channel as we2_channel,
    we2.occurred_at as later
from web_events we1
left join web_events we2
on we1.account_id = we2.account_id
and we1.occurred_at < we2.occurred_at
and we2.occurred_at < we1.occurred_at + interval '24 hours'
```

### Unions

The UNION operator is used to combine the result sets of 2 or more SELECT statements. It removes duplicate rows between the various SELECT statements.

#### Use Cases

**When a user wants to pull together distinct values of specified columns that are spread across multiple tables.** 

For example, a chef wants to pull together the ingredients and respective aisle across three separate meals that are maintained within different tables.

Or, say you want to determine all reasons students are late. Currently, student information is maintained in one table, but each late reason is maintained within tables corresponding to the grade the student is in. The table with the students' information needs to be appended with the late reasons. It requires no aggregation or filter, but all duplicates need to be removed. So the final use case is the one where the UNION operator makes the most sense.

#### Details of UNION

Each SELECT statement within the UNION must have the same number of fields in the result sets with similar data types.

- There must be the same number of expressions in both SELECT statements.
- The corresponding expressions must have the same data type in the SELECT statements. For example, Expression1 must be the same data type in both the first and second SELECT statement.
- The columns do NOT need to have the same names, but they usually do.
- UNION only appends DISTINCT rows. Duplicates are removed. UNION ALL appends all rows. You'll usually use UNION ALL.

Here's an example.

Run this first, to create a view:
```sql
CREATE VIEW web_events_2
AS (SELECT * FROM web_events)
```

Now run this:
```sql
SELECT *
FROM web_events
UNION
SELECT *
FROM web_events_2
```

You should see all 9,073 rows that the two tables have in common.

Another example, this time using UNION ALL, and reusing the view we created above:

```sql
SELECT *
FROM web_events
WHERE channel = 'facebook'
UNION ALL
SELECT *
FROM web_events_2
```

You should see 10,040 rows with the first thousand or so rows showing only "facebook" results from web_events_1 and the remaining rows showing all results from web_events_2.

You can use a UNION inside a subquery like this:

```sql
SELECT channel,
       COUNT(*) AS sessions
FROM (
      SELECT *
      FROM web_events
      UNION ALL
      SELECT *
      FROM web_events_2
     ) web_events
GROUP BY 1
ORDER BY 2 DESC
```
Or you can put it in a common table expression (CTE) like this:

```sql
WITH web_events AS (
      SELECT *
      FROM web_events
      UNION ALL
      SELECT *
      FROM web_events_2
     )
SELECT channel,
       COUNT(*) AS sessions
FROM  web_events
GROUP BY 1
ORDER BY 2 DESC
```

You should see a table of channels and the count of each channel, but with twice the counts that you would see wihout the UNION ALL.

### Performance Tuning

One way to make a query run faster is to reduce the number of calculations that need to be performed. Some of the high-level things that will affect the number of calculations a given query will make include:

- Table size
- Joins
- Aggregations

Query runtime is also dependent on some things that you can’t really control related to the database itself:

- Other users running queries concurrently on the database
- Database software and optimization (e.g., Postgres is optimized differently than Redshift)

#### Tip 1: Reduce table size

Try to run your queries on only a subset of your data. This called "exploratory analysis." Many query editors do this automatically. 

Aggregations: When aggregations appear in the main query, they can really sloq down your query. However, you can create a subset of your data by creating a subquery. The subquery will run first. Then you aggregate on that subquery.

For example:

```sql
SELECT account_id,
        -- Aggregations are expensive!
       SUM(poster_qty) AS sum_poster_qty
       -- So, create a subquery and limit the result rows
       -- The subquery runs first, before the aggregation in the outer query
FROM   (SELECT * FROM orders LIMIT 100) sub
-- The filter will run on the subquery results before the aggregation
WHERE  occurred_at >= '2016-01-01'
AND    occurred_at < '2016-07-01'
GROUP BY 1
-- Note that using LIMIT here will not help you, because the aggregation
-- will happen before the limit is applied to any results. LIMIT does help
-- When you're just selecting and displaying columns.
```

#### Tip 2: Reduce the complexity of tables before JOINing them

Reduce the complexity of tables by:
- reducing size of tables or subqueries before joining them
- performing aggregations on smaller tables first, before joining them. 

For example:

```sql
SELECT 
    a.name,
    sub.web_events
-- Use derived table to count web_events rather than joining web_events and accounts and then doing the count
FROM (
    SELECT 
        account_id,
        COUNT(*) AS web_events
    FROM web_events
    GROUP BY 1
    ) AS sub
JOIN accounts a 
ON a.id = sub.account_id
ORDER BY 2 DESC
```

#### Tip 3: Use EXPLAIN

Adding the command EXPLAIN at the beginning of any query allows you to get a sense of how long it will take your query to run. This will output a Query Plan which outlines the execution order of the query. The query plan will attach a cost to the query and the higher the cost, the longer the runtime. EXPLAIN is most useful to identify and modify those steps that are expensive. Do this then run EXPLAIN again to see if the speed/cost has improved.

```sql
EXPLAIN
SELECT *
FROM   web_events
WHERE  occurred_at >='2016-01-01'
AND    occurred_at < '2016-02-01'
LIMIT 100
```

![Query Plan Example](/assets/query-plan-example.png)

#### Tip 4: Aggregate over subqueries that you then join

Below is an imaginary dashboard showing lots of metrics. The query took around 90 - 110 ms to run on my machine. If we weren't aggregating, we'd get 79,000 + rows of data. This is in part because we're joining web events to orders on 'day'. This join causes a lot of duplication, which is why it's important to do the aggregation over distinct occurrences of each item, which adds more time to the calculation.

```sql
SELECT DATE_TRUNC('day', o.occurred_at) AS date,
       COUNT(DISTINCT a.sales_rep_id) AS active_sales_reps,
       COUNT(DISTINCT o.id) AS orders,
       COUNT(DISTInct we.id) AS web_visits
FROM   accounts a
JOIN   orders o
ON     o.account_id = a.id
JOIN   web_events we
-- Join web events on the day that an event occurred equaling the day that an order occurred
ON     DATE_TRUNC('day', we.occurred_at) = DATE_TRUNC('day', o.occurred_at)
-- group by order date day
GROUP BY 1
-- and order by order date day
ORDER BY 1 DESC
```

But there's a much faster way to do this, which is by aggregating over subqueries and then joining those subqueries. The final result is a bit different in the query below than in the query above, but the instructor didn't seem to think it really mattered in this case. The query below takes 50-80 ms on my machine.

Here's the subquery version of the query:

```sql

SELECT 
    -- get either order date or if that's null, get web event date
    COALESCE(orders.date, web_events.date) AS date,
    -- get active sales reps
    orders.active_sales_reps,
    -- get count of orders
    orders.orders,
    -- get count of web events
    web_events.web_visits
/* A derived table that joins the accounts and orders tables to provide a table of order date, count of sales reps, and count of orders. */
FROM(  
   SELECT DATE_TRUNC('day', o.occurred_at) AS date,
          COUNT(DISTINCT a.sales_rep_id) AS active_sales_reps,
          COUNT(DISTINCT o.id) AS orders
   FROM   accounts a
   JOIN   orders o
   ON     o.account_id = a.id
   GROUP BY 1) AS orders
-- Join the derived 'orders' table to the 'web_events' subquery
FULL JOIN
/* The subquery gets date of web event and count of web events. */
(
   SELECT DATE_TRUNC('day', we.occurred_at) AS date,
          COUNT(we.id) AS web_visits
   FROM   web_events we
   GROUP BY 1) AS web_events
-- Join on date
ON orders.date = web_events.date
-- order by date
ORDER BY 1 DESC
```
