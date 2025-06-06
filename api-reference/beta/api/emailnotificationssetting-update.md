---
title: "Update emailNotificationsSetting"
description: "Update the properties of an emailNotificationsSetting object."
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
ms.date: 05/29/2025
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS subservice. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
doc_type: apiPageType
---

# Update emailNotificationsSetting

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of an emailNotificationsSetting object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "emailnotificationssetting-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/emailnotificationssetting-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /solutions/backupRestore/emailNotificationsSetting
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


**TODO: Remove properties that don't apply**
|Property|Type|Description|
|:---|:---|:---|
|isEnabled|Boolean|**TODO: Add Description** Required.|
|additionalEvents|notificationEventsType|**TODO: Add Description**. The possible values are: `none`, `restoreAndPolicyUpdates`, `unknownFutureValue`. Required.|
|recipients|[notificationRecipients](../resources/notificationrecipients.md)|**TODO: Add Description** Required.|



## Response

If successful, this method returns a `200 OK` response code and an updated [emailNotificationsSetting](../resources/emailnotificationssetting.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_emailnotificationssetting"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/solutions/backupRestore/emailNotificationsSetting
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.emailNotificationsSetting",
  "isEnabled": "Boolean",
  "additionalEvents": "String",
  "recipients": {
    "@odata.type": "microsoft.graph.notificationRecipients"
  }
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

{
  "@odata.type": "#microsoft.graph.emailNotificationsSetting",
  "id": "03960da0-81a4-4f5d-af4d-787a905ef8e3",
  "isEnabled": "Boolean",
  "additionalEvents": "String",
  "recipients": {
    "@odata.type": "microsoft.graph.notificationRecipients"
  }
}
```

