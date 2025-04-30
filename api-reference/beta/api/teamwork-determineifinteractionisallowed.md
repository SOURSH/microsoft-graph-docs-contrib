---
title: "teamwork: determineIfInteractionIsAllowed"
description:  Determine if the specified interaction is allowed between the caller and the specified users.
author: eddie-lee-msft
ms.localizationpriority: medium
ms.subservice: teams
doc_type: apiPageType
ms.date: 04/05/2024
---

# teamwork: determineIfInteractionIsAllowed

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Determines if a specified Microsoft Teams interaction is allowed between the caller and a specified set of users.

> **Note**: All requests to this API are logged in the M365 audit logs of the tenants where the targeted users (`users` parameter) exist. Refer to [this documentation](https://learn.microsoft.com/en-us/purview/audit-log-activities#microsoft-teams-activities) and search for `CreateThreadProbe` to learn more about what is logged.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "teamwork_sendactivitynotificationtorecipients" } -->
[!INCLUDE [permissions-table](../includes/permissions/teamwork-determineifinteractionisallowed-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
POST /teamwork/determineIfInteractionIsAllowed
```

## Request headers

| Name          | Description                 |
| :------------ | :-------------------------- |
| Authorization | Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).   |
| Content-Type  | application/json. Required. |

## Request body

In the request body, supply JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

| Parameter          | Type                                                               | Description                                                  |
| :----------------- | :----------------------------------------------------------------- | :----------------------------------------------------------- |
| interactionType    | [teamworkInteractionType](../resources/teamworkinteractiontype.md) | The type of interaction on Microsoft Teams. |
| users              | [identity](../resources/identity.md) collection                    | The collection of target users with which the caller wants to determine whether interaction is allowed. Supported derived types are [teamworkUserIdentity](../resources/teamworkuseridentity.md) and [emailIdentity](../resources/emailidentity.md). |

## Response

If successful, this action returns a `200 OK` response code and either a `true` or `false` value in the response body.

## Examples

### Example 1: Determine if the current user can create a chat with a user in the same tenant, using their ID.

The following example shows a request that determines whether the current user (authenticated via. delegated context) can create a chat with one other user in the same tenant, by specifying the other user's ID.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "teamwork_determineIfInteractionIsAllowed_1"
}-->
``` http
POST https://graph.microsoft.com/beta/teamwork/determineIfInteractionIsAllowed

{
  "users":
  [
    {
      "@odata.type": "microsoft.graph.teamworkUserIdentity",
      "id": "59b5bc69-ca73-4ffd-a2e0-88a79115d13b"
    }
  ],
  "interactionType": "createChat"
}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Edm.Boolean",
  "value": true
}
```

### Example 2: Determine if the current user can create a chat with a user in another tenant, using their ID and tenant ID.

The following example shows a request that determines whether the current user (authenticated via. delegated context) can create a chat with one other user in a different tenant, using the other user's ID and tenant ID.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "teamwork_determineIfInteractionIsAllowed_2"
}-->
``` http
POST https://graph.microsoft.com/beta/teamwork/determineIfInteractionIsAllowed

{
  "users":
  [
    {
      "@odata.type": "microsoft.graph.teamworkUserIdentity",
      "id": "59b5bc69-ca73-4ffd-a2e0-88a79115d13b",
      "tenantId": "b11186db-6149-4b3d-95ad-23c9e1bf6853"
    }
  ],
  "interactionType": "createChat"
}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Edm.Boolean",
  "value": true
}
```

### Example 3: Determine if the current user can create a chat with another user, using their user principal name.

The following example shows a request that determines whether the current user (authenticated via. delegated context) can create a chat with one other user, by specifying the other user's user principal name. When specifying the user principal name of a user in another tenant, `tenantId` does not need to be specified.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "teamwork_determineIfInteractionIsAllowed_3"
}-->
``` http
POST https://graph.microsoft.com/beta/teamwork/determineIfInteractionIsAllowed

{
  "users":
  [
    {
      "@odata.type": "microsoft.graph.teamworkUserIdentity",
      "userPrincipalName": "maia@contoso.com"
    }
  ],
  "interactionType": "createChat"
}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Edm.Boolean",
  "value": true
}
```

### Example 4: Determine if the current user can create a chat with another user, using their email.

The following example shows a request that determines whether the current user (authenticated via. delegated context) can create a chat with one other user, by specifying the other user's email.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "teamwork_determineIfInteractionIsAllowed_4"
}-->
``` http
POST https://graph.microsoft.com/beta/teamwork/determineIfInteractionIsAllowed

{
  "users":
  [
    {
      "@odata.type": "microsoft.graph.emailIdentity",
      "email": "LauraW@contoso.com"
    }
  ],
  "interactionType": "createChat"
}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Edm.Boolean",
  "value": true
}
```

### Example 5: Determine if the current user can create a chat with three other users.

The following example shows a request that determines whether the current user (authenticated via. delegated context) can create a chat with three other users. It uses a mix of the supported `userIdentity` types. In this example, the interaction is not allowed.

#### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "teamwork_determineIfInteractionIsAllowed_5"
}-->
``` http
POST https://graph.microsoft.com/beta/teamwork/determineIfInteractionIsAllowed

{
  "users":
  [
    {
      "@odata.type": "microsoft.graph.emailIdentity",
      "email": "LauraW@foo.com"
    },
    {
      "@odata.type": "microsoft.graph.teamworkUserIdentity",
      "userPrincipalName": "MaiaR@foobar.com"
    },
    {
      "@odata.type": "microsoft.graph.teamworkUserIdentity",
      "id": "bd6a223f-59b5-46dd-90bc-0ddebaf3da5a"
    }
  ],
  "interactionType": "createChat"
}
```

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Edm.Boolean",
  "value": false
}
```