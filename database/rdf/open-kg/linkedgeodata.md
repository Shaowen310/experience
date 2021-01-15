# LinkedGeoData

## Installation

Use docker see [link](https://joernhees.de/blog/2015/11/23/setting-up-a-linked-data-mirror-from-rdf-dumps-dbpedia-2015-04-freebase-wikidata-linkedgeodata-with-virtuoso-7-2-1-and-docker-optional/)

## Data Download

[Link](https://hobbitdata.informatik.uni-leipzig.de/LinkedGeoData/downloads.linkedgeodata.org/releases/)

## SPARQL Endpoints

Static \(at a certain date\) [link](http://linkedgeodata.org/sparql)

## RDB RDF Mappings

### RDB view of RDF

#### RDB view tables

| View Table | Description |
| :--- | :--- |
| lgd\_map\_datatype\(k, datatype\) | Values of the given keys should be interpreted as members of a certain datatype \(boolean, int or float\) |
| lgd\_map\_literal \(k, property, language\) | Values of the given keys are treated as plain literals having the specified language tag. |
| lgd\_map\_resource\_k \(k, property, object\) | The presence of a key yields triples with the given property and object. |
| lgd\_map\_resource\_kv \(k, v, property, object\) | Similar to above, except that the value is also taken into account. |
| lgd\_map\_property \(k, property\) | Relates keys to corresponding properties. |

#### RDB columns to RDF ontology

[Code link](https://github.com/GeoKnow/LinkedGeoData/blob/master/linkedgeodata-core/src/main/resources/org/aksw/linkedgeodata/sql/Mappings.sql)

Ontology \[lgdo:\] correspond to "relationship". 

Triplify \[lgdr:\] corresponds to "entity".

### SPARQL-to-SQL

Project [Github link](https://github.com/SmartDataAnalytics/Sparqlify)

## Data Scope

Global locations from OpenStreetMap.

## References

1. [LinkedGeoData official website ](http://linkedgeodata.org/)
2. [CSDN: 知识图谱---地理信息数据集](https://blog.csdn.net/github_37002236/article/details/81908446)
3. [Jörn's Blog: Setting up a Linked Data mirror from RDF dumps](https://joernhees.de/blog/2015/11/23/setting-up-a-linked-data-mirror-from-rdf-dumps-dbpedia-2015-04-freebase-wikidata-linkedgeodata-with-virtuoso-7-2-1-and-docker-optional/)

