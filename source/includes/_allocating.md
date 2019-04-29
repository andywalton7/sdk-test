> Allocation Endpoints
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithcheapestquote
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithservicegroup/{mpdCarrierServiceGroupReference}
PUT https://api.electioapp.com/allocation/allocate
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice
PUT https://api.electioapp.com/allocation/allocateConsignmentsWithServiceFilters
```

Once you've created your consignment, you'll need to allocate it to a carrier. PRO has multiple allocation endpoints, giving you the flexibility to allocate to carriers using whatever criteria suits you best. In this case you could allocate via:

* **[Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment)** - Allocates the consignment to the carrier offering the cheapest quote.
* **[Allocate Consignment With Service Group](https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup)** - Allocates the consignment to the cheapest carrier in the specified Carrier Service Group.
* **[Allocate Using Default Rules](https://docs.electioapp.com/#/api/AllocateUsingDefaultRules)** - Allocates the consignment using pre-configured default rules.
* **[Allocate With Carrier Service](https://docs.electioapp.com/#/api/AllocateWithCarrierService)** - Allocates the consignment to the specified carrier service.
* **[Allocate With Service Filters](https://docs.electioapp.com/#/api/AllocateWithServiceFilters)** - Allocates the consignment to the cheapest carrier service that matches the service filters provided in the request.

<aside class="info">
  |In the content of PRO, <strong>allocation</strong> is the process of selecting the carrier service that will take the consignment.
</aside>

Once you have allocated a consignment, its status changes to *Allocated*, enabling you to get shipment labels for it.

This section explains the circumstances in which you might choose to use each allocation endpoint, and gives worked examples.