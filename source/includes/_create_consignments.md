> Create Consignment Endpoint
```
POST https://api.electioapp.com/consignments
```

> Example Create Consignment Request
```json
{
  "Packages": [
    {
      "Items": [
        {
          "Sku": "SKU093434",
          "Model": "ITM-002",
          "Description": "Striped Bamboo Red/White",
          "CountryOfOrigin": {
            "IsoCode": {
              "TwoLetterCode": "GB"
            }
          },
          "HarmonisationCode": "Harmonisation_Code",
          "Weight": {
            "Kg": 0.5
          },
          "Dimensions": {
            "Unit": "Cm",
            "Width": 10.0,
            "Length": 10.0,
            "Height": 10.0
          },
          "Value": {
            "Amount": 5.99,
            "Currency": {
              "IsoCode": "GBP"
            }
          },
          "ItemReferenceProvidedByCustomer": "ITEMREF-098",
          "Barcode": {
            "Code": "09887-091221",
            "BarcodeType": "Code39"
          },
          "MetaData": [
            {
              "KeyValue": "Picker",
              "StringValue": "David Thomas"
            }
          ],
          "Quantity": 1,
          "Unit": "Box",
          "HarmonisationKeyWords": [
            "Keyword1"
          ],
          "ContentClassification": "Unrestricted",
          "ContentClassificationDetails": "NotSpecified"
        }
      ],
      "PackageReferenceProvidedByCustomer": "MYPACK-00923",
      "Weight": {
        "Kg": 0.5
      },
      "Dimensions": {
        "Unit": "Cm",
        "Width": 10.0,
        "Length": 10.0,
        "Height": 10.0
      },
      "Description": "Socks",
      "Value": {
        "Amount": 5.99,
        "Currency": {
          "IsoCode": "GBP"
        }
      },
      "Barcode": {
        "Code": "09887-091221",
        "BarcodeType": "Code39"
      },
      "MetaData": [
        {
          "KeyValue": "WMS-REF",
          "IntValue": 77656555
        }
      ]
    }
  ],
  "Addresses": [
    {
      "AddressType": "Origin",
      "ShippingLocationReference": "TLS_London",
      "IsCached": false
    },
    {
      "AddressType": "Destination",
      "Contact": {
        "Title": "Mr",
        "FirstName": "Peter",
        "LastName": "McPetersson",
        "Telephone": "07702123456",
        "Mobile": "07702123456",
        "LandLine": "0161544123",
        "Email": "peter.mcpetersson@test.com"
      },
      "CompanyName": "Test Company (UK) Ltd.",
      "AddressLine1": "13 Porter Street",
      "AddressLine2": "Pressington",
      "AddressLine3": "Carlsby",
      "Town": "Manchester",
      "Region": "Greater Manchester",
      "Postcode": "M1 5WG",
      "Country": {
        "Name": "Great Britain",
        "IsoCode": {
          "TwoLetterCode": "GB"
        }
      },
      "SpecialInstructions": "Gate code: 4454",
      "LatLong": {
        "Latitude": 53.474220,
        "Longitude": -2.246049
      },
      "IsCached": false
    }
  ]
}
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<CreateConsignmentRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <Addresses>
    	<Address>
            <Contact xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                <Reference xsi:nil="true" />
                <Title />
                <FirstName>TLScontact</FirstName>
                <LastName>London</LastName>
                <Telephone>080015454646</Telephone>
                <Mobile>080015454646</Mobile>
                <LandLine />
                <Email>lon@tls.com</Email>
            </Contact>
            <ShippingLocationReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">TLS_London</ShippingLocationReference>
            <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Unit 19</AddressLine1>
            <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Exhibition House</AddressLine2>
            <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Addison Bridge Place</AddressLine3>
            <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">London</Town>
            <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Greater London</Region>
            <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">W14 8XP</Postcode>
            <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                <Name>United Kingdom</Name>
                <IsoCode>
                    <TwoLetterCode>GB</TwoLetterCode>
                </IsoCode>
            </Country>
            <SpecialInstructions xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
            <AddressType>Origin</AddressType>
        </Address>
        <Address>
            <Contact xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                <Reference xsi:nil="true" />
                <Title>Mr</Title>
                <FirstName>Peter</FirstName>
                <LastName>McPetersson</LastName>
                <Telephone>07702123456</Telephone>
                <Mobile>07702123456</Mobile>
                <LandLine>0161544123</LandLine>
                <Email>peter.mcpetersson@test.com</Email>
            </Contact>
            <CompanyName xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Test Company (UK) Ltd.</CompanyName>
            <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">13 Porter Street</AddressLine1>
            <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pressington</AddressLine2>
            <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Carlsby</AddressLine3>
            <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
            <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Greater Manchester</Region>
            <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">M1 5WG</Postcode>
            <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                <Name>United Kingdom</Name>
                <IsoCode>
                    <TwoLetterCode>GB</TwoLetterCode>
                </IsoCode>
            </Country>
            <SpecialInstructions xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Gate code: 4454</SpecialInstructions>
            <AddressType>Destination</AddressType>
        </Address>
    </Addresses>
    <Packages>
        <Package>
            <Reference>EP-000-05C-BF7</Reference>
            <PackageReferenceProvidedByCustomer>MYPACK-00923</PackageReferenceProvidedByCustomer>
            <ConsignmentLegs />
            <Weight>
                <Kg xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.50000</Kg>
            </Weight>
            <Dimensions>
                <Width xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Width>
                <Length xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Length>
                <Height xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Height>
            </Dimensions>
            <Value>
                <Amount xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">5.9900</Amount>
                <Currency xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Name>Pound Sterling</Name>
                    <IsoCode>GBP</IsoCode>
                </Currency>
            </Value>
            <Description>Socks</Description>
            <Barcode>
                <Code xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">09887-091221</Code>
                <BarcodeType xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Code39</BarcodeType>
            </Barcode>
            <Items>
                <Item>
                    <Reference>4a93a9129d284e999bd2485d9c0a99a3</Reference>
                    <Sku>SKU093434</Sku>
                    <Model>ITM-002</Model>
                    <Description>Striped Bamboo Red/White</Description>
                    <CountryOfOrigin>
                        <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">United Kingdom</Name>
                        <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                            <TwoLetterCode>GB</TwoLetterCode>
                        </IsoCode>
                    </CountryOfOrigin>
                    <HarmonisationCode>Harmonisation_Code</HarmonisationCode>
                    <Weight>
                        <Kg xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.50000</Kg>
                    </Weight>
                    <Dimensions>
                        <Width xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Width>
                        <Length xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Length>
                        <Height xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">10.00</Height>
                    </Dimensions>
                    <Value>
                        <Amount xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">5.9900</Amount>
                        <Currency xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                            <Name>Pound Sterling</Name>
                            <IsoCode>GBP</IsoCode>
                        </Currency>
                    </Value>
                    <ItemReferenceProvidedByCustomer>ITEMREF-098</ItemReferenceProvidedByCustomer>
                    <Barcode>
                        <Code xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">09887-091221</Code>
                        <BarcodeType xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Code39</BarcodeType>
                    </Barcode>
                    <MetaData />
                    <UnitOfQuantity>0</UnitOfQuantity>
                    <HarmonisationKeyWords>
                        <string>Keyword1</string>
                    </HarmonisationKeyWords>
                    <ContentClassification xsi:nil="true" />
                    <ContentClassificationDetails xsi:nil="true" />
                </Item>
            </Items>
            <MetaData />
            <Charges />
        </Package>
    </Packages>
</CreateConsignmentRequest>
```
> Example Create Consignment Response
```json
[
  {
    "Rel": "Link",
    "Href": "https://api.electioapp.com/consignments/EC-000-05A-Z6S"
  }
]
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfApiLink xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <ApiLink>
    <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
    <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-05A-Z6S</Href>
  </ApiLink>
</ArrayOfApiLink>
```

The first step toward manifesting a consignment is to create that consignment in SortedPRO. 

<aside class="info">
  In the context of PRO, the term <strong>"consignment"</strong> refers to a collection of one or more packages that are shipped from the same origin address, to the same destination address, on behalf of the same Sorted customer, using the same carrier service, on the same day
  
  A <strong>package</strong> is an <strong>item</strong> or a collection of items, wrapped or contained together for shipment. Each package can contain one or more items. 

  As an example, suppose that a retailer has received a customer order for a pair of shoes, a coat, and a hat. This would likely break down to:

  * Four items - The left shoe, the right shoe, the coat and the hat.
  * Three packages - One containing both shoes, one containing the coat and one containing the hat.
  * A single consignment corresponding to everything on the order.
</aside>

Consignments are created using the **[Create Consignment](https://docs.electioapp.com/#/api/CreateConsignment)** endpoint, which takes information about new consignments, adds them to the database, and returns a link to the newly-created consignment, including its `{consignmentReference}`. The `{consignmentReference}` is a unique identifier for that consignment within PRO, and is a required parameter for many of PRO's API requests. Each PRO `{consignmentReference}` takes the format `EC-xxx-xxx-xxx`, where `x` is an alphanumeric character.

At a minimum, the **Create Consignments** endpoint requires you to send package, origin address, and destination address data. However, there are lots of other properties you can send when creating a consignment, including:

* Your own consignment reference
* The consignment's source
* Shipping and delivery dates
* Customs documentation
* The consignment's direction of travel
* Metadata and tags.

The consignment's origin address must include a valid <code>ShippingLocationReference</code>. For information on how to obtain a list of your organisation's shipping locations, see the <strong><a href="https://docs.electioapp.com/#/api/GetShippingLocations">Get Shipping Locations</a></strong> page of the API reference.

<aside class="note">
  For full reference information on the <strong>Create Consignment</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/CreateConsignment">Create Consignment</a></strong> page of the API reference.
</aside>

</section>
<section>

### Example

The example to the right shows the creation of a fairly standard consignment. In this case, we have an outbound consignment comprising a single package with a single item inside it.

After receiving the request, PRO returns a `{consignmentReference}` of _EC-000-05A-Z6S_. At this point, you should store the `{consignmentReference}`, as many of PRO's endpoints take `{consignmentReference}` as a parameter.

</section>
</section>