---
title: "List teamsUserConfiguration objects"
description: "Get user configurations for all Teams users belonging to a tenant."
author: "Prasanna Patil"
ms.date: 03/19/2025
ms.localizationpriority: medium
ms.subservice: "Teams"
doc_type: apiPageType
---

# List teamsUserConfiguration objects

Namespace: microsoft.graph.teamsAdministration

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get user configurations for all Teams users belonging to a tenant.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "teamsadministration-teamsadminroot-list-userconfigurations-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/teamsadministration-teamsadminroot-list-userconfigurations-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /admin/teams/userConfigurations
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

If successful, this method returns a `200 OK` response code and a collection of [teamsUserConfiguration](../resources/teamsuserconfiguration.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_teamsuserconfiguration"
}
-->
``` http
GET https://graph.microsoft.com/beta/admin/teams/userConfigurations
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.teamsAdministration.teamsUserConfiguration"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.teamsAdministration.teamsUserConfiguration",
      "id": "5c802b19-3600-83f1-1767-7b9edc7f38ab",
      "userPrincipalName": "String",
      "tenantId": "String",
      "effectivePolicyAssignments": [
        {
          "@odata.type": "microsoft.graph.teamsAdministration.effectivePolicyAssignment"
        }
      ],
      "telephoneNumbers": [
        {
          "@odata.type": "microsoft.graph.teamsAdministration.assignedTelephoneNumber"
        }
      ],
      "isEnterpriseVoiceEnabled": "Boolean",
      "featureTypes": [
        "String"
      ],
      "accountType": "String",
      "createdDateTime": "String (timestamp)",
      "modifiedDateTime": "String (timestamp)"
    }
  ]
}
```

