---
title: "Update deviceRegistrationPolicy"
description: "Update the properties of a deviceRegistrationPolicy object."
author: "myra-ramdenbourg"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---
# Update deviceRegistrationPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [deviceRegistrationPolicy](../resources/deviceregistrationpolicy.md) object. Represents deviceRegistrationPolicy quota restrictions, additional authentication, and authorization policies to register device identities to your organization.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.ReadWrite.DeviceConfiguration|
|Delegated (personal Microsoft account)|Not supported|
|Application|Not supported|

When calling on behalf of a user, the user needs the *Cloud Device Administrator* [Microsoft Entra role](/azure/active-directory/roles/permissions-reference).

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
```http
PUT /policies/deviceRegistrationPolicy
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of a [deviceRegistrationPolicy](../resources/deviceregistrationpolicy.md) object with all the updatable properties. The following table specifies the properties that can be updated.

|Property|Type|Description|
|:---|:---|:---|
|userDeviceQuota|Int32| Required. Specifies the maximum number of devices that a user can have within your organization before blocking new device registrations. Required. |
|multiFactorAuthConfiguration|multiFactorAuthConfiguration| Required. Specifies the authentication policy for a user to complete registration using Microsoft Entra join or Microsoft Entra registered within your organization. Possible values are: `notRequired` or `required`. |
|azureADRegistration|[azureADRegistrationPolicy](../resources/azureadregistrationpolicy.md)| Required. Specifies the authorization policy for controlling registration of new devices using Microsoft Entra registration within your organization. Required. For more information, see [What is a device identity?](/azure/active-directory/devices/overview). If Intune is enabled this property cannot be modified.|
|azureADJoin|[azureAdJoinPolicy](../resources/azureadjoinpolicy.md)| Required. Specifies the authorization policy for controlling registration of new devices using Microsoft Entra join within your organization. Required. For more information, see [What is a device identity?](/azure/active-directory/devices/overview).|
|localAdminPassword|[localAdminPasswordSettings](../resources/localadminpasswordsettings.md)|  Required. Specifies the setting for **Local Admin Password Solution (LAPS)** within your organization.|

## Response

If successful, this method returns a `200 OK` response code and an updated [deviceRegistrationPolicy](../resources/deviceregistrationpolicy.md) object in the response body.

## Examples

### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_deviceregistrationpolicy"
}
-->
``` http
PUT https://graph.microsoft.com/beta/policies/deviceRegistrationPolicy
Content-Type: application/json

{
    "id": "deviceRegistrationPolicy",
    "displayName": "Device Registration Policy",
    "description": "Tenant-wide policy that manages intial provisioning controls using quota restrictions, additional authentication and authorization checks",
    "userDeviceQuota": 50,
    "multiFactorAuthConfiguration": "0",
    "azureADRegistration": {
        "appliesTo": "1",
        "isAdminConfigurable": false,
        "allowedUsers": [],
        "allowedGroups": []
    },
    "azureADJoin": {
        "appliesTo": "1",
        "isAdminConfigurable": true,
        "allowedUsers": [],
        "allowedGroups": []
    },
    "localAdminPassword": {
      "isEnabled": true
    }
}
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-deviceregistrationpolicy-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-deviceregistrationpolicy-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.deviceRegistrationPolicy"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#deviceRegistrationPolicy",
    "id": "deviceRegistrationPolicy",
    "displayName": "Device Registration Policy",
    "description": "Tenant-wide policy that manages intial provisioning controls using quota restrictions, additional authentication and authorization checks",
    "userDeviceQuota": 50,
    "multiFactorAuthConfiguration": "0",
    "azureADRegistration": {
        "appliesTo": "1",
        "isAdminConfigurable": false,
        "allowedUsers": [],
        "allowedGroups": []
    },
    "azureADJoin": {
        "appliesTo": "1",
        "isAdminConfigurable": true,
        "allowedUsers": [],
        "allowedGroups": []
    },
    "localAdminPassword": {
      "isEnabled": true
    }
}
```
