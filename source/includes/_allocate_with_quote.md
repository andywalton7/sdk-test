> Allocate With Quote endpoint
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithquote/{quoteReference}
```
> Example Allocate With Quote Request
```json
PUT https://apisandbox.electioapp.com/allocation/EC-000-05B-1D9/allocatewithquote/112236d5-4460-492f-a6bd-aa3f00f62dfb
```
```xml
PUT https://api.electioapp.com/allocation/EC-000-05B-1D7/allocatewithquote/d0f05553-eed6-44aa-a11b-aa3f00f54784
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
                "Href": "https://apisandbox.electioapp.com/consignments/EC-000-05B-1D9"
            },
            {
                "Rel": "label",
                "Href": "https://apisandbox.electioapp.com/labels/EC-000-05B-1D9"
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
        <Message xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">Consignment EC-000-05B-1D7 has been successfully allocated with UPS STANDARD (Delivery Confirmation Signature Required) for shipping on 01/05/2019 17:00:00 +00:00</Message>
        <Data xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">EC-000-05B-1D7</Data>
        <ApiLinks xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Consignments">
            <ApiLink>
                <Rel xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">detail</Rel>
                <Href xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">https://apisandbox.electioapp.com/consignments/EC-000-05B-1D7</Href>
            </ApiLink>
            <ApiLink>
                <Rel xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">label</Rel>
                <Href xmlns="http://electioapp.com/schemas/v1/MPD.Electio.SDK.DataTypes.Common">https://apisandbox.electioapp.com/labels/EC-000-05B-1D7</Href>
            </ApiLink>
        </ApiLinks>
    </WithMessageOfString>
</ArrayOfWithMessageOfString>
```

To allocate an individual consignment based on a specific delivery quote from a carrier, use the **Allocate With Quote** endpoint.

<aside class="note">
  You can get quote details via PRO's Quotes API. For more information on PRO's quote endpoints (<a href="https://docs.electioapp.com/#/api/GetQuotes">Get Quotes</a>, <a href="https://docs.electioapp.com/#/api/GetQuotesbyConsignmentReference">Get Quotes by Consignment Reference</a> and <a href="https://docs.electioapp.com/#/api/GetServiceGroupQuotes">Get Service Group Quotes</a>), see the API reference.
</aside>

The **Allocate With Quote** endpoint takes the `{consignmentReference}` of the consignment you want to allocate and the `{quoteReference}` of a particular quote. Once the request is received PRO attempts to allocate the consignment to the carrier service specified in the quote, and returns an Allocation Summary.

### Example

The example to the right shows a request to allocate the consignment we created in the previous section (with a `{consignmentReference}` of _EC-000-087-01A_) to the carrier service associated with a quote that has the `{quoteReference}` _dummy-quote-ref_.