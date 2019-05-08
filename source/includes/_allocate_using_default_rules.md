> Allocate Using Default Rules endpoint
```
PUT https://api.electioapp.com/allocation/allocate
```
To allocate one or more consignments based on your organisation's custom allocation rules, use the **[Allocate Using Default Rules](https://docs.electioapp.com/#/api/AllocateUsingDefaultRules)** endpoint.

<aside class="info">
  PRO allocation rules enable you to place constraints - such as physical package size, consignment value, and geographical availability - against individual carrier services. You can configure them via the UI's <a href="https://www.electioapp.com/Configuration/EditCarrierService/acceptanceTestCarrier_f8fe"><strong>Manage Carrier Service Rules</strong></a> page. 
  
  For more information on configuring allocation rules, see the _Configure Allocation Rules_ section of the PRO Admin Portal User Guide.
</aside>

The **Allocate Using Default Rules** endpoint can be used to allocate multiple consignments simultaneously. The request body should contain an array of `{consignmentReference}`s to be allocated. 

Once the request is received, PRO takes each consignment in turn and allocates it to the cheapest eligible carrier, based on your default rules. It then returns an array of Allocation Summaries, one for each allocated consignment. 

<aside class="note">
  For full reference information on the <strong>Allocate Using Default Rules</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/AllocateUsingDefaultRules">Allocate Using Default Rules</a></strong> page of the API reference. 
</aside>

> Example Allocate Using Default Rules Request
```json
PUT https://api.electioapp.com/allocation/allocate

{
  "ConsignmentReferences": [
    "EC-000-05A-Z6S",
    "EC-000-083-45D",
    "EC-000-A04-0DV"
  ]
}
```
```xml
PUT https://api.electioapp.com/allocation/allocate

<?xml version="1.0" encoding="utf-8"?>
<AllocateConsignmentsRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
  <ConsignmentReferences>
    <string>EC-000-05A-Z6S</string>
    <string>EC-000-083-45D</string>
    <string>EC-000-A04-0DV</string>
  </ConsignmentReferences>
</AllocateConsignmentsRequest>
```

### Example

The example to the right shows a request to allocate three consignments, via default rules. 