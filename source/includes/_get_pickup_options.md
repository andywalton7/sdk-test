> Example Pickup Options Request

```json
{
  "Distance": 1.0,
  "MaxResults": 10,
  "GuaranteedOnly": false,
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
      "ShippingLocationReference": "EDC5_SL1",
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
      "IsCached": false
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<PickupOptionsResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.DeliveryOptions">
  <Distance>10</Distance>
  <MaxResults>10</MaxResults>
  <Locations>
    <Location>
      <Name>Mr Banjo's Newsagents</Name>
      <ShopReference>REF000132</ShopReference>
      <Address>
        <CompanyName xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Mr Banjo's Newsagents</CompanyName>
        <AddressLine1 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">12 Whitecroft Road</AddressLine1>
        <AddressLine2 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
        <AddressLine3 xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
        <Town xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Shrewsbury</Town>
        <Region xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Shropshire</Region>
        <Postcode xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">SY3 7TJ</Postcode>
        <Country xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">
          <Name>Great Britain</Name>
          <IsoCode>
            <TwoLetterCode>GB</TwoLetterCode>
          </IsoCode>
        </Country>
      </Address>
      <Distance>5.2</Distance>
      <OpeningTimes>
        <Monday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT19H30M</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Monday>
        <Tuesday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT19H30M</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Tuesday>
        <Wednesday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT19H30M</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Wednesday>
        <Thursday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT19H30M</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Thursday>
        <Friday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT19H30M</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Friday>
        <Saturday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT11H</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT12H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Saturday>
        <Sunday>
          <OpeningTime>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT10H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT14H</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </OpeningTime>
        </Sunday>
      </OpeningTimes>
      <DeliveryOptions>
        <DeliveryOption>
          <Reference>EDO-000-076-R5G</Reference>
          <EstimatedDeliveryDate>
            <Date>2019-05-03T00:00:00.0000000+00:00</Date>
            <Guaranteed>false</Guaranteed>
          </EstimatedDeliveryDate>
          <DeliveryWindow>
            <Start xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT8H</Start>
            <End xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
            <UtcOffset xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
          </DeliveryWindow>
          <Carrier>Electio Carrier A</Carrier>
          <CarrierService>Electio Carrier A Super Service</CarrierService>
          <CarrierServiceReference>ECASS</CarrierServiceReference>
          <CarrierServiceTypes>
            <CarrierServiceType>Standard</CarrierServiceType>
          </CarrierServiceTypes>
          <Price>
            <Net xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Rates">6</Net>
            <Gross xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Rates">5</Gross>
            <TaxRate xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Rates">
              <Reference xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">GB_STANDARD</Reference>
              <CountryIsoCode xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
              <Type xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
              <Rate xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">0.2</Rate>
            </TaxRate>
            <TaxAmount xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Rates">1</TaxAmount>
            <Currency xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Rates">
              <IsoCode xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
            </Currency>
          </Price>
          <AllocationCutOff>2019-05-03T09:19:01.7261580+00:00</AllocationCutOff>
          <OperationalCutOff>2019-05-03T07:19:01.7261580+00:00</OperationalCutOff>
          <ServiceDirection>Outbound</ServiceDirection>
        </DeliveryOption>
      </DeliveryOptions>
      <Reservation>
        <IsReservationRequired>true</IsReservationRequired>
        <ExpiryDate>2019-05-03T00:00:00.0000000+00:00</ExpiryDate>
      </Reservation>
      <AdditionalInformation>
        <AdditionalInformation>
          <Key xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Parking</Key>
          <Value xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Parking available to the rear of the shop</Value>
        </AdditionalInformation>
      </AdditionalInformation>
    </Location>
  </Locations>
</PickupOptionsResponse>
```

> Example Pickup Options Response

```json
{
    "Distance": 1,
    "MaxResults": 10,
    "Locations": [
        {
            "Name": "I-Smart Communications",
            "ShopReference": "GB14002",
            "Address": {
                "AddressLine1": "41 Whitworth Street West",
                "AddressLine2": "",
                "AddressLine3": "The Lock Building",
                "Town": "Manchester",
                "Region": "",
                "Postcode": "M1 5BD",
                "Country": {
                    "Name": "United Kingdom",
                    "IsoCode": {
                        "TwoLetterCode": "GB",
                        "ThreeLetterCode": "GBR",
                        "NumericCode": "826"
                    }
                },
                "RegionCode": "",
                "LatLong": {
                    "Latitude": 53.474181,
                    "Longitude": -2.243738
                },
                "IsCached": false
            },
            "Distance": 0.15,
            "OpeningTimes": {
                "Monday": [
                    {
                        "Start": "11:00:00",
                        "End": "18:00:00",
                        "UtcOffset": "0:00"
                    }
                ],
                "Tuesday": [
                    {
                        "Start": "11:00:00",
                        "End": "18:00:00",
                        "UtcOffset": "0:00"
                    }
                ],
                "Wednesday": [
                    {
                        "Start": "11:00:00",
                        "End": "18:00:00",
                        "UtcOffset": "0:00"
                    }
                ],
                "Thursday": [
                    {
                        "Start": "11:00:00",
                        "End": "18:00:00",
                        "UtcOffset": "0:00"
                    }
                ],
                "Friday": [
                    {
                        "Start": "11:00:00",
                        "End": "18:00:00",
                        "UtcOffset": "0:00"
                    }
                ],
                "Saturday": [],
                "Sunday": []
            },
            "DeliveryOptions": [
                {
                    "Reference": "EDO-000-AHP-093",
                    "EstimatedDeliveryDate": {
                        "Date": "2019-05-20T00:00:00+00:00",
                        "Guaranteed": true,
                        "DayOfWeek": "Monday"
                    },
                    "DeliveryWindow": {
                        "Start": "07:30:00",
                        "End": "19:00:00",
                        "UtcOffset": "+01:00"
                    },
                    "Carrier": "DPD",
                    "CarrierService": "DPD Ship To Shop",
                    "CarrierServiceReference": "EDC5_DPDSS",
                    "Price": {
                        "Net": 5.99,
                        "Gross": 7.19,
                        "VatRate": {
                            "Reference": "GB-0.2000",
                            "CountryIsoCode": "GB",
                            "Type": "Standard",
                            "Rate": 0.2
                        },
                        "VatAmount": 1.2,
                        "Currency": {
                            "Name": "Pound Sterling",
                            "IsoCode": "GBP"
                        }
                    },
                    "AllocationCutOff": "2019-05-17T15:30:00+01:00",
                    "OperationalCutOff": "2019-05-17T15:00:00+01:00"
                },
                {
                    "Reference": "EDO-000-AHP-094",
                    "EstimatedDeliveryDate": {
                        "Date": "2019-05-20T00:00:00+00:00",
                        "Guaranteed": true,
                        "DayOfWeek": "Monday"
                    },
                    "DeliveryWindow": {
                        "Start": "07:30:00",
                        "End": "19:00:00",
                        "UtcOffset": "+01:00"
                    },
                    "Carrier": "DPD",
                    "CarrierService": "DPD Ship To Shop",
                    "CarrierServiceReference": "EDC5_DPDSS",
                    "Price": {
                        "Net": 5.99,
                        "Gross": 7.19,
                        "VatRate": {
                            "Reference": "GB-0.2000",
                            "CountryIsoCode": "GB",
                            "Type": "Standard",
                            "Rate": 0.2
                        },
                        "VatAmount": 1.2,
                        "Currency": {
                            "Name": "Pound Sterling",
                            "IsoCode": "GBP"
                        }
                    },
                    "AllocationCutOff": "2019-05-18T12:30:00+01:00",
                    "OperationalCutOff": "2019-05-18T12:00:00+01:00"
                },
                {
                    "Reference": "EDO-000-AHP-09G",
                    "EstimatedDeliveryDate": {
                        "Date": "2019-05-17T00:00:00+00:00",
                        "Guaranteed": true,
                        "DayOfWeek": "Friday"
                    },
                    "DeliveryWindow": {
                        "Start": "07:30:00",
                        "End": "19:00:00",
                        "UtcOffset": "+01:00"
                    },
                    "Carrier": "DPD",
                    "CarrierService": "DPD Ship To Shop",
                    "CarrierServiceReference": "EDC5_DPDSS",
                    "Price": {
                        "Net": 5.99,
                        "Gross": 7.19,
                        "VatRate": {
                            "Reference": "GB-0.2000",
                            "CountryIsoCode": "GB",
                            "Type": "Standard",
                            "Rate": 0.2
                        },
                        "VatAmount": 1.2,
                        "Currency": {
                            "Name": "Pound Sterling",
                            "IsoCode": "GBP"
                        }
                    },
                    "AllocationCutOff": "2019-05-16T15:30:00+01:00",
                    "OperationalCutOff": "2019-05-16T15:00:00+01:00"
                }
            ],
            "Reservation": {
                "IsReservationRequired": false,
                "ExpiryDate": null
            },
            "AdditionalInformation": [
                {
                    "Key": "Language",
                    "Value": "en"
                },
                {
                    "Key": "DisabledAccess",
                    "Value": "True"
                },
                {
                    "Key": "ParkingAvailable",
                    "Value": "True"
                },
                {
                    "Key": "OpenLate",
                    "Value": "True"
                },
                {
                    "Key": "OpenSaturday",
                    "Value": "False"
                },
                {
                    "Key": "OpenSunday",
                    "Value": "False"
                },
                {
                    "Key": "GeoServiceCodes",
                    "Value": ""
                },
                {
                    "Key": "ActiveStart",
                    "Value": "9/25/2018 12:00:00 AM"
                },
                {
                    "Key": "ActiveEnd",
                    "Value": ""
                },
                {
                    "Key": "DeliveryStart",
                    "Value": "5/22/2019 12:00:00 AM"
                },
                {
                    "Key": "DeliveryEnd",
                    "Value": "5/17/2019 12:00:00 AM"
                },
                {
                    "Key": "OpeningExceptions",
                    "Value": null
                },
                {
                    "Key": "LocationType",
                    "Value": null
                },
                {
                    "Key": "Category",
                    "Value": "Mobile Phone Shop,Non-Pharmacy"
                }
            ]
        }
    ],
    "NonGuaranteedLocation": null
}
```

```xml
<?xml version="1.0"?>
<PickupOptionsResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.DeliveryOptions">
    <Distance>1.0</Distance>
    <MaxResults>10</MaxResults>
    <Locations>
        <Location>
            <Name>I-Smart Communications</Name>
            <ShopReference>GB14002</ShopReference>
            <Address>
                <AddressLine1 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">41 Whitworth Street West</AddressLine1>
                <AddressLine2 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                <AddressLine3 xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">The Lock Building</AddressLine3>
                <Town xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Manchester</Town>
                <Region xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                <Postcode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">M1 5BD</Postcode>
                <Country xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Name>United Kingdom</Name>
                    <IsoCode>
                        <TwoLetterCode>GB</TwoLetterCode>
                    </IsoCode>
                </Country>
                <LatLong xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">
                    <Latitude>53.474181</Latitude>
                    <Longitude>-2.243738</Longitude>
                </LatLong>
            </Address>
            <Distance>0.15</Distance>
            <OpeningTimes>
                <Monday>
                    <OpeningTime>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT11H</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0:00</UtcOffset>
                    </OpeningTime>
                </Monday>
                <Tuesday>
                    <OpeningTime>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT11H</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0:00</UtcOffset>
                    </OpeningTime>
                </Tuesday>
                <Wednesday>
                    <OpeningTime>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT11H</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0:00</UtcOffset>
                    </OpeningTime>
                </Wednesday>
                <Thursday>
                    <OpeningTime>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT11H</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0:00</UtcOffset>
                    </OpeningTime>
                </Thursday>
                <Friday>
                    <OpeningTime>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT11H</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT18H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0:00</UtcOffset>
                    </OpeningTime>
                </Friday>
                <Saturday />
                <Sunday />
            </OpeningTimes>
            <DeliveryOptions>
                <DeliveryOption>
                    <Reference>EDO-000-AHN-ZR3</Reference>
                    <EstimatedDeliveryDate>
                        <Date>2019-05-20T00:00:00.0000000+00:00</Date>
                        <Guaranteed>true</Guaranteed>
                    </EstimatedDeliveryDate>
                    <DeliveryWindow>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT7H30M</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT19H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
                    </DeliveryWindow>
                    <Carrier>DPD</Carrier>
                    <CarrierService>DPD Ship To Shop</CarrierService>
                    <CarrierServiceReference>EDC5_DPDSS</CarrierServiceReference>
                    <Price>
                        <Net>5.99</Net>
                        <Gross>7.19</Gross>
                        <VatRate>
                            <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.2000</Reference>
                            <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                            <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                            <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.2000</Rate>
                        </VatRate>
                        <VatAmount>1.20</VatAmount>
                        <Currency>
                            <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                            <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                        </Currency>
                    </Price>
                    <AllocationCutOff>2019-05-17T15:30:00.0000000+01:00</AllocationCutOff>
                    <OperationalCutOff>2019-05-17T15:00:00.0000000+01:00</OperationalCutOff>
                </DeliveryOption>
                <DeliveryOption>
                    <Reference>EDO-000-AHN-ZR4</Reference>
                    <EstimatedDeliveryDate>
                        <Date>2019-05-20T00:00:00.0000000+00:00</Date>
                        <Guaranteed>true</Guaranteed>
                    </EstimatedDeliveryDate>
                    <DeliveryWindow>
                        <Start xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT7H30M</Start>
                        <End xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">PT19H</End>
                        <UtcOffset xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">+01:00</UtcOffset>
                    </DeliveryWindow>
                    <Carrier>DPD</Carrier>
                    <CarrierService>DPD Ship To Shop</CarrierService>
                    <CarrierServiceReference>EDC5_DPDSS</CarrierServiceReference>
                    <Price>
                        <Net>5.99</Net>
                        <Gross>7.19</Gross>
                        <VatRate>
                            <Reference xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB-0.2000</Reference>
                            <CountryIsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GB</CountryIsoCode>
                            <Type xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Standard</Type>
                            <Rate xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">0.2000</Rate>
                        </VatRate>
                        <VatAmount>1.20</VatAmount>
                        <Currency>
                            <Name xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Pound Sterling</Name>
                            <IsoCode xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GBP</IsoCode>
                        </Currency>
                    </Price>
                    <AllocationCutOff>2019-05-18T12:30:00.0000000+01:00</AllocationCutOff>
                    <OperationalCutOff>2019-05-18T12:00:00.0000000+01:00</OperationalCutOff>
                </DeliveryOption>
            </DeliveryOptions>
            <Reservation>
                <IsReservationRequired>false</IsReservationRequired>
                <ExpiryDate xsi:nil="true" />
            </Reservation>
            <AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Language</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">en</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">DisabledAccess</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">True</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">ParkingAvailable</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">True</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">OpenLate</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">True</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">OpenSaturday</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">False</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">OpenSunday</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">False</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">GeoServiceCodes</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">ActiveStart</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">9/25/2018 12:00:00 AM</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">ActiveEnd</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common" />
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">DeliveryStart</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">5/22/2019 12:00:00 AM</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">DeliveryEnd</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">5/17/2019 12:00:00 AM</Value>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">OpeningExceptions</Key>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">LocationType</Key>
                </AdditionalInformation>
                <AdditionalInformation>
                    <Key xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Category</Key>
                    <Value xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">Mobile Phone Shop,Non-Pharmacy</Value>
                </AdditionalInformation>
            </AdditionalInformation>
        </Location>
    </Locations>
</PickupOptionsResponse>
```