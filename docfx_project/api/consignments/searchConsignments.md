# Search Consignments

Search for matching consignments

```
GET https://api.electioapp.com/consignments/{take}/{skip}?startFrom=date&endAt=date&pageSize=int&startPage=int&createdDateFrom=date&createdDateTo=date&scheduledDeliveryDateFrom=date&scheduledDeliveryDateTo=date&shippedDateFrom=date&shippedDateTo=date&shippingDateFrom=date&shippingDateTo=date&requestedDeliveryDateFrom=date&requestedDeliveryDateTo=date&reference=string&referenceProvidedByCustomer=string&trackingReference=string&state=string&weightInGramsFrom=int&weightInGramsTo=int&carrierService=string&source=string&postCode=string&valueFrom=decimal&valueTo=decimal&labelsPrinted=boolean&searchTerm=string&stateAttribute=string&shippingLocationReference=string&destinationCountryCode=string&destinationRegion=string&packageNumber=string&consignmentNumber=string&creference=string&preference=string`
```

## Request

<div class="tab">
    <button class="requestTabLinks" onclick="openRequestTab(event, 'headers')">Headers</button>
    <button class="requestTabLinks" onclick="openRequestTab(event, 'path')" id="defaultRequest">Path (delete if not required)</button>
    <button class="requestTabLinks" onclick="openRequestTab(event, 'body')">Body (delete if not required)</button>
</div>

<div id="headers"  class="requestTabContent">

[!include[apiheaders](../includes/apiheaders.md)]

</div>

<div id="path"  class="requestTabContent">

<table>
    <tr>
        <th>Property</th>
        <th>Type</th>
        <th>Description</th>
        <th>Validation</th>
        <th>Occurrence</th>
    </tr>
    <tr>
        <th>Property</th>
        <th>Type</th>
        <th>Description</th>
        <th>Validation</th>
        <th>Occurrence</th>
    </tr>
</table> 

<div class="copyheader">

### Example
<div class="copybutton" onclick="CopyToClipboard('pathExample')">Click to Copy</div>

</div>

<div id="pathExample" class="copycontent"onclick="CopyToClipboard('pathExample')">

```
[Example endpoint path in here]
```
</div>

</div>

<div id="body"  class="requestTabContent">

<table>
    <tr>
        <th>Property</th>
        <th>Type</th>
        <th>Description</th>
        <th>Validation</th>
        <th>Occurrence</th>
    </tr>
    <tr>
        <th>Property</th>
        <th>Type</th>
        <th>Description</th>
        <th>Validation</th>
        <th>Occurrence</th>
    </tr>
</table> 

<div class="copyheader">

### Example
<div class="copybutton" onclick="CopyToClipboard('bodyExample')">Click to Copy</div>

</div>

<div id="bodyExample" class="copycontent"onclick="CopyToClipboard('bodyExample')">

```
[Example request body in here]
```
</div>

</div>

## Responses

<div class="tab">
  <button class="responseTabLinks" onclick="openCity(event, '200')" id="defaultResponse">200 (OK)</button>
  <button class="responseTabLinks" onclick="openCity(event, '404')">404 (Not Found)</button>
</div>

<div id="200"  class="responseTabContent">

<table>
    <tr>
        <th>Property</th>
        <th>Type</th>
        <th>Description</th>
        <th>Occurrence</th>
    </tr>
    <tr>
        <td>Property</td>
        <td>Type</td>
        <td>Description</td>
        <td>Occurrence</td>
    </tr> 
</table> 

<div class="copyheader">
    
<h3>Example</h3>
<div class="copybutton" onclick="CopyToClipboard('200example')">Click to Copy</div>

</div>

<div id="200example" class="copycontent" onclick="CopyToClipboard('200example')">

```
[Example 200 response]
```
</div>

</div>

<div id="404"  class="responseTabContent">

[!include[404Content](../includes/404Content.md)]

</div>

<!-- Include for tab and copy scripts. DO NOT DELETE THE BELOW -->

[!include[scripts](../includes/scripts.md)]