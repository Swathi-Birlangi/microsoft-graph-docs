---
title: "reports: getPrinterArchivedPrintJobs"
description: Get a list of archived print jobs that were queued for particular printer.
author: braedenp-msft
localization_priority: Normal
ms.prod: cloud-printing
doc_type: apiPageType
---

# reports: getPrinterArchivedPrintJobs

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of archived print jobs that were queued for particular [printer](../resources/printer.md).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

In addition to the following permissions, the user's tenant must have an active Universal Print subscription.

|Permission type | Permissions (from least to most privileged) |
|:---------------|:--------------------------------------------|
|Delegated (work or school account)| Reports.Read.All |
|Delegated (personal Microsoft account)|Not Supported.|
|Application|Not Supported.|

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /print/reports/getPrinterArchivedPrintJobs(printerId=printerId-value,startDateTime=startDateTime-value,endDateTime=endDateTime-value)
GET /reports/getPrinterArchivedPrintJobs(printerId=printerId-value,startDateTime=startDateTime-value,endDateTime=endDateTime-value)
```
## Request headers
| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token}. Required. |

## Function parameters

| Parameter     | Type                 | Required? | Description                                                          |
|---------------|----------------------|-----------|----------------------------------------------------------------------|
| `printerId`   | `Edm.String`         | Yes       | The ID of the printer to return data for.                            |
| `startDateTime` | `Edm.DateTimeOffset` | No        | The start date (inclusive) for the time period to include data from. |
| `endDateTime`   | `Edm.DateTimeOffset` | No        | The end date (inclusive) for the time period to include data from.   |

## Response
If successful, this method returns a `200 OK` response code and a collection of [archivedPrintJob](../resources/archivedprintjob.md) objects in the response body.

## Example
The following example shows how to call this API.
##### Request
The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "reports-getprinterarchivedprintjobs",
  "sampleKeys": ["016b5565-3bbf-4067-b9ff-4d68167eb1a6"]
}-->
```http
GET https://graph.microsoft.com/beta/print/reports/getPrinterArchivedPrintJobs(printerId='016b5565-3bbf-4067-b9ff-4d68167eb1a6',startDateTime=2021-05-24,endDateTime=2021-05-25)
```

##### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.archivedPrintJob"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 236

{
  "value": [
    {
      "id": "016b5565-3bbf-4067-b9ff-4d68167eb1a6",
      "printer": {
        "id": "016b5565-3bbf-4067-b9ff-4d68167eb1a6"
      },
      "createdBy": {},
      "processingState": "completed"
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "printJob: getPrinterArchivedPrintJobs",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

