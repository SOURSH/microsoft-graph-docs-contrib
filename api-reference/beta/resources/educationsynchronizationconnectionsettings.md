---
title: "educationSynchronizationConnectionSettings resource type (deprecated)"
description: "Represents the provider connection settings. This allows the system to know how to connect to the provider APIs. "
author: "mmast-msft"
ms.localizationpriority: medium
ms.subservice: "education"
doc_type: resourcePageType
ms.date: 07/23/2024
---

# educationSynchronizationConnectionSettings resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [educationsynchronizationprofile-deprecate](../includes/education-deprecate-educationsynchronizationprofile.md)]

Represents the provider connection settings. This allows the system to know how to connect to the provider APIs.

> [!NOTE]
> This complex type is abstract. Refer to the specific types of connection settings listed.

## Derived types

| Type                                                                                                                                      | Description                                                                   |
| :---------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------- |
| [educationSynchronizationOAuth1ConnectionSettings](educationsynchronizationoauth1connectionsettings.md)                                   | Use this type to provide OAuth1 connection settings.                          |
| [educationSynchronizationOAuth2ClientCredentialsConnectionSettings](educationsynchronizationoauth2clientcredentialsconnectionsettings.md) | Use this type to provide OAuth2 Client Credentials Grant connection settings. |

## Properties

| Property     | Type   | Description                                                   |
| :----------- | :----- | :------------------------------------------------------------ |
| clientId     | String | Client ID used to connect to the provider.                    |
| clientSecret | String | Client secret to authenticate the connection to the provider. |

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.educationSynchronizationConnectionSettings"
}-->

```json
{
  "@odata.type": "microsoft.graph.educationSynchronizationConnectionSettings",
  "clientId": "String",
  "clientSecret": "String",
}
```
