---
title: "Update sectionMap"
description: "Update the properties of a sectionMap object in IMDF format."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: apiPageType
---

# Update sectionMap

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [section](../resources/sectionmap.md) on a given floor.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "sectionmap-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/sectionmap-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /places/{buildingPlaceId}/microsoft.graph.building/map/levels/{levelImdfID}/section/{sectionImdfID}
```

> **Note:**
> * `{buildingPlaceId}` is the **placeId** of a [building](../resources/building.md) with which this [section](../resources/sectionmap.md) is associated.
> * `{levelImdfId}` is the **id** of the level in the IMDF file.
> * `{sectionImdfID}` is the **id** of the section in the IMDF file.

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|properties|String|Concatenated key-value pair of all properties of a geojson file for this **section**. Inherited from [baseMapFeature](../resources/basemapfeature.md). Optional.|
|placeId|String|Identifier for the [section](../resources/section.md) to which this **section map** belongs. Optional.|



## Response

If successful, this method returns a `200 OK` response code and an updated [sectionMap](../resources/sectionmap.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_sectionmap"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/building/map/levels/e537d463-475b-43c3-a650-184566c68bc9/sections/005eb3b8-c95d-4d35-a8a0-22d6nb4d6003
Content-Type: application/json

{
    "placeId": "67149ec1-4b99-42d4-88a4-d92cd23cb606",
    "properties": "{\"id\":\"005eb3b8-c95d-4d35-a8a0-22d6nb4d6003\",\"type\":\"Feature\",\"feature_type\":\"section\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8889415,37.3295396],[-121.8889137,37.329503],[-121.8889082,37.3294956],[-121.888907,37.3294941],[-121.8888551,37.3295189],[-121.8888895,37.3295644],[-121.8889415,37.3295396]]]},\"properties\":{\"name\":{\"en\":\"Test section update\"},\"restriction\":\"restricted222222\",\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"address_id\":\"mockAddressId\",\"accessibility\":\"wheelchair222222\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8888983,37.3295292]},\"places_category\":\"unspecified\"}}"
}
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
    "placeId": "67149ec1-4b99-42d4-88a4-d92cd23cb606",
    "id": "005eb3b8-c95d-4d35-a8a0-22d6nb4d6003",
    "properties": "{\"id\":\"005eb3b8-c95d-4d35-a8a0-22d6nb4d6003\",\"type\":\"Feature\",\"feature_type\":\"section\",\"geometry\":{\"type\":\"Polygon\",\"coordinates\":[[[-121.8889415,37.3295396],[-121.8889137,37.329503],[-121.8889082,37.3294956],[-121.888907,37.3294941],[-121.8888551,37.3295189],[-121.8888895,37.3295644],[-121.8889415,37.3295396]]]},\"properties\":{\"name\":{\"en\":\"Test section update\"},\"restriction\":\"restricted222222\",\"level_id\":\"e537d463-475b-43c3-a650-184566c68bc9\",\"address_id\":\"mockAddressId\",\"accessibility\":\"wheelchair222222\",\"display_point\":{\"type\":\"Point\",\"coordinates\":[-121.8888983,37.3295292]},\"places_category\":\"unspecified\"}}"
}

```

