---
title: "userRegistrationActivitySummary resource type"
description: "Represents the summary of the number of successful/unsuccessful registration and reset events for each authentication method."
ms.date: 07/23/2025
author: "egreenberg14"
ms.localizationpriority: medium
ms.subservice: "entra-monitoring-health"
doc_type: resourcePageType
ms.custom: sfi-ga-nochange
---

# userRegistrationActivitySummary resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the summary of the number of successful/unsuccessful registration and reset events for each authentication method.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List](../api/userregistrationactivitysummary-list.md)|[userRegistrationActivitySummary](../resources/userregistrationactivitysummary.md) collection|Get the summary of the number of successful/unsuccessful registration and reset events for each authentication method.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|authMethod|usageAuthMethod|The authentication method for the given summary. The possible values are: `email`, `mobileSMS`, `mobileCall`, `officePhone`, `securityQuestion`, `appNotification`, `appCode`, `alternateMobileCall`, `fido`, `appPassword`, `unknownFutureValue`, `externalAuthMethod`.|
|failureActivityCount|Int64|The total number of failed activities for the corresponding authMethod and feature.|
|feature|featureType|The type of activity. The possible values are: `registration`, `reset`, `unknownFutureValue`.|
|id|String|The unique id for the given summary.|
|successfulActivityCount|Int64|The total number of successful activities for the corresponding authMethod and feature.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.userRegistrationActivitySummary",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.userRegistrationActivitySummary",
  "id": "String (identifier)",
  "feature": "String",
  "successfulActivityCount": "Integer",
  "failureActivityCount": "Integer",
  "authMethod": "String"
}
```

