---
title: "Update copilotAminLimitedMode"
description: "Update the properties of a copilotAdminLimitedMode object."
author: "gautamjain14"
ms.localizationpriority: medium
ms.subservice: "meetings-copilot"
doc_type: apiPageType
---

# Update copilotAdminLimitedMode

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [copilotAdminLimitedMode](../resources/copilotadminlimitedmode.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "copilotadminlimitedmode-update-permissions"
}
-->
> **Note:** Global admin or Global reader permission is required to call this API.

<!-- { "blockType": "permissions", "name": "copilotadminlimitedmode_update" } -->
[!INCLUDE [permissions-table](../includes/permissions/copilotadminlimitedmode-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /copilot/admin/settings/limitedMode
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

|Property|Type|Description|
|:---|:---|:---|
|isEnabledForGroup|Boolean|Enables the user to be in limited mode for Copilot in Teams meetings. When copilotLimitedMode=true, users in this mode can ask any questions, but Copilot doesn't respond to certain questions related to inferring emotions, behavior, or judgments. When copilotLimitedMode=false, the current mode for Copilot, it responds to any types of questions grounded to the meeting conversation. The default value is `false`.|
|groupId|String|The ID of a Microsoft Entra group, of which the value of `isEnabledForGroup` is applied value for its members. The default value is `null`. This parameter is optional. If `isEnabledForGroup` is set to true, the `groupId` value must be provided for the copilotLimitedMode to be enabled for the members of the group.|

## Response

If successful, this method returns a `200 OK` response code and an updated [copilotAdminLimitedMode](../resources/copilotadminlimitedmode.md) object in the response body.

API can return additional HTTP status codes such as `403 Forbidden`, `500 Internal Server Error`, or `429 Too Many Requests`.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_copilotadminlimitedmode"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/copilot/admin/settings/limitedMode
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.copilotAdminLimitedMode",
  "isEnabledForGroup": "Boolean",
  "groupId": "String"
}
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json
```

