---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Models.ReferenceUpdate
{
};
await graphClient.Identity.B2xUserFlows["{b2xIdentityUserFlow-id}"].ApiConnectorConfiguration.PostAttributeCollection.Ref.PutAsync(requestBody);


```