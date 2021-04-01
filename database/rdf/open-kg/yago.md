# YAGO

## Data Download

[link](https://yago-knowledge.org/downloads/yago-4)

```text
wget -r -nc -nH --cut-dirs=1 -np -l1 -A '*.nt.gz' -A '*.owl' -R '*unredirected*' https://yago-knowledge.org/data/yago4/en/2020-02-24/
```

## Data Description

A general knowledge graph combines entities from Wikidata and ontology of classes and relations from schema.org . Latest update on 2020 Feb 24.

### Prefix

```text
PREFIX yago: <http://yago-knowledge.org/resource/>

PREFIX schema: <http://schema.org/>
```

### Triplet Examples

#### Spatial/Geographic

The longitude and latitude of a place

e.g. `yago:Singapore schema:geo geo:1.3000026,103.8002076`

#### History

Founding date

e.g. `yago:Singapore schema:foundingDate "1965-08-09"^^xsd:date`

#### Politics/Organization

Member of

e.g. `yago:Singapore schema:memberOf yago:United_Nations`

#### Link to other KGs

`owl:sameAs` relationship

e.g. `yago:Singapore owl:sameAs dbpedia:Singapore`

## SPARQL Endpoint

[link](https://yago-knowledge.org/sparql)

## References

1. [YAGO official website](https://yago-knowledge.org/)

