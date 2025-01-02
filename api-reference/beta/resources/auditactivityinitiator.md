---
title: "auditActivityInitiator resource type"
description: "Identity the resource object that initiates the activity. The initiator can be a user, an app or a system (which is considered as an app)"
ms.localizationpriority: medium
doc_type: resourcePageType
ms.subservice: "entra-monitoring-health"
author: "egreenberg14"
ms.date: 07/22/2024
---

# auditActivityInitiator resource type

Namespace: microsoft.graph
Identity the resource object that initiates the activity. The initiator can be a user, an app or a system (which is considered as an app)



## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|app|[appIdentity](appidentity.md)|If the actor initiating the activity is an app, this property indicates all its identification information including appId, displayName, servicePrincipalId, and servicePrincipalName.|
|user|[auditUserIdentity](auditUserIdentity.md)|If the actor initiating the activity is a user, this property indicates their identification information including their id, displayName, and userPrincipalName.|

## Relationships
None.

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.auditActivityInitiator"
}-->

```json
{
  "app": {"@odata.type": "microsoft.graph.appIdentity"},
  "user": {"@odata.type": "microsoft.graph.userIdentity"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "auditActivityInitiator resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


