> The Select Option Endpoint

```
POST https://api.electioapp.com/deliveryoptions/select/{deliveryOptionReference}
```

> Example Select Option Request
```
POST https://apisandbox.electioapp.com/deliveryoptions/select/EDO-000-6B2-6BV
```

> Example Select Option Response
```json
[
    {
        "Rel": "detail",
        "Href": "https://apisandbox.electioapp.com/consignments/EC-000-05B-0GT"
    },
    {
        "Rel": "label",
        "Href": "https://apisandbox.electioapp.com/labels/EC-000-05B-0GT"
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