---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = EntitiesSummariesWithStartDateTimeWithEndDateTimeRequestBuilder.EntitiesSummariesWithStartDateTimeWithEndDateTimeRequestBuilderGetQueryParameters(
		filter = "trafficType eq 'microsoft365'",
)

request_configuration = EntitiesSummariesWithStartDateTimeWithEndDateTimeRequestBuilder.EntitiesSummariesWithStartDateTimeWithEndDateTimeRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.network_access.reports.microsoft_graph_networkaccess_entities_summaries_with_start_date_time_with_end_date_time("{endDateTime}","{startDateTime}").get(request_configuration = request_configuration)


```