---
title: REACT API Reference
language_tabs:
  - ruby: Ruby
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v3.6.6 -->

<section>
<h1 id="react-api-reference">REACT API Reference v1.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Welcome to the REACT API reference. For more information on integrating with REACT, see the [integration guide](https://docs.sorted.com/react/registering-shipments/). 

Base URLs:

* <a href="https://react-api-qa.sorted.com/react/shipments">https://react-api-qa.sorted.com/react/shipments</a>

</section>

<section>

# Authentication

* API Key (x-api-key)
    - Parameter Name: **x-api-key**, in: header. To query any of REACT's APIs, you’ll need an API key. You can create one from the **Settings > API Keys** tab on the REACT Dashboard. To use your key, add it in an `x-api-key` header to any reqests you make.

</section>

<section>
<h1 id="react-api-reference-shipments-api">Shipments API</h1>

Enables you to register shipments for tracking in REACT, and to manage your shipments once they're registered.

<a href="https://docs.sorted.com/react/">More information on the Shipment API</a>

<section>

## Register Shipments

<a id="opIdPost"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://react-api-qa.sorted.com/react/shipments/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://react-api-qa.sorted.com/react/shipments/', params={

}, headers = headers)

print r.json()

```

`POST /`

Register one or more shipments for tracking in Sorted.REACT.

> Body parameter

```json
{
  "shipments": [
    {
      "tracking_references": "QWERTYUIOP",
      "custom_references": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "carrier": "string",
      "carrier_service": "string",
      "shipped_date": "2019-04-08T14:05:06Z",
      "order_date": "2019-04-08T14:05:06Z",
      "promised_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "expected_delivery_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "addresses": [
        {
          "address_type": "not_specified",
          "reference": "string",
          "property_number": "string",
          "property_name": "string",
          "address_line1": "string",
          "address_line2": "string",
          "address_line3": "string",
          "locality": "string",
          "region": "string",
          "postal_code": "string",
          "country_iso_code": "string",
          "lat_long": {
            "latitude": 0,
            "longitude": 0
          },
          "external_references": {
            "type": "string",
            "value": "string"
          }
        }
      ],
      "consumer": {
        "reference": "string",
        "email": "string",
        "phone": "string",
        "mobile_phone": "string",
        "first_name": "string",
        "last_name": "string",
        "middle_name": "string",
        "title": "string"
      },
      "metadata": [
        {
          "key": "string",
          "value": "string",
          "type": "string"
        }
      ],
      "retailer": "string",
      "shipment_type": "delivery"
    }
  ]
}
```

<section>
<h3 id="register-shipments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RegisterShipmentRequest](#schemaregistershipmentrequest)|false|none|

</section>

> Example responses

> Success

```json
{
  "id": "sp_18446744073709551615",
  "message": "Shipment record 'sp_18446744073709551615' with tracking reference ['TRK098JKH54ADD'] registered successfully.",
  "tracking_references": [
    "TRK098JKH54ADD"
  ],
  "tags": [
    "BRAND_X",
    "Dewsbury_Hub",
    "Outerwear",
    "JAN_CAMPAIGN"
  ],
  "_links": [
    {
      "href": "https://api.sorted.com/react/shipment/sp_18446744073709551615",
      "rel": "self"
    }
  ]
}
```

<section>
<h3 id="register-shipments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|None|

<h3 id="register-shipments-responseschema">Response Schema</h3>

</section>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
x-api-key
</aside>

</section>

<section>

## Get Shipment

<a id="opIdSearchGet"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://react-api-qa.sorted.com/react/shipments/search',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://react-api-qa.sorted.com/react/shipments/search', params={

}, headers = headers)

print r.json()

```

`GET /search`

Returns shipments matching the provided query string parameters.

<section>
<h3 id="get-shipment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tracking_references|query|array[string]|false|none|
|custom_references|query|array[string]|false|none|
|page|query|integer(int32)|false|none|

</section>

> Example responses

> A shipment object was returned successfully

```json
{
  "Shipment": {
    "properties": {
      "tracking_references": {
        "description": "The carrier's reference for this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "custom_references": {
        "description": "A list of your own custom references for this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "tags": {
        "description": "An optional list of tags to apply to this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "carrier": {
        "description": "The name of the carrier of this shipment.",
        "type": "string"
      },
      "carrier_service": {
        "description": "The name of the carrier service of this shipment.",
        "type": "string"
      },
      "shipped_date": {
        "description": "The date on which the shipment was (or will be) shipped.",
        "format": "date-time",
        "type": "string"
      },
      "order_date": {
        "description": "The date on which the order was placed.",
        "format": "date-time",
        "type": "string"
      },
      "promised_date": {
        "type": "object",
        "properties": {
          "start": {
            "format": "date-time",
            "type": "string"
          },
          "end": {
            "format": "date-time",
            "type": "string"
          }
        }
      },
      "expected_delivery_date": {
        "type": "object",
        "properties": {
          "start": {
            "format": "date-time",
            "type": "string"
          },
          "end": {
            "format": "date-time",
            "type": "string"
          }
        }
      },
      "addresses": {
        "description": "The addresses relevant to a shipment. Each address includes a \"Type\" property indicating the type of address, should include only 1 address of each type (e.g. 1 origin and 1 destination).",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "object",
          "properties": {
            "address_type": {
              "enum": [
                "not_specified",
                "origin",
                "destination",
                "return",
                "billing",
                "hub",
                "alternative_delivery",
                "other"
              ],
              "type": "string"
            },
            "reference": {
              "type": "string"
            },
            "property_number": {
              "type": "string"
            },
            "property_name": {
              "type": "string"
            },
            "address_line1": {
              "type": "string"
            },
            "address_line2": {
              "type": "string"
            },
            "address_line3": {
              "type": "string"
            },
            "locality": {
              "type": "string"
            },
            "region": {
              "type": "string"
            },
            "postal_code": {
              "type": "string"
            },
            "country_iso_code": {
              "type": "string"
            },
            "lat_long": {
              "type": "object",
              "properties": {
                "latitude": {
                  "format": "double",
                  "type": "number"
                },
                "longitude": {
                  "format": "double",
                  "type": "number"
                }
              }
            },
            "external_references": {
              "type": "object",
              "properties": {
                "type": {
                  "type": "string"
                },
                "value": {
                  "type": "string"
                }
              }
            }
          }
        }
      },
      "consumer": {
        "type": "object",
        "properties": {
          "reference": {
            "type": "string"
          },
          "email": {
            "type": "string"
          },
          "phone": {
            "type": "string"
          },
          "mobile_phone": {
            "type": "string"
          },
          "first_name": {
            "type": "string"
          },
          "last_name": {
            "type": "string"
          },
          "middle_name": {
            "type": "string"
          },
          "title": {
            "type": "string"
          }
        }
      },
      "metadata": {
        "description": "Optional metadata about this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "object",
          "properties": {
            "key": {
              "type": "string"
            },
            "value": {
              "type": "string"
            },
            "type": {
              "enum": [
                "string",
                "datetime",
                "datetimeoffset",
                "boolean",
                "integer",
                "decimal",
                "url"
              ],
              "type": "string"
            }
          }
        }
      },
      "retailer": {
        "description": "An identifier for the retailer for this shipment.",
        "type": "string"
      },
      "shipment_type": {
        "description": "A property indicating the type of shipment, e.g. \"delivery\", \"pick_up\", \"drop_off\".",
        "enum": [
          "delivery",
          "return",
          "pick_up",
          "drop_off",
          "drop_off_pick_up",
          "return_drop_off"
        ],
        "type": "string"
      }
    }
  }
}
```

<section>
<h3 id="get-shipment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A shipment object was returned successfully|None|

<h3 id="get-shipment-responseschema">Response Schema</h3>

</section>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
x-api-key
</aside>

</section>

<section>

## Get Shipment by Shipment ID

<a id="opIdByIdGet"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://react-api-qa.sorted.com/react/shipments/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://react-api-qa.sorted.com/react/shipments/{id}', params={

}, headers = headers)

print r.json()

```

`GET /{id}`

Retrieve the details of the specified shipment.

<section>
<h3 id="get-shipment-by-shipment-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

</section>

> Example responses

> A shipment object was returned successfully

```json
{
  "Shipment": {
    "properties": {
      "tracking_references": {
        "description": "The carrier's reference for this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "custom_references": {
        "description": "A list of your own custom references for this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "tags": {
        "description": "An optional list of tags to apply to this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "string"
        }
      },
      "carrier": {
        "description": "The name of the carrier of this shipment.",
        "type": "string"
      },
      "carrier_service": {
        "description": "The name of the carrier service of this shipment.",
        "type": "string"
      },
      "shipped_date": {
        "description": "The date on which the shipment was (or will be) shipped.",
        "format": "date-time",
        "type": "string"
      },
      "order_date": {
        "description": "The date on which the order was placed.",
        "format": "date-time",
        "type": "string"
      },
      "promised_date": {
        "type": "object",
        "properties": {
          "start": {
            "format": "date-time",
            "type": "string"
          },
          "end": {
            "format": "date-time",
            "type": "string"
          }
        }
      },
      "expected_delivery_date": {
        "type": "object",
        "properties": {
          "start": {
            "format": "date-time",
            "type": "string"
          },
          "end": {
            "format": "date-time",
            "type": "string"
          }
        }
      },
      "addresses": {
        "description": "The addresses relevant to a shipment. Each address includes a \"Type\" property indicating the type of address, should include only 1 address of each type (e.g. 1 origin and 1 destination).",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "object",
          "properties": {
            "address_type": {
              "enum": [
                "not_specified",
                "origin",
                "destination",
                "return",
                "billing",
                "hub",
                "alternative_delivery",
                "other"
              ],
              "type": "string"
            },
            "reference": {
              "type": "string"
            },
            "property_number": {
              "type": "string"
            },
            "property_name": {
              "type": "string"
            },
            "address_line1": {
              "type": "string"
            },
            "address_line2": {
              "type": "string"
            },
            "address_line3": {
              "type": "string"
            },
            "locality": {
              "type": "string"
            },
            "region": {
              "type": "string"
            },
            "postal_code": {
              "type": "string"
            },
            "country_iso_code": {
              "type": "string"
            },
            "lat_long": {
              "type": "object",
              "properties": {
                "latitude": {
                  "format": "double",
                  "type": "number"
                },
                "longitude": {
                  "format": "double",
                  "type": "number"
                }
              }
            },
            "external_references": {
              "type": "object",
              "properties": {
                "type": {
                  "type": "string"
                },
                "value": {
                  "type": "string"
                }
              }
            }
          }
        }
      },
      "consumer": {
        "type": "object",
        "properties": {
          "reference": {
            "type": "string"
          },
          "email": {
            "type": "string"
          },
          "phone": {
            "type": "string"
          },
          "mobile_phone": {
            "type": "string"
          },
          "first_name": {
            "type": "string"
          },
          "last_name": {
            "type": "string"
          },
          "middle_name": {
            "type": "string"
          },
          "title": {
            "type": "string"
          }
        }
      },
      "metadata": {
        "description": "Optional metadata about this shipment.",
        "uniqueItems": false,
        "type": "array",
        "items": {
          "type": "object",
          "properties": {
            "key": {
              "type": "string"
            },
            "value": {
              "type": "string"
            },
            "type": {
              "enum": [
                "string",
                "datetime",
                "datetimeoffset",
                "boolean",
                "integer",
                "decimal",
                "url"
              ],
              "type": "string"
            }
          }
        }
      },
      "retailer": {
        "description": "An identifier for the retailer for this shipment.",
        "type": "string"
      },
      "shipment_type": {
        "description": "A property indicating the type of shipment, e.g. \"delivery\", \"pick_up\", \"drop_off\".",
        "enum": [
          "delivery",
          "return",
          "pick_up",
          "drop_off",
          "drop_off_pick_up",
          "return_drop_off"
        ],
        "type": "string"
      }
    }
  }
}
```

<section>
<h3 id="get-shipment-by-shipment-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A shipment object was returned successfully|None|

<h3 id="get-shipment-by-shipment-id-responseschema">Response Schema</h3>

</section>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
x-api-key
</aside>

</section>

<section>

## Update Shipment

<a id="opIdByIdPut"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.put 'https://react-api-qa.sorted.com/react/shipments/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.put('https://react-api-qa.sorted.com/react/shipments/{id}', params={

}, headers = headers)

print r.json()

```

`PUT /{id}`

Update the details of a shipment.

> Body parameter

```json
{
  "shipments": [
    {
      "tracking_references": "QWERTYUIOP",
      "custom_references": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "carrier": "string",
      "carrier_service": "string",
      "shipped_date": "2019-04-08T14:05:06Z",
      "order_date": "2019-04-08T14:05:06Z",
      "promised_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "expected_delivery_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "addresses": [
        {
          "address_type": "not_specified",
          "reference": "string",
          "property_number": "string",
          "property_name": "string",
          "address_line1": "string",
          "address_line2": "string",
          "address_line3": "string",
          "locality": "string",
          "region": "string",
          "postal_code": "string",
          "country_iso_code": "string",
          "lat_long": {
            "latitude": 0,
            "longitude": 0
          },
          "external_references": {
            "type": "string",
            "value": "string"
          }
        }
      ],
      "consumer": {
        "reference": "string",
        "email": "string",
        "phone": "string",
        "mobile_phone": "string",
        "first_name": "string",
        "last_name": "string",
        "middle_name": "string",
        "title": "string"
      },
      "metadata": [
        {
          "key": "string",
          "value": "string",
          "type": "string"
        }
      ],
      "retailer": "string",
      "shipment_type": "delivery"
    }
  ]
}
```

<section>
<h3 id="update-shipment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[RegisterShipmentRequest](#schemaregistershipmentrequest)|false|none|

</section>

> Example responses

> Success

```json
{
  "id": "sp_18446744073709551615",
  "message": "Shipment record 'sp_18446744073709551615' with tracking reference ['TRK098JKH54ADD'] updated successfully.",
  "tracking_references": [
    "TRK098JKH54ADD"
  ],
  "tags": [
    "BRAND_X",
    "Dewsbury_Hub",
    "Outerwear",
    "JAN_CAMPAIGN"
  ],
  "_links": [
    {
      "href": "https://api.sorted.com/react/shipment/sp_18446744073709551615",
      "rel": "self"
    }
  ]
}
```

<section>
<h3 id="update-shipment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|None|

<h3 id="update-shipment-responseschema">Response Schema</h3>

</section>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
x-api-key
</aside>

</section>

<section>

## Delete Shipment

<a id="opIdByIdDelete"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.delete 'https://react-api-qa.sorted.com/react/shipments/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.delete('https://react-api-qa.sorted.com/react/shipments/{id}', params={

}, headers = headers)

print r.json()

```

`DELETE /{id}`

Delete the specified shipment.

<section>
<h3 id="delete-shipment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

</section>

> Example responses

> Success

```json
{
  "id": "sp_18446744073709551615",
  "message": "Shipment record 'sp_18446744073709551615' with tracking reference ['TRK098JKH54ADD'] deleted successfully.",
  "tracking_references": [
    "TRK098JKH54ADD"
  ]
}
```

<section>
<h3 id="delete-shipment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|None|

<h3 id="delete-shipment-responseschema">Response Schema</h3>

</section>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
x-api-key
</aside>

</section>

</section>

<section>

# Schemas

<section>
<h2 id="tocS_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Shipment">Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Shipment</h2>
<!-- backwards compatibility -->
<a id="schemasorted.react.shipment.api.datacontracts.internal.inbound.shipment"></a>
<a id="schema_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Shipment"></a>
<a id="tocSsorted.react.shipment.api.datacontracts.internal.inbound.shipment"></a>
<a id="tocssorted.react.shipment.api.datacontracts.internal.inbound.shipment"></a>

```json
{
  "carrier": "string",
  "carrier_id": "string",
  "carrier_service_reference": "string",
  "shipped_date": "2019-04-08T14:05:06Z",
  "order_date": "2019-04-08T14:05:06Z",
  "promised_date": {
    "start": "2019-04-08T14:05:06Z",
    "end": "2019-04-08T14:05:06Z"
  },
  "expected_delivery_date": {
    "start": "2019-04-08T14:05:06Z",
    "end": "2019-04-08T14:05:06Z"
  },
  "addresses": [
    {
      "address_type": "not_specified",
      "reference": "string",
      "property_number": "string",
      "property_name": "string",
      "address_line1": "string",
      "address_line2": "string",
      "address_line3": "string",
      "locality": "string",
      "region": "string",
      "postal_code": "string",
      "country_iso_code": "string",
      "lat_long": {
        "latitude": 0,
        "longitude": 0
      },
      "external_references": {
        "type": "string",
        "value": "string"
      }
    }
  ],
  "metadata": [
    {
      "key": "string",
      "value": "string",
      "type": "string"
    }
  ],
  "shipment_type": "delivery",
  "shipment_level": 0,
  "delivered_date": "2019-04-08T14:05:06Z",
  "leg_number": 0,
  "lateness": {
    "is_late": true
  },
  "last_tracked": "2019-04-08T14:05:06Z",
  "customer_id": "string",
  "correlation_id": "string",
  "tracking_event_timestamp": "2019-04-08T14:05:06Z",
  "shipment_state": {
    "state": "unknown"
  }
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|carrier|string|false|none|none|
|carrier_id|string|false|none|none|
|carrier_service_reference|string|false|none|none|
|shipped_date|string(date-time)|false|none|none|
|order_date|string(date-time)|false|none|none|
|promised_date|[PromisedDate](#schemapromiseddate)|false|none|none|
|expected_delivery_date|[ExpectedDeliveryDate](#schemaexpecteddeliverydate)|false|none|none|
|addresses|[[Address](#schemaaddress)]|false|none|none|
|metadata|[[Metadata](#schemametadata)]|false|none|none|
|shipment_type|string|false|none|none|
|shipment_level|integer(int32)|false|none|none|
|delivered_date|string(date-time)|false|none|none|
|leg_number|integer(int32)|false|none|none|
|lateness|[Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Lateness](#schemasorted.react.shipment.api.datacontracts.internal.inbound.lateness)|false|none|none|
|last_tracked|string(date-time)|false|none|none|
|customer_id|string|false|none|none|
|correlation_id|string(uuid)|false|none|none|
|tracking_event_timestamp|string(date-time)|false|none|none|
|shipment_state|[Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.ShipmentState](#schemasorted.react.shipment.api.datacontracts.internal.inbound.shipmentstate)|false|none|none|

<section>

#### Enumerated Values

|Property|Value|
|---|---|
|shipment_type|delivery|
|shipment_type|return|
|shipment_type|pick_up|
|shipment_type|drop_off|
|shipment_type|drop_off_pick_up|
|shipment_type|return_drop_off|

</section>

</section>
</section>

<section>
<h2 id="tocS_PromisedDate">PromisedDate</h2>
<!-- backwards compatibility -->
<a id="schemapromiseddate"></a>
<a id="schema_PromisedDate"></a>
<a id="tocSpromiseddate"></a>
<a id="tocspromiseddate"></a>

```json
{
  "start": "2019-04-08T14:05:06Z",
  "end": "2019-04-08T14:05:06Z"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|string(date-time)|false|none|none|
|end|string(date-time)|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_ExpectedDeliveryDate">ExpectedDeliveryDate</h2>
<!-- backwards compatibility -->
<a id="schemaexpecteddeliverydate"></a>
<a id="schema_ExpectedDeliveryDate"></a>
<a id="tocSexpecteddeliverydate"></a>
<a id="tocsexpecteddeliverydate"></a>

```json
{
  "start": "2019-04-08T14:05:06Z",
  "end": "2019-04-08T14:05:06Z"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|start|string(date-time)|false|none|none|
|end|string(date-time)|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_Address">Address</h2>
<!-- backwards compatibility -->
<a id="schemaaddress"></a>
<a id="schema_Address"></a>
<a id="tocSaddress"></a>
<a id="tocsaddress"></a>

```json
{
  "address_type": "not_specified",
  "reference": "string",
  "property_number": "string",
  "property_name": "string",
  "address_line1": "string",
  "address_line2": "string",
  "address_line3": "string",
  "locality": "string",
  "region": "string",
  "postal_code": "string",
  "country_iso_code": "string",
  "lat_long": {
    "latitude": 0,
    "longitude": 0
  },
  "external_references": {
    "type": "string",
    "value": "string"
  }
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address_type|string|false|none|none|
|reference|string|false|none|none|
|property_number|string|false|none|none|
|property_name|string|false|none|none|
|address_line1|string|false|none|none|
|address_line2|string|false|none|none|
|address_line3|string|false|none|none|
|locality|string|false|none|none|
|region|string|false|none|none|
|postal_code|string|false|none|none|
|country_iso_code|string|false|none|none|
|lat_long|[LatLong](#schemalatlong)|false|none|none|
|external_references|[ExternalAddressReference](#schemaexternaladdressreference)|false|none|none|

<section>

#### Enumerated Values

|Property|Value|
|---|---|
|address_type|not_specified|
|address_type|origin|
|address_type|destination|
|address_type|return|
|address_type|billing|
|address_type|hub|
|address_type|alternative_delivery|
|address_type|other|

</section>

</section>
</section>

<section>
<h2 id="tocS_Metadata">Metadata</h2>
<!-- backwards compatibility -->
<a id="schemametadata"></a>
<a id="schema_Metadata"></a>
<a id="tocSmetadata"></a>
<a id="tocsmetadata"></a>

```json
{
  "key": "string",
  "value": "string",
  "type": "string"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|false|none|none|
|value|string|false|none|none|
|type|string|false|none|none|

<section>

#### Enumerated Values

|Property|Value|
|---|---|
|type|string|
|type|datetime|
|type|datetimeoffset|
|type|boolean|
|type|integer|
|type|decimal|
|type|url|

</section>

</section>
</section>

<section>
<h2 id="tocS_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Lateness">Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Lateness</h2>
<!-- backwards compatibility -->
<a id="schemasorted.react.shipment.api.datacontracts.internal.inbound.lateness"></a>
<a id="schema_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.Lateness"></a>
<a id="tocSsorted.react.shipment.api.datacontracts.internal.inbound.lateness"></a>
<a id="tocssorted.react.shipment.api.datacontracts.internal.inbound.lateness"></a>

```json
{
  "is_late": true
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|is_late|boolean|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.ShipmentState">Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.ShipmentState</h2>
<!-- backwards compatibility -->
<a id="schemasorted.react.shipment.api.datacontracts.internal.inbound.shipmentstate"></a>
<a id="schema_Sorted.React.Shipment.Api.DataContracts.Internal.Inbound.ShipmentState"></a>
<a id="tocSsorted.react.shipment.api.datacontracts.internal.inbound.shipmentstate"></a>
<a id="tocssorted.react.shipment.api.datacontracts.internal.inbound.shipmentstate"></a>

```json
{
  "state": "unknown"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|state|string|false|none|none|

<section>

#### Enumerated Values

|Property|Value|
|---|---|
|state|unknown|
|state|action_required|
|state|arrived_at_destination_country|
|state|at_customs|
|state|awaiting_drop_off|
|state|carrier_changed|
|state|carrier_refused_to_collect|
|state|carrier_unable_to_collect|
|state|shipment_issue|
|state|cleared_through_customs|
|state|collected_by_carrier|
|state|collection_rescheduled|
|state|collection_scheduled|
|state|customs_charges_due|
|state|damaged|
|state|delayed|
|state|delivered|
|state|delivered_damaged|
|state|delivered_to_neighbour|
|state|delivered_to_reception|
|state|delivered_to_safe_location|
|state|delivery_address_changed|
|state|delivery_attempted|
|state|delivery_failed|
|state|delivery_failed_card_left|
|state|delivery_refused|
|state|delivery_rescheduled|
|state|delivery_scheduled|
|state|destroyed|
|state|dispatched|
|state|dropped_off|
|state|exchange_failed|
|state|exchange_successful|
|state|failed_to_collect|
|state|final_delivery_attempt|
|state|for_information|
|state|held_by_carrier|
|state|incorrect_label|
|state|in_transit|
|state|in_transit_waiting|
|state|lost|
|state|missing|
|state|missing_manifest|
|state|misrouted|
|state|out_for_delivery|
|state|partially_delivered|
|state|proof_of_delivery_available|
|state|ready_for_collection|
|state|refunded|
|state|will_be_returned_to_sender|
|state|returned_to_sender|
|state|late|
|state|collection_reminder|
|state|final_collection_reminder|
|state|may_be_missing|
|state|unable_to_track|

</section>

</section>
</section>

<section>
<h2 id="tocS_LatLong">LatLong</h2>
<!-- backwards compatibility -->
<a id="schemalatlong"></a>
<a id="schema_LatLong"></a>
<a id="tocSlatlong"></a>
<a id="tocslatlong"></a>

```json
{
  "latitude": 0,
  "longitude": 0
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|latitude|number(double)|false|none|none|
|longitude|number(double)|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_ExternalAddressReference">ExternalAddressReference</h2>
<!-- backwards compatibility -->
<a id="schemaexternaladdressreference"></a>
<a id="schema_ExternalAddressReference"></a>
<a id="tocSexternaladdressreference"></a>
<a id="tocsexternaladdressreference"></a>

```json
{
  "type": "string",
  "value": "string"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|value|string|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_RegisterShipmentRequest">RegisterShipmentRequest</h2>
<!-- backwards compatibility -->
<a id="schemaregistershipmentrequest"></a>
<a id="schema_RegisterShipmentRequest"></a>
<a id="tocSregistershipmentrequest"></a>
<a id="tocsregistershipmentrequest"></a>

```json
{
  "shipments": [
    {
      "tracking_references": "QWERTYUIOP",
      "custom_references": [
        "string"
      ],
      "tags": [
        "string"
      ],
      "carrier": "string",
      "carrier_service": "string",
      "shipped_date": "2019-04-08T14:05:06Z",
      "order_date": "2019-04-08T14:05:06Z",
      "promised_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "expected_delivery_date": {
        "start": "2019-04-08T14:05:06Z",
        "end": "2019-04-08T14:05:06Z"
      },
      "addresses": [
        {
          "address_type": "not_specified",
          "reference": "string",
          "property_number": "string",
          "property_name": "string",
          "address_line1": "string",
          "address_line2": "string",
          "address_line3": "string",
          "locality": "string",
          "region": "string",
          "postal_code": "string",
          "country_iso_code": "string",
          "lat_long": {
            "latitude": 0,
            "longitude": 0
          },
          "external_references": {
            "type": "string",
            "value": "string"
          }
        }
      ],
      "consumer": {
        "reference": "string",
        "email": "string",
        "phone": "string",
        "mobile_phone": "string",
        "first_name": "string",
        "last_name": "string",
        "middle_name": "string",
        "title": "string"
      },
      "metadata": [
        {
          "key": "string",
          "value": "string",
          "type": "string"
        }
      ],
      "retailer": "string",
      "shipment_type": "delivery"
    }
  ]
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shipments|[[Shipment](#schemashipment)]|false|none|none|

</section>
</section>

<section>
<h2 id="tocS_Shipment">Shipment</h2>
<!-- backwards compatibility -->
<a id="schemashipment"></a>
<a id="schema_Shipment"></a>
<a id="tocSshipment"></a>
<a id="tocsshipment"></a>

```json
{
  "tracking_references": "QWERTYUIOP",
  "custom_references": [
    "string"
  ],
  "tags": [
    "string"
  ],
  "carrier": "string",
  "carrier_service": "string",
  "shipped_date": "2019-04-08T14:05:06Z",
  "order_date": "2019-04-08T14:05:06Z",
  "promised_date": {
    "start": "2019-04-08T14:05:06Z",
    "end": "2019-04-08T14:05:06Z"
  },
  "expected_delivery_date": {
    "start": "2019-04-08T14:05:06Z",
    "end": "2019-04-08T14:05:06Z"
  },
  "addresses": [
    {
      "address_type": "not_specified",
      "reference": "string",
      "property_number": "string",
      "property_name": "string",
      "address_line1": "string",
      "address_line2": "string",
      "address_line3": "string",
      "locality": "string",
      "region": "string",
      "postal_code": "string",
      "country_iso_code": "string",
      "lat_long": {
        "latitude": 0,
        "longitude": 0
      },
      "external_references": {
        "type": "string",
        "value": "string"
      }
    }
  ],
  "consumer": {
    "reference": "string",
    "email": "string",
    "phone": "string",
    "mobile_phone": "string",
    "first_name": "string",
    "last_name": "string",
    "middle_name": "string",
    "title": "string"
  },
  "metadata": [
    {
      "key": "string",
      "value": "string",
      "type": "string"
    }
  ],
  "retailer": "string",
  "shipment_type": "delivery"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tracking_references|[string]|false|none|The carrier's reference for this shipment.|
|custom_references|[string]|false|none|A list of your own custom references for this shipment.|
|tags|[string]|false|none|An optional list of tags to apply to this shipment.|
|carrier|string|false|none|The name of the carrier of this shipment.|
|carrier_service|string|false|none|The name of the carrier service of this shipment.|
|shipped_date|string(date-time)|false|none|The date on which the shipment was (or will be) shipped.|
|order_date|string(date-time)|false|none|The date on which the order was placed.|
|promised_date|[PromisedDate](#schemapromiseddate)|false|none|none|
|expected_delivery_date|[ExpectedDeliveryDate](#schemaexpecteddeliverydate)|false|none|none|
|addresses|[[Address](#schemaaddress)]|false|none|The addresses relevant to a shipment. Each address includes a "Type" property indicating the type of address, should include only 1 address of each type (e.g. 1 origin and 1 destination).|
|consumer|[Consumer](#schemaconsumer)|false|none|none|
|metadata|[[Metadata](#schemametadata)]|false|none|Optional metadata about this shipment.|
|retailer|string|false|none|An identifier for the retailer for this shipment.|
|shipment_type|string|false|none|A property indicating the type of shipment, e.g. "delivery", "pick_up", "drop_off".|

<section>

#### Enumerated Values

|Property|Value|
|---|---|
|shipment_type|delivery|
|shipment_type|return|
|shipment_type|pick_up|
|shipment_type|drop_off|
|shipment_type|drop_off_pick_up|
|shipment_type|return_drop_off|

</section>

</section>
</section>

<section>
<h2 id="tocS_Consumer">Consumer</h2>
<!-- backwards compatibility -->
<a id="schemaconsumer"></a>
<a id="schema_Consumer"></a>
<a id="tocSconsumer"></a>
<a id="tocsconsumer"></a>

```json
{
  "reference": "string",
  "email": "string",
  "phone": "string",
  "mobile_phone": "string",
  "first_name": "string",
  "last_name": "string",
  "middle_name": "string",
  "title": "string"
}

```

<section>

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reference|string|false|none|none|
|email|string|false|none|none|
|phone|string|false|none|none|
|mobile_phone|string|false|none|none|
|first_name|string|false|none|none|
|last_name|string|false|none|none|
|middle_name|string|false|none|none|
|title|string|false|none|none|

</section>
</section>

