---
title: "Compute userProtectionScopeContainer"
toc.title: "Compute userProtectionScopeContainer"
description: "Compute the data protection policies and actions applicable to a specific user based on their context."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: apiPageType
---

# Compute userProtectionScopeContainer

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

>**Note:** At this time, returned results don't reflect filtering values provided in the request.

Compute the data protection policies and actions applicable to a specific user based on their context. 

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "userprotectionscopecontainer-compute-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/userprotectionscopecontainer-compute-permissions.md)]

## HTTP request

```http
POST /users/me/dataSecurityAndGovernance/protectionScopes/compute
POST /users/{usersId}/dataSecurityAndGovernance/protectionScopes/compute
```

## Request headers

| Name          | Description   |
| :------------ | :------------ |
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
| Content-Type  | application/json. Required. |
| If-None-Match | Optional. This value is used by the API to determine if the policy state has changed since the last call to the API. |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter             | Type                                                                                                                 | Description                                                                                                                                                         |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| activities            | microsoft.graph.userActivityTypes                                                   | Optional. Flags specifying the user activities the calling application supports or is interested. Possible values are `none`, `uploadText`, `uploadFile`, `downloadText`, `downloadFile`. |
| deviceMetadata        | [deviceMetadata](../resources/devicemetadata.md)                                    | Required. Information about the user's device (type, OS) used for contextual policy evaluation.                                                                    |
| integratedAppMetadata | [integratedApplicationMetadata](../resources/integratedapplicationmetadata.md)      | Required. Information about the calling application (name, version) integrating with Microsoft Purview.                                                                    |
| locations             | [policyLocation](../resources/policylocation.md) collection                         | Optional. List of specific locations (domains or URLs) the application is interested in. If provided, results are trimmed to policies covering these locations.     |
| pivotOn               | microsoft.graph.policyPivotProperty                                                 | Optional. Specifies how the results should be aggregated. If omitted or `none`, results might be less aggregated. Possible values are `activity`,`location`, `none`                  |

## Response headers

| Name          | Description   |
| :------------ | :------------ |
| ETag          | An indicator whether admin configured policy state has changed. If the Etag matches the If-None-Match value and you have cached the results of parsing previous results from this API, there is no need to parse the response and cache the parsed results. Cache this value for calls to [process content](../api/userdatasecurityandgovernance-processcontent.md) |

## Response

If successful, this action returns a `200 OK` response code and a collection of [policyUserScope](../resources/policyuserscope.md) objects in the response body. Each object represents a set of locations and activities governed by a common set of policy actions and execution mode for the specified user.

## Example

### Request

The following example computes the protection scope for a user performing text uploads, interested in a specific domain, pivoting the results by activity.

```http
POST https://graph.microsoft.com/beta/users/adele.vance@contoso.com/dataSecurityAndGovernance/protectionScopes/compute
Content-type: application/json

{
  "activities": "uploadText",
  "locations": [
    {
      "@odata.type": "#microsoft.graph.policyLocationDomain",
      "value": "public.contoso.com"
    }
  ],
  "pivotOn": "activity",
  "deviceMetadata": {
    "deviceType": "Managed",
    "operatingSystemSpecifications": {
       "operatingSystemPlatform": "Windows",
       "operatingSystemVersion": "10.0.19045"
    }
  },
  "integratedAppMetadata": {
      "name": "Contoso Browser Helper",
      "version": "1.2.3"
  }
}
```

### Response

The following example shows the response. It indicates that for the `uploadText` activity to `public.contoso.com`, policies require inline evaluation and trigger a `browserRestriction` action (likely blocking uploads based on sensitive content).

> **Note:** The response object shown here might be shortened for readability.

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#Collection(microsoft.graph.policyUserScope)",
  "value": [
    {
      "@odata.type": "#microsoft.graph.policyUserScope",
      "locations": [
        {
          "@odata.type": "#microsoft.graph.policyLocationDomain",
          "value": "public.contoso.com"
        }
      ],
      "activities": "uploadText",
      "executionMode": "evaluateInline",
      "policyActions": [
         {
            "@odata.type": "#microsoft.graph.browserRestrictionAction",
             "action": "browserRestriction",
             "restrictionAction": "block",
             "message": "Uploading sensitive content to this site is blocked by policy.",
             "triggers": ["upload"], // Conceptual trigger, actual values TBD
             "webSiteGroupId": "website-group-guid"
         }
      ]
    }
    // Potentially other scopes for different activities/locations if requested/applicable
  ]
}
```
