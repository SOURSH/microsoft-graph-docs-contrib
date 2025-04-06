---
title: "timeCard: confirmForUser"
description: "Confirm a specific timeCard for a user."
author: lemikeshifts
ms.date: 03/31/2025
ms.localizationpriority: medium
ms.subservice: teams
doc_type: apiPageType
---

# timeCard: confirmForUser

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Confirm a specific [timeCard](../resources/timecard.md) for a user.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "timecard-confirmforuser-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/timecard-confirmforuser-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /teams/{teamsId}/schedule/timeCards/{timeCardId}/confirmForUser
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the parameters.

The following table lists the parameters that are required when you call this action.

|Parameter|Type|Description|
|:---|:---|:---|
|userId|String|The ID of the user that confirms the **timeCard**.|

## Response

If successful, this action returns a `200 OK` response code and a [timeCard](../resources/timecard.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "timecardthis.confirmforuser"
}
-->
``` http
POST https://graph.microsoft.com/beta/teams/fd15cad8-80f6-484f-9666-3caf695fbf32/schedule/timeCards/TCK_95c44dff-bc12-4de2-8a9a-9772e4421eb4/confirmForUser
Content-Type: application/json

{
  "userId": "2e4b2f0b-e189-4d6c-b273-80b19d6e241a"
}
```

### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
} -->
``` http
HTTP/1.1 204 No Content
```

