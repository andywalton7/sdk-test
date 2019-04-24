<section>

## Allocating to a Quote

> Allocate With Quote endpoint
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithquote/{quoteReference}
```

To allocate an individual consignment based on a specific delivery quote from a carrier, use the **Allocate With Quote** endpoint. **(DOES IT DO ANY VALIDATION THAT THE QUOTE YOU FEED IT IS FOR THE CONSIGNMENT YOU FEED IT?)**

<aside class="note">
  You can get quote details via PRO's Quotes API. For more information on PRO's quote endpoints (<a href="https://docs.electioapp.com/#/api/GetQuotes">Get Quotes</a>, <a href="https://docs.electioapp.com/#/api/GetQuotesbyConsignmentReference">Get Quotes by Consignment Reference</a> and <a href="https://docs.electioapp.com/#/api/GetServiceGroupQuotes">Get Service Group Quotes</a>), see the API reference.
</aside>

The **Allocate With Quote** endpoint takes the `{consignmentReference}` of the consignment you want to allocate and the `{quoteReference}` of a particular quote. Once the request is received PRO attempts to allocate the consignment to the carrier service specified in the quote, and returns an Allocation Summary.

> Example Allocate With Quote Request
```
PUT https://api.electioapp.com/allocation/EC-000-087-01A/allocatewithquote/dummy-quote-ref
```

### Example

The example to the right shows a request to allocate the consignment we created in the previous section (with a `{consignmentReference}` of _EC-000-087-01A_) to the carrier service associated with a quote that has the `{quoteReference}` _dummy-quote-ref_.

</section>