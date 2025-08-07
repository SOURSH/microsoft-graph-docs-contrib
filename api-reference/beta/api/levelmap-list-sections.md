---
title: "List sectionMap objects"
description: "Get a list of the sectionMap objects and their properties."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: apiPageType
---

# List sectionMap objects

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [sections](../resources/sectionmap.md) and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "levelmap-list-sections-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/levelmap-list-sections-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /building/map/levels/{levelMapId}/sections
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

If successful, this method returns a `200 OK` response code and a collection of [sectionMap](../resources/sectionmap.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_sectionmap"
}
-->
``` http
GET https://graph.microsoft.com/beta/building/map/levels/e537d463-475b-43c3-a650-184566c68bc9/sections
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.sectionMap"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://canary.graph.microsoft.com/testprodbetamapserviceapi0613/$metadata#places('91ac6c16-cda9-4506-b55d-e1f4dac3cbe7')/microsoft.graph.building/map/levels('e537d463-475b-43c3-a650-184566c68bc9')/sections",
    "@microsoft.graph.tips": "Use $select to choose only the properties your app needs, as this can lead to performance improvements. For example: GET places('<guid>')/microsoft.graph.building/map/levels('<guid>')/sections?$select=placeId",
    "value": [
        {
            "placeId": null,
            "id": "005eb3b8-c95d-4d35-a8a0-26e3cb4d6998",
            "properties": "{\"id\":\"005eb3b8-c95d-4d35-a8a0-26e3cb4d6998\",\"type\":\"Feature\",\"feature_type\":\"section\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8889415,37.3295396],[-121.8889137,37.329503],[-121.8889082,37.3294956],[-121.888907,37.3294941],[-121.8888551,37.3295189],[-121.8888895,37.3295644],[-121.8889415,37.3295396]]]},\"properties\":{\"name\":{\"en\":\"Test section 01\"},\"restriction\":\"restricted\",\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"address_id\":\"mockAddressId\",\"accessibility\":\"wheelchair\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8888983,37.3295292]},\"places_category\":\"unspecified\"}}"
        },
        {
            "placeId": null,
            "id": "005eb3b8-c95d-4d35-a8a0-22d6nb4d6998",
            "properties": "{\"id\":\"005eb3b8-c95d-4d35-a8a0-22d6nb4d6998\",\"type\":\"Feature\",\"feature_type\":\"section\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8889415,37.3295396],[-121.8889137,37.329503],[-121.8889082,37.3294956],[-121.888907,37.3294941],[-121.8888551,37.3295189],[-121.8888895,37.3295644],[-121.8889415,37.3295396]]]},\"properties\":{\"name\":{\"en\":\"Test section 02\"},\"restriction\":\"restricted222222\",\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"address_id\":\"mockAddressId\",\"accessibility\":\"wheelchair222222\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8888983,37.3295292]},\"places_category\":\"unspecified\"}}"
        }
    ]
}

```

