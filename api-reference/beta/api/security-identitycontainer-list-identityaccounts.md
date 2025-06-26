---
title: "List identityAccounts objects"
description: "Get a list of the identityAccounts objects and their properties."
author: "SamuelBenichou"
ms.date: 06/22/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: apiPageType
---

# List identityAccounts objects

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [identityAccounts](../resources/security-identityaccounts.md) objects and their properties.

## Permissions

One of the following permissions is required to call this API. Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "security-identitycontainer-list-identityaccounts-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/security-identitycontainer-list-identityaccounts-permissions.md)]

[!INCLUDE [rbac-security-identity-accounts-apis](../includes/rbac-for-apis/rbac-security-identity-accounts-apis.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/identities/identityAccounts
```

## Optional query parameters

This method supports the `$filter` and `$select` OData query parameters to help customize the response. For more information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [identityAccounts](../resources/security-identityaccounts.md) objects in the response body.

## Examples

### Example 1: Retrieve details of identity accounts

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_identityaccounts"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/identities/identityAccounts
```

#### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.identityAccounts"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "00104216-0539-4838-88b1-55baafdc296b",
      "displayName": "accoundJon",
      "domain": "domain1.test.local",
      "onPremisesSecurityIdentifier": "S-1-5-21-989687458-3461180213-172365591-281652",
      "cloudSecurityIdentifier": "S-1-12-4-2492432728-1225839317-3974870967-847981844",
      "isEnabled": true,
      "accounts": [
        {
          "provider": "ActiveDirectory",
          "identifier": "256db173-930a-4991-9061-0d51a9a93ba5",
        },
        {
          "provider": "Entra",
          "identifier": "69dfa3ea-1295-4e2c-b469-59564581143d",
        },
        {
          "provider": "Okta",
          "identifier": "878a6911-f3da-41eb-a895-1d46fa054d3e",
          "actions": ["revokeAllSessions"]
        }
      ]
    },
    {
      "id": "00054217-0539-4838-88b1-55baafdc296b",
      "displayName": "account",
      "domain": "domain1.test.local",
      "onPremisesSecurityIdentifier": "S-1-5-21-989687458-3461180213-172365591-391652",
      "cloudSecurityIdentifier": "S-1-12-4-2492432728-1225839317-3974870967-847981844",
      "isEnabled": true,
      "accounts": [
        {
          "provider": "Okta",
          "identifier": "878a6911-f3da-41eb-a895-1d46fa054d3e",
          "actions": ["revokeAllSessions"]
        }
      ]
    }
  ]
}
```

### Example 2: Retrieve details of identity accounts that match a security identifier

#### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_identityaccounts_filtered"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/identities/identityAccounts?$filter=onPremisesSecurityIdentifier eq 'S-1-5-21-989687458-3461180213-172365591-281652'
```

#### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.identityAccounts"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "00104216-0539-4838-88b1-55baafdc296b",
      "displayName": "accoundJon",
      "domain": "domain1.test.local",
      "onPremisesSecurityIdentifier": "S-1-5-21-989687458-3461180213-172365591-281652",
      "cloudSecurityIdentifier": "S-1-12-4-2492432728-1225839317-3974870967-847981844",
      "isEnabled": true,
      "accounts": [
        {
          "provider": "ActiveDirectory",
          "identifier": "256db173-930a-4991-9061-0d51a9a93ba5",
        },
        {
          "provider": "Entra",
          "identifier": "69dfa3ea-1295-4e2c-b469-59564581143d",
        },
        {
          "provider": "Okta",
          "identifier": "878a6911-f3da-41eb-a895-1d46fa054d3e",
          "actions": ["revokeAllSessions"]
        }
      ]
    }
  ]
}
```