---
title: Update salesCreditMemoLines | Microsoft Docs
description: Updates a sales credit memo line object in Dynamics 365 Business Central. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/05/2018
ms.author: solsen
---

# Update salesCreditMemoLines
Update the properties of a sales credit memo line object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
PATCH /businesscentral/companies({id})/salesCreditMemos({id})/salesCreditMemoLines(documentId=({id}),sequence=({number}))
```

## Request headers
|Header|Value|
|------|-----|
|Authorization |Bearer {token}. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **salesCreditMemoLines**, the **salesCreditMemoLines** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated sales credit memo line object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/salesCreditMemos({id})/salesCreditMemoLines(documentId=({id}),sequence=({number}))
Content-type: application/json

{
  "description": "someText"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "documentId": "id-value",
  "sequence": 10000,
  "itemId": "id-value",
  "accountId": "id-value",
  "lineType": "Item",
  "lineDetails": {
    "number": "GL000009",
    "displayName": "GL000009",
    "description": null
  },
  "description": "someText",
  "unitOfMeasure": {
    "code": "BOX",
    "displayName": "Box",
    "symbol": null,
    "unitConversion": null
  },
  "unitPrice": 71.1,
  "quantity": 96,
  "discountAmount": 0,
  "discountPercent": 0,
  "discountAppliedBeforeTax": false,
  "amountExcludingTax": 6825.6,
  "taxCode": "VAT10",
  "taxPercent": 10,
  "totalTaxAmount": 682.56,
  "amountIncludingTax": 7508.16,
  "invoiceDiscountAllocation": 0,
  "netAmount": 6825.6,
  "netTaxAmount": 682.56,
  "netAmountIncludingTax": 7508.16,
  "shipmentDate": "2015-02-24"
}
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Sales credit memo line](../resources/dynamics_salescreditmemoline.md)  
[Get sales credit memo line](../api/dynamics_salescreditmemoline_get.md)  
[Create sales credit memo line](../api/dynamics_create_salescreditmemoline.md)  
[Delete sales credit memo line](../api/dynamics_salescreditmemoline_delete.md)  