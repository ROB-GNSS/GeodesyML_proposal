## GNSS network

As the requirements for the validity of the collected GNSS station information depend on the international networks the GNSS stations belong to, we propose to include this information by exploiting the class `geo:moreInformation` (corresponding to Section 13 of the IGS site log) and introducing a new property `geo:gnssNetwork` together with the associated code list file [`network-codelists.xml`](../codelists/network-codelists.xml):

```xml
    <geo:moreInformation>
      <geo:MoreInformation gml:id="more-info">
        <!-- Network list [0..n] (network details defined in the network-codelists.xml) -->
        <geo:gnssNetwork codeSpace="urn:gnss-metadata.eu:gnss:network" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/network-codelists.xml#GeodesyML_Network" codeListValue="EPOS">EPOS</geo:gnssNetwork>
        <geo:gnssNetwork codeSpace="urn:gnss-metadata.eu:gnss:network" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/network-codelists.xml#GeodesyML_Network" codeListValue="EPN">EPN</geo:gnssNetwork>
        <geo:gnssNetwork codeSpace="urn:gnss-metadata.eu:gnss:network" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/network-codelists.xml#GeodesyML_Network" codeListValue="ROB_GNSS">ROB_GNSS</geo:gnssNetwork>
        <geo:gnssNetwork codeSpace="urn:gnss-metadata.eu:gnss:network" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/network-codelists.xml#GeodesyML_Network" codeListValue="IGS">IGS</geo:gnssNetwork>
        <geo:gnssNetwork codeSpace="urn:gnss-metadata.eu:gnss:network" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/network-codelists.xml#GeodesyML_Network" codeListValue="E-GVAP">E-GVAP</geo:gnssNetwork>
```
