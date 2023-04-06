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

<video src="../video_assets/PostgreSQL_ File Browser.mp4">
</video>
-----------------

## Some Commonly used Aggregation Functions and Clauses in SQL, with examples in PostgreSQL.

### **AVG**
The `AVG` function is used to calculate the average value of a numerical column. Here's an example:

```
SELECT AVG(salary) FROM employees;
```

##### This command will calculate the average salary of all employees in the employees table.

### **COUNT**
The `COUNT` function is used to count the number of rows that match a specified condition. Here's an example:

```
SELECT COUNT(*) FROM employees WHERE department = 'Sales';
```
##### This command will count the number of employees in the Sales department.

### **MAX**
The `MAX` function is used to find the maximum value in a numerical column. Here's an example:

```
SELECT MAX(salary) FROM employees;
```

##### This command will find the highest salary among all employees in the employees table.

### **MIN**
The `MIN` function is used to find the minimum value in a numerical column. Here's an example:

```
SELECT MIN(salary) FROM employees;
```

##### This command will find the lowest salary among all employees in the employees table.

### **SUM**
The `SUM` function is used to calculate the total sum of a numerical column. Here's an example:

```
SELECT SUM(sales_amount) FROM sales;
```

##### This command will calculate the total sales amount from the sales table.

### **ROUND**
The `ROUND` function is used to round a numerical value to a specified number of decimal places. Here's an example:

```
SELECT ROUND(salary, 2) FROM employees;
```

##### This command will round the salary of all employees in the employees table to two decimal places.

### **GROUP BY**
The `GROUP BY` clause is used to group rows with similar values into summary rows. 

Here's an example:

```
SELECT department, AVG(salary) FROM employees 

GROUP BY department;
```

##### This command will group employees by department and calculate the average salary for each department.

When used with the `DATE()` function, it can group records based on the date component of a datetime column.


*For example*, let's say you have a table called `orders` with columns `order_id`, `customer_id`, `order_date`, and `order_amount`. You want to find the total order amount for each day in the month of January 2022.

You can use the `DATE()` function to extract the date component of the order_date column and then group the records by this date using the GROUP BY clause. Here's an example query:

```
SELECT DATE(order_date) as order_day, SUM(order_amount) as total_amount
FROM orders

WHERE order_date >= '2022-01-01' AND order_date < '2022-02-01'

GROUP BY DATE(order_date)

ORDER BY order_day;
```

##### In this query, the WHERE clause limits the records to those with an order_date in January 2022. The SELECT clause uses the DATE() function to extract the date component of order_date and aliases it as order_day. The SUM() function is used to calculate the total order amount for each order_day. Finally, the GROUP BY clause groups the records by order_day.

>The result of this query will be a table with two columns: order_day and total_amount. Each row will show the total order amount for a specific day in January 2022. The ORDER BY clause sorts the result set in ascending order by order_day.


### **ORDER BY**
The `ORDER BY` clause is used to sort the result set in ascending or descending order based on one or more columns. Here's an example:

```
SELECT department, AVG(salary) FROM employees 

GROUP BY department ORDER BY AVG(salary) DESC;
```

##### This command will group employees by department, calculate the average salary for each department, and sort the result set in descending order by average salary.

### **HAVING**
The `HAVING` clause is used to filter the result set based on a condition that involves an aggregate function. Here's an example:

"its like a WHERE statement but for the Aggregation Functions"
```
SELECT department, AVG(salary) FROM employees 

GROUP BY department 

HAVING AVG(salary) > 50000;
```
##### This command will group employees by department, calculate the average salary for each department, and filter the result set to show only departments where the average salary is greater than 50,000.

------------
# SQL join type and operator.

## **AS**
The `AS` operator is used to alias a table or column with a different name. It's especially useful when you need to rename columns or tables in the output to make it more readable and meaningful. The syntax for using the AS operator is:

```
SELECT column_name AS alias_name FROM table_name;
```

For example, in the query we showed earlier:

```
SELECT e.first_name, e.last_name, d.department_name AS dept_name
FROM employees e

INNER JOIN departments d ON e.department_id = d.department_id;
```

##### We are aliasing the departments.department_name column as dept_name using the AS operator. This makes the output more readable and meaningful.

## INNER JOIN
The `INNER JOIN` operator returns only the rows that have matching values in both tables. It's used to combine the rows from two or more tables based on a common column. The syntax for using `INNER JOIN` is:

```
SELECT column_name(s)
FROM table1

INNER JOIN table2

ON table1.column_name = table2.column_name;
```

For example:

```
SELECT e.first_name, e.last_name, d.department_name
FROM employees e

INNER JOIN departments d ON e.department_id = d.department_id;
```

##### This query is using INNER JOIN to combine the employees table with the departments table based on the department_id column. The result set will include only the rows where there is a match in both tables.

## OUTER JOIN
The `OUTER JOIN` operator returns all the rows from one table and the matching rows from the other table. If there is no match in the other table, the result will include NULL values. 

There are two types of outer joins: `LEFT OUTER JOIN` and `RIGHT OUTER JOIN`.

### `LEFT OUTER JOIN` 
returns all the rows from the left table and the matching rows from the right table. If there is no match in the right table, the result will include NULL values.

```
SELECT column_name(s)
FROM table1
LEFT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

### `RIGHT OUTER JOIN` 

returns all the rows from the right table and the matching rows from the left table. If there is no match in the left table, the result will include NULL values.

```
SELECT column_name(s)
FROM table1
RIGHT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

For example:

```
SELECT e.first_name, e.last_name, d.department_name
FROM employees e

LEFT OUTER JOIN departments d ON e.department_id = d.department_id;
```

In this query, the `LEFT OUTER JOIN` operator is used to join the employees table with the departments table based on the department_id column. The result set will include all the rows from the employees table and the matching rows from the departments table. If there is no match in the departments table, the department_name column will contain a NULL value.

### **FULL JOIN**
The `FULL JOIN` operator is used to combine the results of a LEFT JOIN and a RIGHT JOIN. It returns all the rows from both tables and matches the rows that have matching values in both tables. If there are no matching rows in one of the tables, the result set will contain NULL values for the columns of that table.

The syntax for a `FULL JOIN` is as follows:

```
SELECT column_names
FROM table1
FULL JOIN table2
ON table1.column_name = table2.column_name;
```

Here's an example of a FULL JOIN:

Suppose we have two tables, `"Customers"` and `"Orders"`. The `"Customers"` table has columns `"CustomerID"` and `"CustomerName"`, while the `"Orders"` table has columns `"OrderID"`, `"CustomerID"`, and `"OrderDate"`.

To get a list of all customers and their orders, we can use a `FULL JOIN` as follows:

```
SELECT Customers.CustomerName, Orders.OrderID, Orders.OrderDate
FROM Customers

FULL JOIN Orders

ON Customers.CustomerID = Orders.CustomerID

ORDER BY Customers.CustomerName;
```

In this example, we join the two tables using the `"CustomerID"` column. The result set will include all customers, including those who have not placed any orders, and all orders, including those that have not been placed by any customers. 

If there is no matching customer for an order or no matching order for a customer, the corresponding columns in the result set will contain `NULL` values.

> Note that the `ORDER BY` clause is used to sort the result set by the `"CustomerName"` column. This clause can be used with any type of `JOIN` to sort the results according to a specific column.

------------------------

## Advanced SQL Commands:

### TimeStamps and Extract:
`TimeStamps` are a way to represent time and date values in SQL. The Extract function is used to extract specific parts of a timestamp, such as `year`, `month`, `day`, `hour`, `minute`, and `second`.

Here's an example query that uses the Extract function to get the month and year from a timestamp column:

```
SELECT EXTRACT(MONTH FROM timestamp_column) AS month,
       EXTRACT(YEAR FROM timestamp_column) AS year
FROM table_name;
```

### Math Functions:
SQL provides several built-in math functions, such as `ABS`, `ROUND`, `CEIL`, `FLOOR`, and `TRUNC`. These functions can be used to perform arithmetic operations and round numbers.

Here's an example query that uses the ROUND function to round a number to two decimal places:

```
SELECT ROUND(number_column, 2) AS rounded_number
FROM table_name;
```

### String Functions:
SQL also provides several built-in string functions, such as CONCAT, LENGTH, SUBSTR, UPPER, and LOWER. These functions can be used to manipulate string values.

Here's an example query that uses the CONCAT function to concatenate two columns:

```
SELECT CONCAT(column1, ' ', column2) AS full_name
FROM table_name;
```

### Sub-Query:
A `sub-query` is a query that is nested inside another query. It is used to retrieve data that will be used as input for the main query. Sub-queries can be used in the `SELECT`, `WHERE`, and `HAVING` clauses.

Here's an example query that uses a sub-query to get the average of a column:

```
SELECT AVG(column_name)
FROM (SELECT column_name FROM table_name WHERE condition) subquery_alias;
```

### Self-Join:
A `self-join` is a join operation where a table is joined with itself. It is used to relate rows within the same table.

Here's an example query that uses a self-join to find all pairs of employees who have the same manager:

```
SELECT a.employee_name, b.employee_name
FROM employees a
JOIN employees b
ON a.manager_id = b.manager_id
WHERE a.employee_name <> b.employee_name;
```

### To-Char:
The `To-Char` function is used to convert a value to a character string with a specified format. It is commonly used to format date and time values.

Here's an example query that uses the To-Char function to convert a date column to a specific format:

```
SELECT TO_CHAR(date_column, 'MM/DD/YYYY') AS formatted_date
FROM table_name;
```

## Tips & Tricks:

### TimeStamps and Extract:
- Timestamps can be stored in different formats, such as ISO 8601 or Unix time, and SQL has built-in functions to handle these formats.
- The `Extract` function can be used with different parts of a timestamp, such as microseconds, time zones, and time intervals.
- The `EXTRACT` function can also be used with INTERVAL values, which represent a duration of time.

### Math Functions:
- The `ROUND` function can be used with negative numbers to round to the left of the decimal point, such as rounding to the nearest thousand.
- The `CEIL` function rounds a number up to the nearest integer, while the FLOOR function rounds a number down to the nearest integer.
- The `TRUNC` function truncates a number to a specified number of decimal places.
String Functions:
- The `CONCAT` function can be used to concatenate more than two columns or strings, by using multiple arguments separated by commas.
- The `SUBSTR` function can be used to extract a substring from a string, by specifying the starting position and the length.
- The UPPER and LOWER functions can be used to convert a string to uppercase or lowercase, respectively.

### Sub-Query:
- Sub-queries can be nested inside other sub-queries, allowing for complex queries to be constructed.
- Sub-queries can also be used to perform aggregate functions, such as AVG, MAX, and MIN.
- Sub-queries can be used in the WHERE clause to filter rows based on a sub-set of data.

### Self-Join:
- Self-joins can be used to represent hierarchical or recursive relationships, such as a manager-employee relationship or a parent-child relationship.
- Self-joins can be used to find duplicates or matching records within the same table.
- Self-joins can be combined with other SQL commands, such as `GROUP BY` and `HAVING`, to further refine the query results.

### To-Char:
- The TO_CHAR function can be used with a wide range of format codes, such as month `names`, `day names`, and `time zones`.
- The TO_CHAR function can be combined with other SQL commands, such as `WHERE` and `ORDER` `BY`, to filter and sort data based on formatted date values.
- The TO_CHAR function can also be used with numeric and boolean values, allowing for flexible formatting options.

----
