# Parameterized queries

# Procedures
## Safe Stored Procedure (Microsoft SQL Server)
```sql
CREATE PROCEDURE ListCustomers(@Country nvarchar(30))
AS
SELECT city, COUNT(*)
FROM customers
WHERE country LIKE @Country GROUP BY city


EXEC ListCustomers ‘USA’
```
## Injectable Stored Procedure (Microsoft SQL Server)
```sql
CREATE PROCEDURE getUser(@lastName nvarchar(25))
AS
declare @sql nvarchar(255)
set @sql = 'SELECT * FROM users WHERE
            lastname = + @LastName + '
exec sp_executesql @sql
```
