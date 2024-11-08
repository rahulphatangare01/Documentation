# Mysql Interview Questions

## Mysql Basic Interview Questions


<details>
<summary>
1.<b> What is SQL and what is it used for?</b>
</summary>

**SQL (Structured Query Language)** is a domain-specific, declarative programming language designed for managing relational databases. It is the primary language for tasks like data retrieval, data manipulation, and database administration.

**Core Components**

1. **DDL (Data Definition Language)**: Used for defining and modifying the structure of the database.
2. **DML (Data Manipulation Language)**: Deals with adding, modifying, and removing data in the database.
3. **DCL (Data Control Language)**: Manages the permissions and access rights of the database.
4. **TCL (Transaction Control Language)**: Governs the transactional management of the database, such as commits or rollbacks.

**Common Database Management Tasks**
1. **Data Retrieval and Reporting**: Retrieve and analyze data, generate reports, and build dashboards.
2. **Data Manipulation**: Insert, update, or delete records from tables. Powerful features like Joins and Subqueries enable complex operations.

3. **Data Integrity**: Ensure data conform to predefined rules. Techniques like foreign keys, constraints, and triggers help maintain the integrity of the data.

4. **Data Security**: Manage user access permissions and roles.

5. **Data Consistency**: Enforce ACID properties (Atomicity, Consistency, Isolation, Durability) in database transactions.

6. **Data Backups and Recovery**: Perform database backups and ensure data is restorable in case of loss.

7. **Data Normalization**: Design databases for efficient storage and reduce data redundancy.

8. **Indices and Performance Tuning**: Optimize queries for faster data retrieval.

9. **Replication and Sharding**: Advanced techniques for distributed systems.

**Basic SQL Commands**

- **CREATE DATABASE**: Used to create a new database.
- **CREATE TABLE**: Defines a new table.
- **INSERT INTO**: Adds a new record into a table.
- **SELECT**: Retrieves data from one or more tables.
- **UPDATE**: Modifies existing records.
- **DELETE**: Removes records from a table.
- **ALTER TABLE**: Modifies an existing table (e.g., adds a new column, renames an existing column, etc.).
- **DROP TABLE**: Deletes a table (along with its data) from the database.
- **INDEX**: Adds an index to a table for better performance.
- **VIEW**: Creates a virtual table that can be used for data retrieval.
- **TRIGGER**: Triggers a specified action when a database event occurs.
- **PROCEDURE** and **FUNCTION**: Store database logic for reuse and to simplify complex operations.

Code Example: Basic SQL Queries
Here is the SQL code:


```jsx harmony 

-- Create a database
CREATE DATABASE Company;

-- Use Company database
USE Company;

-- Create tables
CREATE TABLE Department (
    DeptID INT PRIMARY KEY AUTO_INCREMENT,
    DeptName VARCHAR(50) NOT NULL
);

CREATE TABLE Employee (
    EmpID INT PRIMARY KEY AUTO_INCREMENT,
    EmpName VARCHAR(100) NOT NULL,
    EmpDeptID INT,
    FOREIGN KEY (EmpDeptID) REFERENCES Department(DeptID)
);

-- Insert data
INSERT INTO Department (DeptName) VALUES ('Engineering');
INSERT INTO Department (DeptName) VALUES ('Sales');

INSERT INTO Employee (EmpName, EmpDeptID) VALUES ('John Doe', 1);
INSERT INTO Employee (EmpName, EmpDeptID) VALUES ('Jane Smith', 2);

-- Select data from database
SELECT * FROM Department;
SELECT * FROM Employee;

-- Perform an inner join to combine data from two tables
SELECT Employee.EmpID, Employee.EmpName, Department.DeptName
FROM Employee
JOIN Department ON Employee.EmpDeptID = Department.DeptID;
```
</details>


<details>
<summary>
2.<b> What does SQL stand for?</b>
</summary>

SQL stands for Structured Query Language. SQL lets you access and manipulate databases. SQL is an ANSI (American National Standards Institute) standard.

</details>


<details>
<summary>
3.<b> SQL is (referring to it as a Programming Language)</b>
</summary>

**SQL is a declarative language in which the expected result or operation is given without the specific details about how to accomplish the task**. The steps required to execute SQL statements are handled transparently by the SQL database. Sometimes SQL is characterized as non-procedural because procedural languages generally require the details of the operations to be specified, such as opening and closing tables, loading and searching indexes, or flushing buffers and writing data to filesystems. Therefore, SQL is considered to be designed at a higher conceptual level of operation than procedural languages because the lower level logical and physical operations aren't specified and are determined by the SQL engine or server process that executes it.

</details>


<details>
<summary>
4.<b> Which of the following is NOT a SQL command? (SELECT, REMOVE, UPDATE, INSERT)</b>
</summary>

REMOVE is not a valid SQL command.

**Some of The Most Important SQL Commands**

```jsx harmony 
SELECT - extracts data from a database
UPDATE - updates data in a database
DELETE - deletes data from a database
INSERT INTO - inserts new data into a database
CREATE DATABASE - creates a new database
ALTER DATABASE - modifies a database
CREATE TABLE - creates a new table
ALTER TABLE - modifies a table
DROP TABLE - deletes a table
CREATE INDEX - creates an index (search key)
DROP INDEX - deletes an index

```
</details>

<details>
<summary>
5.<b> What is MySQL?</b>
</summary>

MySQL is the most popular Open Source SQL database management system developed, distributed, and supported by Oracle Corporation.

**Another common SQL interview question regarding MySQL may come in a different form**

**“What is the difference between SQL and MySQL?” or Difference between SQL and MySQL**:

SQL is a structured query language that is used for manipulating and accessing the relational database, on the other hand, MySQL itself is a relational database that uses SQL as the standard database language.
</details>


<details>
<summary>
6.<b>  What are some properties of PL/SQL?</b>
</summary>

PL/SQL is a combination of SQL along with the procedural features of programming languages. It was developed by Oracle Corporation in the early 90's to enhance the capabilities of SQL. PL/SQL is one of three key programming languages embedded in the Oracle Database, along with SQL itself and Java.

Another common SQL interview question regarding PL/SQL may come in a different form:

**“What is the difference between SQL and PL/SQL? or Difference between SQL and PL/SQL**:
SQL is a Structured Query Language used to issue a single query or execute a single insert/update/delete.

- PL-SQL is a programming language SQL, used to write full programs using variables, loops,operators etc. to carry out multiple selects/inserts/updates/deletes.

- SQL may be considered as the source of data for our reports, web pages and screens.

- PL/SQL can be considered as the application language similar to Java or PHP. It might be the language used to build, format and display those reports, web pages and screens.

- SQL is a data oriented language used to select and manipulate sets of data.

- PL/SQL is a procedural language used to create applications.

**SQL vs. PL-SQL**

- SQL is used to write queries, DDL and DML statements.
- PL/SQL is used to write program blocks, functions, procedures triggers,and packages.
- SQL is executed one statement at a time.
- PL/SQL is executed as a block of code.
- SQL is declarative, i.e., it tells the database what to do but not how to do it. Whereas, PL/SQL is procedural, i.e., it tells the database how to do things.
- SQL can be embedded within a PL/SQL program. But PL/SQL cant be embedded within a SQL statement.
</details>


<details>
<summary>
7.<b> What are the possible values for the BOOLEAN data field in MySQL?</b>
</summary>

MySQL uses TINYINT(1) data type to represent boolean values. A value of zero is considered false . Non-zero values are considered true .

</details>


<details>
<summary>
8.<b> What data type would you choose if you wanted to store the distance (rounded to the nearest mile)?</b>
</summary>

```jsx harmony 
INTEGER (or INT )   

```
</details>


<details>
<summary>
9.<b> Which are valid SQL keywords (statements & clauses)</b>
</summary>

- **SELECT** - extracts data from a database
- **FROM** - clause is used to specify the tables to extract data from
- **WHERE** - clause is used to extract only those records that fulfill a specified condition.
- **GROUP BY** - is often used with aggregate functions (COUNT , MAX , MIN , SUM , AVG ) to group the result-set by one or more columns.
- **HAVING** - clause was added to SQL because the WHERE keyword could not be used with aggregate functions.
- **ORDER BY** - keyword is used to sort the result-set in ascending or descending order.
- **UPDATE** - updates data in a database
- **DELETE** - deletes data from a database
- **INSERT INTO** - inserts new data into a database
- **CREATE DATABASE** - creates a new database
- **ALTER DATABASE** - modifies a database
- **CREATE TABLE** - creates a new table
- **ALTER TABLE** - modifies a table
- **DROP TABLE** - deletes a table
- **CREATE INDEX** - creates an index (search key)
- **DROP INDEX** - deletes an index
</details>


<details>
<summary>
10.<b> Which SQL statement is used to extract data from a database?</b>
</summary>

A **SELECT** statement retrieves zero or more rows from one or more database tables or database views.

As SQL is a declarative programming language, SELECT queries specify a result set, but do not specify how to calculate it.

The SELECT statement has many optional clauses:

- **WHERE** specifies which rows to retrieve.

- **GROUP BY** groups rows sharing a property so that an aggregate function can be applied to each group.

- **HAVING** selects among the groups defined by the GROUP BY clause.

- **ORDER BY** specifies an order in which to return the rows.

- **AS** provides an alias which can be used to temporarily rename tables or columns.

</details>


<details>
<summary>
11.<b> How to select all records from the table 'Products'?</b>
</summary>

`SELECT * FROM Products`;

If you want to select all the fields available in the table, use the * syntax as this:

SELECT * FROM Products;
</details>

<details>
<summary>
12.<b> Can we rename a column in the output of SQL query?</b>
</summary>

Yes, using AS .

SQL aliases are used to give a column in a table, a temporary name.

Aliases are often used to make column names more readable.

An alias only exists for the duration of the query.

Alias Column Syntax:

- SELECT column_name AS alias_name
- FROM table_name;
</details>

<details>
<summary>
13.<b> With SQL, how do you select a column named "FirstName" from a table named "Customers"?</b>
</summary>

`SELECT FirstName FROM Customers`;

The SELECT statement is used to select data from a database.

The data returned is stored in a result table, called the result-set.

SELECT Syntax

```jsx harmony 
SELECT column1, column2, ...
FROM table_name;

```
Here, column1, column2, ... are the field names of the table you want to select data from. If you want to select all the fields available in the table, use the following syntax:

SELECT * FROM table_name;
</details>


<details>
<summary>
14.<b>  What does the SQL FROM clause do?</b>
</summary>

The SQL FROM clause is used to list the tables and any joins required for the SQL statement.

</details>


<details>
<summary>
15.<b>  Which SQL statement is used to return only different values?</b>
</summary>

The SELECT DISTINCT statement is used to return only distinct (different) values.

Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

SELECT DISTINCT Syntax

**SELECT Syntax**

```jsx harmony 
SELECT DISTINCT column1, column2, ...
FROM table_name;

```
</details>

<details>
<summary>
16.<b> Consider the following schema ADDRESSES (id, street_name, number, city, state) Which of the following query would display the distinct cities in the ADDRESSES table?</b>
</summary>

`SELECT DISTINCT city FROM addresses`;

(same theory applies as for the previous question)

</details>


<details>
<summary>
17.<b>  With SQL, how do you select all the records from a table named "Customers" where the value of the column "FirstName" is "John"?</b>
</summary>

`SELECT * FROM Customers WHERE FirstName='John'`;

The WHERE clause is used to filter records.

The WHERE clause is used to extract only those records that fulfill a specified condition.

SQL requires single quotes around text values (most database systems will also allow double quotes).

</details>


<details>
<summary>
18.<b> The OR operator displays a record if ANY conditions listed are true. The AND operator displays a record if ALL of the conditions listed are true.</b>
</summary>

The `WHERE` clause can be combined with `AND` , `OR` , and `NOT` operators.

The `AND` and `OR` operators are used to filter records based on more than one condition:

The `AND` operator displays a record if all the conditions separated by AND are TRUE .

The `OR` operator displays a record if any of the conditions separated by OR are TRUE .

The `NOT` operator displays a record if the condition(s) is NOT TRUE .

**AND Syntax**

```jsx harmony 
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 …;

```

**OR Syntax**

```jsx harmony 
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```

**NOT Syntax**

```jsx harmony 
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```
</details>


<details>
<summary>
19.<b> Which of the following SQL statements has correct syntax?</b>
</summary>

SELECT * FROM Table1 WHERE Column1 >= 100

SQL Comparison Operators

- '=' Equal to

- '>' Greater than

- '<' Less than

- '>=' Greater than or equal to

- '<=' Less than or equal to

- '≠' Not equal to
</details>


<details>
<summary>
20.<b> With SQL, how do you select all the records from a table named "Customers" where the "FirstName" is "John" and the "LastName" is "Jackson"?</b>
</summary>

```jsx harmony 
SELECT * FROM Customers WHERE FirstName='John' AND LastName='Jackson'
```

Same answers as for the previous 2 questions.

You must use the AND operator that displays a record if all the conditions separated by AND are TRUE and the = (‘equal’) comparison operator.
</details>


<details>
<summary>
21.<b> How to select random 10 rows from a table? </b>
</summary>

The easiest way to generate random rows in MySQL is to use the ORDER BY RAND() clause

```jsx harmony 
SELECT * FROM tbl ORDER BY RAND() LIMIT 10;
```

This can work fine for small tables. However, for big table, it will have a serious performance problem as in order to generate the list of random rows, MySQL need to assign random number to each row and then sort them.

Even if you want only 10 random rows from a set of 100k rows, MySQL need to sort all the 100k rows and then, extract only 10 of them.
</details>


<details>
<summary>
22.<b>Examine the following code. What will the value of price be if the statement finds a NULL value? SELECT name, ISNULL(price, 50) FROM PRODUCTS </b>
</summary>

What is a `NULL` Value?

A field with a `NULL` value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

**Note**: It is very important to understand that a NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

**How can you return a default value for a NULL?**

**MySQL**

The `MySQL IFNULL()` function lets you return an alternative value if an expression is NULL:

```jsx harmony 
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products
```

or we can use the `COALESCE()` function, like this:

```jsx harmony 
SELECT ProductName, UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder, 0))
FROM Products
```

**SQL Server**

The **SQL Server** `ISNULL()` function lets you return an alternative value when an expression is NULL :

- SELECT ProductName, UnitPrice * (UnitsInStock + ISNULL(UnitsOnOrder, 0))
- FROM Products

**MS Access**

The MS Access IsNull() function returns TRUE (-1) if the expression is a null value, otherwise FALSE (0) :

- SELECT ProductName, UnitPrice * (UnitsInStock + IIF(IsNull(UnitsOnOrder), 0, UnitsOnOrder))
- FROM Products

**Oracle**

The Oracle NVL() function achieves the same result:
- SELECT ProductName, UnitPrice * (UnitsInStock + NVL(UnitsOnOrder, 0))
- FROM Products
</details>



<details>
<summary>
23.<b> Which operator is used to search for a specified text pattern in a column?</b>
</summary>

The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

There are two wildcards used in conjunction with the `LIKE` operator:

% - The percent sign represents zero, one, or multiple characters

_ - The underscore represents a single character

**Examples**:

- WHERE CustomerName LIKE 'a%' -- Finds any values that starts with "a"
- WHERE CustomerName LIKE '%a' -- Finds any values that ends with "a"
- WHERE CustomerName LIKE '%or%' -- Finds any values that have "or" in any position
- WHERE CustomerName LIKE '_r%' -- Finds any values that have "r" in the second position
- WHERE CustomerName LIKE 'a_%_%' -- Finds any values that starts with "a" and are at least 3 characters in length
- WHERE ContactName LIKE 'a%o' -- Finds any values that starts with "a" and ends with "o"
</details>


<details>
<summary>
24.<b> How to write a query to show the details of a student from Students table whose FirstName starts with 'K'?</b>
</summary>

`SELECT * FROM Students WHERE FirstName LIKE 'K%'`.

Explanation from previous question applies.
</details>


<details>
<summary>
25.<b> Which operator is used to select values within a range?</b>
</summary>

The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

The BETWEEN operator is inclusive: begin and end values are included.

BETWEEN Syntax

```jsx harmony 
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

```
</details>


<details>
<summary>
26.<b></b>
</summary>
</details>


<details>
<summary>
27.<b></b>
</summary>
</details>


<details>
<summary>
28.<b></b>
</summary>
</details>


<details>
<summary>
29.<b></b>
</summary>
</details>


<details>
<summary>
30.<b></b>
</summary>
</details>


<details>
<summary>
31.<b></b>
</summary>
</details>


<details>
<summary>
32.<b></b>
</summary>
</details>


<details>
<summary>
33.<b></b>
</summary>
</details>



<details>
<summary>
34.<b></b>
</summary>
</details>


<details>
<summary>
35.<b></b>
</summary>
</details>



## Mysql Advance Interview Questions

<details>
<summary>
36.<b> Describe the difference between SQL and NoSQL databases.</b>
</summary>

`SQL` and `NoSQL` databases offer different paradigms, each designed to suit various types of data and data handling.

**Top-Level Differences**

- **SQL**: Primarily designed for structured (structured, semi-structured) data — data conforming to a predefined schema.

- **NoSQL**: Suited for unstructured or semi-structured data that evolves gradually, thereby supporting flexible schemas.

- **SQL**: Employs SQL (Structured Query Language) for data modification and retrieval.

- **NoSQL**: Offers various APIs (like the document and key-value store interfaces) for data operations; the use of structured query languages can vary across different NoSQL implementations.

**SQL**: Often provides ACID (Atomicity, Consistency, Isolation, Durability) compliance to ensure data integrity.

**NoSQL**: Databases are oftentimes optimized for high performance and horizontal scalability, with potential trade-offs in consistency.

**Common NoSQL Database Types**

**Document Stores**

**Example**: MongoDB, Couchbase
**Key Features**: Each record is a self-contained document, typically formatted as JSON. Relationship between documents is established through embedded documents or references. Example: Users and their blog posts could be encapsulated within a single document or linked via document references.

**Key-Value Stores**
**Example**: Redis, Amazon DynamoDB
**Key Features**: Data is stored as a collection of unique keys and their corresponding values. No inherent structure or schema is enforced, providing flexibility in data content. Example: Shopping cart items keyed by a user's ID.

**Wide-Column Stores (Column Families)**
**Example**: Apache Cassandra, HBase
**Key Features**: Data is grouped into column families, akin to tables in traditional databases. Each column family can possess a distinct set of columns, granting a high degree of schema flexibility. Example: User profiles, where certain users might have additional or unique attributes.

**Graph Databases**
**Example**: Neo4j, JanusGraph
**Key Features**: Tailored for data with complex relationships. Data entities are represented as nodes, and relationships between them are visualized as edges. Example: A social media platform could ensure efficient friend connections management.

**Data Modeling Differences**
**SQL**: Normalization is employed to minimize data redundancies and update anomalies.
**NoSQL**: Data is often denormalized, packaging entities together to minimize the need for multiple queries.

**Auto-Incrementing IDs**
**SQL**: Often, each entry is assigned a unique auto-incrementing ID.
**NoSQL**: The generation of unique IDs can be driven by external systems or even specific to individual documents within a collection.

**Handling Data Relationships**
**SQL**: Relationships between different tables are established using keys (e.g., primary, foreign).
**NoSQL**: Relationships are handled either through embedded documents, referencing techniques, or as graph-like structures in dedicated graph databases.

**Transaction Support**
**SQL**: Transactions (a series of operations that execute as a single unit) are standard.
**NoSQL**: The concept and features of transactions can be more varied based on the specific NoSQL implementation.

**Data Consistency Levels**
**SQL**: Traditionally ensures strong consistency across the database to maintain data integrity.
**NoSQL**: Offers various consistency models, ranging from strong consistency to eventual consistency. This flexibility enables performance optimizations in distributed environments.

**Scalability**
**SQL**: Typically scales vertically, i.e., by upgrading hardware.
**NoSQL**: Is often designed to scale horizontally, using commodity hardware across distributed systems.

**Data Flexibility**
**SQL**: Enforces a predefined, rigid schema, making it challenging to accommodate evolving data structures.
**NoSQL**: Supports dynamic, ad-hoc schema updates for maximum flexibility.

**Data Integrity & Validation**
**SQL**: Often relies on constraints and strict data types to ensure data integrity and validity.
**NoSQL**: Places greater emphasis on the application layer to manage data integrity and validation.

</details>


<details>
<summary>
37.<b> What are the different types of SQL commands?</b>
</summary>

**SQL** commands fall into four primary categories: **Data Query Language** (DQL), **Data Definition Language** (DDL), **Data Manipulation Language** (DML), and **Data Control Language** (DCL).

**Data Query Language (DQL)**
These commands focus on querying data within tables.

**Keywords and Examples**:
**SELECT**: Retrieve data.
**FROM**: Identify the source table.
**WHERE**: Apply filtering conditions.
**GROUP BY**: Group results based on specified fields.
**HAVING**: Establish qualifying conditions for grouped data.
**ORDER BY**: Arrange data based on one or more fields.
**LIMIT**: Specify result count (sometimes replaces SELECT TOP for certain databases).
**JOIN**: Bring together related data from multiple tables.


**Data Definition Language (DDL)**
DDL commands are for managing the structure of the database, including tables and constraints.

**Keywords and Examples:**
**CREATE TABLE**: Generate new tables.
**ALTER TABLE**: Modify existing tables.
**ADD, DROP**: Incorporate or remove elements like columns, constraints, or properties.
**CREATE INDEX**: Establish indexes to improve query performance.
**DROP INDEX**: Remove existing indexes.
**TRUNCATE TABLE**: Delete all rows from a table, but the table structure remains intact.
**DROP TABLE**: Delete tables from the database.

**Data Manipulation Language (DML)**
These commands are useful for handling data within tables.

**Keywords and Examples**:
**INSERT INTO**: Add new rows of data.
**SELECT**: Copy data from another table or tables.
**UPDATE**: Modify existing data in a table.
**DELETE**: Remove rows of data from a table.

**Data Control Language (DCL)**

DCL is all about managing the access and permissions to database objects.

**Keywords and Examples**:
**GRANT**: Assign permission to specified users or roles for specific database objects.
**REVOKE**: Withdraw or remove these permissions previously granted.


</details>



<details>
<summary>
38.<b> Explain the purpose of the SELECT statement.</b>
</summary>

The **SELECT** statement in SQL is fundamental to data retrieval and manipulation within relational databases. Its primary role is to precisely choose, transform, and organize data per specific business requirements.

**Key Components of the SELECT Statement**
The **SELECT** statement typically comprises the following elements:

**SELECT**: Identifies the columns or expressions to be included in the result set.
**FROM**: Specifies the table(s) from which the data should be retrieved.
**WHERE**: Introduces conditional statements to filter rows based on specific criteria.
**GROUP BY**: Aggregates data for summary or statistical reporting.
**HAVING**: Functions like WHERE, but operates on aggregated data.
**ORDER BY**: Defines the sort order for result sets.
**LIMIT or TOP**: Limits the number of rows returned.

**Practical Applications of SELECT**
The robust design of the **SELECT** statement empowers data professionals across diverse functions, enabling:

**Data Exploration**: Gaining insights through filtered views or aggregated summaries.
**Data Transformation**: Creating new fields via operations such as concatenation or mathematical calculations.
**Data Validation**: Verifying data against defined criteria.
**Data Reporting**: Generating formatted outputs for business reporting needs.
**Data Consolidation**: Bringing together information from multiple tables or databases.
**Data Export**: Facilitating the transfer of query results to other systems or for data backup.
Beyond these functions, proper utilization of the other components ensures efficiency and consistency working with relational databases.

**SELECT Query Example**
Here is the SQL code:

```jsx harmony 
SELECT 
    Orders.OrderID, 
    Customers.CustomerName, 
    Orders.OrderDate, 
    OrderDetails.UnitPrice, 
    OrderDetails.Quantity, 
    Products.ProductName, 
    Employees.LastName
FROM 
    ((Orders
    INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
    INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
    INNER JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID

```
</details>


<details>
<summary>
39.<b> What is the difference between WHERE and HAVING clauses?</b>
</summary>

`WHERE` and H`AVING` clauses are both used in SQL queries to filter data, but they operate in distinct ways.

**WHERE Clause**
The `WHERE` clause is primarily used to filter records before they are grouped or aggregated. It's typically employed with non-aggregated fields or raw data.

**HAVING Clause**
Conversely, the `HAVING` clause filters data **after** the grouping step, often in conjunction with aggregate functions like `SUM` or `COUNT`. This makes it useful for setting group-level conditions.
</details>


<details>
<summary>
40.<b> Define what a JOIN is in SQL and list its types.</b>
</summary>

`Join` operations in SQL are responsible for combining rows from multiple tables, primarily based on related columns that are established using a foreign key relationship.

**The three common types of joins in SQL are**:

1. Inner Join
2. Outer Join
3. Left Outer Join
4. Right Outer Join
5. Full Outer Join
6. Cross Join
7. Self Join
8. Inner Join

Inner Join only returns rows where there is a match in both tables for the specified column(s).

**Visual Representation:**

```jsx harmony 

Table1:        Table2:            Result (Inner Join):

A   B         B    C               A    B    C
-   -         -    -               -    -    -
1  aa         aa   20              1   aa   20
2  bb         bb   30              2   bb   30
3  cc         cc   40    
```

**SQL Query:**

```jsx harmony 
SELECT Table1.A, Table1.B, Table2.C
FROM Table1
INNER JOIN Table2 ON Table1.B = Table2.B;

```
**Outer Join**
Outer Joins—whether left, right or full—include all records from one table (the "left" or the "right" table") and matched existing records from the other table. Unmatched records are filled with NULL values for missing columns from the other table.

**Left Outer Join**
Left Outer Join (or simply Left Join) returns all records from the "left" table and the matched records from the "right" table.

**Visual Representation:**

```jsx harmony 

Table1:        Table2:            Result (Left Outer Join):

A   B         B    C               A    B    C
-   -         -    -               -    -    -
1  aa         aa   20              1   aa   20
2  bb         bb   30              2   bb   30
3  cc         NULL  NULL            3   cc  NULL
```

**SQL Query**:

```jsx harmony 
SELECT Table1.A, Table1.B, Table2.C
FROM Table1
LEFT JOIN Table2 ON Table1.B = Table2.B;

```

**Right Outer Join**
Right Outer Join (or Right Join) returns all records from the "right" table and the matched records from the "left" table.

**Visual Representation:**

```jsx harmony 
Table1:        Table2:            Result (Right Outer Join):

A   B         B    C               A    B    C
-   -         -    -               -    -    -
1  aa         aa   20              1   aa   20
2  bb         bb   30              2   bb   30
NULL NULL      cc   40             NULL NULL  40

```

**SQL Query**:

```jsx harmony 

SELECT Table1.A, Table1.B, Table2.C
FROM Table1
RIGHT JOIN Table2 ON Table1.B = Table2.B;
```

**Full Outer Join**
Full Outer Join (or Full Join) returns all records when there is a match in either the left or the right table.

**Visual Representation**:

```jsx harmony 

Table1:        Table2:            Result (Full Outer Join):

A   B         B    C               A    B    C
-   -         -    -               -    -    -
1  aa         aa   20              1   aa   20
2  bb         bb   30              2   bb   30
3  cc         NULL  NULL            3   cc  NULL                           
NULL NULL      cc   40            NULL NULL  40
```

**SQL Query**:

```jsx harmony 
SELECT COALESCE(Table1.A, Table2.A) AS A, Table1.B, Table2.C
FROM Table1
FULL JOIN Table2 ON Table1.B = Table2.B;

```

**Cross Join**
A Cross Join, also known as a Cartesian Join, produces a result set that is the cartesian product of the two input sets. It will generate every possible combination of rows from both tables.

**Visual Representation**:

```jsx harmony 
Table1:        Table2:            Result (Cross Join):

A   B         C    D               A    B    C    D
-   -         -    -               -    -    -    -
1  aa        20    X               1   aa   20   X
2  bb        30    Y               1   aa   30   Y
3  cc        40    Z               1   aa   40   Z
                                    2   bb   20   X
                                    2   bb   30   Y
                                    2   bb   40   Z
                                    3   cc   20   X
                                    3   cc   30   Y
                                    3   cc   40   Z

```

**SQL Query:**

```jsx harmony 

SELECT Table1.*, Table2.*
FROM Table1
CROSS JOIN Table2;
```

**Self Join**
A Self Join is when a table is joined with itself. This is used when a table has a relationship with itself, typically when it has a parent-child relationship.

**Visual Representation**:

```jsx harmony 
Employee:                              Result (Self Join):

EmpID   Name       ManagerID       EmpID  Name     ManagerID
-       -           -               -       -          -
1      John         3               1     John        3
2      Amy          3               2     Amy         3
3      Chris       NULL              3    Chris      NULL
4      Lisa        2                4     Lisa        2
5      Mike        2                5     Mike        2

```

**SQL Query**:

```jsx harmony 
SELECT E1.EmpID, E1.Name, E1.ManagerID
FROM Employee AS E1
LEFT JOIN Employee AS E2 ON E1.ManagerID = E2.EmpID;
```
</details>


<details>
<summary>
41.<b>  What is a primary key in a database?</b>
</summary>

A `primary key` in a database is a unique identifier for each record in a table.

**Key Characteristics**

- **Uniqueness**: Each value in the primary key column is unique, distinguishing every record.

- **Non-Nullity**: The primary key cannot be null, ensuring data integrity.

- **Stability**: It generally does not change throughout the record's lifetime, promoting consistency.

**Data Integrity Benefits**

**Entity Distinctness**: Enforces that each record in the table represents a unique entity.

**Association Control**: Helps manage relationships across tables and ensures referential integrity in foreign keys.

**Performance Advantages**

**Efficient Indexing**: Primary keys are often auto-indexed, making data retrieval faster.

**Optimized Joins**: When the primary key links to a foreign key, query performance improves for related tables.

**Industry Best Practice**

**Pick a Natural Key**: Whenever possible, choose existing data values that are unique and stable.

**Keep It Simple**: Single-column primary keys are easier to manage.

**Avoid Data in Column Attributes**: Using data can lead to bloat, adds complexity, and can be restrictive.

**Avoid Data Sensitivity**: Decrease potential risks associated with sensitive data by separating it from keys.

**Evaluate Multi-Column Keys Carefully**: Identify and justify the need for such complexity.

**Code Example: Declaring a Primary Key**
Here is the SQL code:


```jsx harmony 
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    grade_level INT,
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);

```
</details>


<details>
<summary>
42.<b> Explain what a foreign key is and how it is used.</b>
</summary>

A `foreign key` (FK) is a column or a set of columns in a table that uniquely identifies a row or a set of rows in another table. It establishes a relationship between two tables, often referred to as the parent table and the child table.

**Key Functions of a Foreign Key**

**Data Integrity**: Assures that each entry in the referencing table has a corresponding record in the referenced table, ensuring the data's accuracy and reliability.

**Relationship Mapping**: Defines logical connections between tables that can be used to retrieve related data.

**Action Propagation**: Specify what action should be taken in the child table when a matching record in the parent table is created, updated, or deleted.

**Cascade Control**: Allows operations like deletion or updates to propagate to related tables, maintaining data consistency.

**Foreign Key Constraints**

The database ensures the following with foreign key constraints:

**Uniqueness**: The referencing column or combination of columns in the child table is unique.

**Consistency**: Each foreign key in the child table either matches a corresponding primary key or unique key in the parent table or contains a null value.

**Use Cases and Best Practices**

**Data Integrity and Consistency**: FKs ensure that references between tables are valid and up-to-date. For instance, a sales entry references a valid product ID and a customer ID.

**Relationship Representation**: FKs depict relationships between tables, such as 'One-to-Many' (e.g., one department in a company can have multiple employees) or 'Many-to-Many' (like in associative entities).

**Querying Simplification**: They aid in performing joined operations to retrieve related data, abstracting away complex data relationships.

**Code Example: Creating a Foreign Key Relationship**
Here is the SQL code:

```jsx harmony 
-- Create the parent (referenced) table first
CREATE TABLE departments (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

-- Add a foreign key reference to the child table
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(id)
);

```
</details>


<details>
<summary>
43.<b> How can you prevent SQL injections?</b>
</summary>

`SQL injection` occurs when untrusted data is mixed with SQL commands. To prevent these attacks, use `parameterized queries` and input validation.

Here are specific methods to guard against SQL injection:

**Parameterized Queries**

**Description**: Also known as a prepared statement, it separates SQL code from user input, rendering direct command injection impossible.

**Code Example:**

Java (JDBC):

```jsx harmony 
String query = "SELECT * FROM users WHERE username = ? AND password = ?";
PreparedStatement ps = con.prepareStatement(query);
ps.setString(1, username);
ps.setString(2, password);
ResultSet rs = ps.executeQuery();

```

Python (MySQL):

```jsx harmony 

cursor.execute("SELECT * FROM users WHERE username = %s AND password = %s", (username, password))
```

**Benefits**:

- Improved security.
- Reliability across different databases.
- No need for manual escaping.

**Stored Procedures**
**Description**: Allows the database to pre-compile and store your SQL code, providing a layer of abstraction between user input and database operations.

**Code Example**:

With MySQL:
- Procedure definition:

```jsx harmony 

CREATE PROCEDURE login(IN p_username VARCHAR(50), IN p_password VARCHAR(50))
BEGIN
  SELECT * FROM users WHERE username = p_username AND password = p_password;
END
```

- Calling the procedure:

```jsx harmony 
cursor.callproc('login', (username, password))
```

**Advantages**:

- Reduction of code redundancy.
- Allows for granular permissions.
- Can improve performance through query plan caching.

**Input Validation**

**Description**: Examine user-supplied data to ensure it meets specific criteria before allowing it in a query.

**Code Example**: Using regex:

```jsx harmony 

if not re.match("^[A-Za-z0-9_-]*$", username):
    print("Invalid username format")
```

**Drawbacks**:

- Not a standalone method for preventing SQL injection.
- Might introduce false positives, limiting the user's input freedom.

**Code Filtering**

**Description**: Sanitize incoming data based on its type, like strings or numbers. This approach works best in conjunction with other methods.

**Code Example**: In Python:

```jsx harmony 
username = re.sub("[^a-zA-Z0-9_-]", "", username)
```

**Considerations**:

- Still necessitates additional measures for robust security.
- Can restrict legitimate user input.

</details>


<details>
<summary>
44.<b> Describe the concept of denormalization and when you would use it.</b>
</summary>

**Denormalization** involves optimizing database performance by reducing redundancy at the cost of some data integrity.

**Common Techniques for Denormalization**

1. **Flattening Relationships**:

- Combining related tables to minimize joins.
- `Example`: Order and Product tables are merged, eliminating the many-to-many relationship.

2. **Aggregating Data**:

- Precomputing derived values to minimize costly calculations.
- `Example`: a Sales_Total column in an Order table.

3. **Adding Additional Redundant Data**:

- Replicating data from one table in another to reduce the need for joins.
- `Example`: The Customer and Sales tables can both have a Country column, even though the country is indirectly linked through the Customer table.


**Common Use Cases**

- **Reporting and Analytics**:
- Companies often need to run complex reports that span numerous tables.
- Denormalization can flatten these tables, making the reporting process more efficient.

- **High-Volume Transaction Systems**:
- In systems where data consistency can be relaxed momentarily, denormalization can speed up operations.
- It's commonly seen in e-commerce sites where a brief delay in updating the sales figures might be acceptable for faster checkouts and improved user experience.

- **Read-Mostly Applications**:
- Systems that are heavy on data reads and relatively light on writes can benefit from denormalization.

**Search- and Query-Intensive Applications**:
- For example, search engines often store data in a denormalized format to enhance retrieval speed.

**Partitioning Data**:
- In distributed systems like Hadoop or NoSQL databases, data is often stored redundantly across multiple nodes for enhanced performance.

**Considerations and Trade-offs**

**Performance vs. Consistency**:
- Denormalization can boost performance but at the expense of data consistency.

**Maintenance Challenges**:
- Redundant data must be managed consistently, which can pose challenges.

**Operational Simplicity**:
- Sometimes, having a simple, denormalized structure can outweigh the benefits of granularity and normalization.

**Query Flexibility**:
- A normalized structure can be more flexible for ad-hoc queries and schema changes. Denormalized structures might require more effort to adapt to such changes.
</details>


<details>
<summary>
45.<b> What are indexes and how can they improve query performance?</b>
</summary>

**Indexes** are essential in SQL to accelerate queries by providing quick data lookups.

**How Do Indexes Improve Performance?**

**Faster Data Retrieval**: Think of an index like a book's table of contents, which leads you right to the desired section.

**Sorted Data Access**: With data logically ordered, lookups are more efficient.

**Reduces Disk I/O**: Queries may read fewer data pages when using an index.

**Enhances Joins**: Indexes help optimize join conditions, particularly in larger tables.

**Aggregates and Uniques**: They can swiftly resolve aggregate functions and enforce data uniqueness.

**Index Types**

**B-Tree**: Standard for most databases, arranges data in a balanced tree structure.
**Hash**: Direct lookup based on a hash of the indexed column.
**Bitmap**: Best used for columns with a low cardinality.
**R-Tree**: Optimized for spatial data, such as maps.
Different databases may offer additional specialized index types.

**When to Use Carefully**
Excessive or unnecessary indexing can:

**Consume Resources**: Indexes require disk space and upkeep during data modifications.
**Slow Down Writes**: Each write operation might trigger updates to associated indexes.

**Best Practices**
**Appropriate Index Count**: Identify crucial columns and refrain from over-indexing.
**Monitor and Refactor**: Regularly assess index performance and refine or remove redundant ones.
**Consistency**: Ensure all queries access data in a consistent manner to take full advantage of indexes.
**Data Type Consideration**: Certain data types are better suited for indexing than others.

**Types of Keys**
**Primary Key**: Uniquely identifies each record in a table.
**Foreign Key**: Establishes a link between tables, enforcing referential integrity.
**Compound Key**: Combines two or more columns to form a unique identifier.
</details>


<details>
<summary>
46.<b> Explain the purpose of the GROUP BY clause.</b>
</summary>

The **GROUP BY** clause in SQL serves to consolidate data and perform operations across groups of records.

**Key Functions**
**Data Aggregation**: Collapses rows into summary data.
**Filtering**: Provides filtering criteria for groups.
**Calculated Fields**: Allows computation on group-level data.

**Usage Examples**
Consider a `Sales` table with the following columns: `Product`, `Region`, and `Amount`.

**Data Aggregation**
For data aggregation, we use aggregate functions such as `SUM`, `AVG`, `COUNT`, `MIN`, or `MAX`.

The query below calculates total sales by region:

```jsx harmony 
SELECT Region, SUM(Amount) AS TotalSales
FROM Sales
GROUP BY Region;

```

**Filtering**
The **GROUP BY** clause can include conditional statements. For example, to count only those sales that exceed $100 in amount:

```jsx harmony 
SELECT Region, COUNT(Amount) AS SalesAbove100
FROM Sales
WHERE Amount > 100
GROUP BY Region;

```

**Calculated Fields**
You can compute derived values for groups. For instance, to find what proportion each product contributes to the overall sales in a region, use this query:

```jsx harmony 
SELECT Region, Product, SUM(Amount) / (SELECT SUM(Amount) FROM Sales WHERE Region = s.Region) AS RelativeContribution
FROM Sales s
GROUP BY Region, Product;

```

**Performance Considerations**
Efficient database design aims to balance query performance with storage requirements. Aggregating data during retrieval can optimize performance, especially when dealing with huge datasets.

It's essential to verify these calculations for accuracy, as improper data handling can lead to skewed results.
</details>


<details>
<summary>
47.<b> What is a subquery, and when would you use one?</b>
</summary>

`Subqueries` are embedded SQL select statements that provide inputs for an outer query. They can perform various tasks, such as filtering and aggregate computations. Subqueries can also be useful for complex join conditions, self-joins, and more.

**Common Subquery Types**

**Scalar Subquery**

A `Scalar Subquery` returns a single value. They're frequently used for comparisons—like >, =, or IN.

Examples:

- Getting the `maximum` value:
`SELECT col1 FROM table1 WHERE col1 = (SELECT MAX(col1) FROM table1);`

- Checking existence:
`SELECT col1, col2 FROM table1 WHERE col1 = (SELECT col1 FROM table2 WHERE condition);`

- Using aggregates:
`SELECT col1 FROM table1 WHERE col1 = (SELECT SUM(col2) FROM table2);`

**Table Subquery**
A `Table Subquery` is like a temporary table. It returns rows and columns and can be treated as a regular table for further processing.

Examples:

- Filtering data:
`SELECT * FROM table1 WHERE col1 IN (SELECT col1 FROM table2 WHERE condition);`

- Data deduplication:
`SELECT DISTINCT col1 FROM table1 WHERE condition1 AND col1 IN (SELECT col1 FROM table2 WHERE condition2);`

**Advantages of Using Subqueries**

**Simplicity**: They offer cleaner syntax, especially for complex queries.

**Structured Data**: Subqueries can ensure that intermediate data is properly processed, making them ideal for multi-step tasks.

**Reduced Code Duplication**: By encapsulating certain logic within a subquery, you can avoid repetitive code.

**Dynamic Filtering**: The data returned by a subquery can dynamically influence the scope of the outer query.

**Milestone Calculations**: For long and complex queries, subqueries can provide clarity and help break down the logic into manageable parts.

**Limitations and Optimization**

**Performance**: Subqueries can sometimes be less efficient. Advanced databases like Oracle, SQL Server, and PostgreSQL offer optimizations, but it's essential to monitor query performance.

**Versatility**: While subqueries are powerful, they can be less flexible in some scenarios compared to other advanced features like Common Table Expressions (CTEs) and Window Functions.

**Understanding and Debugging**: Nested logic might make a stored procedure or more advanced techniques like CTEs easier to follow and troubleshoot.

**Code Example: Using Subqueries**
Here is the SQL code:

```jsx harmony 
-- Assuming you have table1 and table2

-- Scalar Subquery Example
SELECT col1 
FROM table1 
WHERE col1 = (SELECT MAX(col1) FROM table1);

-- Table Subquery Example
SELECT col1, col2 
FROM table1 
WHERE col1 = (SELECT col1 FROM table2 WHERE condition);
```


</details>


<details>
<summary>
48.<b> Describe the functions of the ORDER BY clause</b>
</summary>

The **ORDER BY** clause in SQL serves to sort the result set based on specified columns, in either ascending (`ASC, default`) or descending (`DESC`) order. It's often used in conjunction with various SQL statements like `SELECT` or `UNION` to enhance result presentation.

**Key Features**

**Column-Specific Sorting**: You can designate one or more columns as the basis for sorting. For multiple columns, the order of precedence is from left to right.
**ASC and DESC Directives**: These allow for both ascending and descending sorting. If neither is specified, it defaults to ascending.
**Use Cases**
**Top-N Queries**: Selecting a specific number of top or bottom records can be accomplished using ORDER BY along with LIMIT or OFFSET.

T**rends Identification**: With ORDER BY, you can identify trends or patterns in your data, such as ranking by sales volume or time-based sequences.

**Improved Data Presentation**: By sorting records in a logical order, you can enhance the visual appeal and comprehension of your data representations.

**Code Example: Order by Multiple Columns and Limit Results**
Let's say you have a "sales" table with columns product_name, sale_date, and units_sold. You want to fetch the top 3 products that sold the most units on a specific date, sorted by units sold (in descending order) and product name (in ascending order).

Here is the SQL query:

```jsx harmony 

SELECT product_name, sale_date, units_sold
FROM sales
WHERE sale_date = '2022-01-15'
ORDER BY units_sold DESC, product_name ASC
LIMIT 3;
```

The expected result will show the top 3 products with the highest units sold on the given date. If two products have the same number of units sold, they will be sorted in alphabetical order by their names.

**SQL Server Specific: Order by Column Position**
In `SQL Server`, you can also use the column position in the ORDER BY clause. For example, instead of using column names, you can use 1 for the first column, 2 for the second, and so on. This syntax:

```jsx harmony 

SELECT product_name, sale_date, units_sold
FROM sales
WHERE sale_date = '2022-01-15'
ORDER BY 3 DESC, 1 ASC
LIMIT 3;
```
performs the same operation as the previous example.

**MySQL Specific: Random Order**
In `MySQL`, you can reorder the results in a random sequence. This can be useful, for instance, in a quiz app to randomize the order of questions. The `ORDER BY` clause with the `RAND()` function looks like this:

```jsx harmony 

SELECT product_name
FROM products
ORDER BY RAND()
LIMIT 1;
```

</details>


<details>
<summary>
49.<b> What is DBMS?</b>
</summary>

A `Database Management System` (DBMS) is a program that controls creation, maintenance and use of a database. DBMS can be termed as File Manager that manages data in a database rather than saving it in file systems.
</details>


<details>
<summary>
50.<b>  What is SQL?</b>
</summary>

`Structured Query Language`, also known as `SQL`, is a programming language designed for managing Relational Database Management Systems (RDBMSs). SQL is an International Organization for Standardization (ISO) standard. In RDBMS all the data is stored in tables with each table consisting of rows and columns.

Example of Sql Server 2014 SQL format:

Example of Oracle SQL format below:

Create database:

Output: Here we can see our database is created.
</details>


<details>
<summary>
51.<b> What is PL/SQL?</b>
</summary>

`PL/SQL Control` Statements in Oracle.

**Control Statements**,

• Control statements are very important in PL/SQL.

• Control Statements are elements in a program that control the flow of program execution.

• The syntax of control statements are similar to regular English and are very similar to choices that we make every day.

• Branching statements are as follows:

o If statement

o If - THEN - ELSE o Nested IF

o Branching with logical connectivity

o While

o For Loop
</details>


<details>
<summary>
52.<b> What is RDBMS?</b>
</summary>

**RDBMS**: It is referred as `Relation Database Management Systems` (RDBMS). RDBMS possesses a set of the below given characteristics:

• `Write-intensive operations`: The RDBMS is frequently written to and is often used in transaction-oriented applications.

• `Data in flux or historical data`: The RDBMS is designed to handle frequently changing data. Alternatively, RDBMS can also store vast amounts of historical data, which can later be analyzed or "mined".

• `Application-specific schema`: The RDBMS is configured on a per-application basis and a unique schema exists to support each application.

• Complex data models. The relational nature of the RDBMS makes it suitable for handling sophisticated, complex data models that require many tables, foreign key values, complex join operations, and so on.

• `Data integrity`: The RDBMS features many components designed to ensure data integrity. This includes rollback operations, referential integrity, and transaction-oriented operations.
</details>


<details>
<summary>
53.<b> What is a database table?</b>
</summary>

**Database table**: Table contains records in the form of rows and columns. A permanent table is created in the database you specify and remains in the database permanently, until you delete it.

`Syntax`:

Create table TableName (ID INT, NAME VARCHAR(30) )

Drop syntax: drop table TableName

Select Syntax: Select * from TableName
</details>



<details>
<summary>
54.<b> What is a query</b>
</summary>

A `DB query` is a code written in order to get the information back from the database. Query can be designed in such a way that it matched with our expectation of the result set. Simply, a question to the Database.

</details>



<details>
<summary>
55.<b> What is subquery?</b>
</summary>

A `subquery` is a query within another query. The outer query is called as main query, and inner query is called subquery. SubQuery is always executed first, and the result of subquery is passed on to the main query.


</details>

<details>
<summary>
56.<b> What are the types of subquery?</b>
</summary>

There are two types of `subquery` – `Correlated` and `Non-Correlated`.

A `correlated` subquery cannot be considered as independent query, but it can refer the column in a table listed in the FROM the list of the main query.

A `Non-Correlated` sub query can be considered as independent query and the output of subquery are substituted in the main query.
</details>


<details>
<summary>
57.<b> How to create a table in SQL?</b>
</summary>

`SQL` provides an organized way for table creation.

`Syntax`: Create table TableName (columnName1 datatype, columnName2 datatype )

The following is an example of creating a simple table-

create table Info (Name varchar(20), BirthDate date,Phone nvarchar(12), City varchar(20))
</details>


<details>
<summary>
58.<b> What are tables and Fields?</b>
</summary>

A table is a set of data that are organized in a model with Columns and Rows. Columns can be categorized as vertical, and Rows are horizontal. A table has specified number of column called fields but can have any number of rows which is called record.
</details>


<details>
<summary>
59.<b> How to delete a table in SQL Server?</b>
</summary>

Delete Data Record from Database Table and deleting an existing table by the following method:

`Syntax`: To delete all table records of a table:

Delete TableName DELETE info
</details>


<details>
<summary>
60.<b> How to update a database table using SQL?</b>
</summary>

To update an existing Table we use SQL Command UPDATE: It will update the records as per user defined query/need.

`Syntax`:

Update TableName SET ColumnName = NewData where Condition

Update info Set City = 'Baroda' where id = 2


</details>


<details>
<summary>
61.<b> What is a database relationship?</b>
</summary>

`Relationships` are created by linking the column in one table with the column in another table. There are four different types of relationship that can be created.

The relationships are listed below:

- One to One Relationship

- Many to One relationship

- Many to Many relationship

- One to One relationship

- One to Many & Many to One Relationship:

For a `One to many relationships`, a single column value in one table has one or more dependent column values in another table. Look at the following diagram:

`Many to Many Relationship`:

The third table acts as a bridge between the tables that want to establish a Many to Many relationship. The bridge table stores the common information between Many to Many relationship tables. Have a look at the following diagram:
</details>


<details>
<summary>
62.<b> What is a primary key of a database?</b>
</summary>

**Primary key**:-

A table column with this constraint is called the key column for the table. This constraint helps the table to make sure that the value is not repeated and also that there are no null entries.

Now this column does not allow null values and duplicate values. You can try inserting values to violate these conditions and see what happens. A table can have only one Primary key. Multiple columns can participate on the primary key.

</details>


<details>
<summary>
63.<b> What is a unique key?</b>
</summary>

A **Unique key** constraint uniquely identified each record in the database. This provides uniqueness for the column or set of columns. A Primary key constraint has automatic unique constraint defined on it. But not, in the case of Unique Key. There can be many unique constraint defined per table, but only one Primary key constraint defined per table.
</details>


<details>
<summary>
64.<b> What is a foreign key of a database?</b>
</summary>

To define the relationship between two tables (one is called parent and the other one is the child table) connected by columns, a foreign key constraint is used. In this constraint the values of the child table must appear in the parent table, which means that for a foreign key, one table should point to a Primary Key in another table. A table can have multiple foreign keys and each foreign key can have a different referenced table.

`Example`: To understand the foreign key clearly let's assume the following two tables:

`CUSTOMER {Cust_ID, Cust_Name, Age, ContactNo, Gender, Address} VENDOR {Vend_ID, Vend_Name, Cust_ID}`

`Example`: Foreign Key Constraint while using CREATE TABLE statement.

**Syntax**: `CREATE TABLE table_name(Col1 datatype NOT NULL, Col2 datatype NOT NULL, Col3 datatype NOT NULL, CONSTRAINT FK_Column FOREIGN KEY(Col1, Col2, Col3) REFERENCES parent _table(Col1, Col2, Col3) );`

AT SINGLE COLUMN LEVEL
</details>


<details>
<summary>
65.<b> What is database normalization?</b>
</summary>

`Database normalization` is the process of organizing the fields and tables of a relational database to minimize redundancy and dependency. Normalization usually involves dividing large tables into smaller (and less redundant) tables and defining relationships among them. Normalization is a bottom-up technique for database design.

The evolution of Normalization theories is illustrated below:

• First Normal Form (1NF)

• Second Normal Form (2NF)

• Third Normal Form (3NF)

• Boyce-Codd Normal Form (BCNF)

• 4th Normal Form

• 5th Normal Form

• 6th Normal Form
</details>


<details>
<summary>
66.<b> What are database normalization forms?</b>
</summary>

**Normalization** is the process of organizing data into a related table. it also eliminates redundancy and increases the integrity which improves performance of the query. To normalize a database, we divide the database into tables and establish relationships between the tables.

• First Normal Form (1st NF)

• Second Normal Form (2nd NF)

• Third Normal Form (3rd NF)

• Boyce-Codd Normal Form (BCNF)

• Fourth Normal Form (4th NF)

• Fifth Normal Form (5th NF)

First Normal Form (1NF):

This should remove all the duplicate columns from the table. Creation of tables for the related data and identification of unique columns.

**Second Normal Form (2NF)**:

Meeting all requirements of the first normal form. Placing the subsets of data in separate tables and Creation of relationships between the tables using primary keys. Third Normal Form (3NF):

This should meet all requirements of 2NF. Removing the columns which are not dependent on primary key constraints.

**Fourth Normal Form (3NF)**:

Meeting all the requirements of third normal form and it should not have multi- valued dependencies.
</details>


<details>
<summary>
67.<b> What is Denormalization.</b>
</summary>

**DeNormalization** is a technique used to access the data from higher to lower normal forms of database. It is also process of introducing redundancy into a table by incorporating data from the related tables.
</details>


<details>
<summary>
68.<b> What is a stored procedure?</b>
</summary>

A `Stored Procedure` is a collection or a group of T-SQL statements. Stored Procedures are a precompiled set of one or more statements that are stored together in the database. They reduce the network load because of the precompilation. We can create a Stored Procedure using the "Create proc" statement.
</details>


<details>
<summary>
69.<b> Why we use Stored Procedure</b>
</summary>

There are several reasons to use a `Stored Procedure`. They are a network load reducer and decrease execution time because they are precompiled. The most important use of a Stored Procedure is for security purposes. They can restrict SQL Injection. We can avoid SQL injection by use of a Stored Procedure.

</details>


<details>
<summary>
70.<b> How to create a Stored Procedure</b>
</summary>

`CREATE PROCEDURE spEmployee AS`

**BEGIN**

SELECT `EmployeeId`, `Name`, `Gender`, `DepartmentName` FROM `tblEmployees` `INNER JOIN` `tblDepartments` ON `tblEmployees`.EmployeeDepartmentId = tblDepartments.DepartmentId

**END**

**Advantages of using a Stored Procedure in SQL Server**

• It is very easy to maintain a Stored Procedure and they are re-usable.

• The Stored Procedure retains the state of the execution plans.

• Stored Procedures can be encrypted and that also prevents SQL Injection Attacks
</details>


<details>
<summary>
71.<b> What is a function in SQL Server?</b>
</summary>

A function is a sequence of statements that accepts input, processes them to perform a specific task and provides the output. Functions must have a name but the function name can never start with a special character such as @, $, #, and so on.

**Types of function**

• Pre-Defined Function

• User-Defined Function

User-defined Function:

In a user-defined function we write our logic according to our needs. The main advantage of a user-defined function is that we are not just limited to pre-defined functions. We can write our own functions for our specific needs or to simplify complex SQL code. The return type of a SQL function is either a scalar value or a table.

**Creation of a function**

Create function ss(@id int)

returns table as return select * from item where itemId = @id

Execution of a Function

select * from ss(1)

Output:
</details>



<details>
<summary>
72.<b> What are the different types of functions in SQL Server?</b>
</summary>

A `function` must return a result. So that is also called a function that returns a result or a value. When we create it a function must specify a value type that will return a value.

• Functions only work with select statements.

• Functions can be used anywhere in SQL, such as AVG, COUNT, SUM, MIN, DATE and so on with select statements.

• Functions compile every time.

• Functions must return a value or result.

• Functions only work with input parameters.

• Try and catch statements are not used in functions.

**Function Types**:

The following is the function list in SQL Server databases.

SQL Server contains the following aggregates functions:
</details>


<details>
<summary>
73.<b> What is a trigger in SQL Server?</b>
</summary>

"A `Trigger` is a Database object just like a stored procedure or we can say it is a special kind of Stored Procedure which fires when an event occurs in a database.".

It is a database object that is bound to a table and is executed automatically. We cannot explicitly call any trigger. Triggers provide data integrity and used to access and check data before and after modification using DDL or DML query.

**There are two types of Triggers**:

DDL Trigger

DML trigger

**DDL Triggers**: They fire in response to DDL (Data Definition Language) command events that start with Create, Alter and Drop like Create_table, Create_view, drop_table, Drop_view and Alter_table.

`Code of DDL Triggers:`

create trigger saftey on database for

create_table, alter_table, drop_table as print 'you can not create ,drop and alter table in this database' rollback;

**Output**:

**DML Triggers**: They fire in response to DML (Data Manipulation Language) command events that start with Insert, Update and Delete like insert_table, Update_view and Delete_table.

`Code of DML Trigger`:

create trigger deep on emp for insert, update, delete as print 'you can notinsert,update and delete this table I' rollback;

**Output**:

When we insert, update or delete in a table in a database then the following message appears:
</details>


<details>
<summary>
74.<b> Why do we need triggers?</b>
</summary>

**Why and when to use a trigger**:
We use a trigger when we want some event to happen automatically on certain desirable scenarios. You have a table that changes frequently, now you want to know how many times and when these changes take place. In that case you can create a trigger that will insert the desired data into another table whenever any change in the main table occurs.

In SQL Server we can create the following 3 types of triggers:

• Data Definition Language (DDL) triggers

• Data Manipulation Language (DML) triggers

• Logon triggers

**Example**:

`CREATE TRIGGER trgAfterInsert ON[dbo].[Employee_Test]`

FOR INSERT

AS

declare@ empid int; declare@ empname varchar(100);

declare@ empsal decimal(10, 2);

declare@ audit_action varchar(100);

select@ empid = i.Emp_ID from inserted i;

select@ empname = i.Emp_Name from inserted i;

select@ empsal = i.Emp_Sal from inserted i;

set@ audit_action = 'Inserted Record -- After Insert Trigger.';

insert into Employee_Test_Audit (Emp_ID, Emp_Name, Emp_Sal, Audit_Action, Audit_Timestamp) values(@empid, @empname, @empsal, @audit_action, getdate());

PRINT 'AFTER INSERT trigger fired.'

GO
</details>


<details>
<summary>
75.<b> What are the different types of triggers?</b>
</summary>

Triggers are a special type of stored procedure which is executed automatically based on the occurrence of a database event. These events can be categorized as:

• Data Manipulation Language (DML) and

• Data Definition Language (DDL) events.

The benefit derived from triggers is based in their events driven nature. Once created, the trigger automatically fires without user intervention based on an event in the database.

A. Using DML Triggers: DML triggers are invoked when any DML command such as INSERT, DELETE, and UPDATE occurs on the data of a table and/or view.

• DML triggers are powerful objects for maintaining database integrity and consistency.

• DML triggers evaluate data before it has been committed to the database. o During this evaluation the following actions are performed.

We cannot use the following commands in DML trigger:

o ALTER DATABASE

o CREATE DATABASE

o DISK DATABASE

o LOAD DATABASE

o RESTORE DATABASE

B. Using DDL Triggers:

• These triggers focus on changes to the definition of database objects as opposed to changes to the actual data.

• This type of trigger is useful for controlling development and production database environments.

Let us create DDL trigger now-

The following is the syntax.

CREATE TRIGGER trigger_name ON{ALL SERVER | DATABASE }

[WITH < ddl_trigger_option > [, ...n]]{ FOR | AFTER } {

event_type | event_group }[, ...n] AS

{sql_statement[;][...n] | EXTERNAL NAME < method specifier > [;] }

CREATE TRIGGER tr_TableAudit ON DATABASE FOR CREATE_TABLE, ALTER_TABLE, DROP_TABLE AS PRINT 'You must disable the TableAudit trigger in order to change any table in this database ' ROLLBACK GO
</details>


<details>
<summary>
76.<b> What is a view in the database?</b>
</summary>

A View is nothing but a select query with a name given to it or we can simply say a view is a Named Query. Ok! Why do we need a view? There can be many answers for this. Some of the important stuff I feel is:

• A view can combine data from multiple tables using adequate joins and while bringing it may require complex filters and calculated data to form the required result set. From a user's point of view, all these complexities are hidden data queried from a single table.

• Sometimes for security purposes, access to the table, table structures and table relationships are not given to the database user. All they have is access to a view not knowing what tables actually exist in the database.

• Using the view, you can restrict the user update only portions of the records.

The following are the key points to be noted about views:

1. Multiple views can be created on one table.

2. Views can be defined as read-only or updatable.

3. Views can be indexed for better performance.

4. Insert, update, delete can be done on an updatable view.
</details>


<details>
<summary>
77.<b> Why do I need views in a database?</b>
</summary>

There are a number of scenarios where we have to look for a view as a solution.

• To hide the complexity of the underlying database schema, or customize the data and schema for a set of users.

• To control access to rows and columns of data.

• To aggregate data for performance.

Views are used for security purposes because they provide encapsulation of the name of the table. Data is in the virtual table, not stored permanently. Views display only selected data.

Syntax of a View:

CREATE VIEW view_name AS

SELECT column_name(s) FROM table_name WHERE condition

There are two types of views.

• Simple View

• Complex View
</details>


<details>
<summary>
78.<b> What is the difference between Primary key and unique key?</b>
</summary>

Primary key does not allow the null values but unique key allows one null value.

Primary key will create clustered index on column but unique key will create non-clustered index by default.
</details>


<details>
<summary>
79.<b> How can you increase SQL performance?</b>
</summary>

**Following are tips which will increase your SQl performance**:-

- Every index increases the time takes to perform INSERTS, UPDATES, and DELETES, so the number of indexes should not be too much. Try to use maximum 4-5 indexes on one table, not more. If you have read-only table, then the number of indexes may be increased.
- Keep your indexes as narrow as possible. This reduces the size of the index and reduces the number of reads required to read the index.
- Try to create indexes on columns that have integer values rather than character values.
- If you create a composite (multi-column) index, the orders of the columns in the key are very important. Try to order the columns in the key as to enhance selectivity, with the most selective columns to the leftmost of the key.
- If you want to join several tables, try to create surrogate integer keys for this purpose and create indexes on their columns. Create surrogate integer primary key (identity for example) if your table will not have many insert operations.
- Clustered indexes are more preferable than nonclustered, if you need to select by a range of values or you need to sort results set with GROUP BY or ORDER BY. If your application will be performing the same query over and over on the same table, consider creating a covering index on the table.
- You can use the SQL Server Profiler Create Trace Wizard with "Identify Scans of Large Tables" trace to determine which tables in your database may need indexes. This trace will show which tables are being scanned by queries instead of using an index.
</details>


<details>
<summary>
80.<b> What is the use of OLAP?</b>
</summary>

OLAP is useful because it provides fast and interactive access to aggregated data and the ability to drill down to detail.
</details>


<details>
<summary>
81.<b> What is a measure in OLAP?</b>
</summary>

Measures are the key performance indicator that you want to evaluate. To determine which of the numbers in the data might be measures. A rule of thumb is if a number makes sense when it is aggregated, then it is a measure.
</details>


<details>
<summary>
82.<b> What are dimensions in OLAP?</b>
</summary>

Dimensions are the categories of data analysis. For example, in a revenue report by month by sales region, the two dimensions needed are time and sales region. Typical dimensions include product, time, and region.

</details>


<details>
<summary>
83.<b> What are levels in dimensions?</b>
</summary>

Dimensions are arranged in hierarchical levels, with unique positions within each level. For example, a time dimension may have four levels, such as Year, Quarter, Month, and Day. Or the dimension might have only three levels, for example, Year, Week, and Day. The values within the levels are called members. For example, the years 2002 and 2003 are members of the level Year in the Time dimension.
</details>


<details>
<summary>
84.<b> What are fact tables and dimension tables in OLAP?</b>
</summary>

Twist: - Can you explain the star schema for OLAP?

The dimensions and measures are physically represented by a star schema. Dimension tables revolve around fact table. A fact table contains a column for each measure as well as a column for each dimension. Each dimension column has a foreign -key relationship to the related dimension table, and the dimension columns taken together are the key to the fact table.

</details>



<details>
<summary>
85.<b> What is DTS?</b>
</summary>

DTS is used to import data and while importing it helps us to transform and modify data. The name itself is self explanatory DTS ( Data transformation Services).

</details>



<details>
<summary>
86.<b> What is fill factor ? or When does page split occurs?</b>
</summary>

The 'fill factor' option specifies how full SQL Server will make each index page. When there is no free space to insert new row on the index page, SQL Server will create new index page and transfer some rows from the previous page to the new one. This operation is called page splits. You can reduce the number of page splits by setting the appropriate fill factor option to reserve free space on each index page. The fill factor is a value from 1 through 100 that specifies the percentage of the index page to be left empty. The default value for fill factor is 0. It is treated similarly to a fill factor value of 100, the difference in that SQL Server leaves some space within the upper level of the index tree for FILLFACTOR = 0. The fill factor percentage is used only at the time when the index is created. If the table contains read-only data (or data that very rarely changed), you can set the 'fill factor' option to 100. When the table's data is modified very often, you can decrease the fill factor to 70% or whatever you think is best.
</details>


<details>
<summary>
87.<b> What is RAID and how does it work?</b>
</summary>

Redundant Array of Independent Disks (RAID) is a term used to describe the technique of improving data availability through the use of arrays of disks and various data-striping methodologies. Disk arrays are groups of disk drives that work together to achieve higher data-transfer and I/O rates than those provided by single large drives. An array is a set of multiple disk drives plus a specialized controller (an array controller) that keeps track of how data is distributed across the drives. Data for a particular file is written in segments to the different drives in the array rather than being written to a single drive.

For speed and reliability, it is better to have more disks. When these disks are arranged in certain patterns and are use a specific controller, they are called a Redundant Array of Inexpensive Disks (RAID) set. There are several numbers associated with RAID, but the most common are 1, 5 and 10.

RAID 1 works by duplicating the same writes on two hard drives. Let us assume you have two 20-Gigabyte drives. In RAID 1, data is written at the same time to both the drives. RAID1 is optimized for fast writes.

RAID 5 works by writing parts of data across all drives in the set (it requires at least three drives). If a drive failed, the entire set would be worthless. To combat this problem, one of the drives stores a "parity" bit. Think of a math problem, such as 3 + 7 = 10. You can think of the drives as storing one of the numbers, and the 10 is the parity part. By removing any one of the numbers, you can get it back by referring to the other two, like this: 3 + X = 10. Of course, losing more than one could be evil. RAID 5 is optimized for reads.

RAID 10 is a bit of a combination of both types. It does not store a parity bit, so it is faster, but it duplicates the data on two drives to be safe. You need at least four drives for RAID 10. This type of RAID is probably the best compromise for a database server.

Note :- It's difficult to cover complete aspect of RAID in this book. It's better to take some decent SQL SERVER book for in detail knowledge, but yes from interview aspect you can probably escape with this answer.
</details>


<details>
<summary>
88.<b> What is the difference between DELETE TABLE and TRUNCATE TABLE commands?</b>
</summary>

DELETE TABLE syntax logs the deletes thus make the delete operation slow. TRUNCATE table does not log any information but it logs information about deallocation of data page of the table so TRUNCATE table is faster as compared to delete table.

DELETE table can have criteria while TRUNCATE cannot.

TRUNCATE table does not invoke trigger.

I had mentioned that TRUNCATE table can not be rolled back while delete can be.

</details>


<details>
<summary>
89.<b> If locking is not implemented, what issues can occur?</b>
</summary>

Following are the problems that occur if you do not implement locking properly in `SQLSERVER`.

**Lost Updates**

Lost updates occur if you let two transactions modify the same data at the same time, and the transaction that completes first is lost. You need to watch out for lost updates with the READ UNCOMMITTED isolation level. This isolation level disregards any type of locks, so two simultaneous data modifications are not aware of each other. Suppose that a customer has due of 2000$ to be paid. He pays 1000$ and again buys a product of 500$ . Lets say that these two transactions are now been entered from two different counters of the company.

Now both the counter user starts making entry at the same time 10:00 AM. Actually speaking at 10:01 AM the customer should have 2000$-1000$+500 = 1500$ pending to be paid. But as said in lost updates the first transaction is not considered and the second transaction overrides it. So the final pending is 2000$+500$ = 2500$.....I hope the company does not loose the customer.

**Non-Repeatable Read**

Non-repeatable reads occur if a transaction is able to read the same row multiple times and gets a different value each time. Again, this problem is most likely to occur with the READ UNCOMMITTED isolation level. Because you let two transactions modify data at the same time, you can get some unexpected results. For instance, a customer wants to book flight, so the travel agent checks for the flights availability. Travel agent finds a seat and goes ahead to book the seat. While the travel agent is booking the seat, some other travel agent books the seat. When this travel agent goes to update the record, he gets error saying that “Seat is already booked”. In short, the travel agent gets different status at different times for the seat.

**Dirty Reads**

Dirty reads are a special case of non-repeatable read. This happens if you run a report while transactions are modifying the data that you are reporting on. For example, there is a customer invoice report, which runs on 1:00 AM in afternoon and after that all invoices are sent to the respective customer for payments. Let us say one of the customer has 1000$ to be paid. Customer pays 1000$ at 1:00 AM and at the same time report is run. Actually, customer has no money pending but is still issued an invoice.

**Phantom Reads**

Phantom reads occur due to a transaction being able to read a row on the first read, but not being able to modify the same row due to another transaction deleting rows from the same table. Lets say you edit a record in the mean time somebody comes and deletes the record, you then go for updating the record which does not exist...Panicked.

Interestingly, the phantom reads can occur even with the default isolation level supported by SQL Server: READ COMMITTED. The only isolation level that does not allow phantoms is SERIALIZABLE, which ensures that each transaction is completely isolated from others. In other words, no one can acquire any type of locks on the affected row while it is being modified.
</details>

<details>
<summary>
90.<b> What are different transaction levels in SQL SERVER?</b>
</summary>

**Twist**: - `What are different types of locks in SQL SERVER?`

Transaction Isolation level decides how is one process isolated from other process. Using transaction levels, you can implement locking in SQL SERVER.

There are four transaction levels in SQL SERVER:-

**READ COMMITTED**

The shared lock is held for the duration of the transaction, meaning that no other transactions can change the data at the same time. Other transactions can insert and modify data in the same table, however, as long as it is not locked by the first transaction.

**READ UNCOMMITTED**

No shared locks and no exclusive locks are honored. This is the least restrictive isolation level resulting in the best concurrency but the least data integrity.

**REPEATABLE READ**

This setting disallows dirty and non-repeatable reads. However, even though the locks are held on read data, new rows can still be inserted in the table, and will subsequently be interpreted by the transaction.

**SERIALIZABLE**

This is the most restrictive setting holding shared locks on the range of data. This setting does not allow the insertion of new rows in the range that is locked; therefore, no phantoms are allowed.

Following is the syntax for setting transaction level in SQL SERVER.

SET TRANSACTION ISOLATION LEVEL SERIALIZABLE
</details>


<details>
<summary>
91.<b> What are the different locks in SQL SERVER?</b>
</summary>

Depending on the transaction level, six types of lock can be acquired on data:-

Intent

The intent lock shows the future intention of SQL Server's lock manager to acquire locks on a specific unit of data for a particular transaction. SQL Server uses intent locks to queue exclusive locks, thereby ensuring that these locks will be placed on the data elements in the order the transactions were initiated. Intent locks come in three flavors: intent shared (IS), intent exclusive (IX), and shared with intent exclusive (SIX).

IS locks indicate that the transaction will read some (but not all) resources in the table or page by placing shared locks.

IX locks indicate that the transaction will modify some (but not all) resources in the table or page by placing exclusive locks.

SIX locks indicates that the transaction will read all resources, and modify some (but not all) of them. This will be accomplished by placing the shared locks on the resources read and exclusive locks on the rows modified. Only one SIX lock is allowed per resource at one time; therefore, SIX locks prevent other connections from modifying any data in the resource (page or table), although they do allow reading the data in the same resource.

Shared

Shared locks (S) allow transactions to read data with SELECT statements. Other connections are allowed to read the data at the same time; however, no transactions are allowed to modify data until the shared locks are released.

Update

Update locks (U) are acquired just prior to modifying the data. If a transaction modifies a row, then the update lock is escalated to an exclusive lock; otherwise, it is converted to a shared lock. Only one transaction can acquire update locks to a resource at one time. Using update locks prevents multiple connections from having a shared lock that want to eventually modify a resource using an exclusive lock. Shared locks are compatible with other shared locks, but are not compatible with Update locks.

Exclusive

Exclusive locks (X) completely lock the resource from any type of access including reads. They are issued when data is being modified through INSERT, UPDATE and DELETE statements.

Schema

Schema modification locks (Sch -M) are acquired when data definition language statements, such as CREATE TABLE, CREATE INDEX, ALTER TABLE, and so on are being executed. Schema stability locks (Sch-S) are acquired when store procedures are being compiled.

Bulk Update

Bulk update locks (BU) are used when performing a bulk-copy of data into a table with TABLOCK hint. These locks improve performance while bulk copying data into a table; however, they reduce concurrency by effectively disabling any other connections to read or modify data in the table.
</details>


<details>
<summary>
92.<b> Can we suggest locking hints to SQL SERVER?</b>
</summary>

We can give locking hints that helps you over ride default decision made by SQL Server. For instance, you can specify the ROWLOCK hint with your UPDATE statement to convince SQL Server to lock each row affected by that data modification. Whether it is prudent to do so is another story; what will happen if your UPDATE affects 95% of rows in the affected table? If the table contains 1000 rows, then SQL Server will have to acquire 950 individual locks, which is likely to cost a lot more in terms of memory than acquiring a single table lock. So think twice before you bombard your code with ROWLOCKS
</details>


<details>
<summary>
93.<b> What is LOCK escalation?</b>
</summary>

Lock escalation is the process of converting of low-level locks (like rowlocks, page locks) into higher -level locks (like table locks). Every lock is a memory structure too many locks would mean, more memory being occupied by locks. To prevent this from happening, SQL Server escalates the many fine-grain locks to fewer coarse-grain locks. Lock escalation threshold was definable in SQL Server 6.5, but from SQL Server 7.0 onwards SQL Server dynamically manages it.

</details>


<details>
<summary>
94.<b> What are the different ways of moving data between databases in SQL Server?</b>
</summary>

There are lots of options available; you have to choose your option depending upon your requirements. Some of the options you have are BACKUP/RESTORE, detaching and attaching databases, replication, DTS, BCP, logshipping, INSERT...SELECT, SELECT...INTO, creating INSERT scripts to generate data.
</details>


<details>
<summary>
95.<b> What is the difference between a HAVING CLAUSE and a WHERE CLAUSE?</b>
</summary>

You can use Having Clause with the GROUP BY function in a query and WHERE Clause is applied to each row before, they are part of the GROUP BY function in a query.
</details>


<details>
<summary>
96.<b> What is the difference between UNION and UNION ALL SQL syntax?</b>
</summary>

UNION SQL syntax is used to select information from two tables. But it selects only distinct records from both the table, while UNION ALL selects all records from both the tables.

Note :- Selected records should have same datatype or else the syntax will not work.
</details>


<details>
<summary>
97.<b> What are the different types of triggers in SQl SERVER?</b>
</summary>

There are two types of triggers:-

INSTEAD OF triggers

INSTEAD OF triggers fire in place of the triggering action. For example, if an INSTEAD OF UPDATE trigger exists on the Sales table and an UPDATE statement is executed against the Salestable, the UPDATE statement will not change a row in the sales table. Instead, the UPDATE statement causes the INSTEAD OF UPDATE trigger to be executed.

AFTER triggers

AFTER triggers execute following the SQL action, such as an insert, update, or delete. This is the traditional trigger which existed in SQL SERVER.

INSTEAD OF triggers are executed automatically before the Primary Key and the Foreign Key constraints are checked, whereas the traditional AFTER triggers is executed after these constraints are checked. Unlike AFTER triggers, INSTEAD OF triggers can be created on views.
</details>


<details>
<summary>
98.<b> What is SQL injection?</b> 
</summary>

It is a Form of attack on a database-driven Web site in which the attacker executes unauthorized SQL commands by taking advantage of insecure code on a system connected to the Internet, bypassing the firewall. SQL injection attacks are used to steal information from a database from which the data would normally not be available and/or to gain access to an organization’s host computers through the computer that is hosting the database.

SQL injection attacks typically are easy to avoid by ensuring that a system has strong input validation.

As name suggest we inject SQL which can be relatively dangerous for the database. Example this is a simple SQL

SELECT email, passwd, login_id, full_name FROM members WHERE email = 'x'

Now somebody does not put “x” as the input but puts “x ; DROP TABLE members;”. So the actual SQL which will execute is:-

SELECT email, passwd, login_id, full_name FROM members WHERE email = ‘x’; DROP TABLE members;

Think what will happen to your database.
</details>

<details>
<summary>
99.<b> What is the difference between Stored Procedure (SP) and User Defined Function (UDF)?</b>
</summary>

Following are some major differences between a stored procedure and user defined functions:-

You can not change any data using UDF while you can do everything with a stored procedure.

UDF cannot be used in XML FOR clause but SP’s can be used.

UDF does not return output parameters while SP’s return output parameters.

If there is an error in UDF its stops executing. But in SP’s it just ignores the error and moves to the next statement.

UDF cannot make permanent changes to server environments while SP’s can change some of the server environment.
</details>

<details>
<summary>
100.<b> What is DBCC?</b>
</summary>

`DBCC` (Database Consistency Checker Commands) is used to check logical and physical consistency of database structure.DBCC statements can fix and detect problems. These statements are grouped in to four categories:-

Maintenance commands like `DBCC` `DBREINDEX`, `DBCC` `DBREPAR` etc, they are mainly used for maintenance tasks in SQL SERVER.

Miscellaneous commands like `DBCC` `ROWLOCK`, `DBCC` `TRACEO` etc, they are mainly used for enabling row-level locking or removing DLL from memory.

Status Commands like DBCC OPENTRAN, DBCC SHOWCONTIG etc , they are mainly used for checking status of the database.

Validation Commands like `DBCC` `CHECKALLOC`, `DBCCCHECKCATALOG` etc , they perform validation operations on database.

**Note** :- Check MSDN for list of all DBCC commands, it is very much possible specially during DBA interviews they can ask in depth individual commands.

Below is a sample screen in which DBCC SHOWCONTIG command is run. DBCC SHOWCONTIG is used to display fragmentation information for the data and indexes of the specified table.In the sample screen “Customer” table is checked for fragmentation

Fragmentation information. If “Scan density” is 100 then everything is contigious.The above image has scan density of 95.36% which is decent percentage. So such type of useful information can be collected by DBCC command and database performance and maintenance can be improved.
</details>


<details>
<summary>
101.<b> What is the purpose of Replication?</b>
</summary>

`Replication` is way of keeping data synchronized in multiple databases. SQL server replication has two important aspects publisher and subscriber.

**Publisher**

Database server that makes data available for replication is known as Publisher.

**Subscriber**

Database Servers that get data from the publishers is called as Subscribers.
</details>



<details>
<summary>
102.<b> What are the different types of replication supported by SQL SERVER?</b>
</summary>

**There are three types of replication supported by SQL SERVER**:

**Snapshot Replication**.

Snapshot Replication takes snapshot of one database and moves it to the other database. After initial load data can be refreshed periodically. The only disadvantage of this type of replication is that all data has to be copied each time the table is refreshed.

**Transactional Replication**

In transactional replication, data is copied first time as in snapshot replication, but later only the transactions are synchronized rather than replicating the whole database. You can either specify to run continuously or on periodic basis.

**Merge Replication.**

Merge replication combines data from multiple sources into a single central database. Again as usual, the initial load is like snapshot but later it allows change of data both on subscriber and publisher, later when they come on-line it detects and combines them and updates accordingly.
</details>


<details>
<summary>
103.<b> What is BCP utility in SQL SERVER?</b>
</summary>

`BCP` (Bulk Copy Program) is a command line utility by which you can import and export large amounts of data in and out of `SQL SERVER database`

</details>


<details>
<summary>
104.<b> What is a Cursor?</b>
</summary>

A database `Cursor` is a control which enables traversal over the rows or records in the table. This can be viewed as a pointer to one row in a set of rows. Cursor is very much useful for traversing such as retrieval, addition and removal of database records.

</details>


<details>
<summary>
105.<b> What are local and global variables and their differences?</b>
</summary>

`Local variables` are the variables which can be used or exist inside the function. They are not known to the other functions and those variables cannot be referred or used. Variables can be created whenever that function is called.

`Global variables` are the variables which can be used or exist throughout the program. Same variable declared in global cannot be used in functions. Global variables cannot be created whenever that function is called.

</details>


<details>
<summary>
106.<b> What is an index?</b>
</summary>

An `Index` is one of the most powerful techniques to work with this enormous information. Database tables are not enough for getting the data efficiently in case of a huge amount of data. In order to get the data quickly we need to index the column in a table.

An index is a database object that is created and maintained by the DBMS. Indexed columns are ordered or sorted so that data searching is extremely fast. An index can be applied on a column or a view. A table can have more than one index.

**Types of Index**: Microsoft SQL Server has two types of indexes. These are:

**Clustered Index**: A Clustered Index sorts and stores the data in the table based on keys. A Clustered Index can be defined only once per table in the SQL Server Database, because the data rows can be sorted in only one order. Text, nText and Image data are not allowed as a Clustered index.

SET STATISTICS IO ON

`SELECT * FROM Employee WHERE EmpID = 20001`

EmpID EmpName Cell Dept

20001 Black Smith 12345678901 1

Non-Clustered Index: Non Clustered Indexes or simply indexes are created outside of the table. SQL Server supports 999 Non-Clustered per table and each Non-Clustered can have up to 1023 columns. A Non-Clustered Index does not support the Text, nText and Image data types.

`CREATE NONCLUSTERED INDEX NCL_ID ON Employee(DeptID)`

SET STATISTICS IO ON

`SELECT * FROM Employee WHERE DeptID = 20001`

EmpID EmpName Cell Dept

40001 Black Smith 12345678901 20001
</details>


<details>
<summary>
107.<b> What is a join in SQL Server?</b>
</summary>

If you want to retrieve data from multiple tables then you need to use joins in SQL Server. Joins are used to get data from two or more tables based on the relationships among some of the columns in the tables.

Syntax: The Inner join syntax is as follows:

SELECT < column list >FROM < left joined table > [INNER] JOIN < right joined table > ON < join condition >

The example is developed in SQL Server 2012 using the SQL Server Management Studio.

Creating Table in SQL Server:

Now to create 3 tables in the Master database named Table1, Table2 and Table3.

Table1-

CREATE TABLE Table1 ( ID INT, Name VARCHAR(20) )

Table2-

CREATE TABLE Table2 ( ID INT, Name VARCHAR(30) )

Table3-

CREATE TABLE Table3 ( ID INT, Name VARCHAR(40) )
</details>


<details>
<summary>
108.<b> What are different types of joins in SQL Server?</b>
</summary>

Joins are useful for bringing data together from different tables based on their database relations. First we will see how the join operates between tables. Then we will explore the Order of Execution when both a join and a where condition exist. Finally we will move our exploration to the importance of the Join order.

A Join condition defines a way two tables are related in a query by:

• Specifying the column to be used for the Join from each table. In joining foreign keys in a table and its associated key in the other table.

• To use the logical operator in comparing values from the columns.

There are three type of joins available based on the way we join columns of two different tables.

1. Full Join

2. Inner Join

3. Left outer Join

4. Right outer Join

**Full Join** - A full join is somewhat different from the Cartesian product. A Cartesian product will get all the possible row combinations of the two joining tables. A Full Join takes the matching columns plus all table rows from the left table that does not match the right and all table rows in the right that does not match the left. It applies null for unmatched rows on the other end when doing so. The following example shows the full join between Table_A and Table_C
</details>


<details>
<summary>
109.<b> What is Self-Join?</b>
</summary>

Self-join is set to be query used to compare to itself. This is used to compare values in a column with other values in the same column in the same table. ALIAS ES can be used for the same table comparison.


</details>

<details>
<summary>
110.<b> What is user defined functions?</b>
</summary>

User defined functions are the functions written to use that logic whenever required. It is not necessary to write the same logic several times. Instead, function can be called or executed whenever needed.
</details>


<details>
<summary>
111.<b> What are all types of user defined functions?</b>
</summary>

Three types of user defined functions are.

1.  Scalar Functions.

2.  Inline Table valued functions.

3. Multi statement valued functions.

Scalar returns unit, variant defined the return clause. Other two types return table as a return.
</details>

<details>
<summary>
112.<b> What is collation?</b>
</summary>

Collation is defined as set of rules that determine how character data can be sorted and compared. This can be used to compare A and, other language characters and also depends on the width of the characters.

ASCII value can be used to compare these character data.
</details>


<details>
<summary>
113.<b> What are all different types of collation sensitivity?</b>
</summary>

Following are different types of collation sensitivity -.

1. Case Sensitivity – A and a and B and b.

2. Accent Sensitivity.

3.  Kana Sensitivity – Japanese Kana characters.

4. Width Sensitivity – Single byte character and double byte character.
</details>


<details>
<summary>
114.<b> Advantages and Disadvantages of Stored Procedure?</b>
</summary>

Stored procedure can be used as a modular programming – means create once, store and call for several times whenever required. This supports faster execution instead of executing multiple queries. This reduces network traffic and provides better security to the data. Disadvantage is that it can be executed only in the Database and utilizes more memory in the database server.

</details>

<details>
<summary>
115.<b> What is Online Transaction Processing (OLTP)?</b>
</summary>

Online Transaction Processing or OLTP manages transaction based applications which can be used for data entry and easy retrieval processing of data. This processing makes like easier on simplicity and efficiency. It is faster, more accurate results and expenses with respect to OTLP.

Example – Bank Transactions on a daily basis.

</details>


<details>
<summary>
116.<b> What is CLAUSE?</b>
</summary>

SQL clause is defined to limit the result set by providing condition to the query. This usually filters some rows from the whole set of records.

Example – Query that has WHERE condition

Query that has HAVING condition.

</details>

<details>
<summary>
117.<b> What is recursive stored procedure?</b>
</summary>

A stored procedure which calls by itself until it reaches some boundary condition. This recursive function or procedure helps programmers to use the same set of code any number of times.


</details>


<details>
<summary>
118.<b> What is Union, minus and Interact commands?</b>
</summary>

UNION operator is used to combine the results of two tables, and it eliminates duplicate rows from the tables.

MINUS operator is used to return rows from the first query but not from the second query. Matching records of first and second query and other rows from the first query will be displayed as a result set.

INTERSECT operator is used to return rows returned by both the queries.

</details>


<details>
<summary>
119.<b> What is an ALIAS command?</b>
</summary>

ALIAS name can be given to a table or column. This alias name can be referred in WHERE clause to identify the table or column.

Example-. 1 Select st.StudentID, Ex.Result from student st, Exam as Ex where st.studentID = Ex. StudentID

Here, st refers to alias name for student table and Ex refers to alias name for exam table.
</details>


<details>
<summary>
120.<b> What is the difference between TRUNCATE and DROP statements?</b>
</summary>

TRUNCATE removes all the rows from the table, and it cannot be rolled back. DROP command removes a table from the database and operation cannot be rolled back.


</details>



<details>
<summary>
121.<b> What are aggregate and scalar functions?</b>
</summary>

- Aggregate functions are used to evaluate mathematical calculation and return single values. This can be calculated from the columns in a table.
- Scalar functions return a single value based on the input value.

Example -.

**Aggregate** – max(), count – Calculated with respect to numeric.

**Scalar** – UCASE(), NOW() – Calculated with respect to strings.

</details>



<details>
<summary>
122.<b> What is an inner join in SQL?</b>
</summary>


**Inner or Self Join** - This Join returns a row when there is at least one match in both tables.

Let’s see an example:

`Select * From Table1 Inner Join Table2 on table1.ID = table2.ID`

The following query displays the Employee Name and the corresponding Manager Name within the employee table.

SELECT e1.Employee_Name EmployeeName, e2.Employee_Name ManagerName FROM employee e1(nolock), employee e2(nolock) WHERE e1.EmployeeID = e2.ManagerID

**Output**:

An inner join (sometimes called a "simple join") is a join of two or more tables that returns only those rows that satisfy the join condition.
</details>


<details>
<summary>
123.<b> What is an outer join in SQL?</b>
</summary>

`There are three different types of outer joins; let's see 1 by 1.`

• Left Outer Join

• Right Outer Join

• Full Outer Join

**Left Outer Join** - A LEFT OUTER JOIN is one of the JOIN operations that allows you to specify a join clause. It preserves the unmatched rows from the first (left) table, joining them with a NULL row in the shape of the second (right) table.

`Select * From Table1 Left Outer Join on table1.ID = table2.ID`

**Right Outer Join** - A RIGHT OUTER JOIN is one of the JOIN operations that allows you to specify a JOIN clause. It preserves the unmatched rows from the Table2 (right) table, joining them with a NULL in the shape of the Table1 (left) table. A LEFT OUTER JOIN B is equivalent to B RIGHT OUTER JOIN A, with the columns in a different order.

`Select * From Table1 Right Outer Join on table1.ID = table2.ID`
</details>


<details>
<summary>
124.<b> What is full join in SQL?</b>
</summary>

A **Full Outer Join** fetches all records of both tables; where the record does not match, it returns Null. select e.empId, e.empName, e1.empAdd from emp e full outer join `emp_add e1 on e.empI d = e1.empId`

**Output**:

Or

**Full Outer Join** - FULL OUTER JOIN: This JOIN is a combination of both. All records from both Left_Table and Right_Table are in the result set and matched when they can be on the Join_Condition; when no record is found in the opposite table, NULL values are used for the columns.

`Select * From Table1 Full Outer Join on table1.ID = table2.ID`
</details>

<details>
<summary>
125.<b> What is left join in SQL Server?</b>
</summary>

**Left Join**: A LEFT OUTER JOIN is one of the JOIN operations that allow you to specify a join clause. It preserves the unmatched rows from the first (left) table, joining them with a NULL row in the shape of the second (right) table.

`Select * From Table1 Left Outer Join on table1.ID=table2.ID`

A left outer join displays all the rows from the first table and the matched rows from the second table.

**Example**: The following query retrieves the employee name and the corresponding department he belongs to, whereas all the departments are displayed even if the employee is not assigned to any department.

`SELECT e.EmployeeID, e.Employee_Name, d.Department_Name FROM employee e(nolock) LEFT JOIN department d(nolock) ON e.DepartmentID = d.DepartmentID`

Output:
</details>

<details>
<summary>
126.<b> What is a right join in SQL Server?</b>
</summary>

**Right JOIN** - A RIGHT OUTER JOIN is one of the JOIN operations that allows you to specify a JOIN clause. It preserves the unmatched rows from the Table2 (right) table, joining them with a NULL in the shape of the Table1 (left) table. A LEFT OUTER JOIN B is equivalent to B RIGHT OUTER JOIN A, with the columns in a different order.

`Select * From Table1 Right Outer Join on table1.ID = table2.ID`

The right outer join displays all the rows from the second table and matched rows from the first table.

**Example**:

`SELECT e.EmployeeID, e.Employee_Name, d.Department_Name FROM employee e(nolock) RIGHT JOIN department d(nolock) ON e.DepartmentID = d.DepartmentID`

Output:
</details>

<details>
<summary>
127.<b> What is database engine in SQL Server?</b>
</summary>

The **SQL Server Database** Engine, SQL Server Agent, and several other SQL Server components run as services. These services typically are started when the operating system starts. This depends on what is specified during setup; some services are not started by default.

A service is a type of application (executable) that runs in the system background. Services usually provide core operating system features, such as Web serving, event logging, or file serving. Services can run without showing a user interface on the computer desktop. The SQL Server Database Engine, SQL Server Agent, and several other SQL Server components run as services. These services typically are started when the operating system starts. This depends on what is specified during setup; some services are not started by default.

This describes the management of the various SQL Server services on your machine. Before you log in to an instance of SQL Server, you need to know how to start, stop, pause, resume, and restart an instance of SQL Server. After you are logged in, you can perform tasks such as administering the server or querying a database.

Let's start now, select start/All Programs/Microsoft SQL Server2005/Configuration Tools/SQL Server Configuration Manager.
</details>

<details>
<summary>
128.<b> What are the Analysis Services in SQL Server?</b>
</summary>

The purpose of analysis services is to turn data into information and to provide quick and easy access to that information for decision makers. SSAS provides OLAP by letting you design, create and manage multidimensional structures that contain data aggregated from other data sources, such as relational databases and provides many data mining algorithms for mining data from data sources. So for delivering OLAP and data mining it uses client and server technologies.

The main idea of SSAS is to provide fast results from data sources when we apply a query because in order to make a decision we need data of various dimensions.

**Components of the Architecture in detail**:

1. **Server Architecture**: This runs as a Windows service. The Msmdsrv.exe application is a server component. This application consists of security, XMLA listener, query processor and other components that perform the following tasks:

2. **Client Architecture**: SSAS has a thin client Component Architecture. All queries and calculations are resolved by the server only. So for each request a server to client connection is required. There are several providers with SSAS to support various programming languages. These providers communicate using SOAP packets. You can better understand this by the following diagram:
</details>


<details>
<summary>
129.<b> What are the integration services in SQL Server?</b>
</summary>

**Integration Services** is a platform for building high performance data integration and workflow solutions, including extraction, transformation and loading (ETL) operations for data warehousing.

This includes graphical tools and wizards for building and debugging packages.

**Uses of Integration Services**:

One use of Integration Services is to merge data from multiple data stores and update the data to data warehouses and/or data marts. Create the Data Transformation process logic and automate the data loading process.

Architecture of Integration Services:

**Some important components to using Integration Services**:

• SSIS Designer

• Runtime engine

• Tasks and other executables

• Data Flow engine and Data Flow components

• API or object model

• Integration Services Service

• SQL Server Import and Export Wizard

• Other tools, wizards and command prompt utilities
</details>


<details>
<summary>
130.<b> What are the data quality services in SQL Server?</b>
</summary>

**SQL Server Data Quality Services** - SQL Server 2012 Data Quality Services (DQS) is the data quality product from Microsoft SQL Server 2012. DQS enables you to perform a variety of critical data quality tasks, including correction, enrichment, standardization and de-duplication of your data.

**DQS provides the following features to resolve data quality issues**:

• Data Cleansing

• Matching

• Reference Data Services

• Profiling and Monitoring

• Knowledge Base

DQS enables you to perform data cleansing using cloud-based reference data services provided by reference data providers. DQS also provides profiling that is integrated into its data-quality tasks, enabling to analyze the integrity of the data.

**Data Quality Server** - Data Quality Server is implemented as three SQL Server catalogs DQS_MAIN, DQS_PROJECTS, and DQS_STAGING_DATA. DQS_MAIN includes DQS Stored Procedures, DQS engine, and published Knowledge Bases.

DQS_PROJECTS includes data that is required for Knowledge Base management and DQS project activities.

DQS_STAGING_DATA provides an intermediate staging database where you can copy source data to perform DQS operations, and then export your processed data.
</details>
