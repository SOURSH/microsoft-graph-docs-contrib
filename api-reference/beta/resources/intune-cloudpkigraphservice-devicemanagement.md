---
title: "deviceManagement resource type"
description: "Singleton that acts as container for a collection of Cloud PKI entities."
author: "jaiprakashmb"
ms.localizationpriority: medium
ms.subservice: "intune"
doc_type: resourcePageType
ms.date: 08/01/2024
---

# deviceManagement resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Singleton that acts as container for a collection of Cloud PKI entities.

## Methods
|Method|Return Type|Description|
|:---|:---|:---|
|[Get deviceManagement](../api/intune-cloudpkigraphservice-devicemanagement-get.md)|[deviceManagement](../resources/intune-shared-devicemanagement.md)|Read properties and relationships of the [deviceManagement](../resources/intune-shared-devicemanagement.md) object.|
|[Update deviceManagement](../api/intune-cloudpkigraphservice-devicemanagement-update.md)|[deviceManagement](../resources/intune-shared-devicemanagement.md)|Update the properties of a [deviceManagement](../resources/intune-shared-devicemanagement.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Required Graph property|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|cloudCertificationAuthority|[cloudCertificationAuthority](../resources/intune-cloudpkigraphservice-cloudcertificationauthority.md) collection|Collection of CloudCertificationAuthority records associated with account.|
|cloudCertificationAuthorityLeafCertificate|[cloudCertificationAuthorityLeafCertificate](../resources/intune-cloudpkigraphservice-cloudcertificationauthorityleafcertificate.md) collection|Collection of CloudCertificationAuthorityLeafCertificate records associated with account.|
|reports|[deviceManagementReports](../resources/intune-cloudpkigraphservice-devicemanagementreports.md)|Reports singleton|

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.deviceManagement"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagement",
  "id": "String (identifier)"
}
```
