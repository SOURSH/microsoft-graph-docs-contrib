---
title: "scopeBase resource type"
toc.title: "scopeBase resource type (preview)"
description: "Abstract base type representing a scope identifier for users, groups, or the tenant within policy bindings."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# scopeBase resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Abstract base type representing a scope identifier for users, groups, or the tenant within policy bindings. Derived types (`userScope`, `groupScope`, `tenantScope`) specify the type of scope.

## Properties

| Property | Type   | Description                                                                                        |
| :------- | :----- | :------------------------------------------------------------------------------------------------- |
| identity | String | The identifier for the scope. This could be a user ID, group ID, or a keyword like "All" for tenant scope. |

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type. 
>**Note** This is an abstract type and won't be instantiated directly.
<!-- {
  "blockType": "resource",
  "abstract": true,
  "@odata.type": "microsoft.graph.scopeBase",
  "openType": false
}-->
``` json
{
  "@odata.type": "#microsoft.graph.scopeBase",
  "identity": "String"
  // Derived types specify the @odata.type, e.g., "#microsoft.graph.userScope"
}
```
