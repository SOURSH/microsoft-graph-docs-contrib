---
title: "levelMap resource type"
description: "Represents a level.geojson file in IMDF format showing the physical floor structure within a building."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: resourcePageType
---

# levelMap resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a level.geojson file in IMDF format showing the physical floor structure within a building.

Inherits from [baseMapFeature](./basemapfeature.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List fixtures](../api/levelmap-list-fixtures.md)|[fixtureMap](./fixturemap.md) collection|Get a list of [fixtureMap](./fixturemap.md) objects and their properties.|
|[List sections](../api/levelmap-list-sections.md)|[sectionMap](./sectionmap.md) collection|Get a list of [sectionMap](./sectionmap.md) objects and their properties.|
|[List units](../api/levelmap-list-units.md)|[unitMap](./unitmap.md) collection|Get a list of the [unitMap](./unitmap.md) objects and their properties.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the **levelMap** object. Inherited from [baseMapFeature](./basemapfeature.md).|
|placeId|String|Identifier of the [floor](./floor.md) to which this **levelMap** belongs.|
|properties|String|Concatenated key-value pair of all properties of a geojson file for this **levelMap**. Inherited from [baseMapFeature](./basemapfeature.md).|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|fixtures|[fixtureMap](./fixturemap.md) collection|Collection of fixtures (such as furniture or equipment) on this level. Supports upsert.|
|sections|[sectionMap](./sectionmap.md) collection|Collection of sections (such as zones or partitions) on this level. Supports upsert.|
|units|[unitMap](./unitmap.md) collection|Collection of units (such as rooms or offices) on this level. Supports upsert.|

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.levelMap",
  "baseType": "microsoft.graph.baseMapFeature",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.levelMap",
  "id": "String (identifier)",
  "placeId": "String",
  "properties": "String"
}
```
