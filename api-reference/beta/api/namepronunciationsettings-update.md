---
title: "Update namePronunciationSettings"
description: "Update the properties of a **namePronunciationSettings** object."
author: "fondieki"
ms.localizationpriority: medium
ms.subservice: "people"
doc_type: apiPageType
---

# Update namePronunciationSettings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [namePronunciationSettings](../resources/namepronunciationsettings.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "namepronunciationsettings_update" } -->
[!INCLUDE [permissions-table](../includes/permissions/namepronunciationsettings-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /admin/people/namePronunciation
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|isEnabledInOrganization|Boolean|`true` to enable name pronunciation in the organization; otherwise, `false`. The default value is `false`. Required.|



## Response

If successful, this method returns a `200 OK` response code and an updated [namePronunciationSettings](../resources/namepronunciationsettings.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_namepronunciationsettings"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/admin/people/namePronunciation
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.namePronunciationSettings",
  "isEnabledInOrganization": true
}
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.namePronunciationSettings"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.namePronunciationSettings",
  "id": "5a5ec63c-48e0-993a-788a-d4e9fb4f479e",
  "isEnabledInOrganization": true
}
```

