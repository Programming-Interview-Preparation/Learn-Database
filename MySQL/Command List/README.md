# SQL-Command-List

### AND and OR
| Description | Command |
| --- | --- |
|AND combines two or more conditions for a single query|SELECT * FROM Developers WHERE Country='Bangladesh' AND City='Dhaka'; |
|OR is used similarly, but it will output result with rows that comply with either of the conditions|SELECT * FROM Developers WHERE City='Koln' OR City='Dhaka';|

### ALTER TABLE
#### ALTER TABLE allows you to add or remove columns from a table.
| Description | Command |
| --- | --- |
|Add Column|ALTER TABLE Developers ADD BirthDate date;|
|Drop Colum|ALTER TABLE Developers DROP COLUMN BirthDate;|

### AS (alias)
#### AS allows you to rename a column or table to a more convenient alias (a correlation name) without changing the original names in the database.
|Description|Command|
|---|---|
|Rename Column Name|SELECT ID as CustomerID, Name AS NewColumnName FROM Customers;|


### BETWEEN
#### BETWEEN operator filters the results and returns only the ones that fit the specified range. 
|Description|Command|
|---|---|
|Filter the Specified range|SELECT * FROM Orders WHERE Price BETWEEN 10 AND 15;|


### CREATE DATABASE
|Description|Command|
|---|---|
|Create Database|CREATE DATABASE testingDB;|


### CREATE TABLE
|Description|Command|
|---|---|
|Creates a new table|CREATE TABLE Suppliers (SupplierID int,FirstName varchar(255),LastName varchar(255),City varchar(255),Country varchar(255));|

### CREATE INDEX
#### CREATE INDEX generates an index for a table. This enables retrieving data from a database faster.
|Description|Command|
|---|---|
|Index Column|CREATE INDEX idx_lastname ON Persons (LastName);|

### DELETE
|Description|Command|
|---|---|
|Delete Specific Value|DELETE FROM Developers WHERE Name='Antonio Indigo';|
|Delete All Value|DELETE * FROM Developers;|
|Cascade Deletes |TRUNCATE "products" RESTART IDENTITY CASCADE;|

### DROP Database and Table
|Description|Command|
|---|---|
|Drop Database|DROP DATABASE db_name|
|Drop Table|DROP TABLE tbl_name|

### IN
#### The IN operator includes multiple values into the WHERE clause.
|Description|Command|
|---|---|
|Filter Specific Values|SELECT * FROM Developers WHERE Country IN ('USA', 'France', 'India');|

### INSERT INTO
#### INSERT INTO statement inserts new rows of data into a table.
|Description|Command|
|---|---|
|Insert New Value in Table|INSERT INTO Developers (Name, City, Country) VALUES ('Luke Christon', 'London', 'UK');|

### INNER JOIN
|Description|Command|
|---|---|
|Inner Join|SELECT Orders.ID, Developers.Name FROM Orders INNER JOIN Developers ON Orders.ID = Developers.ID;|

### LEFT JOIN
|Description|Command|
|---|---|
|LEFT JOIN retrieves records from the left table that match records in the right table|SELECT Developers.Name, Customer_orders.ID FROM Developers LEFT JOIN Customer_orders ON Developers.ID = Customer_orders.customer_id ORDER BY Developers.Name;|

### RIGHT JOIN
|Description|Command|
|---|---|
|RIGHT JOIN retrieves records from the right table that match records in the left table|SELECT Customer_orders.ID, Employees.Last_name, Employees.First_name FROM Customer_orders RIGHT JOIN Employees ON Customer_orders.employee_id = Employees.ID ORDER BY Customer_orders.ID;|

### FULL JOIN
|Description|Command|
|---|---|
|FULL JOIN returns all the records that match either in left or right tables|SELECT Customers.Name, Customer_orders.ID FROM Customers FULL OUTER JOIN Orders ON Customers.ID=Customer_orders.customer_id ORDER BY Customers.Name;|

### LIKE
#### Combine LIKE with the WHERE clause for finding specific patterns in columns.
|Description|Command|
|---|---|
|Search Result|SELECT * FROM users WHERE email LIKE '%gmail%';|


### ORDER BY
#### ORDER BY sets the order (ascending by default) of result records.
|Description|Command|
|---|---|
|Order Data|SELECT * FROM users ORDER BY email DESC;|

### SELECT
|Description|Command|
|---|---|
|Select Specific Value|SELECT username,email FROM users;|
|Select All|SELECT * FROM Customers;|
|SELECT DISTINCT returns only the data that is distinct, and does not include duplicate entries.|SELECT DISTINCT City FROM Developers;|
|SELECT INTO statement selects specified data in a table and copies it to another table|SELECT * INTO CustomerBackup2018
FROM Customers;|
||SELECT * INTO CustomerBackup2018 FROM Customers;|
|SELECT TOP|SELECT * FROM Customers LIMIT 3;|
||SELECT TOP 50 PERCENT * FROM Customers;|

### TRUNCATE TABLE
#### TRUNCATE TABLE removes data entries from a table in a database, but keeps the table, its datatype and column parameters.
|Description|Command|
|---|---|
|Truncate Table|TRUNCATE TABLE tbl_name|

### UNION
#### You can combine multiple result-sets using the UNION operator with two or more SELECT statements.
|Description|Command|
|---|---|
|Specific Union|SELECT City FROM Developers UNION SELECT City FROM Customers ORDER BY City;|
|Union All|SELECT City FROM Developers UNION ALL SELECT City FROM Customers ORDER BY City;|

### UPDATE
|Description|Command|
|---|---|
|Update Value|UPDATE Developers SET City = 'Berlin', Country= 'Germany' WHERE Name = 'Hasan Mahmud';|

### WHERE
|Description|Command|
|---|---|
|Clause|SELECT * FROM Developers WHERE Country='France';|


