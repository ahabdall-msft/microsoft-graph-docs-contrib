---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)


request_configuration = DeltaRequestBuilder.DeltaRequestBuilderGetRequestConfiguration(
headers = {
		'Prefer' : "odata.maxpagesize=2",
}

)

result = await graph_client.me.mail_folders.by_mail_folder_id('mailFolder-id').messages.delta.get(request_configuration = request_configuration)


```