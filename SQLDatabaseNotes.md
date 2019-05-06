# Basics
```
CREATE DATABASE databasename;
```
```
DROP DATABASE databasename;
```
```
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak'
WITH DIFFERENTIAL;
```
```
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);
```
```
DROP TABLE table_name;
```
```
TRUNCATE TABLE table_name;
```
- deletes data inside a table, not the table itself