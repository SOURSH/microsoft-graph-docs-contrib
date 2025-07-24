---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.NetworkAccess

$params = @{
	"@odata.type" = "#microsoft.graph.networkaccess.threatIntelligencePolicy"
	name = "Malicious Domains Policy"
	description = "Policy to block traffic to known malicious domains based on threat intelligence"
	version = "1.0"
	settings = @{
		"@odata.type" = "microsoft.graph.networkaccess.threatIntelligencePolicySettings"
		defaultAction = "block"
	}
}

New-MgBetaNetworkAccessThreatIntelligencePolicy -BodyParameter $params

```