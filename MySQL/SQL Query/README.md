# SQL Queries Zone
```sql
-- Create Database
CREATE DATABASE demodb 
-- Drop Database
DROP DATABASE demodb 
```
```sql
-- Create Table 
CREATE TABLE doctors(
    id INT NULL AUTO_INCREMENT,
    status INT,
    doctor_name VARCHAR (255),
    PRIMARY KEY(id),
    FOREIGN KEY(demo_id) REFERENCES demotable(id),
);
```
Table: Doctors

id|status|doctors_name
--- | --- | ---
1 | 0 | Hasan Mahmud
2 | 1 | Nishat Sultana
3 | 1 | Samiya Azad

Table: Appointments

id | slot_id | patient_name | doctor_id 
---|---|---|---
1| 11 | Mr Kamal | 1
2| 12 | Mr Keramot | 2

Table: Slots

id | date | duration | time
---|---|---|---
11 | 2019-10-09|2900|01:01:00
12 | 2019-12-09|900|12:01:00

```sql
-- Insert Data
INSERT INTO doctors(status, doctor_name)
VALUES (0,'Hasan Mahmud'),
       (1, 'Nishat Sultana'),
       (1, 'Samiya Azad');
```
```sql
-- Update Data
UPDATE doctors 
SET status = 1
WHERE id = 1
```
```sql
-- Delete Data
DELETE FROM doctors 
WHERE id = 4;
```
```sql
-- Alter Table(Add/Remove/Modify Column)

-- Add Column
ALTER TABLE doctors 
ADD  mobile_number VARCHAR (15);

-- Modify Column
ALTER TABLE doctors
MODIFY COLUMN mobile_number INT(11);

-- Delete Column
ALTER TABLE doctors
DROP COLUMN mobile_number;
```
```sql
-- Select Data

-- All Data and Limit 
SELECT * FROM doctors;
SELECT * FROM doctors LIMIT 3;
SELECT * FROM doctors LIMIT 3,4; -- [3,4] 

-- Specific Data
SELECT DISTINCT doctor_name FROM doctors ORDER BY doctor_name DESC;
SELECT doctor_name FROM doctors WHERE id = 2 ORDER BY doctor_name ASC;
```
SQL Arithmetic Operators

Operator | Description
---|---
+	| Add	
-	| Subtract	
*	| Multiply	
/	| Divide	
%	| Modulo

SQL Bitwise Operators

Operator | Description
---|---
&	| Bitwise AND
|	| Bitwise OR
^	| Bitwise exclusive OR

SQL Comparison Operators

Operator | Description
---|---
=	| Equal to	
	| Greater than	
	| Less than	
>=	| Greater than or equal to	
<=	| Less than or equal to	
<>	| Not equal to

SQL Compound Operators

Operator | Description
---|---
+=	| Add equals
-=	| Subtract equals
*=	| Multiply equals
/=	| Divide equals
%=	| Modulo equals
&=	| Bitwise AND equals
^-=	| Bitwise exclusive equals
|*=	| Bitwise OR equals

SQL Logical Operators

Operator | Description
---|---
ALL	| TRUE if all of the subquery values meet the condition	
AND	| TRUE if all the conditions separated by AND is TRUE	
ANY	| TRUE if any of the subquery values meet the condition	
BETWEEN |	TRUE if the operand is within the range of comparisons	
EXISTS	| TRUE if the subquery returns one or more records	
IN	| TRUE if the operand is equal to one of a list of expressions	
LIKE |	TRUE if the operand matches a pattern	
NOT |	Displays a record if the condition(s) is NOT TRUE	
OR	 | TRUE if any of the conditions separated by OR is TRUE	
SOME |	TRUE if any of the subquery values meet the condition

```sql
-- Between Operator
SELECT * FROM slots 
WHERE duration
BETWEEN 1000 AND 1500;
```
```sql
-- Like Operator 
SELECT * FROM doctors 
WHERE doctor_name LIKE '%r'; -- Last Word 'r' of Doctor Name

SELECT * FROM doctors 
WHERE doctor_name LIKE 'N%'; -- First Word 'N' of Doctor Name

SELECT * FROM doctors 
WHERE doctor_name NOT LIKE '%is%'; -- Middle Word 'is' of Doctor Name
```
```sql
-- IN Operator 
SELECT * FROM doctors 
WHERE doctor_name IN('Hasan', 'Nisha'); -- Retrive Multiple Values
```
```sql
-- Indexes
-- 01. Data More Quickly and Efficient for Retrive
-- 02 Users don't see indexes, they are just used to speed up searches/queries
-- 03. Only create indexes on columns(and tables) that will be frequently searched against
-- Create Index
CREATE INDEX doctor_id 
ON doctors(id);
-- Drop Index
DROP INDEX doctor_id
ON doctors;
```
