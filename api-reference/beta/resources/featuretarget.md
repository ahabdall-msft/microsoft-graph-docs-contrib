---
title: "featureTarget resource type"
description: "Defines a single group, Microsoft Entra role, or administrative unit that is included or excluded in the settings specified in the authenticationMethodFeatureConfiguration object."
author: "jpettere"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# featureTarget resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Defines a single group, Microsoft Entra role, or administrative unit that is included or excluded in the settings specified in the [authenticationMethodFeatureConfiguration](authenticationmethodfeatureconfiguration.md) object.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|The ID of the entity that's targeted in the include or exclude rule or `all_users` to target all users.|
|targetType|featureTargetType|The kind of entity that's targeted. The possible values are: `group`, `administrativeUnit`, `role`, `unknownFutureValue`.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.featureTarget"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.featureTarget",
  "targetType": "String",
  "id": "String (identifier)"
}
```
