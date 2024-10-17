---
title: "enrollmentTimeDeviceMembershipTarget resource type"
description: "The EnrollmentTimeDeviceMembershipTarget entity represents the targets that devices will become members of when enrolled with the associated profile. The only device membership targets supported at this time is static security groups."
author: "jaiprakashmb"
ms.localizationpriority: medium
ms.subservice: "intune"
doc_type: resourcePageType
---

# enrollmentTimeDeviceMembershipTarget resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

The EnrollmentTimeDeviceMembershipTarget entity represents the targets that devices will become members of when enrolled with the associated profile. The only device membership targets supported at this time is static security groups.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|targetType|[enrollmentTimeDeviceMembershipTargetType](../resources/intune-shared-enrollmenttimedevicemembershiptargettype.md)|The type of the targets that devices will become members of when enrolled with the asociated profile. Possible values are staticSecurityGroup. Default value : unknown. Possible values are: `unknown`, `staticSecurityGroup`, `unknownFutureValue`.|
|targetId|String|The unique identifiers of the targets that devices will become members of when enrolled with the asociated profile.|

## Relationships
None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.enrollmentTimeDeviceMembershipTarget"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.enrollmentTimeDeviceMembershipTarget",
  "targetType": "String",
  "targetId": "String"
}
```
