---
title: "reportRemoteAssistance action"
description: "A post call to submit the reporting payload"
author: "jaiprakashmb"
ms.localizationpriority: medium
ms.subservice: "intune"
doc_type: apiPageType
ms.date: 08/01/2024
---

# reportRemoteAssistance action

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

A post call to submit the reporting payload

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementServiceConfig.Read.All, DeviceManagementConfiguration.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementServiceConfig.Read.All, DeviceManagementConfiguration.Read.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /deviceManagement/reportRemoteAssistance
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Accept|application/json|

## Request body
In the request body, supply JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Property|Type|Description|
|:---|:---|:---|
|reportingPayload|[remoteAssistanceReporting](../resources/intune-remoteassistance-remoteassistancereporting.md)||



## Response
If successful, this action returns a `204 No Content` response code.

## Example

### Request
Here is an example of the request.
``` http
POST https://graph.microsoft.com/beta/deviceManagement/reportRemoteAssistance

Content-type: application/json
Content-length: 1425

{
  "reportingPayload": {
    "@odata.type": "microsoft.graph.remoteAssistanceReporting",
    "id": "Id value",
    "startDateTime": "2016-12-31T23:58:46.7156189-08:00",
    "endDateTime": "2017-01-01T00:03:30.9241974-08:00",
    "remoteAssistanceSessionType": "fullControl",
    "helperEmail": "Helper Email value",
    "helperTenantId": "Helper Tenant Id value",
    "helperUserId": "Helper User Id value",
    "helperFirstName": "Helper First Name value",
    "helperLastName": "Helper Last Name value",
    "helperOs": "Helper Os value",
    "deviceId": "Device Id value",
    "helperDeviceAadId": "Helper Device Aad Id value",
    "helperDeviceName": "Helper Device Name value",
    "helperEnrollmentState": "enrolled",
    "sharerEmail": "Sharer Email value",
    "sharerTenantId": "Sharer Tenant Id value",
    "sharerUserId": "Sharer User Id value",
    "sharerFirstName": "Sharer First Name value",
    "sharerLastName": "Sharer Last Name value",
    "sharerDeviceAadId": "Sharer Device Aad Id value",
    "sharerDeviceName": "Sharer Device Name value",
    "sharerOs": "Sharer Os value",
    "sharerEnrollmentState": "enrolled",
    "sharerDeviceSerialNumber": "Sharer Device Serial Number value",
    "helperCompanyName": "Helper Company Name value",
    "sessionCreateDateTime": "2016-12-31T23:59:28.4529247-08:00",
    "sessionDiagnosticCode": "Session Diagnostic Code value"
  }
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 204 No Content
```
