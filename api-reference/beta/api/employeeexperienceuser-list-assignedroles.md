---
title: "List engagementRole objects"
description: "Get a list of the engagementRole objects and their properties."
author: "richafnu"
ms.date: 03/27/2025
ms.localizationpriority: medium
ms.subservice: "viva-engage"
doc_type: apiPageType
---

# List assigned roles

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get all roles assigned to a user in Viva Engage.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "employeeexperienceuser-list-assignedroles-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/employeeexperienceuser-list-assignedroles-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /me/employeeExperience/assignedRoles
GET /users/{userId}/employeeExperience/assignedRoles
```
>**Note:** In the API above, the userId represents the office user id for a user.

[!INCLUDE [me-apis-sign-in-note](../includes/me-apis-sign-in-note.md)]

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [engagementRole](../resources/engagementrole.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_engagementrole"
}
-->
``` http
GET https://graph.microsoft.com/beta/employeeExperience/roles
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.engagementRole"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
        "id": "ec791927-d09f-4f91-bd76-d3b05e1c1a31",
        "displayName": "Network Admin"
    },
    {
        "id": "b0de8e6d-4457-4722-bdc5-5a32a09bf064",
        "displayName": "Hybrid Admin"
    },
    {
        "id": "77aa7d76-bdf6-4cc0-80e2-fd1ac5a28471",
        "displayName": "Corporate Communicator"
    }
  ]
}
```

