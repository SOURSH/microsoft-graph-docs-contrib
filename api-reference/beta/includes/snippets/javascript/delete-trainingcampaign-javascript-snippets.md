---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

await client.api('/security/attackSimulation/trainingCampaigns/{trainingCampaignId}')
	.version('beta')
	.delete();

```