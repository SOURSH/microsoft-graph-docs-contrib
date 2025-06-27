---
title: "fixtureMap resource type"
description: "Represents a fixture.geojson file in IMDF format showing movable or semi-permanent physical assets within a space."
author: tiwarisakshi02
ms.date: 06/12/2025
ms.localizationpriority: medium
ms.subservice: 
doc_type: resourcePageType
---

# fixtureMap resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a fixture.geojson file in IMDF format showing movable or semi-permanent physical assets within a space that supports utility, service, or aesthetic functions without affecting structural integrity.

Inherits from [baseMapFeature](./basemapfeature.md).


## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[Create](../api/levelmap-post-fixtures.md)|[fixtureMap](./fixturemap.md)|Create a new **fixtureMap** object.|
|[Delete](../api/levelmap-delete-fixtures.md)|None|Delete a **fixtureMap** object.|
|[Get](../api/fixturemap-get.md)|[fixtureMap](./fixturemap.md)|Get the properties and relationships of a **fixtureMap** object in IMDF format.|
|[List](../api/levelmap-list-fixtures.md)|[fixtureMap](./fixturemap.md) collection|Get a list of **fixtureMap** objects and their properties.|
|[Update](../api/fixturemap-update.md)|[fixtureMap](./fixturemap.md)|Update the properties of a **fixtureMap** object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the **fixtureMap** object. Inherited from [entity](./entity.md). |
|placeId|String|Identifier for the [floor](./floor.md) to which this **fixtureMap** belongs. |
|properties|String|Concatenated key-value pair of all properties of a geojson file for this **fixtureMap**. Inherited from [baseMapFeature](./basemapfeature.md).|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.fixtureMap",
  "baseType": "microsoft.graph.baseMapFeature",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.fixtureMap",
  "id": "String (identifier)",
  "properties": "String",
  "placeId": "String"
}
```

