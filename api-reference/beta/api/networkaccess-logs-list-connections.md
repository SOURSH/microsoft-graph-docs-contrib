---
title: "List connections"
description: "Get a list of the connection objects and their properties."
author: "miritsadon"
ms.date: 04/20/2025
ms.localizationpriority: medium
ms.subservice: "entra-id"
doc_type: apiPageType
---

# List connections

Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of [connection](../resources/networkaccess-connection.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "networkaccess-logs-list-connections-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/networkaccess-logs-list-connections-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /networkAccess/logs/connections
```

## Optional query parameters

This method supports the following OData query parameters to help customize the response:
- `$filter` to filter results by connection properties. Example: `status eq 'active'`
- `$orderby` to sort results by properties. Example: `createdDateTime desc`
- `$top` and `$skip` for pagination
- `$select` to specify which properties to include

For general information about query parameters, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [microsoft.graph.networkaccess.connection](../resources/networkaccess-connection.md) objects in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "list_connection"
}
-->
``` http
GET https://graph.microsoft.com/beta/networkAccess/logs/connections
```

### Response
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.networkaccess.connection)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.networkaccess.connection",
      "id": "6e3f9793-04a3-9473-f647-29adc069debb",
      "createdDateTime": "2025-04-20T10:00:00Z",
      "tenantId": "contoso.onmicrosoft.com",
      "lastUpdateDateTime": "2025-04-20T10:15:00Z",
      "endDateTime": "2025-04-20T10:30:00Z",
      "status": "active",
      "trafficType": "internet",
      "transactionCount": 10,
      "transactionBlockCount": 1,
      "sentBytes": 15360,
      "receivedBytes": 30720,
      "destinationIp": "13.107.6.152",
      "destinationPort": 443,
      "destinationFqdn": "graph.microsoft.com",
      "userId": "87d349ed-44d7-43e1-9a83-5f2406dee5bd",
      "sourceIp": "192.168.1.100",
      "sourcePort": 54321,
      "initiatingProcessName": "msedge.exe",
      "deviceId": "5b7c0300-45c3-487c-a6d3-a3098cb6e51b",
      "deviceOperatingSystem": "Windows",
      "deviceOperatingSystemVersion": "10.0.19045",
      "agentVersion": "1.0.2307.15",
      "applicationSnapshot": {
        "@odata.type": "microsoft.graph.networkaccess.applicationSnapshot",
        "appId": "00000003-0000-0000-c000-000000000000"
      },
      "privateAccessDetails": {
        "@odata.type": "microsoft.graph.networkaccess.privateAccessDetails",
        "connectorId": "e1a83a2c-5689-4f1c-b8ba-698606c784c9",
        "connectorName": "connector-1",
        "connectorIp": "10.0.0.100",
        "connectionStatus": "active",
        "accessType": "privateAccess",
        "processingRegion": "westus2"
      },
      "deviceCategory": "client",
      "userPrincipalName": "johndoe@contoso.com",
      "transportProtocol": "tcp",
      "networkProtocol": "ipv4",
      "popProcessingRegion": "westus2"
    },
    {
      "@odata.type": "#microsoft.graph.networkaccess.connection",
      "id": "7f4e8694-15b4-8584-g758-30bdc179efcc",
      "createdDateTime": "2025-04-20T10:05:00Z",
      "tenantId": "contoso.onmicrosoft.com",
      "lastUpdateDateTime": "2025-04-20T10:20:00Z",
      "status": "active",
      "trafficType": "microsoft365",
      "transactionCount": 5,
      "transactionBlockCount": 0,
      "sentBytes": 8192,
      "receivedBytes": 16384,
      "destinationIp": "40.99.4.10",
      "destinationPort": 443,
      "destinationFqdn": "outlook.office365.com",
      "userId": "87d349ed-44d7-43e1-9a83-5f2406dee5bd",
      "sourceIp": "192.168.1.100",
      "sourcePort": 54322,
      "initiatingProcessName": "outlook.exe",
      "deviceId": "5b7c0300-45c3-487c-a6d3-a3098cb6e51b",
      "deviceCategory": "client",
      "userPrincipalName": "johndoe@contoso.com",
      "transportProtocol": "tcp",
      "networkProtocol": "ipv4",
      "popProcessingRegion": "westus2"
    }
  ]
}
