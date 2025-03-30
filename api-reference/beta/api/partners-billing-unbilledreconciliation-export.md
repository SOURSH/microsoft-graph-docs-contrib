---
title: "unbilledReconciliation: export"
description: "Export the unbilled invoice reconciliation data for a specific billing period and a given currency."
author: "tingh-msft"
ms.localizationpriority: medium
ms.subservice: "reports"
doc_type: apiPageType
ms.date: 03/20/2025
---

# unbilledReconciliation: export

Namespace: microsoft.graph.partners.billing

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [alerts-callout-csp-partner-only](../includes/alerts-callout-csp-partner-only.md)]

Export the unbilled invoice reconciliation data for a specific billing period and a given currency.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "partners_billing_unbilledreconciliation_export" } -->
[!INCLUDE [permissions-table](../includes/permissions/partners-billing-unbilledreconciliation-export-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /reports/partners/billing/reconciliation/unbilled/export
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
|Content-Type|application/json. Required.|

## Request body

In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that you can use with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|attributeSet|[microsoft.graph.partners.billing.attributeSet](../resources/partners-billing-attributeset.md)|Attributes that should be exported. Possible values are: `full`, `basic`, `unknownFutureValue`. The default value is `full`. Choose `full` for a complete response or `basic` for a subset of attributes. Optional.|
|billingPeriod|[microsoft.graph.partners.billing.billingPeriod](../resources/partners-billing-unbilledusage.md#billingperiod-values)|The billing period for the export data. Possible values are: `current`, `last`, `unknownFutureValue`. Choose `current` for the current billing period and `last` for the last billing period. Required.|
|currencyCode|String|The currency code for the partner billing. Required.|

## Response

If successful, this method returns a `202 Accepted` response code and a `Location` header that contains the URL to the long-running operation. You can check the status of the long-running operation by making a GET request to this URL that returns one of the following objects in the response body: [microsoft.graph.partners.billing.runningOperation](../resources/partners-billing-runningoperation.md), [microsoft.graph.partners.billing.exportSuccessOperation](../resources/partners-billing-exportsuccessoperation.md), or [microsoft.graph.partners.billing.failedOperation](../resources/partners-billing-failedoperation.md).

## Examples

### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "unbilledReconciliationthis.export"
}
-->
``` http
POST https://graph.microsoft.com/beta/reports/partners/billing/reconciliation/unbilled/export
Content-Type: application/json

{
  "currencyCode": "USD",
  "attributeSet": "full",
  "billingPeriod": "current"
}
```

### Response

The following example shows the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 202 Accepted
Location: https://graph.microsoft.com/beta/reports/partners/billing/operations/9ab9cb54-d07f-4f52-9ea6-a09d7de52c14
```
