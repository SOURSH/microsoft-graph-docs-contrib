---
title: "Get enhancedPersonalizationSetting"
description: "Read the properties and relationships of an enhancedPersonalizationSetting object."
author: "Ross-GH"
ms.date: 04/03/2025
ms.localizationpriority: medium
ms.service: "microsoft-365-copilot"
doc_type: apiPageType
---

# Get enhancedPersonalizationSetting

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of an enhancedPersonalizationSetting object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "enhancedpersonalizationsetting-get-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/enhancedpersonalizationsetting-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /copilot/settings/people/enhancedPersonalization
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

If successful, this method returns a `200 OK` response code and an [enhancedPersonalizationSetting](../resources/enhancedpersonalizationsetting.md) object in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "get_enhancedpersonalizationsetting"
}
-->
``` http
GET https://graph.microsoft.com/beta/copilot/settings/people/enhancedPersonalization
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.enhancedPersonalizationSetting"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.enhancedPersonalizationSetting",
    "id": "51fa8563-8080-0196-2a0e-379155e1f134",
    "isEnabledInOrganization": "Boolean",
    "disabledForGroup": "String"
  }
}
```

