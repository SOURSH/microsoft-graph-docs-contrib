---
title: "classificationError resource type"
toc.title: "classificationError resource type(preview)"
description: "Represents a detailed error object, potentially containing multiple nested errors, encountered during classification or policy evaluation."
author: "ArunGedela"
ms.date: 04/08/2025
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: resourcePageType
---

# classificationError resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a detailed error object, potentially containing multiple nested errors, encountered during classification or policy evaluation.

## Properties

| Property | Type                                                                                                       | Description                                                   |
| :------- | :--------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------ |
| code       | String                                                                                           | A service-defined error code string. Inherited properties from [classifcationErrorBase](../resources/classifcationerrorbase.md) |
| details  | [classifcationErrorBase](../resources/classifcationerrorbase.md) collection | A collection of more specific errors that contribute to the overall error.|
| innerError | [classificationInnerError](../resources/classificationinnererror.md) | Contains more specific, potentially internal error details. Inherited properties from [classifcationErrorBase](../resources/classifcationerrorbase.md) |
| message    | String                                                                                           | A human-readable representation of the error. Inherited properties from [classifcationErrorBase](../resources/classifcationerrorbase.md) |
| target     | String                                                                                           | The target of the error (for example, the specific property or item causing the issue). Inherited properties from [classifcationErrorBase](../resources/classifcationerrorbase.md) |

## Relationships

None.

## JSON representation

The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.classificationError",
  "baseType": "microsoft.graph.classifcationErrorBase",
  "openType": false
}-->
``` json
{
  "code": "String",
  "message": "String",
  "target": "String",
  "innerError": {
    "@odata.type": "microsoft.graph.classificationInnerError"
  },
  "details": [
    {
      "@odata.type": "#microsoft.graph.classifcationErrorBase",
    }
  ]
}
```
