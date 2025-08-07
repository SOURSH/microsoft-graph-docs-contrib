---
title: "sectionMap resource type"
description: "Represents a section.geojson file in IMDF format showing sections (such as zones or partitions) on the floor of a building."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: outlook
doc_type: resourcePageType
---

# sectionMap resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a section.geojson file in IMDF format showing sections (such as zones or partitions) on the floor of a building.

Inherits from [baseMapFeature](../resources/basemapfeature.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[Create](../api/levelmap-post-sections.md)|[sectionMap](../resources/sectionmap.md)|Create a new **sectionMap** object.|
|[Delete](../api/levelmap-delete-sections.md)|None|Delete a **sectionMap** object.|
|[Get](../api/sectionmap-get.md)|[sectionMap](../resources/sectionmap.md)|Get the properties and relationships of a **sectionMap** object in IMDF format.|
|[List](../api/levelmap-list-sections.md)|[sectionMap](../resources/sectionmap.md) collection|Get a list of **sectionMap** objects and their properties.|
|[Update](../api/sectionmap-update.md)|[sectionMap](../resources/sectionmap.md)|Update the properties of a **sectionMap** object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the **sectionMap** object. Inherited from [entity](../resources/entity.md). |
|placeId|String|Identifier of the [section](./section.md) to which this **sectionMap** belongs.|
|properties|String|Concatenated key-value pair of all properties of a geojson file for this **sectionMap**. Inherited from [baseMapFeature](../resources/basemapfeature.md).|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.sectionMap",
  "baseType": "microsoft.graph.baseMapFeature",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.sectionMap",
  "id": "String (identifier)",
  "properties": "String",
  "placeId": "String"
}
```

