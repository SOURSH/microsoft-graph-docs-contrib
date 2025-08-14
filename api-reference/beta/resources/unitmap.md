---
title: "unitMap resource type"
description: "Represents a unit.geojson file in IMDF format showing units (such as rooms or offices) on the floor of a building."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: resourcePageType
---

# unitMap resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a unit.geojson file in IMDF format showing units (such as rooms or offices) on a floor of a building.

Inherits from [baseMapFeature](../resources/basemapfeature.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[Create](../api/levelmap-post-units.md)|[unitMap](../resources/unitmap.md)|Create a new **unitMap** object.|
|[Delete](../api/levelmap-delete-units.md)|None|Delete a **unitMap** object.|
|[Update](../api/unitmap-update.md)|[unitMap](../resources/unitmap.md)|Update the properties of a **unitMap** object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the **unitMap** object. Inherited from [entity](../resources/entity.md). |
|placeId|String|Identifier of the [place](./place.md) (such as a [room](./room.md)) to which this **unitMap** belongs.|
|properties|String|Concatenated key-value pair of all properties of a geojson file for this **unitMap**. Inherited from [baseMapFeature](../resources/basemapfeature.md).|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.unitMap",
  "baseType": "microsoft.graph.baseMapFeature",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.unitMap",
  "id": "String (identifier)",
  "properties": "String",
  "placeId": "String"
}
```

