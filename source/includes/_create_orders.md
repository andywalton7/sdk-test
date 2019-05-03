> Example Create Order Request

```json
POST https://apisandbox.electioapp.com/orders

{
  "OrderReferenceProvidedByCustomer": "MY_ORDER_REF_001",
  "RequiredDeliveryDate": {
    "Date": "2019-05-08T00:00:00+00:00",
    "IsToBeExactlyOnTheDateSpecified": false
  },
  "Source": "Api",
  "ShippingDate": "2019-05-06T14:53:23.0482516Z",
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
            "Value": 0.5,
            "Unit": "Kg"
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
        "Value": 0.5,
        "Unit": "Kg"
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
  "CustomsDocumentation": {
    "DesignatedPersonResponsible": "Peter McPetersson",
    "ImportersVatNumber": "02345555",
    "CategoryType": "Other",
    "ShipperCustomsReference": "CREF0001",
    "ImportersTaxCode": "TC001",
    "ImportersTelephone": "0161123456",
    "ImportersFax": "01611124547",
    "ImportersEmail": "peter.mcpetersson@test.com",
    "CN23Comments": "Comments",
    "ReferencesOfAttachedInvoices": [
      "INV001"
    ],
    "ReferencesOfAttachedCertificates": [
      "CERT001"
    ],
    "ReferencesOfAttachedLicences": [
      "LIC001"
    ],
    "CategoryTypeExplanation": "Explanation",
    "DeclarationDate": "2019-05-03T00:00:00+00:00",
    "OfficeOfPosting": "Manchester",
    "ReasonForExport": "Sale",
    "ShippingTerms": "CFR",
    "ShippersVatNumber": "874541414",
    "ReceiversTaxCode": "TC5454",
    "ReceiversVatNumber": "8745474",
    "InvoiceDate": "2019-05-03T00:00:00+00:00"
  },
  "Addresses": [
    {
      "AddressType": "Origin",
      "ShippingLocationReference": "Shipping_Location_Reference",
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
  ],
  "MetaData": [
    {
      "KeyValue": "Key1",
      "StringValue": "Value1"
    },
    {
      "KeyValue": "Key2",
      "DecimalValue": 12.45
    }
  ],
  "Direction": "Outbound",
  "Tags": [
    "TagA",
    "TagB"
  ]
}
```

```xml
POST https://apisandbox.electioapp.com/orders

<?xml version="1.0" encoding="utf-8"?>
<CreateOrderRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Orders">
  <ShippingDate xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">2019-05-06T14:53:23.0482516Z</ShippingDate>
  <Packages xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <Package>
      <PackageReferenceProvidedByCustomer>MYPACK-00923</PackageReferenceProvidedByCustomer>
      <Weight>
        <Value xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">0.5</Value>
        <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Kg</Unit>
      </Weight>
      <Dimensions>
        <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Cm</Unit>
        <Width xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Width>
        <Length xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Length>
        <Height xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Height>
      </Dimensions>
      <Description>Socks</Description>
      <Value>
        <Amount xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">5.99</Amount>
        <Currency xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
          <IsoCode>GBP</IsoCode>
        </Currency>
      </Value>
      <Barcode>
        <Code xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">09887-091221</Code>
        <BarcodeType xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Code39</BarcodeType>
      </Barcode>
      <MetaData>
        <MetaData>
          <KeyValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">WMS-REF</KeyValue>
          <IntValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">77656555</IntValue>
          <DecimalValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
          <DateTimeValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
          <BoolValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
        </MetaData>
      </MetaData>
      <ConsignmentLegs>
        <ConsignmentLeg>
          <Leg>1</Leg>
          <TrackingReferences>
            <string>TRK00098HG</string>
            <string>PKJJGH434333</string>
          </TrackingReferences>
          <CarrierReference>CR001</CarrierReference>
          <CarrierName>Carrier A</CarrierName>
        </ConsignmentLeg>
      </ConsignmentLegs>
      <Items>
        <Item>
          <Sku>SKU093434</Sku>
          <Model>ITM-002</Model>
          <Description>Striped Bamboo Red/White</Description>
          <CountryOfOrigin>
            <IsoCode xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
              <TwoLetterCode>GB</TwoLetterCode>
            </IsoCode>
          </CountryOfOrigin>
          <HarmonisationCode>Harmonisation_Code</HarmonisationCode>
          <Weight>
            <Value xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">0.5</Value>
            <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Kg</Unit>
          </Weight>
          <Dimensions>
            <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Cm</Unit>
            <Width xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Width>
            <Length xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Length>
            <Height xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Height>
          </Dimensions>
          <Value>
            <Amount xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">5.99</Amount>
            <Currency xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
              <IsoCode>GBP</IsoCode>
            </Currency>
          </Value>
          <ItemReferenceProvidedByCustomer>ITEMREF-098</ItemReferenceProvidedByCustomer>
          <Barcode>
            <Code xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">09887-091221</Code>
            <BarcodeType xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Code39</BarcodeType>
          </Barcode>
          <MetaData>
            <MetaData>
              <KeyValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Picker</KeyValue>
              <StringValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">David Thomas</StringValue>
              <IntValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
              <DecimalValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
              <DateTimeValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
              <BoolValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
            </MetaData>
          </MetaData>
          <Quantity>1</Quantity>
          <Unit>Box</Unit>
          <HarmonisationKeyWords>
            <string>Keyword1</string>
          </HarmonisationKeyWords>
          <ContentClassification>Unrestricted</ContentClassification>
          <ContentClassificationDetails>NotSpecified</ContentClassificationDetails>
        </Item>
      </Items>
      <Charges>
        <KeyValuePairOfCustomChargeTypeDecimal>
          <Key xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Duty</Key>
          <Value xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">1.7</Value>
        </KeyValuePairOfCustomChargeTypeDecimal>
      </Charges>
    </Package>
  </Packages>
  <CustomsDocumentation xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <DesignatedPersonResponsible>Peter McPetersson</DesignatedPersonResponsible>
    <ImportersVatNumber>02345555</ImportersVatNumber>
    <CategoryType>Other</CategoryType>
    <ShipperCustomsReference>CREF0001</ShipperCustomsReference>
    <ImportersTaxCode>TC001</ImportersTaxCode>
    <ImportersTelephone>0161123456</ImportersTelephone>
    <ImportersFax>01611124547</ImportersFax>
    <ImportersEmail>peter.mcpetersson@test.com</ImportersEmail>
    <CN23Comments>Comments</CN23Comments>
    <ReferencesOfAttachedInvoices>
      <string>INV001</string>
    </ReferencesOfAttachedInvoices>
    <ReferencesOfAttachedCertificates>
      <string>CERT001</string>
    </ReferencesOfAttachedCertificates>
    <ReferencesOfAttachedLicences>
      <string>LIC001</string>
    </ReferencesOfAttachedLicences>
    <CategoryTypeExplanation>Explanation</CategoryTypeExplanation>
    <DeclarationDate>2019-05-03T00:00:00.0000000+00:00</DeclarationDate>
    <OfficeOfPosting>Manchester</OfficeOfPosting>
    <ReasonForExport>Sale</ReasonForExport>
    <ShippingTerms>CFR</ShippingTerms>
    <ShippersVatNumber>874541414</ShippersVatNumber>
    <ReceiversTaxCode>TC5454</ReceiversTaxCode>
    <ReceiversVatNumber>8745474</ReceiversVatNumber>
    <InvoiceDate />
  </CustomsDocumentation>
  <Addresses xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <Address>
      <ShippingLocationReference xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Shipping_Location_Reference</ShippingLocationReference>
      <AddressType>Origin</AddressType>
    </Address>
    <Address>
      <Contact xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
        <Reference xsi:nil="true" />
        <Title>Mr</Title>
        <FirstName>Peter</FirstName>
        <LastName>McPetersson</LastName>
        <Telephone>07702123456</Telephone>
        <Mobile>07702123456</Mobile>
        <LandLine>0161544123</LandLine>
        <Email>peter.mcpetersson@test.com</Email>
      </Contact>
      <CompanyName xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Test Company (UK) Ltd.</CompanyName>
      <AddressLine1 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">13 Porter Street</AddressLine1>
      <AddressLine2 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Pressington</AddressLine2>
      <AddressLine3 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Carlsby</AddressLine3>
      <Town xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
      <Region xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Greater Manchester</Region>
      <Postcode xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">M1 5WG</Postcode>
      <Country xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
        <Name>Great Britain</Name>
        <IsoCode>
          <TwoLetterCode>GB</TwoLetterCode>
        </IsoCode>
      </Country>
      <SpecialInstructions xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Gate code: 4454</SpecialInstructions>
      <LatLong xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
        <Latitude>53.474220</Latitude>
        <Longitude>-2.246049</Longitude>
      </LatLong>
      <AddressType>Destination</AddressType>
    </Address>
  </Addresses>
  <MetaData xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <MetaData>
      <KeyValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Key1</KeyValue>
      <StringValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Value1</StringValue>
      <IntValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
      <DecimalValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
      <DateTimeValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
      <BoolValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
    </MetaData>
    <MetaData>
      <KeyValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Key2</KeyValue>
      <IntValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
      <DecimalValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">12.45</DecimalValue>
      <DateTimeValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
      <BoolValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
    </MetaData>
  </MetaData>
  <Direction xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">Outbound</Direction>
  <Tags xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
    <Tag>TagA</Tag>
    <Tag>TagB</Tag>
  </Tags>
  <OrderReferenceProvidedByCustomer>MY_ORDER_REF_001</OrderReferenceProvidedByCustomer>
  <RequiredDeliveryDate>
    <IsToBeExactlyOnTheDateSpecified xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">false</IsToBeExactlyOnTheDateSpecified>
    <Date xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">2019-05-08T00:00:00.0000000+00:00</Date>
  </RequiredDeliveryDate>
  <Source>Api</Source>
</CreateOrderRequest>
```

> Example Create Order Response

```json
[
  {
    "Rel": "Order",
    "Href": "https://apisandbox.electioapp.com/orders/EO-000-0DE-9FD"
  }
]
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfApiLink xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <ApiLink>
    <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Order</Rel>
    <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://apisandbox.electioapp.com/orders/EO-000-0DE-9FD</Href>
  </ApiLink>
</ArrayOfApiLink>
```

