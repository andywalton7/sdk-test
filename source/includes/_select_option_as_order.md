> Example Select Delivery Option as an Order Request

```json
{
  "DeliveryOptions": [
    {
      "Reference": "EDO-000-AHQ-NRA",
      "OrderReferenceProvidedByCustomer": "MYORDEREF001",
      "MetaData": [
        {
          "KeyValue": "OrderReference",
          "StringValue": "10045634343"
        }
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<SelectOrderRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Orders">
  <DeliveryOptions>
    <SelectDeliveryOptionRequest>
      <Reference>EDO-000-AHQ-NRA</Reference>
      <OrderReferenceProvidedByCustomer>MYORDEREF001</OrderReferenceProvidedByCustomer>
      <MetaData>
        <MetaData>
          <KeyValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">OrderReference</KeyValue>
          <StringValue xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">10045634343</StringValue>
          <IntValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
          <DecimalValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
          <DateTimeValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
          <BoolValue xsi:nil="true" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common" />
        </MetaData>
      </MetaData>
    </SelectDeliveryOptionRequest>
  </DeliveryOptions>
</SelectOrderRequest>
```

> Example Select Delivery Option as an Order Response

```json
{
  "SelectOrderResults": [
    {
      "DeliveryOptionReference": "EDO-000-AHQ-NRA",
      "OrderReference": "EO-000-00J-Z6V",
      "Status": 201,
      "Message": null,
      "Links": [
        {
          "Rel": "Detail",
          "Href": "https://api.electioapp.com/orders/EO-000-00J-Z6V"
        }
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<SelectOrderResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Orders">
  <SelectOrderResults>
    <SelectOrderResult>
      <DeliveryOptionReference>EDO-000-AHQ-NRA</DeliveryOptionReference>
      <OrderReference>EO-000-00J-Z6V</OrderReference>
      <Status>201</Status>
      <Message>Delivery option EDO-000-AHQ-NRA selected successfully</Message>
      <Links>
        <ApiLink>
          <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Order</Rel>
          <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/orders/EO-000-00J-Z6V</Href>
        </ApiLink>
      </Links>
    </SelectOrderResult>
  </SelectOrderResults>
</SelectOrderResponse>
```