---
title: "Update fileStorageContainerTypeRegistration"
description: "Update the properties of a fileStorageContainerTypeRegistration object."
author: "javieralvarezchiang"
ms.date: 06/30/2025
ms.localizationpriority: medium
ms.subservice: "onedrive"
doc_type: apiPageType
---

# Update fileStorageContainerTypeRegistration

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [fileStorageContainerTypeRegistration](../resources/filestoragecontainertyperegistration.md) object.

> [!NOTE]
> * [The settings in the fileStorageContainerType](../resources/filestoragecontainertypesettings.md) control which [settings](../resources/filestoragecontainertyperegistrationsettings.md) can be updated.
> * The updated settings change the behavior of new **fileStorageContainer** objects, but existing containers might require their [settings](../resources/filestoragecontainer.md) to be updated directly. Some settings can't be updated at all. For example, changing storage capability.

ETag is used for optimistic concurrency control. It must match the value from [Create](./filestorage-post-containertyperegistrations.md), [Get](./filestoragecontainertyperegistration-get.md) or the previous Update.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "filestoragecontainertyperegistration-update-permissions"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/filestoragecontainertyperegistration-update-permissions.md)]

>**Note:**
> * When delegated tokens are used, either the SharePoint Embedded admin role or the Global admin role is required.
> * If the `FileStorageContainerTypeReg.Selected` permission is used, changes are limited to [registrations](../resources/filestoragecontainertyperegistration.md) owned by the application that makes the call.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /storage/fileStorage/containerTypeRegistrations/{fileStorageContainerTypeRegistrationId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

|Property|Type|Description|
|:---|:---|:---|
|settings|[fileStorageContainerTypeRegistrationSettings](../resources/filestoragecontainertyperegistrationsettings.md)|fileStorageContainerTypeRegistration settings. The subset that can be updated depends on the overridable settings in the [fileStorageContainerTypeSettings](../resources/filestoragecontainertypesettings.md). Optional.|
|applicationPermissionGrants|[fileStorageContainerTypeAppPermissionGrant](../resources/fileStorageContainerTypeAppPermissionGrant.md) collection|define the access privileges of applications on containers of a specific fileStorageContainerType. Optional.|
|etag|String|Used for optimistic concurrency control. Must match the value returned from a [Create](filestorage-post-containertyperegistrations.md) or [Get](filestoragecontainertyperegistration-get.md) request. Required.|


## Response

If successful, this method returns a `200 OK` response code and an updated [fileStorageContainerTypeRegistration](../resources/filestoragecontainertyperegistration.md) object in the response body.

## Examples

### Example 1: Update a fileStorageContainerTypeRegistration setting

The following example shows how to update a **fileStorageContainerTypeRegistration** where the owning **fileStorageContainerType** marked **isSearchEnabled** as an overridable setting. The **sharingCapability** property can always be overridden.

#### Request
The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_filestoragecontainertyperegistration"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/storage/fileStorage/containerTypeRegistrations/de988700-d700-020e-0a00-0831f3042f00
Content-Type: application/json

{
  "settings": {
    "sharingCapability": "externalUserAndGuestSharing",
    "isSearchEnabled": false
  },
  "applicationPermissionGrants": [
    {
      "appId": "33225700-9a00-4c00-84dd-0c210f203f01",
      "delegatedPermissions": ["full"],
      "applicationPermissions": ["none"]
    }
  ],
  "etag": "RVRhZw=="
}
```

#### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.fileStorageContainerTypeRegistration"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.fileStorageContainerTypeRegistration",
  "id": "de988700-d700-020e-0a00-0831f3042f00",
  "name": "Container Type Name",
  "owningAppId": "11335700-9a00-4c00-84dd-0c210f203f00",
  "billingClassification": "trial",
  "billingStatus": "valid",
  "registredDateTime": "01/20/2025",
  "expirationDateTime": "02/20/2025",
  "etag": "RVRhZyArIDE=",
  "settings": {
    "sharingCapability": "externalUserAndGuestSharing",
    "urlTemplate": "https://app.contoso.com/redirect?tenant={tenant-id}&drive={drive-id}&folder={folder-id}&item={item-id}",
    "isDiscoverabilityEnabled": true,
    "isSearchEnabled": false,
    "isItemVersioningEnabled": true,
    "itemMajorVersionLimit": 50,
    "maxStoragePerContainerInBytes": 104857600,
    "isSharingRestricted": false
  },
  "applicationPermissionGrants": [
    {
      "appId": "33225700-9a00-4c00-84dd-0c210f203f01",
      "delegatedPermissions": ["full"],
      "applicationPermissions": ["none"]
    }
  ]
}
```

### Example 2: Update a fileStorageContainerTypeRegistration without ETag

The following example shows how to update a **fileStorageContainerTypeRegistration** without an **etag** that results in a `400 Bad Request`.

#### Request
The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_filestoragecontainertyperegistration_no_etag"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/storage/fileStorage/containerTypeRegistrations/de988700-d700-020e-0a00-0831f3042f00
Content-Type: application/json

{
  "settings": {
    "sharingCapability": "externalUserAndGuestSharing"
  },
  "applicationPermissionGrants": [
    {
      "appId": "33225700-9a00-4c00-84dd-0c210f203f01",
      "delegatedPermissions": ["full"],
      "applicationPermissions": ["none"]
    }
  ]
}
```

#### Response
The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 400 Bad Request
```

### Example 3: Update a non-overridable fileStorageContainerTypeRegistration setting

The following example shows how to update a **fileStorageContainerTypeRegistration** setting that isn't overridable in the **fileStorageContainerType**. In this example, the **urlTemplate** property isn't overridable.

#### Request
The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "update_filestoragecontainertyperegistration_not_overridable"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/storage/fileStorage/containerTypeRegistrations/de988700-d700-020e-0a00-0831f3042f00
Content-Type: application/json

{
  "settings": {
    "urlTemplate": "https://fabrikam.example.com/{0}"
  },
  "applicationPermissionGrants": [
    {
      "appId": "33225700-9a00-4c00-84dd-0c210f203f01",
      "delegatedPermissions": ["full"],
      "applicationPermissions": ["none"]
    }
  ]
}
```

#### Response
The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 400 Bad Request
```
