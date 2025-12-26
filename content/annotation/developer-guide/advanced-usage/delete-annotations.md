---
id: "delete-annotations"
url: "annotation/delete-annotations"
title: "Delete Annotations"
productName: "GroupDocs.Annotation Cloud"
weight: 3
description: ""
keywords: ""
toc: True
---
Delete method allows to remove all added annotations.

## API usage

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Download document with annotations
1. Delete annotations

```html
HTTP POST ~/annotation/remove
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

# cURL example to delete annotations in the document
curl -v "https://api.groupdocs.cloud/v2.0/annotation/remove" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{ "FileInfo": { "FilePath": "annotationdocs/input.docx" }, "AnnotationIds": [ 1, 2, 3 ], "OutputPath": "Output/output.docx"}'
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

# cURL example to delete annotations in the document
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/remove" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'FileInfo': { 'FilePath': 'annotationdocs/input.docx' },
    'AnnotationIds': [ 1, 2, 3 ],
    'OutputPath': 'Output/output.docx'
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
rem First get JSON Web Token
rem Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl.exe -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

rem cURL example to delete annotations in the document
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/remove" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"annotationdocs/input.docx\"},\"AnnotationIds\":[1,2,3],\"OutputPath\":\"Output/output.docx\"}"
```

{{< /tab >}}
{{< tab "Response" >}}

```javascript
{
  "href": "https://api.groupdocs.cloud/v2.0/annotation/storage/file/Output/output.docx",
  "rel": "self",
  "type": "file",
  "title": "output.docx"
}
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
 
var fileInfo = new FileInfo { FilePath = "one-page.docx" };
var options = new RemoveOptions();
options.FileInfo = fileInfo;
options.AnnotationIds = new List<int?> {1, 2, 3};
options.OutputPath = "Output/output.docx";
var request = new RemoveAnnotationsRequest(options);
 
var link = apiInstance.RemoveAnnotations(request);
Console.WriteLine("DeleteAnnotations: Annotations deleted: " + link.Title);
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
 
RemoveOptions options = new RemoveOptions();
options.setFileInfo(fileInfo);        
options.setAnnotationIds(Arrays.asList(1, 2, 3));
options.setOutputPath("Output/output.docx");
 
RemoveAnnotationsRequest request = new RemoveAnnotationsRequest(options);
 
// Executing api method.
AnnotationApiLink result = apiInstance.removeAnnotations(request);
 
System.out.println("DeleteAnnotation: Annotation deleted from document: " + result.getHref());
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
 
$options = new GroupDocs\Annotation\Model\RemoveOptions();
$options->setFileInfo($fileInfo);
$options->setAnnotationIds([1, 2, 3]);
$options->setOutputPath("Output\\output.docx");
 
$request = new GroupDocs\Annotation\Model\Requests\removeAnnotationsRequest($options);
$result = $apiInstance->removeAnnotations($request);
 
echo "DeleteAnnotations: Annotations deleted. " . $result->getHref();
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
let options = new annotation_cloud.RemoveOptions();
options.fileInfo = fileInfo;
options.annotationIds = [1, 2, 3];
options.outputPath = "Output/output.docx";
 
// Remove annotations
let result = await annotateApi.removeAnnotations(new annotation_cloud.RemoveAnnotationsRequest(options));
 
console.log("DeleteAnnotations: annotations delete: " + result.href);
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
options = RemoveOptions()
options.file_info = file_info
options.annotation_ids = [1, 2, 3]
options.output_path = "Output\\output.docx"
 
request = RemoveAnnotationsRequest(options)
result = api.remove_annotations(request)
 
print("RemoveAnnotations: Annotations removed: " + result['href'])
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
 
options = GroupDocsAnnotationCloud::RemoveOptions.new()
options.file_info = file_info
options.annotation_ids = [1, 2, 3]
options.output_path = "Output/output.docx"
 
$request = GroupDocsAnnotationCloud::RemoveAnnotationsRequest.new(options)
 
# Executing an API.
$response = $api.remove_annotations($request)
 
puts("RemoveAnnotations: Annotations deleted from document: " + $response.href)
```

{{< /tab >}} {{< /tabs >}}
