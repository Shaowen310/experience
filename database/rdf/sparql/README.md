# SPARQL

## Basic Patterns

```text
SELECT ?givenName
WHERE
  { ?y  <http://www.w3.org/2001/vcard-rdf/3.0#Family>  "Smith" .
    ?y  <http://www.w3.org/2001/vcard-rdf/3.0#Given>  ?givenName .
  }
```

Or

```text
PREFIX vcard:      <http://www.w3.org/2001/vcard-rdf/3.0#>

SELECT ?givenName
WHERE
 { ?y vcard:Family "Smith" .
   ?y vcard:Given  ?givenName .
 }
```

Notes

```text
PREFIX vcard:      <http://www.w3.org/2001/vcard-rdf/3.0#>
```

This command replaces `vcard:` in query by `http://www.w3.org/2001/vcard-rdf/3.0#`

Result

```text
-------------
| givenName |
=============
| "John"    |
| "Rebecca" |
-------------
```

## References

1. [Apache Jena Tutorials](https://jena.apache.org/tutorials/)

