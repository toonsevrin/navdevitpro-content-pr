---
title: Update salesQuoteLines | Microsoft Docs
description: Updates a sales quote line in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
---

# Update salesQuoteLines
Update the properties of a sales quote line object for Dynamics 365 Business Central.

## HTTP request

```
PATCH /financials/companies({id})/salesQuotes({id})/salesQuoteLines
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **salesQuoteLines**, the **salesQuoteLines** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated **salesQuoteLines** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://graph.microsoft.com/beta/financials/companies({id})/salesQuotes({id})/salesQuoteLines
Content-type: application/json

{
  "description": "someText"
}
```

**Response**

Here is an example of the response. 

> **Note**: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "documentId": "id-value",
  "sequence": 10000,
  "itemId": "id-value",
  "accountId": "id-value",
  "lineType": "Item",
  "description": "someText",
  "unitPrice": 6165,
  "quantity": 1,
  "discountAmount": 0,
  "discountPercent": 0,
  "discountAppliedBeforeTax": false,
  "amountExcludingTax": 6165,
  "taxCode": "VAT10",
  "taxPercent": 10,
  "totalTaxAmount": 0,
  "amountIncludingTax": 6165,
  "netAmount": 6165,
  "netTaxAmount": 0,
  "netAmountIncludingTax": 6165
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with Dynamics 365 Business Central in Microsoft Graph](../resources/dynamics_overview.md)  
[Error Codes](../dynamics_error_codes.md)  
[Sales Quote Line](../resources/dynamics_salesquoteline.md)  
[Get Sales Quote Line](../api/dynamics_salesquoteline_get.md)  
[Create Sales Quote Line](../api/dynamics_create_salesquoteline.md)  
[Delete Sales Quote Line](../api/dynamics_salesquoteline_delete.md)  