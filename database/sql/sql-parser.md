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

Enhanced and removed all extra whitespace tokens.

#### Example

JOIN query

```text
query = join_query...
|- 0 DML 'SELECT'
|- 1 Whitespace ' '
|- 2 IdentifierList 'T1.COU...'
|  |- 0 Identifier 'T1.COU...'
|  |  |- 0 Name 'T1'
|  |  |- 1 Punctuation '.'
|  |  `- 2 Name 'COUNTRY'
|  |- 1 Punctuation ','
|  |- 2 Newline ' '
|  |- 3 Identifier 'T1.NAME'
|  |  |- 0 Name 'T1'
|  |  |- 1 Punctuation '.'
|  |  `- 2 Name 'NAME'
|  |- 4 Punctuation ','
|  |- 5 Newline ' '
|  `- 6 Function 'COUNT(...'
|     |- 0 Identifier 'COUNT'
|     |  `- 0 Name 'COUNT'
|     `- 1 Parenthesis '(*)'
|        |- 0 Punctuation '('
|        |- 1 Wildcard '*'
|        `- 2 Punctuation ')'
|- 3 Newline ' '
|- 4 Keyword 'FROM'
|- 5 Whitespace ' '
|- 6 Identifier 'AIRLIN...'
|  |- 0 Name 'AIRLIN...'
|  |- 1 Whitespace ' '
|  |- 2 Keyword 'AS'
|  |- 3 Whitespace ' '
|  `- 4 Identifier 'T1'
|     `- 0 Name 'T1'
|- 7 Newline ' '
|- 8 Keyword 'JOIN'
|- 9 Whitespace ' '
|- 10 Identifier 'ROUTES...'
|  |- 0 Name 'ROUTES'
|  |- 1 Whitespace ' '
|  |- 2 Keyword 'AS'
|  |- 3 Whitespace ' '
|  `- 4 Identifier 'T2'
|     `- 0 Name 'T2'
|- 11 Whitespace ' '
|- 12 Keyword 'ON'
|- 13 Whitespace ' '
|- 14 Comparison 'T1.ALI...'
|  |- 0 Identifier 'T1.ALID'
|  |  |- 0 Name 'T1'
|  |  |- 1 Punctuation '.'
|  |  `- 2 Name 'ALID'
|  |- 1 Whitespace ' '
|  |- 2 Comparison '='
|  |- 3 Whitespace ' '
|  `- 4 Identifier 'T2.ALID'
|     |- 0 Name 'T2'
|     |- 1 Punctuation '.'
|     `- 2 Name 'ALID'
|- 15 Newline ' '
|- 16 Keyword 'GROUP ...'
|- 17 Whitespace ' '
`- 18 IdentifierList 'T1.COU...'
   |- 0 Identifier 'T1.COU...'
   |  |- 0 Name 'T1'
   |  |- 1 Punctuation '.'
   |  `- 2 Name 'COUNTRY'
   |- 1 Punctuation ','
   |- 2 Newline ' '
   `- 3 Identifier 'T1.NAME'
      |- 0 Name 'T1'
      |- 1 Punctuation '.'
      `- 2 Name 'NAME'
```

Subquery

```text

query = subquery...
|- 0 DML 'SELECT'
|- 1 Whitespace ' '
|- 2 Function 'COUNT(...'
|  |- 0 Identifier 'COUNT'
|  |  `- 0 Name 'COUNT'
|  `- 1 Parenthesis '(*)'
|     |- 0 Punctuation '('
|     |- 1 Wildcard '*'
|     `- 2 Punctuation ')'
|- 3 Newline ' '
|- 4 Keyword 'FROM'
|- 5 Whitespace ' '
|- 6 Identifier 'ROUTES'
|  `- 0 Name 'ROUTES'
|- 7 Newline ' '
`- 8 Where 'WHERE ...'
   |- 0 Keyword 'WHERE'
   |- 1 Whitespace ' '
   |- 2 Identifier 'DST_AP...'
   |  `- 0 Name 'DST_AP...'
   |- 3 Whitespace ' '
   |- 4 Keyword 'IN'
   |- 5 Newline ' '
   |- 6 Parenthesis '(SELEC...'
   |  |- 0 Punctuation '('
   |  |- 1 DML 'SELECT'
   |  |- 2 Whitespace ' '
   |  |- 3 Identifier 'APID'
   |  |  `- 0 Name 'APID'
   |  |- 4 Newline ' '
   |  |- 5 Keyword 'FROM'
   |  |- 6 Whitespace ' '
   |  |- 7 Identifier 'AIRPOR...'
   |  |  `- 0 Name 'AIRPOR...'
   |  |- 8 Newline ' '
   |  |- 9 Where 'WHERE ...'
   |  |  |- 0 Keyword 'WHERE'
   |  |  |- 1 Whitespace ' '
   |  |  `- 2 Comparison 'COUNTR...'
   |  |     |- 0 Identifier 'COUNTRY'
   |  |     |  `- 0 Name 'COUNTRY'
   |  |     |- 1 Whitespace ' '
   |  |     |- 2 Comparison '='
   |  |     |- 3 Whitespace ' '
   |  |     `- 4 Single ''CANAD...'
   |  `- 10 Punctuation ')'
   |- 7 Newline ' '
   |- 8 Keyword 'AND'
   |- 9 Whitespace ' '
   |- 10 Identifier 'SRC_AP...'
   |  `- 0 Name 'SRC_AP...'
   |- 11 Whitespace ' '
   |- 12 Keyword 'IN'
   |- 13 Newline ' '
   `- 14 Parenthesis '(SELEC...'
      |- 0 Punctuation '('
      |- 1 DML 'SELECT'
      |- 2 Whitespace ' '
      |- 3 Identifier 'APID'
      |  `- 0 Name 'APID'
      |- 4 Newline ' '
      |- 5 Keyword 'FROM'
      |- 6 Whitespace ' '
      |- 7 Identifier 'AIRPOR...'
      |  `- 0 Name 'AIRPOR...'
      |- 8 Newline ' '
      |- 9 Where 'WHERE ...'
      |  |- 0 Keyword 'WHERE'
      |  |- 1 Whitespace ' '
      |  `- 2 Comparison 'COUNTR...'
      |     |- 0 Identifier 'COUNTRY'
      |     |  `- 0 Name 'COUNTRY'
      |     |- 1 Whitespace ' '
      |     |- 2 Comparison '='
      |     |- 3 Whitespace ' '
      |     `- 4 Single ''UNITE...'
      `- 10 Punctuation ')'
```

