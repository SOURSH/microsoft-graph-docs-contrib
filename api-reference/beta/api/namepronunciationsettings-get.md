---
title: "Get namePronunciationSettings"
description: "Read the properties and relationships of a namePronunciationSettings object."
author: "fondieki"
ms.localizationpriority: medium
ms.subservice: "people"
doc_type: apiPageType
---

# Get namePronunciationSettings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [namePronunciationSettings](../resources/namepronunciationsettings.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "namepronunciationsettings_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/namepronunciationsettings-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /admin/people/namePronunciation
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [namePronunciationSettings](../resources/namepronunciationsettings.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "get_namepronunciationsettings"
}
-->
``` http
GET https://graph.microsoft.com/beta/admin/people/namePronunciation
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
  "value": {
    "@odata.type": "#microsoft.graph.namePronunciationSettings",
    "id": "5a5ec63c-48e0-993a-788a-d4e9fb4f479e",
    "isEnabledInOrganization": true
  }
}
```

