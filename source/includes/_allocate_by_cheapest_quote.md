> Allocate Consignment endpoint
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithcheapestquote
```

To allocate a single consignment to the cheapest available carrier service, use the **[Allocate Consignment](https://docs.electioapp.com/#/api/AllocateConsignment)** endpoint. Once an **Allocate Consignment** request is received and validated, PRO checks for quotes to ship the consignment in question, and automatically allocates the consignment to the cheapest service. 

This endpoint takes a `{consignmentReference}` as a path parameter, and returns an Allocation Summary.

> Example Allocate Consignment Request
```
PUT https://api.electioapp.com/allocation/EC-000-05A-Z6S/allocatewithcheapestquote
```
### Example

The example to the right shows a request to allocate the consignment we created in the previous section (with a `{consignmentReference}` of _EC-000-05A-Z6S_) via the **Allocate Consignment** endpoint. 

<aside class="note">
  For full reference information on the <strong>Allocate Consignment</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignment">Allocate Consignment API Reference</a></strong>. 
</aside>