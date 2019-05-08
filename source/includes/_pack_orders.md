> Example Pack Order Request

```json
{
  "OrderReference": "EO-000-002-97F",
  "OrderReferenceProvidedByCustomer": "MyOrderRef001",
  "Packages": [
    {
      "Dimensions": {
        "Unit": "Cm",
        "Width": 15.4,
        "Length": 21.7,
        "Height": 10.0
      },
      "Weight": {
        "Value": 1.3,
        "Unit": "Kg"
      },
      "PackageSizeReference": "",
      "Items": [
        {
          "Sku": "SKU001",
          "Quantity": 1
        }
        {
          "Sku": "SKU002",
          "Quantity": 1
        }        
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackOrderRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.PackOrders">
  <OrderReference>EO-000-002-97F</OrderReference>
  <OrderReferenceProvidedByCustomer>MyOrderRef001</OrderReferenceProvidedByCustomer>
  <Packages>
    <Package>
      <Dimensions>
        <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Cm</Unit>
        <Width xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">15.4</Width>
        <Length xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">21.7</Length>
        <Height xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10</Height>
      </Dimensions>
      <Weight>
        <Value xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">1.3</Value>
        <Unit xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Kg</Unit>
      </Weight>
      <PackageSizeReference />
      <Items>
        <Item>
          <Sku>SKU001</Sku>
        </Item>
        <Item>
          <Sku>SKU002</Sku>
        </Item>
      </Items>
    </Package>
  </Packages>
</PackOrderRequest>
```

> Example Pack Order Response

```json
{
  "Results": [
    {
      "Result": "ConsignmentCreated",
      "Message": "Consignment EC-000-001-2AD created successfully",
      "Data": "EC-000-001-2AD",
      "ApiLinks": [
        {
          "Rel": "Consignment",
          "Href": "https://api.electioapp.com/consignments/EC-000-001-2AD"
        }
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackOrderResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.PackOrders">
  <Results>
    <PackOrderResult>
      <Result>ConsignmentCreated</Result>
      <Message>Consignment EC-000-001-2AD created successfully</Message>
      <Data>EC-000-001-2AD</Data>
      <ApiLinks>
        <ApiLink>
          <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Consignment</Rel>
          <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-001-2AD</Href>
        </ApiLink>
      </ApiLinks>
    </PackOrderResult>
  </Results>
</PackOrderResponse>
```

Once your order is created, you'll need to use the **[Pack Order](https://docs.electioapp.com/#/api/PackOrder)** endpoint to create consignments from it.

It's important to understand the difference between a consignment and an order when using **Pack Order**:

* An **order** is a collection of packages that is to be transported to the same destination and on behalf of the same customer
* A **consignment** is a collection of packages that is to be transported to the same destination, on behalf of the same customer, _from the same origin, and by the same carrier_.

This means that orders can contain items that will not ship from the same location, but consignments cannot. You can also use orders to manage items that will ship from the same location but at different times (for example, because one of the items a customer has purchased is out of stock).

The **Pack Order** endpoint enables you to take those items on a consignment that share an origin and are to be shipped together, and generate a shippable consignment for them. You will need to send one **Pack Order** request per consignment that you want to create from the order.

To make a **Pack Order** request, send a GET request to `https://api.electioapp.com/orders/{orderReference}/pack`. The body of the request can contain various properties that are used when creating the consignment, but at a minimum should contain the `{orderReference}` of the associated order and details of at least one `{item}` (and its accompanying `{package}`). The items and packages listed make up the consignment.

<aside class = "info">
  For example, suppose that you have created an order for a pair of shoes, a coat and a hat. The shoes are located in warehouse A, and the coat and hat in warehouse B. This would likely break down to:

  * Four items - The left shoe, the right shoe, the coat and the hat.
  * Three packages - One containing both shoes, one containing the coat and one containing the hat.
  * Two consignments - one for the shoes and another for the coat and hat.

  In this circumstance, you would need to run **Pack Order** twice - once sending the details of the shoes and once sending the details of the coat and hat. 
</aside>

Once PRO has received a **Pack Order** request, it creates the consignment and returns the relevant `{consignmentReference}`.

<aside class="note">
  For full reference information on the <strong>Pack Order</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/PackOrder">Pack Order</a></strong> page of the API reference.
</aside>

### Example

The example to the right shows a **Pack Order** request to create a consignment with one package containing two items from order _EO-000-002-97F_. PRO creates the consignment and responds with a `{consignmentReference}` of _EC-000-001-2AD_.

