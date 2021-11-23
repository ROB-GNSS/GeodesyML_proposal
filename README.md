# GeodesyML proposal

As discussed during the first “GeodesyML Discussion” meeting (26.10.2021), we propose to enrich [GeodesyML's](https://github.com/GeoscienceAustralia/GeodesyML) functionalities by exploiting existing classes and including additional ones.

Here's a short version of the proposal:

- [Introduction](docs/Introduction.md)
- [New `geo:Document` properties: `geo:license` & `geo:keywords`](docs/Document.md)
- [New class `geo:Metadata`](docs/Metadata.md)
- [New code list for data centers: `datacenter-codelists.xml`](docs/Data_Centers.md)
- [New `geo:siteLog/geo:moreInformation` property: `geo:gnssnetwork`](docs/Networks.md)
- [New `geo:siteLog/geo:FormInformation` property: `geo:modifiedSection`](docs/Modified_Sections.md)


In the tables below, an overview of some of the proposed changes (see also the example [`BRUX00BEL.xml`](examples/0.6/BRUX00BEL.xml))

**Additional metadata elements**

| name | description |
| ------ | ------ |
| `geo:license` | *data/file license of use* |
| `geo:keywords` | *descriptive keywords to be used as “filters” for documents attached to GeodesyML* |
| `geo:Metadata ` | *provenance information for the GeodesyML file* |
| `geo:modifiedSection` | *changes made in the site log* |
| `geo:gnssnetwork` | *international network a given GNSS station belongs to* |



**Additional code list files**

| name | description |
| ------ | ------ |
| [`type-codelists.xml`](codelists/type-codelists.xml) | *controlled terminology for types of attached documents e.g., ATX files* |
| [`license-codelists.xml`](codelists/license-codelists.xml) | *controlled terminology for data license types* |
| [`datacenter-codelists.xml`](codelists/datacenter-codelists.xml) | *controlled terminology for GNSS data centers*|
| [`network-codelists.xml`](codelists/network-codelists.xml) | *controlled terminology for GNSS international networks*|
