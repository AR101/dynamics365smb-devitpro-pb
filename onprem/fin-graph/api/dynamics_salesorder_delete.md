---
title: Delete salesOrders | Microsoft Docs
description: Deletes a sales order object in Dynamics 365 Business Central.
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

# Delete salesOrders
Delete a sales order object from Dynamics 365 Business Central.

## HTTP request
```
DELETE /businesscentral/companies({id})/salesOrders({id})
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **salesOrders**, the **salesOrders** will not be updated. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It does not return anything in the response body.

## Example

**Request**

Here is an example of the request.

```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({id})/salesOrders({id})
```

**Response** 

Here is an example of the response. 

```json
HTTP/1.1 204 No Content
```

## See also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Sales order](../resources/dynamics_salesorder.md)  
[Get sales order](../api/dynamics_salesorder_get.md)  
[Create sales order](../api/dynamics_create_salesorder.md)  
[Update sales order](../api/dynamics_salesorder_update.md)  