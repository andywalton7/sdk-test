---
title: PRO Call Flows
language_tabs:
  - json: JSON
  - xml: XML
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<section>

<h1 id="header">SortedPRO Call Flows.</h1>

Ready to get started with SortedPRO? This guide explains some common use cases for PRO's APIs, helping you to see what PRO can do for your business. 

We will cover:

* **[Creating and manifesting a consignment](#creating-and-manifesting-a-consignment)** 
   
   A simple flow to create a consignment, allocate it to a carrier service using criteria of your choosing, retrieve and print delivery labels, and confirm the delivery with the carrier. 

* **[Offering and using delivery options](#selecting-delivery-options)** 

   Used when you want to present delivery options to your customer at point of purchase. PRO creates and allocates consignments based on the options the customer selects.

* **[Offering and using pickup options](#selecting-pickup-options)**

   Similar to the delivery option flow, but used when offering delivery to a pickup/drop-off (PUDO) location rather than home delivery. 

* **[Creating a pack order flow from a PRO order](#creating-a-pack-order-flow-from-an-existing-order)**

   Used when you can't guarantee that all parts of a customer's order will be picked, packed and dispatched from the same place at the same time. PRO can generate multiple consignments from a single order where required.

* **[Using delivery options to create a pack order flow](#creating-a-pack-order-flow-from-delivery-options)**

   Used when you can't guarantee that all parts of a customer's order will be picked, packed and dispatched from the same place at the same time, and you want to present delivery options to your customer at point of purchase.

* **[Obtaining and selecting delivery quotes](#selecting-quotes)**

   Used to obtain a full list of potential delivery services for a consignment. Often used to validate a consignment's detail or, in customer service use cases, to enable an operator to get quotes for a customer manually and act on the customer's response.

<aside class="note">
  This guide is intended as a primer for PRO. If you're already familiar with the basics of PRO, or you just need reference info for PRO's APIs, see the <strong><a href="https://docs.electioapp.com/#/api">API reference</a></strong>.
</aside>

</section>

<section>

# Getting Started

<section>

## Authentication

> Example API Key

```
ocp-apim-subscription-key: [qwerrtyuiioop0987654321]
```

You will need to provide a valid API key in every API call you make to SortedPRO. Each PRO user is allocated a unique API key, which is generated when the user's account is created. To view your API key:

1. Log in to the PRO dashboard and select **Settings > Users & roles > User Accounts** to display the **User Accounts** page. A list of the user accounts that you have access to is displayed.
2. Click the **Edit User** button for your account to display your account details.
3. Click **Show API Key**. PRO prompts you to re-enter your UI password.
4. Enter your password and click **Retrieve API Key** to display your API key.

To use your API key, include it in an `ocp-apim-subscription-key` header when making calls to PRO. If you make an API call to PRO without including an API key, then PRO returns an error with a status code of _401 (Unauthorized)_.

</section>

<section>

## Specifying Request / Response Format

PRO's APIs support both JSON and XML content types. By default, PRO returns `application/json` data. As such, you must specify which content type you are sending for each API request. To do so, pass a `content-type` header with a value of `application/json`, `text/xml` or `application/xml` (as applicable) in your request. All other `content-type` values are invalid.

You can also specify the content type that you want PRO to use in API responses. To do so, pass an `accept` header with a value of `application/json`, `text/xml`, or `application/xml` in your request. If you don't pass an `accept` header then PRO responds with `application/json`.

</section>

</section>

<section>

# Creating and Manifesting a Consignment

> Step 1: Create Consignments endpoint
```
POST https://api.electioapp.com/consignments
```
> Step 2: Allocation endpoints
```
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithcheapestquote
PUT https://api.electioapp.com/allocation/{consignmentReference}/allocatewithservicegroup/{mpdCarrierServiceGroupReference}
PUT https://api.electioapp.com/allocation/allocate
PUT https://api.electioapp.com/allocation/allocatewithcarrierservice
PUT https://api.electioapp.com/allocation/allocateConsignmentsWithServiceFilters
```
> Step 3: Get Labels endpoint
```
GET https://api.electioapp.com/labels/{consignmentReference}
```
> Step 4: Manifest Consignments endpoint
```
PUT https://api.electioapp.com/consignments/manifest
```
Creating a new consignment, allocating it to a suitable carrier service, printing its delivery labels, and then adding it to that service's manifest is perhaps PRO's most basic use case. This call flow is useful if you want to keep your customer checkout journey simple, and you know that all your items will ship from the same physical location.

There are four steps to the flow:

1. **Create the consignment** - Use the **[Create Consignment](https://docs.electioapp.com/#/api/CreateConsignment)** endpoint to record the details of your new consignment.
2. **Allocate the consignment** - Use one of PRO's **[Allocation](https://docs.electioapp.com/#/api/AllocateConsignment)** endpoints to select the carrier service that your consignment will use. You can nominate a specific service or group of services, ask PRO to determine the best one to use from a pre-defined group of services, allocate based on pre-set allocation rules, or use filters to select the best service for an individual consignment.
3. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get the delivery label for your consignment.
4. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignment with the selected carrier. At this point, the consignment is ready to ship.

![alt text](source/images/create-manifest-flow.png)

This section gives more detail on each step of the flow, and provides worked examples.

<section>

## Step 1: Creating Consignments

!INCLUDE includes\_create_consignments.md

<section>

## Step 2: Allocating Consignments

!INCLUDE includes\_allocating.md

</section>

<section>

## Step 2a: Allocating by Cheapest Quote

!INCLUDE includes\_allocate_by_cheapest_quote.md

</section>

<section>

## Step 2b: Allocating from a Service Group

!INCLUDE includes\_allocate_with_service_group.md

</section>

<section>

## Step 2c: Allocating using Default Rules

!INCLUDE includes\_allocate_using_default_rules.md

</section>

<section>

## Step 2d: Allocating to a Specific Carrier Service

!INCLUDE includes\_allocate_with_carrier_service.md

</section>

<section>

## Step 2e: Allocating Using Service Filters

!INCLUDE includes\_allocate_with_service_filters.md

</section>

</section>

<section>

## Step 3: Getting Shipment Labels

!INCLUDE includes\_get_labels.md

</section>

<section>

## Step 4: Manifesting a Consignment

!INCLUDE includes\_manifest_consignments.md

### Next Steps

And we're done! Read on to learn how to allocate consignments based on options presented to the customer at point of purchase, and deal with orders that may require multiple consignments to fulfil. 

</section>

</section>

<section>

# Selecting Delivery Options

> Step 1: Delivery Options endpoint
```
POST https://api.electioapp.com/deliveryoptions
```

> Step 2: Select Option endpoint
```
POST https://api.electioapp.com/deliveryoptions/select/{deliveryOptionReference}
```

> Step 3: Get Labels endpoint
```
GET https://api.electioapp.com/labels/{consignmentReference}
```

> Step 4: Manifest Consignments endpoint
```
PUT https://api.electioapp.com/consignments/manifest
```

The **Select Delivery Options** flow enables you to provide delivery windows to your customer at point of purchase. When the customer selects their preferred option, PRO creates and allocates a consignment based on the details given.

There are four steps to the flow:

1. **Get delivery options** - Use the **[Delivery Options](https://docs.electioapp.com/#/api/DeliveryOptions)** endpoint to request a list of available delivery options for the (as yet uncreated) consignment that the customer's order will generate.
2. **Select delivery option** - Use the **[Select Option](https://docs.electioapp.com/#/api/SelectOption)** endpoint to tell PRO which option the customer selected. At this point, PRO has all the information it needs to create and allocate a consignment.
3. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get the delivery label for your consignment.
4. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignment with the selected carrier. At this point, the consignment is ready to ship.

![delivery-options](source/images/delivery-options.png)

This section gives more detail on each step of the flow, and provides worked examples. 

<section>

## Step 1: Getting Delivery Options

!INCLUDE includes\_getting_delivery_options.md

</section>

<section>

## Step 2: Selecting a Delivery Option

!INCLUDE includes\_select_option.md

</section>

<section>

## Step 3: Getting Labels

!INCLUDE includes\_get_labels.md

</section>

<section>

## Step 4: Manifesting the Consignment

!INCLUDE includes\_manifest_consignments.md

</section>

### Next Steps

The next section explains a similar call flow that enables you to offer pickup options (aka click-and-collect) rather than home delivery timeslots.

</section>

<section>

# Selecting Pickup Options

The **Select Pickup Options** flow is very similar to the **Select Delivery Options** flow covered in the previous section. Rather than enabling the customer to select options for direct delivery, the **Select Pickup Options** flow enables you to build click-and-collect functionality that lets your customers select a pickup location and timeslot for their consignment.

There are four steps to the flow:

1. **Get Pickup Options** - Use the **[Pickup Options](https://docs.electioapp.com/#/api/PickupOptions)** endpoint to request a list of available delivery locations and timeslots for the (as yet uncreated) consignment that the customer's order will generate.
2. **Select Delivery Option** - Use the **[Select Option](https://docs.electioapp.com/#/api/SelectOption)** endpoint to tell PRO which option the customer selected. At this point, PRO has all the information it needs to create and allocate a consignment.
3. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get the delivery label for your consignment.
4. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignment with the selected carrier. At this point, the consignment is ready to ship.

![pickup-options](source/images/pickup-options.png)

This section gives more detail on each step of the flow, and provides worked examples. 

<section>

## Step 1: Getting Pickup Options

!INCLUDE includes\_get_pickup_options.md

</section>

<section>

## Step 2: Selecting a Pickup Option

!INCLUDE includes\_select_option.md

</section>

<section>

## Step 3: Get Shipment Labels

!INCLUDE includes\_get_labels.md

</section>

<section>

## Step 4: Manifest the Consignment

!INCLUDE includes\_manifest_consignments.md

</section>

### Next Steps

Read on to learn how to use delivery options to fulfil multiple-consignment orders.

</section>

<section>

# Creating a Pack Order Flow From an Existing Order

Like the **Delivery Options > Pack Order** flow, the **Existing Order > Pack Order** flow enables you to manage customer orders with items that ship from different physical locations. In the **Existing Order > Pack Order** flow, the order is created in PRO first, rather than from delivery options. As such, this flow should be used when you don't need to offer the customer delivery timeslots at point of purchase.

There are five steps to the flow:

1. **Create Order** - Use the **[Create Order](https://docs.electioapp.com/#/api/CreateOrder)** endpoint to record the customer's order in PRO.
2. **Pack Order** - Use the **[Pack Order](https://docs.electioapp.com/#/api/PackOrder)** endpoint to create one or more consignments from the order.
3. **Allocate the consignments** - Use one of PRO's **[Allocation](https://docs.electioapp.com/#/api/AllocateConsignment)** endpoints to select the carrier service that your consignments will use. You can select a specific service or group of services, allocate based on pre-set allocation rules, or use filters to select the best service for an individual consignment.
4. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get delivery labels for your consignments.
5. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignments with their selected carriers. At this point, the consignments are ready to ship.

![order-pack-order-flow](source/images/order-pack-order-flow.png)

This section gives more detail on each step of the flow, and provides worked examples. 

<section>

## Step 1: Creating the Order

!INCLUDE includes\_create_orders.md

</section>

<section>

## Step 2: Packing the Order

!INCLUDE includes\_pack_orders.md

</section>

<section>

## Step 3: Allocating the Consignment

!INCLUDE includes\_allocating.md

<aside class="note">
   You'll need to allocate all of the consignments packed from your order. Bear in mind that <strong><a href="https://docs.electioapp.com/#/api/AllocateUsingDefaultRules">Allocate Using Default Rules</a></strong>, <strong><a href="https://docs.electioapp.com/#/api/AllocateWithCarrierService">Allocate With Carrier Service</a></strong>, and <strong><a href="https://docs.electioapp.com/#/api/AllocateWithServiceFilters">Allocate With Service Filters</a></strong> enable you to allocate multiple consignments at once, but you can only allocate one consignment at a time via <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignment">Allocate Consignment</a></strong> and <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup">Allocate Consignment With Service Group</a></strong>. If you allocate via <strong>Allocate Consignment</strong> and <strong>Allocate Consignment With Service Group</strong> you'll need to make one API call per consignment on the order.
</aside>

<section>

## Step 3a: Allocating by Cheapest Quote

!INCLUDE includes\_allocate_by_cheapest_quote.md

</section>

<section>

## Step 3b: Allocating to a Service Group

!INCLUDE includes\_allocate_with_service_group.md

</section>

<section>

## Step 3c: Allocating using Default Rules

!INCLUDE includes\_allocate_using_default_rules.md

</section>

<section>

## Step 3d: Allocating to a Specific Carrier Service

!INCLUDE includes\_allocate_with_carrier_service.md

</section>

<section>

## Step 3e: Allocating Using Service Filters

!INCLUDE includes\_allocate_with_service_filters.md

</section>

</section>

## Step 4: Getting Shipment Labels

!INCLUDE includes\_get_labels.md

<aside class="note">
   You'll need to make one <strong>Get Labels</strong> call per consignment on the order.
</aside>

</section>

<section>

## Step 5: Manifesting the Consignment

!INCLUDE includes\_manifest_consignments.md

<aside class="note">
   You'll need to manifest all the consignments on the order.
</aside>

</section>

### Next Steps

Finished! The next section explains a similar process, whereby the order is generated from delivery options that the customer selects rather than created up front.

</section>

<section>

# Using Delivery Options to Create a Pack Order Flow

Like the **Delivery Options** flow, the **Delivery Options > Pack Order** flow enables you to provide delivery timeslots to your customer at point of purchase. However, rather than generating a single consignment from the options selected, this flow generates orders, which can then be packed into multiple consignments. 

The **Delivery Options > Pack Order** flow is useful if you want to provide front-end delivery options but you cannot guarantee that the contents of your customer's online basket will map directly to a single consignment. For example, you might operate more than one warehouse and so may need to ship some products separately.

There are six steps to the flow:

1. **Get Delivery Options** - Use the **[Delivery Options](https://docs.electioapp.com/#/api/DeliveryOptions)** endpoint to request a list of available delivery options for the (as yet uncreated) consignment that the customer's purchase will generate.
2. **Select option as an order** -- Use the **[Select Delivery Option as an Order](https://docs.electioapp.com/#/api/SelectDeliveryOptionasanOrder)** to generate an order from the selected delivery option. 
3. **Pack the order** - Use the **[Pack Order](https://docs.electioapp.com/#/api/PackOrder)** endpoint to create one or more consignments from the order.
4. **Allocate the consignments** - Use one of PRO's **[Allocation](https://docs.electioapp.com/#/api/AllocateConsignment)** endpoints to select the carrier service that your consignments will use. You can select a specific service or group of services, allocate based on pre-set allocation rules, or use filters to select the best service for an individual consignment.
5. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get delivery labels for your consignments.
6. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignments with their selected carriers. At this point, the consignments are ready to ship.

![delivery-options-pack-order-flow](source/images/delivery-options-pack-order-flow.png)

This section gives more detail on each step of the flow, and provides worked examples. 

<section>

## Step 1: Getting Options

!INCLUDE includes\_getting_delivery_options.md

<aside class="note">
   Although this guide focuses on generating an order from the <strong>Delivery Options</strong> endpoint, you can also generate orders from pickup options via the <strong>Pickup Options</strong> endpoint. For more information on the <strong>Pickup Options</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/PickupOptions">Pickup Options</a></strong> page of the API reference.
</aside>

</section>

<section>

## Step 2: Selecting an Option as an Order

!INCLUDE includes\_select_option_as_order.md

</section>

<section>

## Step 3: Packing the Order

!INCLUDE includes\_pack_orders.md

</section>

<section>

## Step 4: Allocating the Consignment

!INCLUDE includes\_allocating.md

<aside class="note">
   You'll need to allocate all of the consignments packed from your order. Bear in mind that <strong><a href="https://docs.electioapp.com/#/api/AllocateUsingDefaultRules">Allocate Using Default Rules</a></strong>, <strong><a href="https://docs.electioapp.com/#/api/AllocateWithCarrierService">Allocate With Carrier Service</a></strong>, and <strong><a href="https://docs.electioapp.com/#/api/AllocateWithServiceFilters">Allocate With Service Filters</a></strong> enable you to allocate multiple consignments at once, but you can only allocate one consignment at a time via <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignment">Allocate Consignment</a></strong> and <strong><a href="https://docs.electioapp.com/#/api/AllocateConsignmentWithServiceGroup">Allocate Consignment With Service Group</a></strong>. If you allocate via <strong>Allocate Consignment</strong> and <strong>Allocate Consignment With Service Group</strong> you'll need to make one API call per consignment on the order.
</aside>

<section>

## Step 4a: Allocating by Cheapest Quote

!INCLUDE includes\_allocate_by_cheapest_quote.md

</section>

<section>

## Step 4b: Allocating to a Service Group

!INCLUDE includes\_allocate_with_service_group.md

</section>

<section>

## Step 4c: Allocating using Default Rules

!INCLUDE includes\_allocate_using_default_rules.md

</section>

<section>

## Step 4d: Allocating to a Specific Carrier Service

!INCLUDE includes\_allocate_with_carrier_service.md

</section>

<section>

## Step 4e: Allocating Using Service Filters

!INCLUDE includes\_allocate_with_service_filters.md

</section>

</section>

<section>

## Step 5: Getting Shipment Labels

!INCLUDE includes\_get_labels.md

<aside class="note">
   You'll need to make one <strong>Get Labels</strong> call per consignment on the order.
</aside>

</section>

<section>

## Step 6: Manifesting the Consignment

!INCLUDE includes\_manifest_consignments.md

<aside class="note">
   You'll need to manifest all the consignments on the order.
</aside>

</section>

### Next Steps

The final section explains how to set up a call flow that enables you to retrieve and select quotes manually.

</section>

<section>

# Selecting Quotes

The **Selecting Quotes** flow is intended as a back-end customer service integration to help you resolve delivery issues that require manual intervention. In this flow, a consignment is created and then allocated to a carrier service based on a specific quote for that consignment.

There are five steps to the flow:

1. **Create the consignment** - Use the **[Create Consignment](https://docs.electioapp.com/#/api/CreateConsignment)** endpoint to record the details of a new consignment.
2. **Get quotes for the consignment** - Use the **[Get Quotes by Consignment Reference](https://docs.electioapp.com/#/api/GetQuotesbyConsignmentReference)** endpoint to get delivery quotes for the consignment.
3. **Select a quote** - Use the **[Allocate With Quote](https://docs.electioapp.com/#/api/AllocateWithQuote)** endpoint to select one of the returned quotes.
4. **Get the consignment's labels** - Use the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint to get the delivery label for your consignment.
5. **Manifest the consignment** - Use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint to confirm the consignment with the selected carrier. At this point, the consignment is ready to ship.

![get-quotes](source/images/get-quotes.png)

This section gives more detail on each step of the flow, and provides worked examples. 

<section>

## Step 1: Creating a Consignment

!INCLUDE includes\_create_consignments.md

</section>

<section>

## Step 2: Getting Quotes

!INCLUDE includes\_get_quotes_by_con_ref.md

</section>

<section>

## Step 3: Selecting a Quote

!INCLUDE includes\_allocate_with_quote.md

</section>

## Step 4: Getting Labels

!INCLUDE includes\_get_labels.md

</section>

<section>

## Step 5: Manifesting a Consignment

!INCLUDE includes\_manifest_consignments.md

</section>

</section>

</section>
