## Provenance information for GeodesyML files

We propose to introduce a new class `geo:Metadata` to include provenance infomation about the GoedesyML file itself 
and attach rich metadata (as stated by one of the FAIR data principles: *“F2. data are described with rich metadata”* 
Wilkinson et al. The FAIR Guiding Principles for scientific data management and stewardship. [Sci Data 3, 160018 (2016)](https://www.nature.com/articles/sdata201618)) 
to the GeodesyML file itself. 

The following information, included as [`gml:MD_Metadata` data type](http://www.datypic.com/sc/niem21/e-gmd_MD_Metadata.html), will allow identifying the organization that validated and distributes the station information encoded in the GeodesyML file:

- the publisher of the GeodesyML file
- the publication date of the GeodesyML file
- the license attached to the GeodesyML file
- the source of the GeodesyML file

For example:

```xml

  <!-- Provenance information for the GeodesyML file (Publisher/ File source/ Publication date/ xml creation date/ Contact/ Legal constraints to use the metadata file)
Data Type is gml:MD_Metadata. More info at http://www.datypic.com/sc/niem21/e-gmd_MD_Metadata.html
-->
  <geo:Metadata>
    <!-- GeodesyML file name -->
    <gmd:fileIdentifier>
      <gco:CharacterString>BRUX00BEL.xml</gco:CharacterString>
    </gmd:fileIdentifier>
    <gmd:language>
      <gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="eng"/>
    </gmd:language>
    <gmd:characterSet>
      <gmd:MD_CharacterSetCode codeList="http://data.daff.gov.au/anrdl/resources/codeList/codeList20120313.xml#MD_CharacterSetCode" codeListValue="utf8">utf8</gmd:MD_CharacterSetCode>
    </gmd:characterSet>
    <gmd:hierarchyLevel>
      <gmd:MD_ScopeCode codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/Codelist/ML_gmxCodelists.xml#MD_ScopeCode" codeListValue="service"/>
    </gmd:hierarchyLevel>
    <!-- GeodesyML file publisher: name, contact info-->
    <gmd:contact>
      <gmd:CI_ResponsibleParty id="publisher">
        <gmd:organisationName>
          <gco:CharacterString>Royal Observatory of Belgium</gco:CharacterString>
        </gmd:organisationName>
        <gmd:contactInfo>
          <gmd:CI_Contact>
            <gmd:address>
              <gmd:CI_Address>
                <gmd:electronicMailAddress>
                  <gco:CharacterString>m3g@oma.be</gco:CharacterString>
                </gmd:electronicMailAddress>
              </gmd:CI_Address>
            </gmd:address>
          </gmd:CI_Contact>
        </gmd:contactInfo>
        <gmd:role>
          <gmd:CI_RoleCode
codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/Codelist/ML_gmxCodelists.xml#CI_RoleCode" codeListValue="custodian"/>
        </gmd:role>
      </gmd:CI_ResponsibleParty>
    </gmd:contact>
    <!-- GeodesyML file publication date -->
    <gmd:dateStamp>
      <gco:DateTime>2021-08-10T15:38:45Z</gco:DateTime>
    </gmd:dateStamp>
    <gmd:identificationInfo>
      <gmd:MD_DataIdentification>
        <gmd:citation>
          <gmd:CI_Citation>
            <gmd:title>
              <gco:CharacterString>Station metadata for BRUX00BEL</gco:CharacterString>
            </gmd:title>
            <gmd:date>
              <gmd:CI_Date>
                <gmd:date>
                  <gco:Date>2021-08-10</gco:Date>
                </gmd:date>
                <gmd:dateType>
                  <gmd:CI_DateTypeCode  codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/Codelist/ML_gmxCodelists.xml#CI_DateTypeCode" codeListValue="publication"/>
                </gmd:dateType>
              </gmd:CI_Date>
            </gmd:date>
          </gmd:CI_Citation>
        </gmd:citation>
        <gmd:abstract>
          <gco:CharacterString></gco:CharacterString>
        </gmd:abstract>
        <gmd:resourceConstraints>
          <gmd:MD_LegalConstraints>
            <gmd:otherConstraints>
              <gco:CharacterString>
      License: CC By 4.0 (https://creativecommons.org/licenses/by/4.0/)
      Copyright: Royal Observatory of Belgium (please acknowledge us and/or cite doi:10.24414/ROB-GNSS-M3G)
      </gco:CharacterString>
            </gmd:otherConstraints>
          </gmd:MD_LegalConstraints>
        </gmd:resourceConstraints>
        <gmd:language>
          <gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="eng"/>
        </gmd:language>
      </gmd:MD_DataIdentification>
    </gmd:identificationInfo>
    <gmd:distributionInfo>
      <gmd:MD_Distribution>
        <gmd:transferOptions>
          <gmd:MD_DigitalTransferOptions>
            <gmd:onLine>
              <!-- GeodesyML file source -->
              <gmd:CI_OnlineResource>
                <gmd:linkage>
                  <gmd:URL>https://gnss-metadata.eu/v1/sitelog/exportxml?id=BRUX00BEL</gmd:URL>
                </gmd:linkage>
                <gmd:protocol>
                  <gco:CharacterString>https</gco:CharacterString>
                </gmd:protocol>
                <gmd:name>
                  <gco:CharacterString>M3G API</gco:CharacterString>
                </gmd:name>
                <gmd:description>
                  <gco:CharacterString>M3G Web API (More info: https://gnss-metadata.eu/site/api-docs)</gco:CharacterString>
                </gmd:description>
                <gmd:function>
                  <gmd:CI_OnLineFunctionCode   codeList="http://standards.iso.org/ittf/PubliclyAvailableStandards/ISO_19139_Schemas/resources/codelist/ML_gmxCodelists.xml#CI_OnLineFunctionCode" codeListValue="download">download</gmd:CI_OnLineFunctionCode>
                </gmd:function>
              </gmd:CI_OnlineResource>
            </gmd:onLine>
          </gmd:MD_DigitalTransferOptions>
        </gmd:transferOptions>
      </gmd:MD_Distribution>
    </gmd:distributionInfo>
  </geo:Metadata>
  ```
