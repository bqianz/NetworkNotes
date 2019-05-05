SQL Notes taken from https://www.w3schools.com/sql/

## Comments
- `\* Comments *\` or `--` for single line

## Stored Procedure
Example:
- procedure definition:
```
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;
```
- calling:
```
EXEC SelectAllCustomers City = "London", PostalCode = "WA1 1DP";
```
- note: `nvarchar(n)` is variable-length string data

## IFNULL()
Allows you to return an alternative value if an expression is NULL.
- Example: suppose UnitsOnOrder has some null entries, then
```
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products;
```

## Case
Syntax:
```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

## INSERT INTO __ SELECT __
Syntax:
```
INSERT INTO table2
SELECT * FROM table1
WHERE condition;
```