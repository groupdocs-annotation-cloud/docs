---
id: "delete-annotations"
url: "annotation/delete-annotations"
title: "Delete Annotations"
productName: "GroupDocs.Annotation Cloud"
weight: 3
description: ""
keywords: ""
---

Delete method allows to remove all added annotations.

### API Usage ###

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Export document with annotations
1. Delete annotations

```html
HTTP DELETE ~/annotation
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
-X DELETE\
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```javascript
204 No Content
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

var request = new DeleteAnnotationsRequest("one-page.docx");

apiInstance.DeleteAnnotations(request);
Console.WriteLine("DeleteAnnotations: Annotations deleted.");

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyClientId, MyClientSecret);
  
AnnotateApi apiInstance = new AnnotateApi(configuration);

// Create request object.
DeleteAnnotationsRequest request = new DeleteAnnotationsRequest("Annotationdocs\\one-page.docx");

// Executing api method.
apiInstance.deleteAnnotations(request);

System.out.println("DeleteAnnotation: Annotation deleted from document.");

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

$request = new GroupDocs\Annotation\Model\Requests\DeleteAnnotationsRequest("annotationdocs\\one-page.docx");
$apiInstance->deleteAnnotations($request);

echo "DeleteAnnotations: Annotations deleted. ";

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(clientId, clientSecret);

var request = new annotation_cloud.DeleteAnnotationsRequest("Annotationdocs\\one-page.docx");
await annotateApi.deleteAnnotations(request)
console.log("DeleteAnnotations: annotations deleted.");

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(client_id, client_secret)

request = DeleteAnnotationsRequest("annotationdocs\\one-page.docx")
api.delete_annotations(request)

print("DeleteAnnotations: Annotation deleted from document.")
```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($client_id, $client_secret)

$request = GroupDocsAnnotationCloud::DeleteAnnotationsRequest.new("Annotationdocs\\one-page.docx")

# Executing an API.
$response = $api.delete_annotations($request)

puts("DeleteAnnotations: Annotations deleted from document.")

```

{{< /tab >}} {{< /tabs >}}
