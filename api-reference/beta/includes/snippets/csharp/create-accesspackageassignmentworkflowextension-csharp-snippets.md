---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new CustomCalloutExtension
{
	AdditionalData = new Dictionary<string, object>
	{
		{
			"value" , new AccessPackageAssignmentWorkflowExtension
			{
				OdataType = "#microsoft.graph.accessPackageAssignmentWorkflowExtension",
				DisplayName = "test_action_0127_email",
				Description = "this is for graph testing only",
				EndpointConfiguration = new LogicAppTriggerEndpointConfiguration
				{
					OdataType = "#microsoft.graph.logicAppTriggerEndpointConfiguration",
					SubscriptionId = "38ab2ccc-3747-4567-b36b-9478f5602f0d",
					ResourceGroupName = "test",
					LogicAppWorkflowName = "elm-extension-email",
				},
				AuthenticationConfiguration = new AzureAdPopTokenAuthentication
				{
					OdataType = "#microsoft.graph.azureAdPopTokenAuthentication",
				},
			}
		},
	},
};
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageCatalogs["{accessPackageCatalog-id}"].AccessPackageCustomWorkflowExtensions.PostAsync(requestBody);


```