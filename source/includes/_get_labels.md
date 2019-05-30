> Get Labels Endpoint
```
GET https://api.electioapp.com/labels/{consignmentReference}
```
> Example Get Labels Request
```
GET https://api.electioapp.com/labels/EC-000-05A-Z6S
```
> Example Get Labels Response
```json
{
  "File": "SlZCRVJpMHhMalFLSmRQcjZ ... [truncated for brevity] ... TVRrNU9ERUtKU1ZGVDBZPQ==",
  "ContentType": "application/pdf"
}
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<GetLabelsResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.LabelGeneration">
  <File>SlZCRVJpMHhMalFLSmRQcjZ ... [truncated for brevity] ... TVRrNU9ERUtKU1ZGVDBZPQ==</File>
  <ContentType>application/pdf</ContentType>
</GetLabelsResponse>
```

When a consignment is allocated, SortedPRO automatically generates delivery labels for it. The next step in the process is to retrieve those delivery labels via the **[Get Labels](https://docs.electioapp.com/#/api/GetLabels)** endpoint.

The **Get Labels** endpoint takes the `{consignmentReference}` of the consignment you want to get labels for as a path parameter, and returns all label file data associated with that consignment as a base64-encoded byte array, as well as a `ContentType` property indicating the file format that the label(s) are in.

Labels are only valid for the combination of the consignment and its allocated carrier service. If you were to de-allocate a consignment for any reason, the consignment's existing labels would be purged from the database, and you would need to run **Get Labels** again once the consignment had been re-allocated.

<aside class="note">
  For full reference information on the <strong>Get Labels</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/GetLabels">Get Labels</a></strong> page of the API reference. 
  
  In addition to the <strong>Get Labels</strong> endpoint, the following PRO endpoints also return label data:

  * <strong><a href="https://docs.electioapp.com/#/api/GetLabelsinFormat">Get Labels in Format</a></strong> - returns a consignment's labels in a file format of your choice.
  * <strong><a href="https://docs.electioapp.com/#/api/GetPackageLabel">Get Package Label</a></strong> - returns a label for an individual package.
  * <strong><a href="https://docs.electioapp.com/#/api/GetPackageLabelinFormat">Get Package Label in Format</a></strong> - returns a label for an individual package in a file format of your choice.
</aside>  

### Examples

The example to the right shows a request to get labels for a consignment with a `{consignmentReference}` of _EC-000-05A-Z6S_. The file data in the response has been truncated for clarity.

You would next need to decode the file's Base64 in order to view the label itself. If you are unsure how to do so, see the **[MDN docs](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding)** for more information.