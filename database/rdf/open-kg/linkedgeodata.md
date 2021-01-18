# LinkedGeoData

## Data Download

[Link](https://hobbitdata.informatik.uni-leipzig.de/LinkedGeoData/downloads.linkedgeodata.org/releases/)

```text
wget -r -nc -nH --cut-dirs=1 -np -l1 -A '*.nt.bz2' -A '*.owl' -R '*unredirected*' https://hobbitdata.informatik.uni-leipzig.de/LinkedGeoData/downloads.linkedgeodata.org/releases/2015-11-02/
```

## Data Description

Global locations from OpenStreetMap. Latest update on 2015 Nov 02.

### Prefix

```text
PREFIX gadm-o: <http://linkedgeodata.org/ld/gadm2/ontology/>
PREFIX gadm-r: <http://linkedgeodata.org/ld/gadm2/resource/>
PREFIX lgd-geom: <http://linkedgeodata.org/geometry/>
PREFIX lgdo: <http://linkedgeodata.org/ontology/>
PREFIX lgdr:<http://linkedgeodata.org/triplify/>
PREFIX meta: <http://linkedgeodata.org/meta/>
PREFIX meta-o: <http://linkedgeodata.org/ld/meta/ontology/>

PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

PREFIX dcterms: <http://purl.org/dc/terms/>

PREFIX ogc: <http://www.opengis.net/ont/geosparql#>

PREFIX geom: <http://geovocab.org/geometry#>
PREFIX spatial: <http://geovocab.org/spatial#>

PREFIX bif: <http://www.openlinksw.com/schemas/bif#>
# For jena, PREFIX bif: <bif:>
```

`lgdo` for ontology.

`lgdr` for place entity.

`meta` indicates it is a `Node` \(place\) or `Way` \(region\).

### Examples of Triplets

The type of a POI

e.g. `<lgdr:node3315834991 rdf:type lgdo:Zoo>`

`<lgdr:node3315834991 rdf:type lgdo:TourismThing>`

`<lgdr:node3315834991 rdf:type meta:Node>`

`<lgdr:node3315834991 rdf:type spatial:Feature>`

The name of a POI

e.g. `<lgdr:node3315834991 rdfs:label "Snake farm">` 

The longitude and latitude of a POI

e.g. `<lgdr:node3315834991 geo:long 99.9458>` `<lgdr:node3315834991 geo:lat 9.43117>`

The postal code of a POI

e.g. `<lgdr:node330310968 lgdo:postalCode "PL20 6SP">`

Note: `<lgdr:node330310968 rdfs:label "Cherrybrook Hotel">`

The type of a region

e.g. `<lgdr:way108855775 rdf:type meta:Way>`

Note: `<lgdr:way108855775 rdfs:label "Whangarata Zoo Park">`

The geometry of a region

e.g. `<lgd-geom:way108855775 ogc:asWKT  "LINESTRING(174.9863815 -37.2555661,174.987351 -37.2548129,174.9873908 -37.2547205,174.987766 -37.2538185,174.9871252 -37.2535789,174.9870256 -37.2535841,174.9867567 -37.2535789,174.986604 -37.253526,174.9856711 -37.2547627,174.9863815 -37.2555661)"^^<http://www.openlinksw.com/schemas/virtrdf#Geometry>>`

Note: the query is

```text
PREFIX meta: <http://linkedgeodata.org/meta/>
PREFIX lgdo: <http://linkedgeodata.org/ontology/>
PREFIX geom: <http://geovocab.org/geometry#>
PREFIX ogc: <http://www.opengis.net/ont/geosparql#>
SELECT * {
  lgdr:way108855775 geom:geometry [ogc:asWKT ?w]
}
```

### OSM Queries

[link](http://linkedgeodata.org/OSM)

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

## Note

For latest data, [download](https://download.geofabrik.de/) from OpenStreetMap.

## References

1. [LinkedGeoData official website ](http://linkedgeodata.org/)
2. [CSDN: 知识图谱---地理信息数据集](https://blog.csdn.net/github_37002236/article/details/81908446)
3. [Jörn's Blog: Setting up a Linked Data mirror from RDF dumps](https://joernhees.de/blog/2015/11/23/setting-up-a-linked-data-mirror-from-rdf-dumps-dbpedia-2015-04-freebase-wikidata-linkedgeodata-with-virtuoso-7-2-1-and-docker-optional/)

