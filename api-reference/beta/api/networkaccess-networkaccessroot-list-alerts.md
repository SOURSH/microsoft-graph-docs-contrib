---
title: "List alert objects"
description: "Get a list of the alert objects and their properties."
author: "miritsadon"
ms.date: 04/07/2025
ms.localizationpriority: medium
ms.subservice: "entra-global-secure-access"
doc_type: apiPageType
---

# List alert objects

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the alert objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "networkaccess-networkaccessroot-list-alerts-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/networkaccess-networkaccessroot-list-alerts-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /networkAccessRoot/alerts
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

If successful, this method returns a `200 OK` response code and a collection of [alert](../resources/alert.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_alert"
}
-->
``` http
GET https://graph.microsoft.com/beta/networkAccessRoot/alerts
```

### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.networkaccess.alert"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.networkaccess.alert",
      "id": "6fb54016-77df-4d32-9946-7603af8433e1",
      "alertType": "String",
      "creationDateTime": "String (timestamp)",
      "description": "String",
      "actions": [
        {
          "@odata.type": "microsoft.graph.networkaccess.alertAction"
        }
      ],
      "relatedResources": [
        {
          "@odata.type": "microsoft.graph.networkaccess.relatedRemoteNetwork"
        }
      ],
      "vendorName": "String",
      "detectionTechnology": "String",
      "severity": "String",
      "displayName": "String",
      "productName": "String",
      "componentName": "String",
      "categories": [
        "String"
      ],
      "techniques": [
        "String"
      ],
      "subTechniques": [
        "String"
      ],
      "firstActivityDateTime": "String (timestamp)",
      "lastActivityDateTime": "String (timestamp)",
      "isPreview": "Boolean",
      "extendedProperties": {
        "@odata.type": "microsoft.graph.networkaccess.extendedProperties"
      }
    }
  ]
}
