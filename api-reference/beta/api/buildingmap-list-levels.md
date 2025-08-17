---
title: "List levelMap objects"
description: "Get a list of the level map objects and their properties."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: apiPageType
---

# List levelMap objects

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [level map](../resources/levelmap.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "buildingmap-list-levels-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/buildingmap-list-levels-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /places/{buildingPlaceId}/microsoft.graph.building/map/levels
```
> **Note:** `{buildingPlaceId}` is the unique **placeId** of a [building](../resources/building.md) with which the [level map](../resources/levelmap.md) objects are associated.

## Optional query parameters

This method supports the `$select` OData query parameter to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [levelMap](../resources/levelmap.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_levelmap"
}
-->
``` http
GET https://graph.microsoft.com/beta/places/4bff9586-c9ee-401d-9d35-c476231a33e6/microsoft.graph.building/map/levels
```

### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.levelMap)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "placeId": "4bff9586-c9ee-401d-9d35-c476231a33e6",
      "id": "e537d463-475b-43c3-a650-184566c68bc9",
      "properties": "{\"id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"type\":\"Feature\",\"feature_type\":\"level\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8891473,37.3297928],[-121.8893961,37.3299621],[-121.8894513,37.3300349],[-121.8894531,37.3300373],[-121.8891236,37.3297614],[-121.8891473,37.3297928]……]]},\"properties\":{\"name\":{\"en\":\"Test Floor 1\"},\"building_ids\":[\"26f04b4f-9ae2-45e3-99d1-393c66d58eb4\"],\"address_id\":\"e105efb7-b0d1-4144-8b8e-72eadf95724f\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.88904,37.3289553]},\"places_category\":\"unspecified\",\"directory_id\":\"4bff9586-c9ee-401d-9d35-c476231a33e6\",\"ordinal\":0}}"
    }
  ]
}
```

