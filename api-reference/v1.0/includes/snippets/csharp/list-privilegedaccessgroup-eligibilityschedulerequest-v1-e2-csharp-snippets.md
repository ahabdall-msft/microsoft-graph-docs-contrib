---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.IdentityGovernance.PrivilegedAccess.Group.EligibilityScheduleRequests.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Filter = "groupId eq '2b5ed229-4072-478d-9504-a047ebd4b07d' and principalId eq '3cce9d87-3986-4f19-8335-7ed075408ca2'";
	requestConfiguration.QueryParameters.Select = new string []{ "principalId","action","groupId" };
});


```