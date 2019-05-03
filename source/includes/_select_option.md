> The Select Option Endpoint

```
POST https://api.electioapp.com/deliveryoptions/select/{deliveryOptionReference}
```

> Example Select Option Request
```
POST https://api.electioapp.com/deliveryoptions/select/EDO-000-6B2-6BV
```

> Example Select Option Response
```json
[
    {
        "Rel": "detail",
        "Href": "https://api.electioapp.com/consignments/EC-000-05B-0GT"
    },
    {
        "Rel": "label",
        "Href": "https://api.electioapp.com/labels/EC-000-05B-0GT"
    }
]
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfApiLink xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <ApiLink>
    <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
    <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-05B-0GT</Href>
  </ApiLink>
  <ApiLink>
    <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
    <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-05B-0GT</Href>
  </ApiLink>
</ArrayOfApiLink>
```

Once the customer has selected an available delivery option, you'll need to record their choice in PRO via the **[Select Option](https://docs.electioapp.com/#/api/SelectOption)** endpoint. The **Select Option** endpoint takes the `{Reference}` of the selected option as a path parameter.

Once it has received the selected `{Reference}`, PRO has all the information it need to create and allocate a consignment. The consignment details were passed as part of the original request to get options, and the `{Reference}` passed to the **Select Option** endpoint confirms the carrier service that PRO should allocate to.

As such, PRO creates and allocates a consignment with the selected details, and returns an array containing the `{consignmentReference}` for the newly-created consignment and a link to the labels for that consignment.

### Example

The example to the right shows a request to select a delivery option that has a `{Reference}` of _EDO-000-6B2-6BV_. PRO creates a consignment with a `{consignmentReference}` of _EC-000-05B-0GT_, which it then immediately allocates to the carrier service associated with delivery option _EDO-000-6B2-6BV_. PRO the responds with the relevant `{consignmentReference}` and label link, enabling the user to get labels for and manifest the consignment.