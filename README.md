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









