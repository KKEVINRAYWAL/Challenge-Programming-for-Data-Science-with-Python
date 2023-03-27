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