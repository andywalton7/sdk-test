> Allocate With Carrier Service Endpoint
```
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice
```

To allocate one or more consignments to a specific carrier service, use the **[Allocate With Carrier Service](https://docs.electioapp.com/#/api/AllocateWithCarrierService)** endpoint. 

The **Allocate With Carrier Service** request body can contain an array of one or more `{consignmentReference}`s to be allocated, and the `{MpdCarrierServiceReference}` of the carrier service that they should be allocated to. 

Once the request is received, SortedPRO attempts to allocate the consignments to the specified carrier service. It then returns an array of Allocation Summaries, one for each allocated consignment. 

<aside class="note">
  For full reference information on the <strong>Allocate With Carrier Service</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/AllocateWithCarrierService">Allocate With Carrier Service</a></strong> page of the API reference. 
</aside>

> Example Allocate With Carrier Service Request

```json
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice

{
  "MpdCarrierServiceReference": "Example-Carrier-Service",
  "ConsignmentReferences": [
    "EC-000-05A-Z6S",
    "EC-000-083-45D",
    "EC-000-A04-0DV"
  ]
}
```
```xml
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice

<?xml version="1.0" encoding="utf-8"?>
<AllocateConsignmentsWithCarrierServiceRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
  <ConsignmentReferences>
    <string>EC-000-05A-Z6S</string>
    <string>EC-000-083-45D</string>
    <string>EC-000-A04-0DV</string>
  </ConsignmentReferences>
  <MpdCarrierServiceReference>Example-Carrier-Service</MpdCarrierServiceReference>
</AllocateConsignmentsWithCarrierServiceRequest>
```

### Example

The example to the right shows a request to allocate three consignments to a carrier service with an `{MpdCarrierServiceReference}` of _Example-Carrier-Service_ .