---
title: "serviceActivity: getMetricsForConditionalAccessBlockedSignIn"
description: "Get the number of user authentication requests, during a specific time period, that satisfy a Conditional Access policy requiring the authentication to be blocked."
author: "Zacharypeng"
ms.localizationpriority: medium
ms.subservice: "entra-monitoring-health"
doc_type: apiPageType
ms.date: 04/04/2024
---

# serviceActivity: getMetricsForConditionalAccessBlockedSignIn
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the number of user authentication requests, during a specific time period, that satisfy a Conditional Access policy requiring the authentication to be blocked.

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "serviceactivity_getmetricsforconditionalaccessblockedsignin" } -->
[!INCLUDE [permissions-table](../includes/permissions/serviceactivity-getmetricsforconditionalaccessblockedsignin-permissions.md)]

[!INCLUDE [rbac-entra-health-service-activity-apis](../includes/rbac-for-apis/rbac-entra-health-service-activity-apis.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /reports/serviceActivity/getMetricsForConditionalAccessBlockedSignIn
```

## Function parameters
In the request URL, provide the following query parameters with values.

|Parameter|Type|Description|
|:---|:---|:---|
|inclusiveIntervalStartDateTime|DateTimeOffset|Sets the starting date and time in UTC. The earliest start time allowed is 30 days in the past. Required.|
|exclusiveIntervalEndDateTime|DateTimeOffset|Sets the ending date and time in UTC. Required|
|aggregationIntervalInMinutes|Int32|Aggregation interval in minutes. The default value is 15, which sets the data to be aggregated into 15-minute sets. Allowed values are 5, 10, 15 and 30. Optional.|

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body
Don't supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a [serviceActivityValueMetric](../resources/serviceactivityvaluemetric.md) collection in the response body.

## Examples

### Request
The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "serviceactivitythis.getmetricsforconditionalaccessblockedsignin"
}
-->
``` http
GET https://graph.microsoft.com/beta/reports/serviceActivity/getMetricsForConditionalAccessBlockedSignIn(inclusiveIntervalStartDateTime=2023-01-01T00:00:00Z,exclusiveIntervalEndDateTime=2023-01-01T00:20:00Z,aggregationIntervalInMinutes=10)
```
---

### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.serviceActivityValueMetric)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/networkAccess/reports/$metadata#Collection(serviceActivityValueMetric)",
  "value": [
    {
      "intervalStartDateTime": "2023-01-10T00:00:00Z",
      "value": 4
    },
    {
      "intervalStartDateTime": "2023-01-10T00:10:00Z",
      "value": 5
    },
    {
      "intervalStartDateTime": "2023-01-10T00:20:00Z",
      "value": 4
    }
  ]
}
```
