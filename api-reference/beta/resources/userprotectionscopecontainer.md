---
title: "userProtectionScopeContainer resource type"
description: "Container for user-specific protection scope computation actions."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# userProtectionScopeContainer resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Container for user-specific protection scope computation actions.

This is accessed via the `protectionScopes` navigation property on [userDataSecurityAndGovernance](../resources/userdatasecurityandgovernance.md).

## Methods

| Method                                          | Return Type                                                                                   | Description                                                           |
| :---------------------------------------------- | :-------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------- |
| [compute protection scopes](../api/userprotectionscopecontainer-compute.md) | [policyUserScope](../resources/policyuserscope.md) collection | Compute the data protection policies applicable to the specific user. |

## Properties

None. This type primarily serves as a container for actions.

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.userProtectionScopeContainer",
  "openType": false
}-->
``` json
{
  "@odata.type": "#microsoft.graph.userProtectionScopeContainer"
}
```
