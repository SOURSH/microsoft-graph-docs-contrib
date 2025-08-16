---
title: "adhocCall resource type"
description: "Contains information about an ad hoc call."
author: "kanchm"
ms.date: 07/04/2025
ms.localizationpriority: medium
ms.subservice: "cloud-communications"
doc_type: resourcePageType
---

# adhocCall resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains information about an ad hoc call.

This resource supports subscribing to [change notifications](/graph/change-notifications-overview).

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|The unique identifier for the ad hoc call. Read-only.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|recordings|[callRecording](../resources/callrecording.md) collection | The recordings of a call. Read-only. |
|transcripts|[callTranscript](../resources/calltranscript.md) collection | The transcripts of a call. Read-only. |

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.adhocCall",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.adhocCall",
  "id": "String (identifier)"
}
```

