---
title: "forwardingPolicy: updatePolicyRules"
description: "Update the rules within a forwarding policy."
author: Moti-ba
ms.localizationpriority: medium
ms.prod: global-secure-access
doc_type: apiPageType
---

# forwardingPolicy: updatePolicyRules
Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the rules within a forwarding policy.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|NetworkAccessPolicy.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

[!INCLUDE [rbac-global-secure-access-apis-write](../includes/rbac-for-apis/rbac-global-secure-access-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /networkAccess/forwardingPolicies/{id}/updatePolicyRules
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|id|[microsoft.graph.networkaccess.policyRule](../resources/networkaccess-policyrule.md)|Unique Identifier for the rule.|
|action|[microsoft.graph.networkaccess.policyRuleDelta](../resources/networkaccess-policyruledelta.md)|Action for the traffic, possible values are `forward` or `bypass`. Required.|


## Response

If successful, this action returns a `204 No Content` response code.

## Examples

### Request
The following example shows a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "forwardingpolicythis.updatepolicyrules"
}
-->
``` http
POST https://graph.microsoft.com/beta/networkAccess/forwardingPolicies/{id}/updatePolicyRules
Content-Type: application/json

{
  "rules": [
    {
      "ruleId": "e296c914-768c-4ce9-a279-e4b6145a8a4b",
      "action": "forward"
    }
  ]
}
```

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/forwardingpolicythisupdatepolicyrules-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/forwardingpolicythisupdatepolicyrules-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/forwardingpolicythisupdatepolicyrules-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following example shows a response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

