---
title: "reports: connectionSummaries"
description: "Represent a report of connections count per traffic type."
author: "miritsadon"
ms.date: 04/20/2025
ms.localizationpriority: medium
ms.subservice: "entra-global-secure-access"
doc_type: apiPageType
---

# reports: connectionSummaries

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

An API part of Global Secure Access (GSA) product, reports of connections count per traffic type: Private/Internet/Microsoft.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "networkaccess-reports-getconnectionsummaries-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/networkaccess-reports-getconnectionsummaries-permissions.md)]

[!INCLUDE [rbac-global-secure-access-apis-read](../includes/rbac-for-apis/rbac-global-secure-access-apis-read.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /networkAccess/reports/getConnectionSummaries(startDateTime='{startDateTime}',endDateTime='{endDateTime}')
```

## Function parameters
In the request URL, provide the following query parameters with values.

|Parameter|Type|Description|
|:---|:---|:---|
|startDateTime|DateTimeOffset|Start of the period for aggregating connections.|
|endDateTime|DateTimeOffset|End of the period for aggregating connections.|

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [connectionSummary](../resources/networkaccess-connectionsummary.md) objects in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "get_connection_summaries"
}
-->
``` http
GET https://graph.microsoft.com/beta/networkAccess/reports/getConnectionSummaries(startDateTime='2025-04-19T00:00:00Z',endDateTime='2025-04-20T00:00:00Z')
```

### Response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.networkaccess.connectionSummary)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.networkaccess.connectionSummary",
      "trafficType": "internet",
      "totalCount": 150
    },
    {
      "@odata.type": "#microsoft.graph.networkaccess.connectionSummary",
      "trafficType": "microsoft365",
      "totalCount": 75
    },
    {
      "@odata.type": "#microsoft.graph.networkaccess.connectionSummary",
      "trafficType": "private",
      "totalCount": 25
    }
  ]
}
```
