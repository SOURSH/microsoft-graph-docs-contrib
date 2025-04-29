---
title: "integratedApplicationMetadata resource type"
toc.title: "integratedApplicationMetadata resource type (preview)"
description: "Represents metadata about the application integrated with Purview data security APIs."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# integratedApplicationMetadata resource type

Namespace: microsoft.dataClassificationService.contract

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents metadata about the application integrated with Purview data security APIs.

For example, [protectionScopes/compute](./../api/userdatasecurityandgovernance-post-protectionscopes.md), [processContent](../api/userdatasecurityandgovernance-post-processcontent.md), and [processContentAsync](./../api/tenantdatasecurityandgovernance-post-processcontentasync.md).

## Properties

| Property | Type   | Description                                      |
| :------- | :----- | :----------------------------------------------- |
| name     | String | The name of the integrated application.        |
| version  | String | The version number of the integrated application. |

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.integratedApplicationMetadata",
  "openType": false
}-->
``` json
{
  "@odata.type": "#microsoft.graph.integratedApplicationMetadata",
  "name": "String",
  "version": "String"
}
```
