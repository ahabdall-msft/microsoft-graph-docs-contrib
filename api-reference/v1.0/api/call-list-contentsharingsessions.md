---
title: "List contentSharingSessions"
description: "Retrieve a list of contentSharingSession objects in a call."
author: "satyakonmsft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# List contentSharingSessions

Namespace: microsoft.graph

Retrieve a list of [contentSharingSession](../resources/contentsharingsession.md) objects in a call.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

| Permission type                        | Permissions (from least to most privileged)                                                              |
|:---------------------------------------|:---------------------------------------------------------------------------------------------------------|
| Delegated (work or school account)     | Not supported.                                                                                           |
| Delegated (personal Microsoft account) | Not supported.                                                                                           |
| Application                            | Calls.JoinGroupCallAsGuest.All, Calls.JoinGroupCall.All, Calls.Initiate.All, Calls.InitiateGroupCall.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /communications/calls/{id}/contentSharingSessions
```

## Request headers

| Name          | Description               |
|:--------------|:--------------------------|
| Authorization | Bearer {token}. Required. |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [contentSharingSession](../resources/contentsharingsession.md) objects in the response body.

## Example

### Request

The following is an example of a request.



# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get-contentsharingsessions"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/communications/calls/7531d31f-d10d-44de-802f-c569dbca451c/contentSharingSessions
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-contentsharingsessions-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-contentsharingsessions-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-contentsharingsessions-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-contentsharingsessions-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-contentsharingsessions-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-contentsharingsessions-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-contentsharingsessions-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-contentsharingsessions-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following example shows the response.

<!-- {
  "blockType": "response",
  "@odata.type": "microsoft.graph.contentSharingSession",
  "isCollection": true,
  "truncated": true
}-->
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
   "value":[
      {
         "@odata.type":"#microsoft.graph.contentSharingSession",
         "id":"a7ebfb2d-871e-419c-87af-27290b22e8db"
      },
      {
         "@odata.type":"#microsoft.graph.contentSharingSession",
         "id":"278405a3-f568-4b3e-b684-009193463064"
      }
   ],
   "@odata.context":"https://graph.microsoft.com/v1.0/$metadata#communications/calls('7531d31f-d10d-44de-802f-c569dbca451c')/contentSharingSessions"
}

```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "List contentSharingSessions",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
