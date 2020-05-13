# SQL Parser

Conditions:

* Python

Abbreviations:

* AST \(Abstract Syntax Tree\)

Example queries \(from [spider](https://yale-lily.github.io/spider) dataset\)

JOIN query

```sql
SELECT T1.country,
       T1.name,
       count(*)
FROM airlines AS T1
JOIN routes AS T2 ON T1.alid = T2.alid
GROUP BY T1.country,
         T1.name
```

Subquery

```sql
SELECT count(*)
FROM routes
WHERE dst_apid IN
    (SELECT apid
     FROM airports
     WHERE country = 'Canada')
  AND src_apid IN
    (SELECT apid
     FROM airports
     WHERE country = 'United States')
```

## pglast

### Summary

* Python
* Uses `libpg_query` , and supports only strict Postgres query \(no TSQL etc.\)
* Postgres internal AST
* SQL formatter

### Error handling

Stops parsing at the first error occurred.

Typical error message

```text

```

### Typical AST format

#### Example

JOIN query

```text

```

Subquery

```text

```

## sqlparse

### Summary

* Python
* Non-validating, and supports any SQL-like syntax
* Custom SQL AST
* SQL formatter

### Error handling

Non-validating

### Typical AST format

#### Example

JOIN query

```text

```

Subquery

```text

```

