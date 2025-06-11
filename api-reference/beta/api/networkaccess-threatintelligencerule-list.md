---
title: "List threatIntelligenceRule objects"
description: "Get a list of the threatIntelligenceRule objects and their properties."
author: "fgomulka"
ms.date: 06/05/2025
ms.localizationpriority: medium
ms.subservice: "entra-global-secure-access"
doc_type: apiPageType
---

# List threatIntelligenceRule objects

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the threatIntelligenceRule objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "networkaccess-threatintelligencerule-list-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/networkaccess-threatintelligencerule-list-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET ** Collection URI for microsoft.graph.networkaccess.threatIntelligenceRule not found
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [threatIntelligenceRule](../resources/threatintelligencerule.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_threatintelligencerule"
}
-->
``` http
GET https://graph.microsoft.com/beta** Collection URI for microsoft.graph.networkaccess.threatIntelligenceRule not found
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.networkaccess.threatIntelligenceRule"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.networkaccess.threatIntelligenceRule",
      "id": "45e8cf05-fb70-b38a-7288-0b47feb253b0",
      "name": "String",
      "description": "String",
      "action": "String",
      "priority": "Integer",
      "settings": {
        "@odata.type": "microsoft.graph.networkaccess.threatIntelligenceRuleSettings"
      },
      "matchingConditions": {
        "@odata.type": "microsoft.graph.networkaccess.threatIntelligenceMatchingConditions"
      }
    }
  ]
}
```

