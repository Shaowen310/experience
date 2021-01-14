# SQL Variations

ANSI-SQL is the standard.

T-SQL is for SQL Server.

## Delimiters for Identifiers

T-SQL uses square brackets `[]`

```sql
UPDATE [dbo].[Customers]
SET [FirstName] = N'Ian'
WHERE [CustomerID] = 7
```

ANSI-SQL uses double quotes `"`

```sql
UPDATE "dbo"."Customers"
SET "FirstName" = N'Ian'
WHERE "CustomerID" = 7
```

### Escaping delimiters

Use `]]` to escape `]` , use `""` to escape `"` .

### Case sensitivity

According to ANSI-SQL, delimited identifiers are case sensitive.

SQL Server still treats delimited identifiers to be case insensitive by default.

SQL Server is, by default, case insensitive; however, it is possible to create a case-sensitive SQL Server database and even to make specific table columns case sensitive. The way to determine if a database or database object is to check its "COLLATION" property and look for "CI" or "CS" in the result.

### Configurations

#### SET QUOTED\_IDENTIFIER \(Transact-SQL\)

`ON` causes SQL Server to follow the ISO rules regarding quotation mark delimiting identifiers and literal strings.

