---
title: "crossTenantIdentitySyncPolicyPartner: restore"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
ms.date: 06/18/2025
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS subservice. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
doc_type: apiPageType
---

# crossTenantIdentitySyncPolicyPartner: restore

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "crosstenantidentitysyncpolicypartner-restore-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/crosstenantidentitysyncpolicypartner-restore-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /policies/deletedItems/crossTenantSyncPolicyPartners/{crossTenantIdentitySyncPolicyPartnerId}/restore
POST /policies/crossTenantAccessPolicy/partners/{crossTenantAccessPolicyConfigurationPartnerId}/identitySynchronization/restore
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this action returns a `200 OK` response code and a [crossTenantIdentitySyncPolicyPartner](../resources/crosstenantidentitysyncpolicypartner.md) in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "crosstenantidentitysyncpolicypartnerthis.restore"
}
-->
``` http
POST https://graph.microsoft.com/beta/policies/deletedItems/crossTenantSyncPolicyPartners/{crossTenantIdentitySyncPolicyPartnerId}/restore
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.crossTenantIdentitySyncPolicyPartner"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.crossTenantIdentitySyncPolicyPartner",
    "deletedDateTime": "String (timestamp)",
    "tenantId": "String (identifier)",
    "displayName": "String",
    "externalCloudAuthorizedApplicationId": "String",
    "userSyncInbound": {
      "@odata.type": "microsoft.graph.crossTenantUserSyncInbound"
    }
  }
}
```
