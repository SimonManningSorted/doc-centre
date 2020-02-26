# Manifesting Consignments

Get Customer Manifest

Get Customer Manifests

Set Ready To Ship

Set Not Ready To Ship

Manifest Consignments

> Manifest Consignments Endpoint
```
PUT https://api.electioapp.com/consignments/manifest
```
> Example Manifest Consignment Request

```json
{
  "ConsignmentReferences": [
    "EC-000-05A-Z6S",
    "EC-000-083-45D",
    "EC-000-A04-0DV"
  ]
}
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<ManifestConsignmentsRequest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
  <ConsignmentReferences>
    <string>EC-000-05A-Z6S</string>
    <string>EC-000-083-45D</string>
    <string>EC-000-A04-0DV</string>
  </ConsignmentReferences>
</ManifestConsignmentsRequest>
```

> Example Manifest Consignment Response

```json
[
  {
    "IsSuccess": true,
    "Message": "Consignment EC-000-002-5FG has been manifested successfully.",
    "Data": "EC-000-002-5FG",
    "ApiLinks": [
      {
        "Rel": "Link",
        "Href": "https://api.electioapp.com/consignments/EC-000-002-5FG"
      }
    ]
  },
  {
    "IsSuccess": true,
    "Message": "Consignment EC-000-002-5FG has been manifested successfully.",
    "Data": "EC-000-002-5FG",
    "ApiLinks": [
      {
        "Rel": "Link",
        "Href": "https://api.electioapp.com/consignments/EC-000-002-5FG"
      }
    ]
  },
  {
    "IsSuccess": true,
    "Message": "Consignment EC-000-002-5FG has been manifested successfully.",
    "Data": "EC-000-002-5FG",
    "ApiLinks": [
      {
        "Rel": "Link",
        "Href": "https://api.electioapp.com/consignments/EC-000-002-5FG"
      }
    ]
  }
]
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<ArrayOfWithMessageOfString xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <WithMessageOfString>
    <IsSuccess xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">true</IsSuccess>
    <Message xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">Consignment EC-000-002-5FG has been manifested successfully.</Message>
    <Data xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">EC-000-002-5FG</Data>
    <ApiLinks xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
      <ApiLink>
        <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
        <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-002-5FG</Href>
      </ApiLink>
    </ApiLinks>
  </WithMessageOfString>
  <WithMessageOfString>
    <IsSuccess xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">true</IsSuccess>
    <Message xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">Consignment EC-000-002-5FG has been manifested successfully.</Message>
    <Data xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">EC-000-002-5FG</Data>
    <ApiLinks xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
      <ApiLink>
        <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
        <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-002-5FG</Href>
      </ApiLink>
    </ApiLinks>
  </WithMessageOfString>
  <WithMessageOfString>
    <IsSuccess xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">true</IsSuccess>
    <Message xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">Consignment EC-000-002-5FG has been manifested successfully.</Message>
    <Data xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">EC-000-002-5FG</Data>
    <ApiLinks xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Consignments">
      <ApiLink>
        <Rel xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">Link</Rel>
        <Href xmlns="http://electioapp.com/schemas/v1.1/MPD.Electio.SDK.DataTypes.Common">https://api.electioapp.com/consignments/EC-000-002-5FG</Href>
      </ApiLink>
    </ApiLinks>
  </WithMessageOfString>    
</ArrayOfWithMessageOfString>
```

Once you've created a consignment, allocated it to a carrier service and printed labels for it, you're ready to manifest it. To manifest a consignment, use the **[Manifest Consignments](https://docs.electioapp.com/#/api/ManifestConsignments)** endpoint.

<aside class="info">
  In the context of SortedPRO, the term "manifest" refers to advising the carrier of all the consignments/packages to be collected from the shipper.
</aside>

The **Manifest Consignments** endpoint can be used to manifest multiple consignments at once. The request should contain an array of `{consignmentReference}`s, corresponding to the consignments to be manifested. 

All the consignments you provide in the request should be in a state of either _Allocated_ or _Manifest Failed_. If you attempt to manifest a consignment that is not in one of these states then PRO returns an error.

Once PRO has received the request and attempted to manifest the consignments, the **Manifest Consignments** endpoint returns an array of messages indicating whether each individual consignment was successfully manifested or not.

<aside class="note">
  For full reference information on the <strong>Manifest Consignments</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/ManifestConsignments">Manifest Consignments</a></strong> page of the API Reference. 
</aside>

### Examples

The example shows a request to manifest three consignments. The response indicates that all three consignments were successfully manifested.

Manifest Consignments From Query

<div class="tab">
    <button class="staticTabButton">Manifest Consignments From Query Endpoint</button>
    <div class="copybutton" onclick="CopyToClipboard('ManifestQueryEndpoint')">Click to Copy</div>
</div>

<div id="ManifestQueryEndpoint" class="staticTabContent" onclick="CopyToClipboard('ManifestQueryEndpoint')">

```
PUT https://api.electioapp.com/consignments/manifestFromQuery
```
</div>

Once you've created a consignment, allocated it to a carrier service and printed labels for it, you're ready to manifest it. To manifest a consignment, use the **[Manifest Consignments From Query](https://docs.electioapp.com/#/api/ManifestConsignmentsFromQuery)** endpoint.

> <span class="note-header">More Information:</span>
>  In the context of SortedPRO, the term "manifest" refers to advising the carrier that the consignment in question needs to be collected from the shipper.

The **Manifest Consignments From Query** endpoint enables you to use a query to select consignments to be manifested. You can select consignments via the following criteria:

* `ShippingLocationReference` - The shipping location that the consignment will ship from. For information on how to obtain a list of your organisation's shipping locations and their references, see the [Get Shipping Locations](https://docs.electioapp.com/#/api/GetShippingLocations) page of the API reference.
* `States` - The state that the consignments should be in. All the consignments you provide in the request should be in a state of either _Allocated_ or _Manifest Failed_. If you attempt to manifest a consignment that is not in one of these states then PRO returns an error.
* `Carriers` - The carriers that the consignments are allocated to.
* `LabelsPrinted` - Whether or not the labels for the consignments have already been printed.
* `ShippingDate` - The date that the consignment is scheduled to ship.
* `ShippingDateRanges`- A range of scheduled shipping dates.

Once PRO has attempted to add the consignments to the manifest queue, the **Manifest Consignments From Query** endpoint returns a `Message` indicating how many consignments met the terms of the query and how many it was able to queue. It also returns a `FailedConsignments` array listing the `consignmentReferences` of those consignments that PRO was unable to queue for manifest.

> <span class="note-header">Note:</span>
>  For full reference information on the <strong>Manifest Consignments From Query</strong> endpoint, see the <strong><a href="https://docs.electioapp.com/#/api/ManifestConsignmentsFromQuery">Manifest Consignments From Query</a></strong> page of the API Reference. 

### Manifest Consignments From Query Example

The example shows a request to manifest all consignments that are allocated to Carrier X, shipping from a location with the `ShippingLocationReference` _Location1_, and have already had their labels printed. The response indicates that PRO found 10 consignments meeting these criteria, and that all 10 were successfully queued for manifest.

<div class="tab">
    <button class="staticTabButton">Example Manifest Consignments From Query Request</button>
    <div class="copybutton" onclick="CopyToClipboard('ManifestQueryRequest')">Click to Copy</div>
</div>

<div id="ManifestQueryRequest" class="staticTabContent" onclick="CopyToClipboard('ManifestQueryRequest')">

```json
{
  "ShippingLocationReferences": [
    "Location1"
  ],
  "States": [
    "Allocated"
  ],
  "Carriers": [
    "CARRIER_X"
  ],
  "LabelsPrinted": true
}
```
</div>

<div class="tab">
    <button class="staticTabButton">Example Manifest Consignments From Query Response</button>
    <div class="copybutton" onclick="CopyToClipboard('ManifestQueryResponse')">Click to Copy</div>
</div>

<div id="ManifestQueryResponse" class="staticTabContent" onclick="CopyToClipboard('ManifestQueryResponse')">

```json
{
  "Message": "Query found 10 consignment(s). 10 successfully queued to manifest. 0 failed to be added to the queue"
}
```

</div>

<script src="../../scripts/requesttabs.js"></script>
<script src="../../scripts/responsetabs.js"></script>
<script src="../../scripts/copy.js"></script>