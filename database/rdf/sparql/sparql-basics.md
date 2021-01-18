# SPARQL Basics

## Variable

A name starts with "?", e.g. `?mbox`

## WHERE Clause

```text
PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
SELECT ?name ?mbox
WHERE
  { ?x foaf:name ?name .
    ?x foaf:mbox ?mbox }
```

`?x foaf:name ?name` matches a triplet in a KG. `?x` refers to the head entity. `foaf:name` matches a relationship. `?name` refers to the tail entity. The period operator `.` means "AND".

## Operators

### Semicolon

Triple patterns with a common subject can be written so that the subject is only written once and is used for more than one triple pattern by employing the ";" notation.

```text
?x  foaf:name  ?name ;
    foaf:mbox  ?mbox .
```

is same as

```text
?x  foaf:name  ?name .
?x  foaf:mbox  ?mbox .
```

## References

1. [W3C: SPARQL Specifications](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/)
2. [Stack Overflow: Meaning of SPARQL Operator](https://stackoverflow.com/questions/18214338/meaning-of-sparql-operator)

