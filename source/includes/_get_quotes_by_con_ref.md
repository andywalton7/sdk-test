> Example Get Quotes by Consignment Reference Request

```
https://apisandbox.electioapp.com/quotes/consignment/EC-000-05B-1CM
```

> Example Get Quotes by Consignment Reference Response

```json
{
    "QuoteRequestReference": "6f9c7ee5-a97e-4df9-bc07-aa3f00e99316",
    "Quotes": [
        {
            "MpdCarrierServiceSource": 2,
            "MpdCarrierService": "1st and 2nd Class Account Mail (1st Parcel)",
            "OriginAddress": {
                "ShippingLocationReference": "EDC5_Electio",
                "AddressLine1": "Third Floor",
                "AddressLine2": "Merchant Exchange",
                "AddressLine3": "Whitworth Street West",
                "Town": "Manchester",
                "Region": "",
                "Postcode": "M1 5WG",
                "Country": {
                    "Name": "United Kingdom",
                    "IsoCode": {
                        "TwoLetterCode": "GB",
                        "ThreeLetterCode": "GBR",
                        "NumericCode": "826"
                    }
                },
                "RegionCode": "",
                "SpecialInstructions": "",
                "IsCached": false
            },
            "DestinationAddress": {
                "AddressLine1": "13 Porter Street",
                "AddressLine2": "Pressington",
                "AddressLine3": "Carlsby",
                "Town": "Manchester",
                "Region": "Greater Manchester",
                "Postcode": "M1 5WG",
                "Country": {
                    "Name": "United Kingdom",
                    "IsoCode": {
                        "TwoLetterCode": "GB",
                        "ThreeLetterCode": "GBR",
                        "NumericCode": "826"
                    }
                },
                "SpecialInstructions": "Gate code: 4454",
                "IsCached": false
            },
            "CollectionDate": "2019-05-01T00:00:00",
            "EarliestDeliveryDate": "2019-05-02T00:00:00",
            "LatestDeliveryDate": "2019-05-02T23:59:00",
            "BasePrice": {
                "Net": 27.69,
                "Gross": 33.23,
                "VatRate": {
                    "Reference": "GB-0.2000",
                    "CountryIsoCode": "GB",
                    "Type": "Standard",
                    "Rate": 0.2
                },
                "VatAmount": 5.54,
                "Currency": {
                    "Name": "Pound Sterling",
                    "IsoCode": "GBP"
                }
            },
            "Price": {
                "Net": 27.69,
                "Gross": 33.23,
                "VatRate": {
                    "Reference": "GB-0.2000",
                    "CountryIsoCode": "GB",
                    "Type": "Standard",
                    "Rate": 0.2
                },
                "VatAmount": 5.54,
                "Currency": {
                    "Name": "Pound Sterling",
                    "IsoCode": "GBP"
                }
            },
            "Surcharges": [],
            "Legs": [
                {
                    "JourneyStage": 1,
                    "CarrierService": {
                        "Reference": "RMDBPR1STPSU",
                        "Name": "1st and 2nd Class Account Mail (1st Parcel)",
                        "CarrierReference": "ROYAL_MAIL",
                        "CarrierName": null,
                        "IsDropOff": false,
                        "IsPickUp": false,
                        "IsTimed": false
                    },
                    "CarrierAccountReference": "RM1",
                    "DeliveryHub": null,
                    "CostItems": null,
                    "VolumetricParcelWeight": null,
                    "CollectionType": "NotApplicable"
                }
            ],
            "CarrierAccountOwner": null,
            "IsElectioService": false,
            "QuoteReference": "f6374a18-a6b5-48c1-841c-aa3f00e9951a",
            "CreationDate": "2019-04-30T14:10:26.8551633+00:00",
            "ExpiryDate": "2019-05-01T00:00:00+01:00",
            "Requestor": "Andy Walton",
            "ConsignmentReference": "EC-000-05B-1CM",
            "ConsignmentReferenceProvidedByCustomer": "",
            "MpdCarrierServiceReference": "MPD_RMDBPR1STPSU"
        },
        {
            "MpdCarrierServiceSource": 2,
            "MpdCarrierService": "Tracked 48 Signed For",
            "OriginAddress": {
                "ShippingLocationReference": "EDC5_Electio",
                "AddressLine1": "Third Floor",
                "AddressLine2": "Merchant Exchange",
                "AddressLine3": "Whitworth Street West",
                "Town": "Manchester",
                "Region": "",
                "Postcode": "M1 5WG",
                "Country": {
                    "Name": "United Kingdom",
                    "IsoCode": {
                        "TwoLetterCode": "GB",
                        "ThreeLetterCode": "GBR",
                        "NumericCode": "826"
                    }
                },
                "RegionCode": "",
                "SpecialInstructions": "",
                "IsCached": false
            },
            "DestinationAddress": {
                "AddressLine1": "13 Porter Street",
                "AddressLine2": "Pressington",
                "AddressLine3": "Carlsby",
                "Town": "Manchester",
                "Region": "Greater Manchester",
                "Postcode": "M1 5WG",
                "Country": {
                    "Name": "United Kingdom",
                    "IsoCode": {
                        "TwoLetterCode": "GB",
                        "ThreeLetterCode": "GBR",
                        "NumericCode": "826"
                    }
                },
                "SpecialInstructions": "Gate code: 4454",
                "IsCached": false
            },
            "CollectionDate": "2019-05-01T00:00:00",
            "EarliestDeliveryDate": "2019-05-03T00:00:00",
            "LatestDeliveryDate": "2019-05-03T23:59:00",
            "BasePrice": {
                "Net": 27.69,
                "Gross": 33.23,
                "VatRate": {
                    "Reference": "GB-0.2000",
                    "CountryIsoCode": "GB",
                    "Type": "Standard",
                    "Rate": 0.2
                },
                "VatAmount": 5.54,
                "Currency": {
                    "Name": "Pound Sterling",
                    "IsoCode": "GBP"
                }
            },
            "Price": {
                "Net": 27.69,
                "Gross": 33.23,
                "VatRate": {
                    "Reference": "GB-0.2000",
                    "CountryIsoCode": "GB",
                    "Type": "Standard",
                    "Rate": 0.2
                },
                "VatAmount": 5.54,
                "Currency": {
                    "Name": "Pound Sterling",
                    "IsoCode": "GBP"
                }
            },
            "Surcharges": [],
            "Legs": [
                {
                    "JourneyStage": 1,
                    "CarrierService": {
                        "Reference": "RMDTPS48HNAST",
                        "Name": "Tracked 48 Signed For",
                        "CarrierReference": "ROYAL_MAIL",
                        "CarrierName": null,
                        "IsDropOff": false,
                        "IsPickUp": false,
                        "IsTimed": false
                    },
                    "CarrierAccountReference": "RM1",
                    "DeliveryHub": null,
                    "CostItems": null,
                    "VolumetricParcelWeight": null,
                    "CollectionType": "NotApplicable"
                }
            ],
            "CarrierAccountOwner": null,
            "IsElectioService": false,
            "QuoteReference": "f63bd4ab-d519-4547-b361-aa3f00e9951a",
            "CreationDate": "2019-04-30T14:10:26.8551633+00:00",
            "ExpiryDate": "2019-05-01T00:00:00+01:00",
            "Requestor": "Andy Walton",
            "ConsignmentReference": "EC-000-05B-1CM",
            "ConsignmentReferenceProvidedByCustomer": "",
            "MpdCarrierServiceReference": "MPD_RMDTPS48HNAST"
        }
    ],
    "Message": null,
    "UnqualifiedServices": [
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "acceptanceTestCarrier_825d",
            "MpdCarrierServiceReference": "acceptanceTestCarrier_f8fe",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": false,
            "Rates": false,
            "MpdCarrierService": "Express With Signature Parcel",
            "MpdCarrierServiceReference": "MPD_ANPOS-00001",
            "ExclusionReason": "This service is not available for the selected collection/delivery dates."
        },
        {
            "Available": false,
            "Rates": true,
            "MpdCarrierService": "Next Day Monday - Saturday",
            "MpdCarrierServiceReference": "MPD_MNZIS-00001",
            "ExclusionReason": "This service is not available between the selected addresses."
        },
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "UPS EXPRESS (Delivery Confirmation Signature Required)",
            "MpdCarrierServiceReference": "EDC5_UPSHEXDCS",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "UPS EXPRESS (Saturday Delivery, Delivery Confirmation Signature Required)",
            "MpdCarrierServiceReference": "EDC5_UPSHEXSDDCS",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "UPS EXPRESS PLUS (Delivery Confirmation Signature Required)",
            "MpdCarrierServiceReference": "EDC5_UPSHEP",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "UPS SAVER (Delivery Confirmation Signature Required)",
            "MpdCarrierServiceReference": "EDC5_UPSHSADCS",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": true,
            "Rates": false,
            "MpdCarrierService": "UPS STANDARD (Delivery Confirmation Signature Required)",
            "MpdCarrierServiceReference": "EDC5_UPSHSTDCS",
            "ExclusionReason": "No cost and/or pricing data configured"
        },
        {
            "Available": false,
            "Rates": false,
            "MpdCarrierService": "wnDirect International Economy",
            "MpdCarrierServiceReference": "MPD_WNDECOM",
            "ExclusionReason": "This service is not available between the selected addresses. This service is not available for the given package dimensions/weight."
        }
    ]
}
```

```xml
<?xml version="1.0"?>
<QuoteResult xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Quotes">
    <QuoteRequestReference>e3a69d97-88c7-411d-a6ce-aa3f00ea7785</QuoteRequestReference>
    <Quotes>
        <Quote>
            <QuoteReference>cfa29a3b-724e-4ad7-ab9b-aa3f00ea78ad</QuoteReference>
            <Requestor>Andy Walton</Requestor>
            <CreationDate>2019-04-30T14:13:41.0520333+00:00</CreationDate>
            <ExpiryDate>2019-04-30T15:30:00.0000000+01:00</ExpiryDate>
            <ConsignmentReference>EC-000-05B-1CM</ConsignmentReference>
            <ConsignmentReferenceProvidedByCustomer />
            <MpdCarrierServiceReference>EDC5_UPSHSTDCS</MpdCarrierServiceReference>
            <MpdCarrierServiceSource>External</MpdCarrierServiceSource>
            <MpdCarrierService>UPS STANDARD (Delivery Confirmation Signature Required)</MpdCarrierService>
            <OriginAddress>
                <ShippingLocationReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_Electio</ShippingLocationReference>
                <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Third Floor</AddressLine1>
                <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Merchant Exchange</AddressLine2>
                <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Whitworth Street West</AddressLine3>
                <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
                <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">M1 5WG</Postcode>
                <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Name>United Kingdom</Name>
                    <IsoCode>
                        <TwoLetterCode>GB</TwoLetterCode>
                    </IsoCode>
                </Country>
                <SpecialInstructions xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
            </OriginAddress>
            <DestinationAddress>
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
            </DestinationAddress>
            <CollectionDate>2019-04-30T17:00:00</CollectionDate>
            <EarliestDeliveryDate>2019-05-01T00:00:00</EarliestDeliveryDate>
            <LatestDeliveryDate>2019-05-01T23:30:00</LatestDeliveryDate>
            <BasePrice>
                <Net>5.49</Net>
                <Gross>6.59</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200364298724954463</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200364298724954463</Rate>
                </VatRate>
                <VatAmount>1.10</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </BasePrice>
            <Price>
                <Net>5.49</Net>
                <Gross>6.59</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200364298724954463</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200364298724954463</Rate>
                </VatRate>
                <VatAmount>1.10</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </Price>
            <Surcharges />
            <Legs>
                <Leg>
                    <JourneyStage xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">1</JourneyStage>
                    <CarrierService xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                        <Reference>UPSHSTDCS</Reference>
                        <Name>UPS STANDARD (Delivery Confirmation Signature Required)</Name>
                        <CarrierReference>UPS</CarrierReference>
                        <IsDropOff>false</IsDropOff>
                        <IsPickUp>false</IsPickUp>
                        <IsTimed>false</IsTimed>
                    </CarrierService>
                    <CarrierAccountReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_UPS</CarrierAccountReference>
                    <CollectionType xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">NotApplicable</CollectionType>
                </Leg>
            </Legs>
            <IsElectioService>false</IsElectioService>
        </Quote>
        <Quote>
            <QuoteReference>25003dae-259a-4de9-96e4-aa3f00ea78ad</QuoteReference>
            <Requestor>Andy Walton</Requestor>
            <CreationDate>2019-04-30T14:13:41.0520333+00:00</CreationDate>
            <ExpiryDate>2019-04-30T15:30:00.0000000+01:00</ExpiryDate>
            <ConsignmentReference>EC-000-05B-1CM</ConsignmentReference>
            <ConsignmentReferenceProvidedByCustomer />
            <MpdCarrierServiceReference>EDC5_UPSHSADCS</MpdCarrierServiceReference>
            <MpdCarrierServiceSource>External</MpdCarrierServiceSource>
            <MpdCarrierService>UPS SAVER (Delivery Confirmation Signature Required)</MpdCarrierService>
            <OriginAddress>
                <ShippingLocationReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_Electio</ShippingLocationReference>
                <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Third Floor</AddressLine1>
                <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Merchant Exchange</AddressLine2>
                <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Whitworth Street West</AddressLine3>
                <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
                <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">M1 5WG</Postcode>
                <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Name>United Kingdom</Name>
                    <IsoCode>
                        <TwoLetterCode>GB</TwoLetterCode>
                    </IsoCode>
                </Country>
                <SpecialInstructions xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
            </OriginAddress>
            <DestinationAddress>
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
            </DestinationAddress>
            <CollectionDate>2019-04-30T17:00:00</CollectionDate>
            <EarliestDeliveryDate>2019-05-01T00:00:00</EarliestDeliveryDate>
            <LatestDeliveryDate>2019-05-01T12:00:00</LatestDeliveryDate>
            <BasePrice>
                <Net>9.49</Net>
                <Gross>11.39</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200210748155953635</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200210748155953635</Rate>
                </VatRate>
                <VatAmount>1.90</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </BasePrice>
            <Price>
                <Net>9.49</Net>
                <Gross>11.39</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200210748155953635</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200210748155953635</Rate>
                </VatRate>
                <VatAmount>1.90</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </Price>
            <Surcharges />
            <Legs>
                <Leg>
                    <JourneyStage xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">1</JourneyStage>
                    <CarrierService xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                        <Reference>UPSHSADCS</Reference>
                        <Name>UPS SAVER (Delivery Confirmation Signature Required)</Name>
                        <CarrierReference>UPS</CarrierReference>
                        <IsDropOff>false</IsDropOff>
                        <IsPickUp>false</IsPickUp>
                        <IsTimed>false</IsTimed>
                    </CarrierService>
                    <CarrierAccountReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_UPS</CarrierAccountReference>
                    <CollectionType xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">NotApplicable</CollectionType>
                </Leg>
            </Legs>
            <IsElectioService>false</IsElectioService>
        </Quote>
        <Quote>
            <QuoteReference>6086b4c7-55af-46fa-a306-aa3f00ea78ad</QuoteReference>
            <Requestor>Andy Walton</Requestor>
            <CreationDate>2019-04-30T14:13:41.0520333+00:00</CreationDate>
            <ExpiryDate>2019-04-30T15:30:00.0000000+01:00</ExpiryDate>
            <ConsignmentReference>EC-000-05B-1CM</ConsignmentReference>
            <ConsignmentReferenceProvidedByCustomer />
            <MpdCarrierServiceReference>EDC5_UPSHEXDCS</MpdCarrierServiceReference>
            <MpdCarrierServiceSource>External</MpdCarrierServiceSource>
            <MpdCarrierService>UPS EXPRESS (Delivery Confirmation Signature Required)</MpdCarrierService>
            <OriginAddress>
                <ShippingLocationReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_Electio</ShippingLocationReference>
                <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Third Floor</AddressLine1>
                <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Merchant Exchange</AddressLine2>
                <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Whitworth Street West</AddressLine3>
                <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
                <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">M1 5WG</Postcode>
                <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Name>United Kingdom</Name>
                    <IsoCode>
                        <TwoLetterCode>GB</TwoLetterCode>
                    </IsoCode>
                </Country>
                <SpecialInstructions xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
            </OriginAddress>
            <DestinationAddress>
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
            </DestinationAddress>
            <CollectionDate>2019-04-30T17:00:00</CollectionDate>
            <EarliestDeliveryDate>2019-05-01T00:00:00</EarliestDeliveryDate>
            <LatestDeliveryDate>2019-05-01T10:30:00</LatestDeliveryDate>
            <BasePrice>
                <Net>11.49</Net>
                <Gross>13.79</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200174064403829417</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200174064403829417</Rate>
                </VatRate>
                <VatAmount>2.30</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </BasePrice>
            <Price>
                <Net>11.49</Net>
                <Gross>13.79</Gross>
                <VatRate>
                    <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.200174064403829417</Reference>
                    <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                    <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                    <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.200174064403829417</Rate>
                </VatRate>
                <VatAmount>2.30</VatAmount>
                <Currency>
                    <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                    <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                </Currency>
            </Price>
            <Surcharges />
            <Legs>
                <Leg>
                    <JourneyStage xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">1</JourneyStage>
                    <CarrierService xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                        <Reference>UPSHEXDCS</Reference>
                        <Name>UPS EXPRESS (Delivery Confirmation Signature Required)</Name>
                        <CarrierReference>UPS</CarrierReference>
                        <IsDropOff>false</IsDropOff>
                        <IsPickUp>false</IsPickUp>
                        <IsTimed>false</IsTimed>
                    </CarrierService>
                    <CarrierAccountReference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">EDC5_UPS</CarrierAccountReference>
                    <CollectionType xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">NotApplicable</CollectionType>
                </Leg>
            </Legs>
            <IsElectioService>false</IsElectioService>
        </Quote>
    </Quotes>
    <UnqualifiedServices>
        <UnqualifiedService>
            <Available>true</Available>
            <Rates>false</Rates>
            <MpdCarrierService>acceptanceTestCarrier_825d</MpdCarrierService>
            <MpdCarrierServiceReference>acceptanceTestCarrier_f8fe</MpdCarrierServiceReference>
            <ExclusionReason>No cost and/or pricing data configured</ExclusionReason>
        </UnqualifiedService>
        <UnqualifiedService>
            <Available>false</Available>
            <Rates>false</Rates>
            <MpdCarrierService>Express With Signature Parcel</MpdCarrierService>
            <MpdCarrierServiceReference>MPD_ANPOS-00001</MpdCarrierServiceReference>
            <ExclusionReason>This service is not available for the selected collection/delivery dates.</ExclusionReason>
        </UnqualifiedService>
        <UnqualifiedService>
            <Available>false</Available>
            <Rates>true</Rates>
            <MpdCarrierService>Next Day Monday - Saturday</MpdCarrierService>
            <MpdCarrierServiceReference>MPD_MNZIS-00001</MpdCarrierServiceReference>
            <ExclusionReason>This service is not available between the selected addresses.</ExclusionReason>
        </UnqualifiedService>
        <UnqualifiedService>
            <Available>false</Available>
            <Rates>false</Rates>
            <MpdCarrierService>wnDirect International Economy</MpdCarrierService>
            <MpdCarrierServiceReference>MPD_WNDECOM</MpdCarrierServiceReference>
            <ExclusionReason>This service is not available between the selected addresses. This service is not available for the given package dimensions/weight.</ExclusionReason>
        </UnqualifiedService>
    </UnqualifiedServices>
</QuoteResult>
```