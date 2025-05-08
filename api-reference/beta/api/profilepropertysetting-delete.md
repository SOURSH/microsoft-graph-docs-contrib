---
title: "Delete profilePropertySetting"
description: "Delete a profilePropertySetting object."
author: "rwaithera"
ms.date: 05/02/2025
ms.localizationpriority: medium
ms.subservice: "people"
doc_type: apiPageType
---

# Delete profilePropertySetting

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [profilePropertySetting](../resources/profilepropertysetting.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "profilepropertysetting-delete-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/profilepropertysetting-delete-permissions.md)]

>**Note:** Using delegated permissions for this operation requires the signed-in user to have the [People Administrator](/entra/identity/role-based-access-control/permissions-reference#people-administrator) role.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /admin/people/profilePropertySettings/{profilePropertySettingId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "delete_profilepropertysetting"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/admin/people/profilePropertySettings/00000000-0000-0000-0000-000000000001
```

### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

