---
title: "cloudPcBulkRestore resource type"
description: "Represents the entity that performs a bulk restore action."
author: "Guoan-Tang"
ms.localizationpriority: medium
ms.subservice: "cloud-pc"
doc_type: resourcePageType
ms.date: 07/23/2024
---

# cloudPcBulkRestore resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

This defines the entity for perform bulk restore action with executeAction API and it inherits from CloudPcBulkAction base type. Perform bulk restore for a set of Cloud PCs with associated cloud PC ID and restore point date time. If some of the devices don't have any snapshot to restore, then they will be set as restore failed, while the others with snapshots will still be triggered restore.

Inherits from [cloudPcBulkAction](../resources/cloudpcbulkaction.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|actionSummary|[cloudPcBulkActionSummary](../resources/cloudpcbulkactionsummary.md)|Run summary of this bulk action. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md). |
|cloudPcIds|String collection|IDs of the Cloud PCs the bulk action applies to. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md). |
|createdDateTime|DateTimeOffset|The date and time when the bulk action was created. The timestamp type represents date and time information using ISO 8601 format and is always in UTC. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md). |
|displayName|String|Name of the bulk action. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md). |
|id|String|ID of the bulk action. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md). |
|ignoreUnhealthySnapshots|Boolean|`True` indicates that snapshots of unhealthy Cloud PCs are ignored. If no healthy snapshot exists within the selected **timeRange**, the healthy snapshot closest to the **restorePointDateTime** is used. `False` indicates that the snapshot within the selected **timeRange** and closest to the **restorePointDateTime** is used. The default value is `false`.|
|initiatedByUserPrincipalName|String|Indicates the user principal name (UPN) of the user who initiated this bulk action. Read-only. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md).|
|restorePointDateTime|DateTimeOffset|Indicates the date and time to restore selected Cloud PCs to. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: '2014-01-01T00:00:00Z'.|
|scheduledDuringMaintenanceWindow|Boolean|Indicates whether the bulk action is scheduled according to the maintenance window. When `true`, the bulk action uses the maintenance window to schedule the action; `false` means that the bulk action doesn't use the maintenance window. The default value is `false`. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md).|
|status|[cloudPcBulkActionStatus](../resources/cloudpcbulkaction.md#cloudpcbulkactionstatus-values)|Indicates the status of bulk actions. Possible values are `pending`, `succeeded`, `failed`, `unknownFutureValue`. The default value is `pending`. Read-only. Inherited from [cloudPcBulkAction](../resources/cloudpcbulkaction.md).|
|timeRange|restoreTimeRange|Indicates the time range of restore point. Value can be `before`, `after` or `beforeOrAfter`, default value is `before`.   |

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.cloudPcBulkRestore",
  "baseType": "microsoft.graph.cloudPcBulkAction",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.cloudPcBulkRestore",
  "actionSummary": {"@odata.type": "microsoft.graph.cloudPcBulkActionSummary"},
  "cloudPcIds": ["String"],
  "createdDateTime": "String (timestamp)",
  "displayName": "String",
  "id": "String (identifier)",
  "ignoreUnhealthySnapshots": "Boolean",
  "initiatedByUserPrincipalName": "String",
  "restorePointDateTime": "String (timestamp)",
  "scheduledDuringMaintenanceWindow": "Boolean",
  "status": "String",
  "timeRange": "String"
}
```
