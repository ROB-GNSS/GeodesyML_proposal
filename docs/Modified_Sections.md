## Provenance information for the site log

For the same reason that led to the introduction of the new class [`geo:Metadata`](docs/Metadata.md), to indicate changes made in the site log (corresponding to the class `geo:siteLog`), we introduce a new property `geo:modifiedSection` within the `geo:FormInformation` class. In particular, `xlink` allows us to uniquely identify which sections of the site log have been changed in a given site log update (`geo:FormInformation`); the use of a code list [`sitelogchange-codelists.xml`](../codelists/sitelogchange-codelists.xml) allows us to classify the type of change occured in each site log section:

```xml
<!-- Trackable information on the site log updates  -->
<geo:formInformation>
  <geo:FormInformation gml:id="form-info-1">
    <geo:preparedBy>Carine Bruyninx</geo:preparedBy>
    <geo:datePrepared>2020-01-20</geo:datePrepared>
    <geo:reportType>UPDATE</geo:reportType>
  </geo:FormInformation>
  <geo:FormInformation gml:id="form-info-2">
    <geo:preparedBy>Carine Bruyninx</geo:preparedBy>
    <geo:datePrepared>2021-04-20</geo:datePrepared>
    <geo:reportType>UPDATE</geo:reportType>
    <!-- Links to the site log sections that have been modified in the site log update -->
    <geo:modifiedSection xlink:href="#site-identification" codeSpace="urn:gnss-metadata.eu:gnss:sitelogchange" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/sitelogchange-codelists.xml" codeListValue="DOMES_no"></geo:modifiedSection>
    <geo:modifiedSection xlink:href="#site-identification" codeSpace="urn:gnss-metadata.eu:gnss:sitelogchange" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/sitelogchange-codelists.xml" codeListValue="Monument_info"></geo:modifiedSection>
  </geo:FormInformation>
</geo:formInformation>
```
