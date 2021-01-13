---
id: "get-pages"
url: "annotation/get-pages"
title: "Get Document Pages"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

GetPages method allows to create an image representation of each page of the document.  
The following table contains method parameters description

Parameter|Type|Description
---|---|---
filePath|string|Document path in storage. Required.
format|string|Preview format: “PNG” (default), "JPEG", or “BMP
height|integer|Preview image height
pageNumbersToConvert|array [integer]|The list of page numbers to convert
password|string|Source document opening password
renderComments|boolean|Render comments (false by default)
width|integer|Preview image width
withoutAnnotations|boolean|If true returns specific pages without annotations

### API Usage ###

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Call Preview method
1. Download result pages from cloud storage
1. Delete pages in cloud storage

```html
HTTP GET ~/annotation/pages
```

[Swagger UI](https://apireference.groupdocs.cloud/annotation/) lets you call this REST API directly from the browser.

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```javascript
// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in the "client_id" and Client Secret in the "client_secret" arguments.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type=client_credentials&client_id=xxxx&client_secret=xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
  
// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/annotation/pages?filePath=annotationdocs%2Fone-page.docx" \
-X GET \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```javascript
{
  "totalCount": 1,
  "entries": [
    {
      "number": 0,
      "link": {
        "href": "https://api-qa.groupdocs.cloud/v2.0/annotation/storage/file/one-page_docx/page_0.png",
        "rel": "self",
        "type": "file",
        "title": "page_0.png"
      }
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](annotation/available-sdks).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java  & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
var configuration = new Configuration(MyClientId, MyClientSecret);
  
var apiInstance = new AnnotateApi(configuration);

var request = new GetPagesRequest("one-page.docx");

var response = apiInstance.GetPages(request);
Console.WriteLine("GetPages: pages count = " + response.TotalCount);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyClientId, MyClientSecret);
  
AnnotateApi apiInstance = new AnnotateApi(configuration);

// Create request object.
GetPagesRequest request = new GetPagesRequest();
request.setfilePath("Annotationdocs\\one-page.docx");

// Executing api method.
PageImages response = apiInstance.getPages(request);

System.out.println("GetPages: pages count = " + response.getTotalCount());

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;

$ClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance = new GroupDocs\Annotation\AnnotateApi($configuration);

$request = new GroupDocs\Annotation\Model\Requests\GetPagesRequest("annotationdocs\\one-page.docx");
$response = $apiInstance->getPages($request);

echo "GetPages: pages count = ", $response->getTotalCount();

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(clientId, clientSecret);

var request = new annotation_cloud.GetPagesRequest("Annotationdocs\\one-page.docx");
let response = await previewApi.getPages(request)
console.log("GetPages: pages count = " + response.totalCount);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(client_id, client_secret)

request = GetPagesRequest("annotationdocs\\one-page.docx", None, None, None, None, None, None, None)
response = api.get_pages(request)

print("GetPages: pages count = " + str(response.total_count))
```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($client_id, $client_secret)

$request = GroupDocsAnnotationCloud::GetPagesRequest.new("Annotationdocs\\one-page.docx", nil, nil, nil, nil, nil, nil, "")

# Executing an API.
$response = $api.get_pages($request)

puts("GetPages: pages count = " + ($response.total_count).to_s)

```

{{< /tab >}} {{< /tabs >}}
