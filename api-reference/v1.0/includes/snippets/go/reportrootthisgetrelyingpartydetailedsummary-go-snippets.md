---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



period := "{period}"
getRelyingPartyDetailedSummary, err := graphClient.Reports().GetRelyingPartyDetailedSummaryWithPeriod(&period).GetAsGetRelyingPartyDetailedSummaryWithPeriodGetResponse(context.Background(), nil)


```