| Description | Command |
| --- | --- |
|Connect with Postgresql Database|psql -U username[postgres] -h localhost dbname |
| Create Database| create database mydb; |
| List of Database|\l|
| Delete Database|drop database mydb;|
|Connect with Selective Database|psql -U postgres dbname|
|Connect with Selective Database|psql -h localhost -p 5432 -U postgres dbname|
|Change Databases|\c|
|Show All table|\dt|
|Show table structure|\d tablename|
|See Command List|\h|
|Truncate Table with ID|truncate table restart identity or TRUNCATE "products" RESTART IDENTITY CASCADE;|
|Initially Locate Directory(DB Export)|C:\Program files\Postgresql\10\bin|
| Export Database| pg_dump/psql -U postgres dbname > Location[D:\backup.sql] | 
| Import Database|pg_dump/psql -U postgres dbname < Location[D:\backup.sql]|


