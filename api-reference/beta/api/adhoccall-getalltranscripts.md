---
title: "adhocCall: getAllTranscripts"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
ms.date: 07/04/2025
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS subservice. See [topic-level metadata reference](https://eng.ms/docs/products/microsoft-graph-service/microsoft-graph/document-apis/metadata)**"
doc_type: apiPageType
---

# adhocCall: getAllTranscripts

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "adhoccall-getalltranscripts-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/adhoccall-getalltranscripts-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /communications/adhocCalls/getAllTranscripts
GET /users/{usersId}/adhocCalls/getAllTranscripts
```

## Function parameters
In the request URL, provide the following query parameters with values.

|Parameter|Type|Description|
|:---|:---|:---|
|userId|String|**TODO: Add Description**|
|startDateTime|DateTimeOffset|**TODO: Add Description**|
|endDateTime|DateTimeOffset|**TODO: Add Description**|


## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a [callTranscript](../resources/calltranscript.md) collection in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "adhoccallthis.getalltranscripts"
}
-->
``` http
GET https://graph.microsoft.com/beta/communications/adhocCalls/getAllTranscripts(userId='parameterValue',startDateTime=String (timestamp),endDateTime=String (timestamp))
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(Microsoft.Teams.GraphSvc.callTranscript)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#Microsoft.Teams.GraphSvc.callTranscript",
      "id": "String (identifier)",
      "meetingId": "String",
      "callId": "String",
      "contentCorrelationId": "String",
      "meetingOrganizer": {
        "@odata.type": "microsoft.graph.identitySet"
      },
      "transcriptContentUrl": "String",
      "createdDateTime": "String (timestamp)",
      "endDateTime": "String (timestamp)",
      "content": "Stream",
      "metadataContent": "Stream"
    }
  ]
}
```

