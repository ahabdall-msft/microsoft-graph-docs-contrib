---
title: "Get whoisRecord"
description: "Get the specified whoisRecord resource."
author: "joerattazzi-microsoft"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Get whoisRecord

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [threatintelligence-api-disclaimer](../../includes/threatintelligence-api-disclaimer.md)]

Get the specified [whoisRecord](../resources/security-whoisrecord.md) resource. 

Specify the desired **whoisRecord** in one of the following two ways:
- Identify a [host](../resources/security-host.md) and get its current **whoisRecord**. 
- Specify an **id** value to get the corresponding **whoisRecord**.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | ThreatIntelligence.Read.All                 |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | ThreatIntelligence.Read.All                 |

## HTTP request

To get the current **whoisRecord** for the specified **host**:
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/threatIntelligence/hosts/{hostId}/whois
```

To get the specified **whoisRecord**:
<!-- {
  "blockType": "ignored"
}
-->

```http
GET /security/threatIntelligence/whoisRecords/{whoisRecordId}
```

## Optional query parameters

This method supports the `$select` OData query parameter to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [microsoft.graph.security.whoisRecord](../resources/security-whoisrecord.md) object in the response body.

## Examples

### Example 1: Get the whoisRecord resource for the specified host

#### Request

The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_whois_for_host",
  "sampleKeys": ["contoso.com"]
}
-->
``` http
GET https://graph.microsoft.com/beta/security/threatIntelligence/hosts/contoso.com/whois
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-whois-for-host-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-whois-for-host-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-whois-for-host-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-whois-for-host-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-whois-for-host-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-whois-for-host-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-whois-for-host-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-whois-for-host-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.whoisRecord"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#microsoft.graph.security.whoisRecord",
    "id": "Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM=",
    "expirationDateTime": "2023-08-31T00:00:00Z",
    "registrationDateTime": "2022-07-30T09:43:19Z",
    "firstSeenDateTime": null,
    "lastSeenDateTime": null,
    "lastUpdateDateTime": "2023-06-24T08:34:15.984Z",
    "billing": null,
    "noc": null,
    "zone": null,
    "whoisServer": "rdap.markmonitor.com",
    "domainStatus": "client update prohibited,client transfer prohibited,client delete prohibited",
    "rawWhoisText": "Registrar: \n  Handle: 1891582_DOMAIN_COM-VRSN\n  LDH Name: contoso.com\n  Nameserver: \n    LDH Name: ns1-205.azure-dns.com\n    Event: \n      Action: last changed\n...",
    "abuse": {
        "email": "abusecomplaints@markmonitor.com",
        "name": null,
        "organization": null,
        "telephone": "+1.5555555555",
        "fax": null,
        "address": {
            "city": null,
            "countryOrRegion": null,
            "postalCode": null,
            "state": null,
            "street": null,
            "type": "unknown"
        }
    },
    "admin": {
        "email": "domains@microsoft.com",
        "name": "Domain Administrator",
        "organization": "Microsoft Corporation",
        "telephone": "+1.5555555555",
        "fax": "+1.5555555555",
        "address": {
            "city": "Redmond",
            "countryOrRegion": "US",
            "postalCode": "98052",
            "state": "WA",
            "street": "One Microsoft Way",
            "type": "unknown"
        }
    },
    "registrar": {
        "email": null,
        "name": null,
        "organization": "MarkMonitor Inc.",
        "telephone": null,
        "fax": null,
        "address": {
            "city": "Meridian",
            "countryOrRegion": "US",
            "postalCode": "83646",
            "state": "ID",
            "street": "3540 E Longwing Ln",
            "type": "unknown"
        }
    },
    "registrant": {
        "email": "domains@microsoft.com",
        "name": "Domain Administrator",
        "organization": "Microsoft Corporation",
        "telephone": "+1.5555555555",
        "fax": "+1.5555555555",
        "address": {
            "city": "Redmond",
            "countryOrRegion": "US",
            "postalCode": "98052",
            "state": "WA",
            "street": "One Microsoft Way",
            "type": "unknown"
        }
    },
    "technical": {
        "email": "msnhst@microsoft.com",
        "name": "MSN Hostmaster",
        "organization": "Microsoft Corporation",
        "telephone": "+1.5555555555",
        "fax": "+1.5555555555",
        "address": {
            "city": "Redmond",
            "countryOrRegion": "US",
            "postalCode": "98052",
            "state": "WA",
            "street": "One Microsoft Way",
            "type": "unknown"
        }
    },
    "nameservers": [
      {
        "firstSeenDateTime": null,
        "lastSeenDateTime": null,
        "host": {
            "id": "ns1-205.azure-dns.com"
        }
      },
      {
        "firstSeenDateTime": null,
        "lastSeenDateTime": null,
        "host": {
            "id": "ns2-205.azure-dns.net"
        }
      },
      {
        "firstSeenDateTime": null,
        "lastSeenDateTime": null,
        "host": {
            "id": "ns3-205.azure-dns.org"
        }
      },
      {
        "firstSeenDateTime": null,
        "lastSeenDateTime": null,
        "host": {
            "id": "ns4-205.azure-dns.info"
        }
      }
  ],
    "host": {
        "@odata.type": "#microsoft.graph.security.host",
        "id": "contoso.com"
    }
}
```

### Example 2: Get the whoisRecord resource using its id property

#### Request

The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_whoisrecord",
  "sampleKeys": ["Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM="]
}
-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/security/threatIntelligence/whoisRecords/Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM=
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-whoisrecord-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-whoisrecord-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-whoisrecord-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-whoisrecord-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-whoisrecord-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-whoisrecord-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-whoisrecord-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-whoisrecord-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following example shows the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.whoisRecord"
}
-->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.security.whoisRecord",
  "id": "Y29udG9zby5jb20kJDY5NjQ3ODEyMDc3NDY1NzI0MzM=",
  "expirationDateTime": "2023-08-31T00:00:00Z",
  "registrationDateTime": "2022-07-30T09:43:19Z",
  "firstSeenDateTime": null,
  "lastSeenDateTime": null,
  "lastUpdateDateTime": "2023-06-24T08:34:15.984Z",
  "billing": null,
  "noc": null,
  "zone": null,
  "whoisServer": "rdap.markmonitor.com",
  "domainStatus": "client update prohibited,client transfer prohibited,client delete prohibited",
  "rawWhoisText": "Registrar: \n  Handle: 1891582_DOMAIN_COM-VRSN\n  LDH Name: contoso.com\n  Nameserver: \n    LDH Name: ns1.contoso.com\n    Event: \n      Action: last changed\n...",
  "abuse": {
    "email": "noreply@contoso.com",
    "name": null,
    "organization": null,
    "telephone": "+1.5555555555",
    "fax": null,
    "address": {
      "city": null,
      "countryOrRegion": null,
      "postalCode": null,
      "state": null,
      "street": null,
      "type": "unknown"
    }
  },
  "admin": {
    "email": "noreply@contoso.com",
    "name": "Domain Administrator",
    "organization": "Contoso Org",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "registrar": {
    "email": null,
    "name": null,
    "organization": "MarkMonitor Inc.",
    "telephone": null,
    "fax": null,
    "address": null
  },
  "registrant": {
    "email": "noreply@contoso.com",
    "name": "Domain Administrator",
    "organization": "Contoso Corporation",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "technical": {
    "email": "noreply@contoso.com",
    "name": "Hostmaster",
    "organization": "Contoso Corporation",
    "telephone": "+1.5555555555",
    "fax": "+1.5555555555",
    "address": {
      "city": "Redmond",
      "countryOrRegion": "US",
      "postalCode": "98052",
      "state": "WA",
      "street": "123 Fake St.",
      "type": "unknown"
    }
  },
  "nameservers": [
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns1.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns2.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns3.contoso-dns.com"
      }
    },
    {
      "firstSeenDateTime": null,
      "lastSeenDateTime": null,
      "host": {
        "id": "ns4.contoso-dns.com"
      }
    }
  ],
  "host": {
    "id": "contoso.com"
  }
}
```
