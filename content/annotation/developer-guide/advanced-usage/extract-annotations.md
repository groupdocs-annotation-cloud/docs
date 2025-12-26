---
id: "extract-annotations"
url: "annotation/extract-annotations"
title: "Extract Annotations"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---
Get method allows to retrieve all added annotations for given document as list of json objects

## API usage

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Download document with annotations
1. Extract or Delete annotations

```html
HTTP POST ~/annotation/extract
```

[Swagger UI](https://apireference.groupdocs.cloud/annotation/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to extract annotations
curl -v "https://api.groupdocs.cloud/v2.0/annotation/extract" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{"FilePath":"annotationdocs/input.docx"}'
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to extract annotations
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/extract" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{ 'FilePath': 'annotationdocs/input.docx' }"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: First get JSON Web Token
:: Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: cURL example to extract annotations
curl -v "https://api.groupdocs.cloud/v2.0/annotation/extract" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FilePath\":\"annotationdocs/input.docx\"}"
```
{{< /tab >}}
{{< tab "Response" >}}

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

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here]({{< ref "/annotation/getting-started/available-sdks.md" >}}).



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
var configuration = new Configuration(MyAppSid, MyAppKey);
  
var apiInstance = new AnnotateApi(configuration);
 
var fileInfo = new FileInfo { FilePath = "input.docx" };
 
var response = apiInstance.Extract(new ExtractRequest(fileInfo));
 
Console.WriteLine("ExtractAnnotations: annotations count = " + response.Count);
```

{{< /tab >}} {{< tab "Java  & Android" >}}

```java
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyAppSid, MyAppKey);
  
AnnotateApi apiInstance = new AnnotateApi(configuration);
 
// Create request object.
FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Annotationdocs\\input.docx");
 
ExtractRequest request = new ExtractRequest();
request.setfileInfo(fileInfo);
 
// Executing api method.
List<AnnotationInfo> response = apiInstance.extract(request);
 
System.out.println("GetAnnotations: annotations count = " + response.size());
```

{{< /tab >}} {{< tab "PHP" >}}

```php
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;
 
$AppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);
 
$apiInstance = new GroupDocs\Annotation\AnnotateApi($configuration);
 
$fileInfo = new GroupDocs\Annotation\Model\FileInfo();
$fileInfo->setFilePath("input\\input.docx");
 
$request = new GroupDocs\Annotation\Model\Requests\extractRequest($fileInfo);
$result = $apiInstance->extract($request);
 
echo "GetAnnotations: annotations count = ", count($result);
```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");
 
global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(appSid, appKey);
 
let fileInfo = new annotation_cloud.FileInfo();
fileInfo.filePath = "input\\input.docx";
let result = await annotateApi.extract(new annotation_cloud.ExtractRequest(fileInfo));   
console.log("GetAnnotations: annotations count = " + result.length);
```

{{< /tab >}} {{< tab "Python" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud
 
app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(app_sid, app_key)
 
file_info = FileInfo()
file_info.file_path = "annotationdocs\\input.docx"
 
request = ExtractRequest(file_info)
result = api.extract(request)        
 
print("ExtractAnnotations: annotations count: " + str(len(result)))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'
 
$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($app_sid, $app_key)
 
file_info = GroupDocsAnnotationCloud::FileInfo.new()
file_info.file_path = "annotationdocs\\input.docx"
 
$request = GroupDocsAnnotationCloud::ExtractRequest.new(file_info)
 
# Executing an API.
$response = $api.extract($request)
 
puts("ExtractAnnotations: annotations count = " + $response.length.to_s)
```

{{< /tab >}} {{< /tabs >}}
