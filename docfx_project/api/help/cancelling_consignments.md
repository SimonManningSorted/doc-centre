# Cancelling Consignments

This page explains how to cancel consignments in PRO, both individually and in bulk. <span class="highlight">At what point are Cancelled consignments removed from the system?</span>

---

## Cancelling Individual Consignments

To cancel an individual consignment, use the **Cancel Consignment** endpoint. You can call **Cancel Consignment** by sending a `PUT` request to `https://api.electioapp.com/consignments/{consignmentReference}/cancel`. Once the request has been received, PRO changes the consignment's `ConsignmentState` to _Cancelled_ and returns a code 200 response with no body.

## Cancelling Consignments in Bulk

If you need to cancel multiple consignments in one operation, use the **Cancel Consignments** endpoint. You can call **Cancel Consignments** by sending a `PUT` request to `https://api.electioapp.com/consignments/cancellist`. The body of the request should comprise an array listing the `consignmentReference`s of the consignments you want to cancel.

Once the request has been received, PRO changes the each consignment's `consignmentState` to _Cancelled_ and returns a list with a confirmation message in it for each consignment.

### Cancel Consignments Example

This example shows three consignments being cancelled at once via **Cancel Consignments** endpoint.

<div class="tab">
    <button class="staticTabButton">Example Cancel Consignments Request</button>
    <div class="copybutton" onclick="CopyToClipboard('cancelConsRequest')">Click to Copy</div>
</div>

<div id="cancelConsRequest" class="staticTabContent" onclick="CopyToClipboard('cancelConsRequest')">

```json
[
  "EC-000-05D-1NS",
  "EC-000-05D-1NT",
  "EC-000-05D-1NV"
]
```
</div>

<div class="tab">
    <button class="staticTabButton">Example Cancel Consignments Response</button>
    <div class="copybutton" onclick="CopyToClipboard('cancelConsResponse')">Click to Copy</div>
</div>

<div id="cancelConsResponse" class="staticTabContent" onclick="CopyToClipboard('cancelConsResponse')">

```json
[
    {
        "IsSuccess": true,
        "Message": "Consignment cancellation completed successfully",
        "Data": "EC-000-05D-1NS",
        "ApiLinks": null
    },
    {
        "IsSuccess": true,
        "Message": "Consignment cancellation completed successfully",
        "Data": "EC-000-05D-1NT",
        "ApiLinks": null
    },
    {
        "IsSuccess": true,
        "Message": "Consignment cancellation completed successfully",
        "Data": "EC-000-05D-1NV",
        "ApiLinks": null
    }
]
```
</div>

## Next Steps

* Learn how to allocate consignments at the [Allocating Consignments to Carriers](/api/help/allocating_consignments_to_carriers.html) page.
* Learn how to get and print delivery labels at the [Getting Labels](/api/help/getting_labels.html) page.
* Learn how to add consignments to a carrier manifest at the [Manifesting Consignments](/api/help/manifesting_consignments.html) page.

<script src="../../scripts/requesttabs.js"></script>
<script src="../../scripts/responsetabs.js"></script>
<script src="../../scripts/copy.js"></script>