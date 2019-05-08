> Allocation Endpoints
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithcheapestquote
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithservicegroup/{mpdCarrierServiceGroupReference}
PUT https://api.electioapp.com/allocation/allocate
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice
PUT https://api.electioapp.com/allocation/allocateConsignmentsWithServiceFilters
```

Once you've created a consignment, you'll need to allocate it to a carrier. PRO has multiple allocation endpoints, giving you the flexibility to allocate to carriers using whatever criteria suits you best. In this case you could allocate via:

* **[Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment)** - Allocates the consignment to the carrier offering the cheapest quote.
* **[Allocate Consignment With Service Group](https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup)** - Allocates the consignment to the cheapest carrier in the specified Carrier Service Group.
* **[Allocate Using Default Rules](https://docs.electioapp.com/#/api/AllocateUsingDefaultRules)** - Allocates the consignment using pre-configured default rules.
* **[Allocate With Carrier Service](https://docs.electioapp.com/#/api/AllocateWithCarrierService)** - Allocates the consignment to the specified carrier service.
* **[Allocate With Service Filters](https://docs.electioapp.com/#/api/AllocateWithServiceFilters)** - Allocates the consignment to the cheapest carrier service that matches the service filters provided in the request.

<aside class="info">
  In the context of PRO, <strong>allocation</strong> is the process of selecting the carrier service that will take the consignment.
</aside>

Once you have allocated a consignment, its status changes to *Allocated*, enabling you to get shipment labels for it.

This section explains the circumstances in which you might choose to use each allocation endpoint, and gives worked examples.

### The Allocation Summary Response

> Example Allocation Summary Response
```json
[
    {
        "IsSuccess": true,
        "Message": "Consignment EC-000-05A-Z6S has been successfully allocated with Carrier X Next Day Super for shipping on 25/04/2019 16:00:00 +00:00",
        "Data": "EC-000-05A-Z6S",
        "ApiLinks": [
            {
                "Rel": "detail",
                "Href": "https://api.electioapp.com/consignments/EC-000-05A-Z6S"
            },
            {
                "Rel": "label",
                "Href": "https://api.electioapp.com/labels/EC-000-05A-Z6S"
            }
        ]
    }
]
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<AllocationSummary xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
  <StatusCode>200</StatusCode>
  <ApiLinks>
    <ApiLink>
      <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
      <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-05A-Z6S</Href>
    </ApiLink>
    <ApiLink>
      <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Label</Rel>
      <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/labels/EC-000-05A-Z6S</Href>
    </ApiLink>
  </ApiLinks>
  <Description>Consignment EC-000-05A-Z6S allocated with Carrier X Next Day Super successfully.</Description>
  <ConsignmentLegs>
    <ConsignmentLeg>
      <Leg>0</Leg>
      <TrackingReferences>
        <string>TRK00009823</string>
      </TrackingReferences>
      <CarrierReference>CARRIER_X</CarrierReference>
      <CarrierName>Carrier X</CarrierName>
    </ConsignmentLeg>
  </ConsignmentLegs>
  <CarrierReference>CARRIER_X</CarrierReference>
  <CarrierName>Carrier X</CarrierName>
  <CarrierServiceReference>CX_NDS</CarrierServiceReference>
  <CarrierServiceName>Next Day Super</CarrierServiceName>
</AllocationSummary>
```

All allocation endpoints return an Allocation Summary, either singularly or (where multiple consignments have been allocated at once) in an array. The Allocation Summary contains links to the consignment resource that was allocated and a summary of the carrier service that the consignment was allocated to.

In the example to the right, a consignment with a `{consignmentReference}` of _EC-000-05A-Z6S_ has been allocated to a (dummy) carrier service called _Carrier X Next Day Super_.