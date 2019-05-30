> Allocate With Quote Endpoint
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithquote/{quoteReference}
```
> Example Allocate With Quote Request
```
PUT https://api.electioapp.com/allocation/EC-000-05B-1D9/allocatewithquote/112236d5-4460-492f-a6bd-aa3f00f62dfb
```
> Example Allocate With Quote Response
```json
[
    {
        "IsSuccess": true,
        "Message": "Consignment EC-000-05B-1D9 has been successfully allocated with UPS STANDARD (Delivery Confirmation Signature Required) for shipping on 01/05/2019 17:00:00 +00:00",
        "Data": "EC-000-05B-1D9",
        "ApiLinks": [
            {
                "Rel": "detail",
                "Href": "https://api.electioapp.com/consignments/EC-000-05B-1D9"
            },
            {
                "Rel": "label",
                "Href": "https://api.electioapp.com/labels/EC-000-05B-1D9"
            }
        ]
    }
]
```

```xml
<?xml version="1.0"?>
<ArrayOfWithMessageOfString xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <WithMessageOfString>
        <IsSuccess xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">true</IsSuccess>
        <Message xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">Consignment EC-000-05B-1D9 has been successfully allocated with UPS STANDARD (Delivery Confirmation Signature Required) for shipping on 01/05/2019 17:00:00 +00:00</Message>
        <Data xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">EC-000-05B-1D9</Data>
        <ApiLinks xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">
            <ApiLink>
                <Rel xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">detail</Rel>
                <Href xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-05B-1D9</Href>
            </ApiLink>
            <ApiLink>
                <Rel xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">label</Rel>
                <Href xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/labels/EC-000-05B-1D9</Href>
            </ApiLink>
        </ApiLinks>
    </WithMessageOfString>
</ArrayOfWithMessageOfString>
```

To allocate an individual consignment based on a specific delivery quote from a carrier, use the **[Allocate With Quote](https://docs.electioapp.com/#/api/AllocateWithQuote)** endpoint.

<aside class="note">
  You can get quote details via SortedPRO's Quotes API. For more information on PRO's quote endpoints (<strong><a href="https://docs.electioapp.com/#/api/GetQuotes">Get Quotes</a></strong>, <strong><a href="https://docs.electioapp.com/#/api/GetQuotesbyConsignmentReference">Get Quotes by Consignment Reference</a></strong>, and <strong><a href="https://docs.electioapp.com/#/api/GetServiceGroupQuotes">Get Service Group Quotes</a></strong>), see the API reference.
</aside>

The **Allocate With Quote** endpoint takes the `{consignmentReference}` of the consignment you want to allocate and the `{quoteReference}` of a particular quote. Once the request is received PRO attempts to allocate the consignment to the carrier service specified in the quote, and returns an Allocation Summary.

<aside class="note">
  For full reference information on the <strong>Allocate With Quote</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/AllocateWithQuote">Allocate With Quote</a></strong> page of the API reference.
</aside>

### Example

The example to the right shows a request to allocate a consignment with a `{consignmentReference}` of _EC-000-087-01A_ to the carrier service associated with a quote that has the `{quoteReference}` _dummy-quote-ref_.