---
title: "swapShiftsChangeRequest: decline"
description: "Decline a swap shift request."
ms.localizationpriority: medium
author: "akumar39"
ms.prod: "microsoft-teams"
doc_type: "apiPageType"
---

# swapShiftsChangeRequest: decline

Namespace: microsoft.graph

Decline a [swapShiftsChangeRequest](../resources/swapshiftschangerequest.md) object.

>**Note:** Only the recipient of the request can decline a [swapShiftsChangeRequest](../resources/swapshiftschangerequest.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Schedule.ReadWrite.All, Group.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | Schedule.ReadWrite.All                      |

> **Note**: This API supports admin permissions. Global admins can access groups that they are not a member of.

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /teams/{teamId}/schedule/swapShiftsChangeRequests/{swapShiftChangeRequestId}/decline
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token}. Required. |
| Content-type | application/json. Required. |
| MS-APP-ACTS-AS  | A user ID (GUID). Required only if the authorization token is an application token; otherwise, optional. |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter    | Type        | Description |
|:-------------|:------------|:------------|
|message|String|A custom decline message.|

## Response

If successful, this method returns a `200 OK` response code. It doesn't return anything in the response body.

## Examples

The following example shows how to call this API.

### Request

The following is an example of a request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "swapshiftchangerequest_decline"
}-->

```http
POST https://graph.microsoft.com/v1.0/teams/{teamId}/schedule/swapShiftsChangeRequests/{swapShiftChangeRequestId}/decline
Content-type: application/json

{
  "message": "message-value"
}
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/swapshiftchangerequest-decline-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/swapshiftchangerequest-decline-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 204 NO CONTENT
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "swapShiftChangeRequest: decline",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
