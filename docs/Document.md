## Exploiting availability of site pictures and (individual) antenna calibration files

We propose to exploit the `geo:Document`class to include files carrying additional station information e.g., station pictures or the (individual) antenna calibration (ANTEX files). 
File types are listed in the code list file [`type-codelists.xml`](../codelists/type-codelists.xml), in an effort to extend standardization to the different types of files in use. For example, to include an individual ATX file:

```xml
   <geo:Document gml:id="atx_3">
        <gml:description>Chamber Individual Calibration</gml:description>
        <!-- Code list for the various data types related to the type of attached document -->
        <geo:type codeSpace="urn:gnss-metadata.eu:gnss:file-type" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/type-codelists.xml#FileType" codeListValue="ATX_INDIVIDUAL">
            <![CDATA[ATX_INDIVIDUAL]]>
        </geo:type>
```

In addition, to better comply with FAIR data principles, we propose to include `geo:license` as a new property to the `geo:Document` class, together with its associated code list file [`license-codelists.xml`](../codelists/type-codelists.xml), for example:

```xml
       <!-- Code list for the various license types that can be assigned to the attached document -->
        <geo:license codeSpace="urn:gnss-metadata.eu:gnss:license" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/license-codelists.xml" codeListValue="CC0-1.0">
            <![CDATA[CC0-1.0]]>
        </geo:license>
```

We also propose to introduce in `geo:Document` the new property `geo:keywords` to indicate descriptive keywords to be used as “filters” e.g., to identify the different pictures of GNSS antenna, monument etc., following the example of [SensorML](http://www.sensorml.com/sensorML-2.0/examples/description.html)

```xml
    <!-- Keywords to set up a filter for the attached documents -->
        <geo:keywords>
            <geo:KeywordList>
                <geo:keyword>Individual Calibration</geo:keyword>
                <geo:keyword>Chamber Calibration</geo:keyword>
            </geo:KeywordList>
        </geo:keywords>
```
See [this section](#include-site-pictures) for a complete example.

### `geo:Document` to include ATX files
Here's an example of use of the `geo:Document` class to include information on an antenna calibration file (an extended example to illustrate how to include different types of ATX is available [here](../examples/WARN00DEU_antenna_calibration.xml)):


```xml
   <geo:Document gml:id="atx_3">
        <gml:description>Chamber Individual Calibration</gml:description>
        <!-- Code list for the various data types related to the type of attached document -->
        <geo:type codeSpace="urn:gnss-metadata.eu:gnss:file-type" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/type-codelists.xml#FileType" codeListValue="ATX_INDIVIDUAL">
            <![CDATA[ATX_INDIVIDUAL]]>
        </geo:type>
        <!-- Keywords to set up a filter for the attached documents -->
        <geo:keywords>
            <geo:KeywordList>
                <geo:keyword>Individual Calibration</geo:keyword>
                <geo:keyword>Chamber Calibration</geo:keyword>
            </geo:KeywordList>
        </geo:keywords>
        <!-- Dates corresponding to: document creation, date when the document was received by the publisher, publication date -->
        <geo:createdDate>2018-10-15Z</geo:createdDate>
        <geo:receivedDate>2018-11-01Z</geo:receivedDate>
        <geo:publishedDate>2021-03-12Z</geo:publishedDate>
        <!-- Owner/ Creator/ Publisher (agencies' details defined in the file contacts.xml) -->
        <geo:custodian xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aaa024f"/>
        <geo:creator xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aaa0110"/>
        <geo:publisher xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aa3054f"/>
        <!-- Code list for the various license types that can be assigned to the attached document -->
        <geo:license codeSpace="urn:gnss-metadata.eu:gnss:license" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/license-codelists.xml" codeListValue="CC0-1.0">
            <![CDATA[CC0-1.0]]>
        </geo:license>
        <geo:body>
            <!-- Link to the physical file corresponding to the attached document-->
            <geo:fileReference           xlink:href="https://epncb.oma.be/ftp/station/general/indiv_calibrations/LEIAR25R4_LEIT_725559_CHAMBER_BONN_20181015.atx"
        />
        </geo:body>
    </geo:Document>
```

### <a name="include-site-pictures">`geo:Document` to include site pictures</a>
Information about available station pictures can be included in the GeodesyML file via `geo:Document`:

```xml
  <geo:Document gml:id="img_1">
    <gml:description>BRUX antenna on telescope dome.</gml:description>
    <!-- Code list for the various data types related to the type of attached document -->
    <geo:type codeSpace="urn:gnss-metadata.eu:gnss:file-type" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/type-codelists.xml#FileType" codeListValue="PICTURE">PICTURE</geo:type>
    <!-- Keywords to set up a filter for the attached documents -->
    <geo:keywords>
      <geo:KeywordList>
        <geo:keyword>Station Picture</geo:keyword>
        <geo:keyword>GNSS Antenna</geo:keyword>
        <geo:keyword>Monument</geo:keyword>
        <geo:keyword>South</geo:keyword>
      </geo:KeywordList>
    </geo:keywords>
    <!-- Dates corresponding to: document creation, date when the document was received by the publisher, publication date -->
    <geo:createdDate>2011-09-14Z</geo:createdDate>
    <geo:receivedDate>2020-11-17T14:02:00Z</geo:receivedDate>
    <geo:publishedDate>2021-10-03Z</geo:publishedDate>
    <!-- Owner/ Creator/ Publisher (agencies' details defined in the file contacts.xml) -->
    <geo:custodian xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aa3054f"/>
    <geo:creator xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aa3054f"/>
    <geo:publisher xlink:href="https://gnss-metadata.eu/GeodesyML_ext/codelists/contacts.xml#agency_59d4d762b6ae0c10a256a102_5bbcb5aa3054f"/>
    <!-- Code list for the various license types that can be assigned to the attached document -->
    <geo:license codeSpace="urn:gnss-metadata.eu:gnss:license" codeList="https://gnss-metadata.eu/GeodesyML_ext/codelists/license-codelists.xml" codeListValue="CC0-1.0">
      <![CDATA[CC0-1.0]]>
    </geo:license>
    <geo:remarks>BRUX antenna on telescope dome</geo:remarks>
    <geo:body>
      <!-- Link to the physical file corresponding to the attached document -->
      <geo:fileReference
      xlink:href="https://gnss-metadata.eu/sitepicture/image?id=5fb3d4e7a6b612502c092468"
    />
    </geo:body>
  </geo:Document>
```

### `geo:associatedDocument` to link associated documents to a specific antenna
The documents attached to the GeodesyML file via `geo:Document` (e.g., the antenna picture and calibration files in the example [`BRUX00BEL.xml`](../examples/BRUX00BEL.xml)) can be linked to a specific antenna (`geo:GnssAntenna`) inside the `geo:siteLog` by exploiting `geo:associatedDocument` and `xlink` as below: 

```xml
                <!-- Antenna calibration and/or site pictures can be linked to the specific antenna-->
                <geo:associatedDocument xlink:href="#img_1"/>
                <geo:associatedDocument xlink:href="#atx_1"/>
```
