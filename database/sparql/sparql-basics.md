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

## References

1. [W3C: SPARQL Specifications](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/)

