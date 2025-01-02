---
title: "educationSynchronizationProfileStatus resource type (deprecated)"
description: "Represents the synchronization status of a school data synchronization profile."
author: "mmast-msft"
ms.localizationpriority: medium
ms.subservice: "education"
doc_type: resourcePageType
toc.title: Synchronization profile status (deprecated)
ms.date: 07/23/2024
---

# educationSynchronizationProfileStatus resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [educationsynchronizationprofile-deprecate](../includes/education-deprecate-educationsynchronizationprofile.md)]

Represents the synchronization status of a school data [synchronization profile](educationsynchronizationprofile.md).

> **Note:** Updates to the **educationSynchronizationProfileStatus** might be delayed due to the asynchronous nature of background sync processing.

## Methods

| Method                                                                      | Return Type                               | Description                                              |
| :-------------------------------------------------------------------------- | :---------------------------------------- | :------------------------------------------------------- |
| [Get](../api/educationsynchronizationprofilestatus-get.md) | **educationSynchronizationProfileStatus** | Return the status of a specific synchronization profile. |

## Properties

| Property                    | Type                           | Description                                                                                                              |
| :-------------------------- | :----------------------------- | :----------------------------------------------------------------------------------------------------------------------- |
| errorCount | Int64                 | Number of errors during synchronization.                                        |
| id                          | String                         | The unique identifier for the resource. Read-only.                                                                      |
| lastActivityDateTime | DateTimeOffset                 | Date and time when most recent changes were observed in the profile.                                        |
| lastSynchronizationDateTime | DateTimeOffset                 | Date and time of the most recent successful synchronization.                                        |
| status                      | educationSynchronizationStatus | The status of a sync. The possible values are: `paused`, `inProgress`, `success`, `error`, `validationError`, `quarantined`, `unknownFutureValue`, `extracting`, `validating`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following values in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `extracting`, `validating`.|
| statusMessage | String                 | Status message for the synchronization stage of the current profile.                                        |


## Relationships
None.

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationSynchronizationProfileStatus"
}-->

```json
{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#education/synchronizationProfiles/{id}/profileStatus/$entity",
  "errorCount": "Int64",
  "id": "String",
  "lastActivityDateTime": "DateTimeOffset",
  "lastSynchronizationDateTime": "DateTimeOffset",
  "status": "String",
  "statusMessage": "String"
}
```
