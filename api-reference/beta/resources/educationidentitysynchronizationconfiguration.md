---
title: "educationIdentitySynchronizationConfiguration resource type (deprecated)"
description: "Abstract base class for all school data profile identity synchronization configurations. The derived classes define the behavior for synchronizing identities. The following are the derived types."
author: "mmast-msft"
ms.localizationpriority: medium
ms.subservice: "education"
doc_type: resourcePageType
ms.date: 07/23/2024
---

# educationIdentitySynchronizationConfiguration resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [educationsynchronizationprofile-deprecate](../includes/education-deprecate-educationsynchronizationprofile.md)]

Abstract base class for all school data profile identity synchronization configurations. The derived classes define the behavior for synchronizing identities. The following are the derived types.

## Derived types

| Type                                                                                | Description                                                                         |
| :---------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------- |
| [educationIdentityMatchingConfiguration](educationidentitymatchingconfiguration.md) | Use this type to **match existing** user accounts in Microsoft Entra ID. |
| [educationIdentityCreationConfiguration](educationidentitycreationconfiguration.md) | Use this type to **create new** user accounts in Microsoft Entra ID.                              |

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
   "isAbstract":true,
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationIdentitySynchronizationConfiguration"
}-->

```json
{}
```
