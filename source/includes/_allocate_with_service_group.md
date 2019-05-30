> Allocate Consignment With Service Group Endpoint
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithservicegroup/{mpdCarrierServiceGroupReference}
```

To allocate a consignment to the cheapest carrier service in a particular carrier service group, use the **[Allocate Consignment With Service Group](https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup)** endpoint.  

<aside class="info">
  SortedPRO carrier service groups are pools of carrier services that you can allocate consignments to in specific situations. For example, you might create a carrier service group containing all available services that will accept high-value goods. 

  To configure carrier service groups, use the <strong><a href="https://www.electioapp.com/Configuration/CarrierServiceGroups">Configuration - Carrier Service Groups</a></strong> UI page. 
</aside>  

Allocating by service group can help you to avoid inadvertently allocating a consignment to an unsuitable service. For example, if your organisation was to receive an order for a particularly high-value consignment, you could use the **Allocate Consignment With Service Group** endpoint to allocate that consignment to one of the services in your high-value service group. This would remove the risk and inconvenience of allocating the consignment to a "standard" service, only to have it rejected by the carrier. 

The **Allocate Consignment With Service Group** endpoint takes the `{consignmentReference}` of the consignment you want to allocate and the `{mpdCarrierServiceGroupReference}` of the service group you want to allocate to as path parameters, and returns an Allocation Summary with details of the service that was allocated. 

The `{mpdCarrierServiceGroupReference}` is a unique identifier for each carrier service group. To find the `{mpdCarrierServiceGroupReference}` for a particular group, log in to the UI's **[Configuration - Carrier Service Groups](https://www.electioapp.com/Configuration/CarrierServiceGroups)** page and locate the tile for that group. The `{mpdCarrierServiceGroupReference}` is shown in the **Code** field.

<aside class="note">
  For full reference information on the <strong>Allocate Consignment With Service Group</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup">Allocate Consignment With Service Group</a></strong> page of the API reference. 
</aside>

> Example Allocate Consignment With Service Group Request
```
PUT https://api.electioapp.com/allocation/EC-000-05A-Z6S/allocatewithservicegroup/valuableGoods
```

### Example

The example to the right shows a request to allocate a consignment with a `{consignmentReference}` of _EC-000-05A-Z6S_ to a carrier service within a group named `valuableGoods`.