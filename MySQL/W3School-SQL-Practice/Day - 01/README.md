#### What is SQL?

* SQL stands for Structured Query Language
* SQL lets you access and manipulate databases
* SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987

#### What Can SQL do?

* Execute queries against a database
* Retrieve data from a database
* Insert records in a database
* Update records in a database
* Delete records from a database
* Create new databases
* Create new tables in a database
* Create stored procedures in a database
* Create views in a database
* Set permissions on tables, procedures, and views

#### Database Tables

A database most often contains one or more tables. Each table is identified by a name (e.g. "Customers" or "Orders"). Tables contain records (rows) with data.

#### SQL Statements

Most of the actions you need to perform on a database are done with SQL statements. The following SQL statement selects all the records in the "Customers" table. 
Example
```sql
SELECT * FROM Customers;
```

#### Keep in Mind That...
* SQL keywords are NOT case sensitive: select is the same as SELECT

#### Semicolon after SQL Statements?

Some database systems require a semicolon at the end of each SQL statement. Semicolon is the standard way to separate each SQL statement in database systems that allow more than one SQL statement to be executed in the same call to the server.

#### Some of The Most Important SQL Commands

8 SELECT - extracts data from a database

* UPDATE - updates data in a database
* DELETE - deletes data from a database
* INSERT INTO - inserts new data into a database
* CREATE DATABASE - creates a new database
* ALTER DATABASE - modifies a database
* CREATE TABLE - creates a new table
* ALTER TABLE - modifies a table
* DROP TABLE - deletes a table
* CREATE INDEX - creates an index (search key)
* DROP INDEX - deletes an index

#### The SQL SELECT Statement

The SELECT statement is used to select data from a database. The data returned is stored in a result table, called the result-set.

```sql
SELECT column1, column2, ... FROM table_name;
```

SELECT * Example

The following SQL statement selects all the columns from the "Customers" table:

```sql
SELECT * FROM Customers;
```

#### The SQL SELECT DISTINCT Statement

The SELECT DISTINCT statement is used to return only distinct (different) values. Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

```sql
SELECT DISTINCT column1, column2, ... FROM table_name;
```
The following SQL statement lists the number of different (distinct) customer countries:

```sql
SELECT COUNT(DISTINCT Country) FROM Customers;
```

#### The SQL WHERE Clause

The WHERE clause is used to filter records. The WHERE clause is used to extract only those records that fulfill a specified condition.

```sql
SELECT column1, column2, ... FROM table_name WHERE condition;
```
Note: The WHERE clause is not only used in SELECT statement, it is also used in UPDATE, DELETE statement, etc.!

#### The SQL AND, OR and NOT Operators

The WHERE clause can be combined with AND, OR, and NOT operators. The AND and OR operators are used to filter records based on more than one condition:

* The AND operator displays a record if all the conditions separated by AND are TRUE.
* The OR operator displays a record if any of the conditions separated by OR is TRUE.
* The NOT operator displays a record if the condition(s) is NOT TRUE.

AND Syntax
```sql
SELECT column1, column2, ... FROM table_name WHERE condition1 AND condition2 AND condition3 ...;
```

OR Syntax
```sql
SELECT column1, column2, ... FROM table_name WHERE condition1 OR condition2 OR condition3 ...;
```

NOT Syntax
```sql
SELECT column1, column2, ... FROM table_name WHERE NOT condition;
```

#### Combining AND, OR and NOT
You can also combine the AND, OR and NOT operators.

```sql
SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');
```

```sql
SELECT * FROM Customers WHERE NOT Country='Germany' AND NOT Country='USA';
```

#### The SQL ORDER BY Keyword

The ORDER BY keyword is used to sort the result-set in ascending or descending order. The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

#### INSERT INTO Syntax

It is possible to write the INSERT INTO statement in two ways. The first way specifies both the column names and the values to be inserted:

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

#### What is a NULL Value?

A field with a NULL value is a field with no value. If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

Note: A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

#### How to Test for NULL Values?

It is not possible to test for NULL values with comparison operators, such as =, <, or <>. We will have to use the IS NULL and IS NOT NULL operators instead.

IS NULL Syntax

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```
IS NOT NULL Syntax
```sql
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

#### The SQL UPDATE Statement
The UPDATE statement is used to modify the existing records in a table.

UPDATE Syntax
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

UPDATE Multiple Records

It is the WHERE clause that determines how many records will be updated. The following SQL statement will update the contactname to "Juan" for all records where country is "Mexico":
```sql
UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';
```
Note: Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!


#### The SQL DELETE Statement
The DELETE statement is used to delete existing records in a table.

```sql
DELETE FROM table_name WHERE condition;
```
Note: Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!

Delete All Records

It is possible to delete all rows in a table without deleting the table. This means that the table structure, attributes, and indexes will be intact:
```sql
DELETE FROM table_name;
```