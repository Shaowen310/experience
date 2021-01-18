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

is equivalent to

```text
?x  foaf:name  ?name .
?x  foaf:mbox  ?mbox .
```

### Square brackets

It is a syntax for blank nodes.

Subject case

```text
[ :p "v" ] :q "w" .
```

is equivalent to

```text
_:b57 :p "v" .
_:b57 :q "w" .
```

Object case

```text
:x :q [ :p "v" ] .
```

is equivalent to

```text
:x  :q _:b57 .
_:b57 :p "v" .
```

## References

1. [W3C: SPARQL Specifications](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/)
2. [Stack Overflow: Meaning of SPARQL Operator](https://stackoverflow.com/questions/18214338/meaning-of-sparql-operator)
3. [Stack Overflow: Meaning of square brackets “\[\]” when querying RDF with SPARQL](https://stackoverflow.com/questions/25278044/meaning-of-square-brackets-when-querying-rdf-with-sparql)

