---
title: "Get section"
description: "Read the properties and relationships of a section object."
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
ms.date: 06/11/2025
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS subservice. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
doc_type: apiPageType
---

# Get section

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a section object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "section-get-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/section-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /section
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

If successful, this method returns a `200 OK` response code and a [section](../resources/section.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "get_section"
}
-->
``` http
GET https://graph.microsoft.com/beta/section
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.section"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.section",
    "id": "33491080-b007-37f2-c045-b46746ef402f",
    "displayName": "String",
    "geoCoordinates": {
      "@odata.type": "microsoft.graph.outlookGeoCoordinates"
    },
    "phone": "String",
    "address": {
      "@odata.type": "microsoft.graph.physicalAddress"
    },
    "placeId": "String",
    "parentId": "String",
    "resourceLinks": [
      {
        "@odata.type": "microsoft.graph.resourceLink"
      }
    ],
    "tags": [
      "String"
    ],
    "isWheelChairAccessible": "Boolean",
    "label": "String"
  }
}
```

