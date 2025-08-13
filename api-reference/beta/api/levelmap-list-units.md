---
title: "List unitMap objects"
description: "Get a list of the unitMap objects and their properties."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: apiPageType
---

# List unitMap objects

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [units](../resources/unitmap.md) and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "levelmap-list-units-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/levelmap-list-units-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /places/{buildingPlaceId}/microsoft.graph.building/map/levels/{levelMapId}/units
```
{buildingPlaceId} - **placeID** of the building with which this map is associated

{levelImdfID} - **id** of the level with which this map is associated

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [unitMap](../resources/unitmap.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_unitmap"
}
-->
``` http
GET https://graph.microsoft.com/beta/building/map/levels/e537d463-475b-43c3-a650-184566c68bc9/units
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.unitMap"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://canary.graph.microsoft.com/testprodbetamapserviceapi0613/$metadata#places('91ac6c16-cda9-4506-b55d-e1f4dac3cbe7')/microsoft.graph.building/map/levels('e537d463-475b-43c3-a650-184566c68bc9')/units",
    "@microsoft.graph.tips": "Use $select to choose only the properties your app needs, as this can lead to performance improvements. For example: GET places('<guid>')/microsoft.graph.building/map/levels('<guid>')/units?$select=placeId",
    "value": [
        {
            "placeId": null,
            "id": "005eb3b8-c95d-4d35-a8a0-22d3cb4d6542",
            "properties": "{\"id\":\"005eb3b8-c95d-4d35-a8a0-22d3cb4d6542\",\"type\":\"Feature\",\"feature_type\":\"unit\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8889415,37.3295396],[-121.8889137,37.329503],[-121.8889082,37.3294956],[-121.888907,37.3294941],[-121.8888551,37.3295189],[-121.8888895,37.3295644],[-121.8889415,37.3295396]]]},\"properties\":{\"name\":{\"en\":\"Test room from Test Floor 1 (120.3)\"},\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8888983,37.3295292]},\"places_category\":\"room\"}}"
        },
        {
            "placeId": null,
            "id": "92171039-cf9b-4590-a406-43ca824c8418",
            "properties": "{\"id\":\"92171039-cf9b-4590-a406-43ca824c8418\",\"type\":\"Feature\",\"feature_type\":\"unit\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8884352,37.3296641],[-121.8883999,37.329681],[-121.8883976,37.3296821],[-121.8883886,37.3296864],[-121.8883712,37.3296947],[-121.8884224,37.3297623],[-121.888436,37.3297802],[-121.8884642,37.3297667],[-121.8884817,37.3297583],[-121.8885142,37.3297428],[-121.8885182,37.3297408],[-121.8885162,37.3297381],[-121.8884834,37.3296948],[-121.8884725,37.3296805],[-121.8884577,37.3296608],[-121.8884535,37.3296554],[-121.8884495,37.3296573],[-121.8884352,37.3296641]]]},\"properties\":{\"name\":{\"en\":\"Test room 2 from Test Floor 1 (120.14)\"},\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8884437,37.3297165]},\"places_category\":\"conferenceroom\"}}"
        },
    ]
}

```

