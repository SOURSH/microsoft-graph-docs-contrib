---
title: "tenantProtectionScopeContainer resource type"
toc-title: "tenantProtectionScopeContainer resource type (preview)"
description: "Container for tenant-wide protection scope computation actions."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# tenantProtectionScopeContainer resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Container for tenant-wide protection scope computation actions. 

This is accessed via the `protectionScopes` navigation property on [tenantDataSecurityAndGovernance](../resources/tenantdatasecurityandgovernance.md).

## Methods

| Method                                          | Return Type                                                                                     | Description                                                           |
| :---------------------------------------------- | :---------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------- |
| [compute protection scopes](../api/tenantprotectionscopecontainer-compute.md) | [policyTenantScope](../resources/policytenantscope.md) collection | Compute the data protection policies applicable across the tenant.    |

## Properties

None. This type primarily serves as a container for actions.

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.tenantProtectionScopeContainer",
  "openType": false
}-->
``` json
{
  "@odata.type": "#microsoft.graph.tenantProtectionScopeContainer"
}
```
