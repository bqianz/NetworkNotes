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
- backs up only the parts that have changed since last backup
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

# Altering table
`ALTER TABLE`: add, delete, or modify columns in existing table, or add/drop constraints.
```
ALTER TABLE Customers
ADD Email varchar(255)
DROP COLUMN Email
ALTER COLUMN DateOfBirth year;
```
# Constraints
Used to specify rules for the data in a table
	- e.g limit type of data that can go into a table
Used with `CREATE TABLE` or `ALTER TABLE`

### NOT NULL
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```
```
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

### UNIQUE
ensure all values in a column are different
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```
```
ALTER TABLE Persons
ADD UNIQUE (ID);
```
(dropping unique constraint?)


## PRIMARY KEY
- only one PRIMARY KEY constraint per table
- `NOT NULL` and `UNIQUE` combined
```
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```
```
ALTER TABLE Persons
DROP PRIMARY KEY;
```

## FOREIGN KEY
a field or fields in one table that refers to the primary key in another table
	- __parents table__: containing the field as primary key
	- __child table__: containing the field as foreign key
```
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```
