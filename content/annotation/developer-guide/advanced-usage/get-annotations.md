---
id: "get-annotations"
url: "annotation/get-annotations"
title: "Get Annotations"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

Get method allows to retrieve all added annotations for given document as list of json objects

### API Usage ###

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Export document with annotations
1. Get or Delete annotations

```html
HTTP GET ~/annotation
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
curl -v "https://api.groupdocs.cloud/v2.0/annotation?filePath=annotationdocs%2Fone-page.docx" \
-X GET \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```javascript
[
  {
    "id": 0,
    "text": "This is ellipse annotation",
    "textToReplace": null,
    "horizontalAlignment": 0,
    "verticalAlignment": 0,
    "creatorId": 0,
    "creatorName": "Anonym A.",
    "creatorEmail": null,
    "box": {
      "x": 100,
      "y": 100,
      "width": 100,
      "height": 100
    },
    "points": null,
    "pageNumber": 0,
    "annotationPosition": null,
    "svgPath": null,
    "type": 4,
    "replies": [
      {
        "id": 0,
        "userId": 0,
        "userName": null,
        "userEmail": null,
        "comment": "First comment",
        "repliedOn": "2020-10-02T06:52:01.376Z",
        "parentReplyId": 0
      },
      {
        "id": 0,
        "userId": 0,
        "userName": null,
        "userEmail": null,
        "comment": "Second comment",
        "repliedOn": "2020-10-02T06:52:01.376Z",
        "parentReplyId": 0
      }
    ],
    "createdOn": "2020-10-02T06:52:01.376Z",
    "fontColor": null,
    "penColor": null,
    "penWidth": null,
    "penStyle": null,
    "backgroundColor": null,
    "fontFamily": null,
    "fontSize": null,
    "opacity": null,
    "angle": null,
    "url": null,
    "imagePath": null
  }
]
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java  & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
var configuration = new Configuration(MyClientId, MyClientSecret);
  
var apiInstance = new AnnotateApi(configuration);

// Set request.
var request = new GetImportRequest
{
    filePath = "one-page.docx"
};

var response = apiInstance.GetImport(request);
Console.WriteLine("GetAnnotations: annotations count = " + response.Count);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyClientId, MyClientSecret);
  
AnnotateApi apiInstance = new AnnotateApi(configuration);

// Create request object.
GetImportRequest request = new GetImportRequest();
request.setfilePath("Annotationdocs\\one-page.docx");

// Executing api method.
List<AnnotationInfo> response = apiInstance.getImport(request);

System.out.println("GetAnnotations: annotations count = " + response.size());

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

$request = new GroupDocs\Annotation\Model\Requests\GetImportRequest("annotationdocs\\one-page.docx");
$response = $apiInstance->getImport($request);

echo "GetAnnotations: annotations count = ", count($response);

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(clientId, clientSecret);

var request = new annotation_cloud.GetImportRequest("Annotationdocs\\one-page.docx");
let response = await annotateApi.getImport(request)
console.log("GetAnnotations: annotations count = " + response.length);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(client_id, client_secret)

request = GetImportRequest("annotationdocs\\one-page.docx")
response = api.get_import(request)

print("GetAnnotations: annotations count: " + str(len(response)))
```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($client_id, $client_secret)

$request = GroupDocsAnnotationCloud::GetImportRequest.new("Annotationdocs\\one-page.docx")

# Executing an API.
$response = $api.get_import($request)

puts("GetAnnotations: annotations count = " + $response.length.to_s)

```

{{< /tab >}} {{< /tabs >}}
