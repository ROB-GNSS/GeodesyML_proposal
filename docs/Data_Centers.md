## Data Centers

In an effort to
- increase the level of standardization in storing the information on data centers hosting station data,
- improve the data validation process,

we propose, as a first step, to introduce a code list file [`datacenter-codelists.xml`](codelists/datacenter-codelists.xml) to define data centers as `gml:CodeType` and exploit it inside the `geo:moreInformation` class (corresponding to Section 13 of the IGS site log) , within the existing `geo:dataCenter` property:

```xml
    <geo:moreInformation>
      <geo:MoreInformation gml:id="more-info">
        <!-- Data center list [0..n] defined as gml:CodeType (as in the code list datacenter-codelists.xml) -->
        <geo:dataCenter codeSpace="urn:gnss-metadata.eu:gnss:datacenter" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/datacenter-codelists.xml#GeodesyML_DataCenter" codeListValue="ROB">ROB</geo:dataCenter>
        <geo:dataCenter codeSpace="urn:gnss-metadata.eu:gnss:datacenter" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/datacenter-codelists.xml#GeodesyML_DataCenter" codeListValue="BKG">BKG</geo:dataCenter>
```
