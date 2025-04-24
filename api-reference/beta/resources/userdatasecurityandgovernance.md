---
title: "userDataSecurityAndGovernance resource type"
description: "Provides access to data security and governance functionalities specifically scoped to the context of a single user."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# userDataSecurityAndGovernance resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Provides access to data security and governance functionalities specifically scoped to the context of a single user.

Accessed via the `dataSecurityAndGovernance` navigation property on a `user` resource.

Inherits from [microsoft.graph.dataSecurityAndGovernance](../resources/datasecurityandgovernance.md).

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [processContent](../api/userdatasecurityandgovernance-post-processcontent.md) | [processContentResponse](../resources/processcontentresponse.md) | Process content against data security and governance policies in the context of this user. |
| [protectionScopes](../api/userdatasecurityandgovernance-post-processcontent.md) | [policyUserScope](../resources/policyuserscope.md) collection | Compute the protection scopes for this user. |

## Properties

None specific to this derived type.

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|activities|[microsoft.graph.activitiesContainer](../resources/activitiescontainer.md)|Container for activity logs (content processing and audit) related to this user. ContainsTarget: true.|

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.userDataSecurityAndGovernance"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.userDataSecurityAndGovernance",
  "activities": { "@odata.type": "microsoft.graph.activitiesContainer" },
}
```
