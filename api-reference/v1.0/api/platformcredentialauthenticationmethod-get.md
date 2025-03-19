---
title: "Get platformCredentialAuthenticationMethod"
description: "Read the properties and relationships of a platformCredentialAuthenticationMethod object."
author: "ploegert"
ms.date: 02/28/2025
ms.localizationpriority: medium
ms.subservice: "entra-sign-in"
doc_type: apiPageType
---

# Get platformCredentialAuthenticationMethod

Namespace: microsoft.graph

Read the properties and relationships of a [platformCredentialAuthenticationMethod](../resources/platformcredentialauthenticationmethod.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

### Permissions acting on self

|Permission type      | Permissions (from least to most privileged)              |
|:---------------------------------------|:-------------------------|
| Delegated (work or school account)     | UserAuthenticationMethod.Read, UserAuthenticationMethod.ReadWrite |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Not supported. |

### Permissions acting on other users

|Permission type      | Permissions (from least to most privileged)              |
|:---------------------------------------|:-------------------------|
| Delegated (work or school account)     | UserAuthenticationMethod.Read.All, UserAuthenticationMethod.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | UserAuthenticationMethod.Read.All, UserAuthenticationMethod.ReadWrite.All |

[!INCLUDE [rbac-authentication-methods-apis-read-others](../includes/rbac-for-apis/rbac-authentication-methods-apis-read-others.md)]

## HTTP request

To read details of your own Platform Credential authentication method:
<!-- { "blockType": "ignored" } -->
``` http
GET /me/authentication/platformCredentialMethods/{platformCredentialAuthenticationMethodId}
```

To read details of your own or another user's Platform Credential authentication method:
<!-- { "blockType": "ignored" } -->
``` http
GET /users/{id | userPrincipalName}/authentication/platformCredentialMethods/{platformCredentialAuthenticationMethodId}
```

## Optional query parameters

This method supports the $expand query parameter to customize the response. For general information, see [OData query parameters](/graph/query-parameters).

To read the **device** navigation property for another user, specify it in an `$expand` query as follows: `/users/{id}/authentication/platformCredentialMethods/{id}?$expand=device`.

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [platformCredentialAuthenticationMethod](../resources/platformcredentialauthenticationmethod.md) object in the response body.

## Examples

### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "get_platformcredentialauthenticationmethod_1",
  "sampleKeys": ["R18B3t8Ogh9XIOGmPt81d6p_KXJs1YTxfGgGqeVFJSM1"]
}-->

``` http
GET https://graph.microsoft.com/beta/me/authentication/platformCredentialMethods/R18B3t8Ogh9XIOGmPt81d6p_KXJs1YTxfGgGqeVFJSM1
```

### Response

The following example shows the response.

**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.platformCredentialAuthenticationMethod"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json
 
{
  "value": 
    {
      "@odata.type": "#microsoft.graph.platformCredentialAuthenticationMethod",
      "id": "R18B3t8Ogh9XIOGmPt81d6p_KXJs1YTxfGgGqeVFJSM1",       
      "displayName": "My Macbook Pro",      
      "creationDateTime": "2023-09-02T04:16:49Z"
      "keyStrength": "normal"
      "platform": "macOS"
    }
}
```
