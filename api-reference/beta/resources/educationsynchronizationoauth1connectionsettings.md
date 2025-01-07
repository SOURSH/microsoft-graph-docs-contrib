---
title: educationSynchronizationOAuth1ConnectionSettings resource type (deprecated)
description: "When OAuth1 is to be used to connect to the data provider, this connection settings type should be used to set up the profile."
ms.localizationpriority: medium
author: "mmast-msft"
ms.subservice: "education"
doc_type: resourcePageType
ms.date: 07/23/2024
---

# educationSynchronizationOAuth1ConnectionSettings resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [educationsynchronizationprofile-deprecate](../includes/education-deprecate-educationsynchronizationprofile.md)]

When OAuth1 is to be used to connect to the data provider, this connection settings type should be used to set up the profile.

Derived from [educationSynchronizationConnectionSettings].

## Properties

| Property     | Type   | Description                                                                                                                |
| :----------- | :----- | :------------------------------------------------------------------------------------------------------------------------- |
| clientId     | String | Client ID used to connect to the provider. Inherited from [educationSynchronizationConnectionSettings].                    |
| clientSecret | String | Client secret to authenticate the connection to the provider. Inherited from [educationSynchronizationConnectionSettings]. |

[educationsynchronizationconnectionsettings]: educationsynchronizationconnectionsettings.md

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.educationSynchronizationOAuth1ConnectionSettings"
}-->

```json
{
  "@odata.type": "microsoft.graph.educationSynchronizationOAuth1ConnectionSettings",
  "clientId": "String",
  "clientSecret": "String"
}
```


