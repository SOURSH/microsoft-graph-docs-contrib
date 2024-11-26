---
title: "cloudPcCrossRegionDisasterRecoverySetting resource type"
description: "Represents the settings for cross-region disaster recovery on a Cloud PC."
author: "Guoan-Tang"
ms.localizationpriority: medium
ms.subservice: "cloud-pc"
doc_type: resourcePageType
toc.title: Cloud PC cross-region disaster recovery setting
ms.date: 08/29/2024
---

# cloudPcCrossRegionDisasterRecoverySetting resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the settings for cross-region disaster recovery on a Cloud PC.

## Properties

|Property|Type|Description|
|:---|:---|:---|
|crossRegionDisasterRecoveryEnabled|Boolean|`True` if an end user is allowed to set up cross-region disaster recovery for Cloud PC; otherwise, `false`. The default value is `false`.|
|disasterRecoveryNetworkSetting|[cloudPcDisasterRecoveryNetworkSetting](../resources/cloudpcdisasterrecoverynetworksetting.md)|Indicates the network settings of the Cloud PC during a cross-region disaster recovery operation.|
|maintainCrossRegionRestorePointEnabled|Boolean|Indicates whether Windows 365 maintain the cross-region disaster recovery function generated restore points. If `true`, the Windows 365 stored restore points; `false` indicates that Windows 365 doesn't generate or keep the restore point from the original Cloud PC. If a disaster occurs, the new Cloud PC can only be provisioned using the initial image. This limitation can result in the loss of some user data on the original Cloud PC. The default value is `false`.|

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.cloudPcCrossRegionDisasterRecoverySetting"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.cloudPcRestorePointSetting",
  "crossRegionDisasterRecoveryEnabled": "Boolean",
  "disasterRecoveryNetworkSetting": {"@odata.type": "microsoft.graph.cloudPcDisasterRecoveryNetworkSetting"},
  "maintainCrossRegionRestorePointEnabled": "Boolean"
}
```
