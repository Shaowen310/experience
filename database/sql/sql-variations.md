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

### Configurations

#### SET QUOTED\_IDENTIFIER \(Transact-SQL\)

`ON` causes SQL Server to follow the ISO rules regarding quotation mark delimiting identifiers and literal strings.

