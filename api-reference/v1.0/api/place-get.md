---
title: "Get place"
description: "Retrieve the properties and relationships of a place object."
ms.localizationpriority: medium
author: "vrod9429"
ms.prod: "outlook"
doc_type: "apiPageType"
---

# Get place

Namespace: microsoft.graph

Get the properties and relationships of a [place](../resources/place.md) object specified by either its ID or email address.

The **place** object can be one of the following types:

* A [room](../resources/room.md) which includes rich properties such as an email address for the room, and accessibility, capacity, and device support.
* A [room list](../resources/roomlist.md) which includes an email address for the room list, and a navigation property to get the collection of **room** instances in that room list.

Both **room** and **roomList** are derived from the [place](../resources/place.md) object.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Place.Read.All |
| Delegated (personal Microsoft account) | Not supported |
| Application                            | Place.Read.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /places/{id}
```

## Optional query parameters
Use `$select` to get specific **place** properties.

For more information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          | Description               |
|:--------------|:--------------------------|
| Authorization | Bearer {token}. Required. |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the requested [place](../resources/place.md) object in the response body.

## Examples

### Example 1: Get a room
#### Request

The following example specifies the **id** of a **room** to get its properties.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_room",
  "sampleKeys": ["979e9793-3e91-40eb-b18c-0ea937893956"]
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/places/979e9793-3e91-40eb-b18c-0ea937893956
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-room-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-room-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following example shows the response.

>**Note**: The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "name": "get_room",
  "truncated": true,
  "@odata.type": "microsoft.graph.room"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#places/$entity",
    "@odata.type": "#microsoft.graph.roomList",
    "id": "979e9793-3e91-40eb-b18c-0ea937893956",
    "displayName": "Building 2 Rooms",
    "address": null,
    "geoCoordinates": null,
    "phone": "",
    "emailAddress": "Building2Rooms@M365x214355.onmicrosoft.com"
}
```

### Example 2: Get a room list
#### Request

The following example specifies the **emailAddress** of a **roomList** to get its properties.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_roomlist",
  "sampleKeys": ["Building2Rooms@M365x214355.onmicrosoft.com"]
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/places/Building2Rooms@M365x214355.onmicrosoft.com
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-roomlist-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-roomlist-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following example shows the response.

>**Note**: The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "name": "get_roomlist",
  "truncated": true,
  "@odata.type": "microsoft.graph.roomList"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#places/$entity",
    "@odata.type": "#microsoft.graph.roomList",
    "id": "979e9793-3e91-40eb-b18c-0ea937893956",
    "displayName": "Building 2 Rooms",
    "address": null,
    "geoCoordinates": null,
    "phone": "",
    "emailAddress": "Building2Rooms@M365x214355.onmicrosoft.com"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get place",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

