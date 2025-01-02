---
title: "List allMembers"
description: "List all members in a team channel."
author: "sumitgupta"
ms.localizationpriority: high
ms.subservice: "teams"
doc_type: apiPageType
ms.date: 12/20/2024
---

# List allMembers

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a list of [conversationMember](../resources/conversation member.md) objects from a team [channel](../resources/channel.md). It supports all types of channels. In the case of shared channels, it includes all cross-tenant and cross-team members in a channel.

> [!NOTE]
> The membership IDs returned by the server must be treated as opaque strings. The client should not try to parse or make any assumptions about these resource IDs.
> In the future, membership results could be mapped to users from different tenants, as indicated in the response. The client should not assume that all members are from the current tenant.
> [!NOTE] 
> Currently, pagination is not supported, a maximum of 999 members can be returned in the response. If there are more than 999 members in a channel, the API only fetches the first 999 members.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Least privileged permissions       | Higher privileged permissions |
|:--------------------|:---------------------------------------------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Group.Read.All | ChannelMember.ReadWrite.All, ChannelMember.Read.AllChannelMember.Read.All |
|Delegated (personal Microsoft account) | Not supported | Not supported |
|Application | ChannelMember.Read.All | ChannelMember.ReadWrite.All |

## HTTP request

<!-- { "blockType" : "ignored" } -->

### Optional query parameters

This method supports the `$filter` and `$select` [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers

| Header       | Value |
|:---------------|:--------|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a list of [conversationMember](../resources/conversationmember.md) objects in the response body.

## Examples

### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "channel-list-allMembers",
  "sampleKeys": ["2ab9c796-2902-45f8-b712-7c5a63cf41c4", "19%3A20bc1df46b1148e9b22539b83bc66809%40thread.skype"]
} -->
```msgraph-interactive
GET https://graph.microsoft.com/beta/teams/2ab9c796-2902-45f8-b712-7c5a63cf41c4/channels/19%3A20bc1df46b1148e9b22539b83bc66809%40thread.skype/allMembers
```


### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.conversationMember"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
"@odata.context": "https://graph.microsoft.com/v1.0/$metadata#teams('2ab9c796-2902-45f8-b712-7c5a63cf41c4')/channels('19%3A20bc1df46b1148e9b22539b83bc66809%40thread.skype')/allMembers",
"@odata.count": 2,
    "value": [
        {
        "@odata.type": "#microsoft.graph.aadUserConversationMember",
        "id": "MmFiOWM3OTYtMjkwMi00NWY4LWI3MTItN2M1YTYzY2Y0MWM0IyNlZWY5Y2IzNi0wNmRlLTQ2OWItODdjZC03MGY0Y2JlMzJkMTQ=",
        "roles": [
            "Member"
        ],
        "displayName": "Caleb Foster",
        "userId": "eef9cb36-06de-469b-87cd-70f4cbe32d14",
        "email": "calfos@contoso.com",
        "tenantId": "ar8133445-c7e2-418a-8803-0e68d4b88607"
        },
        {
        "@odata.type": "#microsoft.graph.aadUserConversationMember",
        "id": "MmFiOWM3OTYtMjkwMi00NWY4LWI3MTItN2M1YTYzY2Y0MWM0IyNiMzI0NmY0NC1jMDkxLTQ2MjctOTZjNi0yNWIxOGZhMmM5MTA=",
        "roles": [
            "Owner"
        ],
        "displayName": "Eric Solomon",
        "userId": "b3246f44-c091-4627-96c6-25b18fa2c910",
        "email": "ericsol@contoso.com",
        "tenantId": "df81db53-c7e2-418a-8803-0e68d4b88607"
        }
    ]
}

```
