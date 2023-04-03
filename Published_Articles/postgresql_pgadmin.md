# SQL

`SQL`, or `Structured Query Language`, is a standard programming language used for managing and manipulating data in a relational database management system (`RDBMS`). `PostgreSQL`, also known as `Postgres`, is a powerful open-source `RDBMS` that has gained significant popularity over the years due to its advanced features and robustness. In this article, we will discuss the basics of `SQL` and its application in `PostgreSQL`, as well as the popular `PostgreSQL` management tool, `pgAdmin`.

## SQL
`SQL` is used for various tasks, including creating, modifying, and deleting database structures, inserting, updating, and deleting data in a database, and querying data from a database. It uses a set of commands or statements that can be executed against a database. These commands include SELECT, INSERT, UPDATE, DELETE, CREATE, and DROP, among others.

## PostgreSQL
`PostgreSQL` is a free and open-source RDBMS that supports various advanced features, including nested transactions, user-defined types, and stored procedures. It is compatible with many programming languages, including C, C++, Java, Perl, Python, Ruby, and many others. PostgreSQL is known for its stability, reliability, and performance, making it a popular choice for many applications.

## PgAdmin
`PgAdmin` is a popular PostgreSQL management tool that provides a graphical user interface (GUI) for managing PostgreSQL databases. It is an open-source tool that is available for Windows, Linux, and macOS. With pgAdmin, you can manage database objects such as tables, views, and indexes, execute SQL queries, and monitor server activity, among other things.

##  Windows Installation - PostGreSQL and PgAdmin with Database Setup
To get started with PostgreSQL and pgAdmin, you first need to install them. PostgreSQL can be installed on Windows, Linux, or macOS, and pgAdmin can be installed on any of these operating systems as well. Once installed, you can create a new database using pgAdmin, create tables and other database objects, and insert data into the database. You can also execute SQL queries using the pgAdmin Query Tool or the PostgreSQL command-line interface (CLI).


----
## SQL Statements Fundamentals

> Let's dive into some of the most commonly used SQL commands and their usage in PostgreSQL.

### **SELECT**
The `SELECT` command is used to query data from a table in a database. It allows you to retrieve one or more columns from one or more tables based on certain criteria. Here's an example:

```
SELECT * FROM employees;
```

##### This command will retrieve all columns from the employees table.

### **SELECT DISTINCT**
The `SELECT DISTINCT` command is used to retrieve unique values from a table. Here's an example:

```
SELECT DISTINCT department FROM employees;
```

##### This command will retrieve distinct department names from the employees table.

### **COUNT**
The `COUNT` command is used to count the number of rows in a table that meet certain criteria. Here's an example:

```
SELECT COUNT(*) FROM employees 

WHERE department = 'Sales';
```

##### This command will count the number of employees in the Sales department.

### **SELECT WHERE**
The `SELECT WHERE` command is used to retrieve data from a table based on certain conditions. Here's an example:

```
SELECT * FROM employees 

WHERE salary > 50000;
```

##### This command will retrieve all columns from the employees table where the salary is greater than 50,000.

### **ORDER BY**
The ORDER BY command is used to sort the result set in ascending or descending order based on one or more columns. Here's an example:

```
SELECT * FROM employees 

ORDER BY last_name ASC, first_name ASC;
```

##### This command will retrieve all columns from the employees table and order the result set by last name in ascending order, and then by first name in ascending order.

### **LIMIT**
The `LIMIT` command is used to limit the number of rows returned by a query. Here's an example:

```
SELECT * FROM employees 

LIMIT 10;
```

##### This command will retrieve the first 10 rows from the employees table.

### **BETWEEN**
The `BETWEEN` command is used to retrieve values that fall within a specified range. Here's an example:

```
SELECT * FROM employees 

WHERE salary BETWEEN 40000 AND 60000;
```

##### This command will retrieve all columns from the employees table where the salary falls between 40,000 and 60,000.

### **IN**
The `IN` command is used to retrieve values that match any one of a specified set of values. Here's an example:

```
SELECT * FROM employees 

WHERE department IN ('Sales', 'Marketing');
```

##### This command will retrieve all columns from the employees table where the department is either Sales or Marketing.

### **LIKE/ILIKE**
The `LIKE/ILIKE` command is used to retrieve values that match a specified pattern. The `ILIKE` command is case-insensitive. Here's an example:

```
SELECT * FROM employees 

WHERE first_name LIKE 'J%';
```

##### This command will retrieve all columns from the employees table where the first name starts with the letter J.

### **% _%**
The `%` and `_` characters are wildcards used with the `LIKE/ILIKE` command. The `%` character represents any number of characters, while the `_` character represents a single character. Here's an example:


```
SELECT * FROM employees 

WHERE last_name LIKE 'Sm_th';
```
##### This command will retrieve all columns from the employees table where the last name is Smith, Smyth, or any other last name that matches the pattern.

---

## pgAdmin

If you're looking for a user-friendly way to manage your `PostgreSQL` database, look no further than `PgAdmin`. As an open-source graphical user interface (GUI) tool, `PgAdmin` provides an easy-to-use interface for a variety of tasks: 

such as creating and modifying tables, executing SQL queries, and managing user permissions. 

Getting started with `PgAdmin` is easy; simply After installing it you can use the intuitive GUI to perform operations on your database, like creating and modifying database objects, running SQL scripts, and viewing query results. 

> For more advanced users, `PgAdmin` provides features like server groups, which let you organize your database servers into logical groups to make managing large numbers of servers easier.


And here is a video clarifying the GUI of pgAdmin:

<video src="../video_assets/PostgreSQL_ File Browser.mp4" controls>
</video>