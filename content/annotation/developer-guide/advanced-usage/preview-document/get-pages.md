---
id: "get-pages"
url: "annotation/get-pages"
title: "Get Document Pages"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---
GetPages method allows to create an image representation of each page of the document.  

## API usage

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Call Preview method
1. Download result pages from cloud storage

```html
HTTP POST ~/annotation/preview/create
```

[Swagger UI](https://apireference.groupdocs.cloud/annotation/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# First get JSON Web Token
# Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to create document preview images
curl -v "https://api.groupdocs.cloud/v2.0/annotation/preview/create" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{ "FileInfo": { "FilePath": "one-page.docx" } }'
```

{{< /tab >}}
{{< tab "Windows PowerShell" >}}

```powershell
# First get JSON Web Token
# Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to create document preview images
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/preview/create" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{ 'FileInfo': { 'FilePath': 'one-page.docx' } }"
```

{{< /tab >}}
{{< tab "Windows CMD" >}}

```cmd
:: First get JSON Web Token
:: Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: cURL example to create document preview images
curl -v "https://api.groupdocs.cloud/v2.0/annotation/preview/create" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\": { \"FilePath\": \"one-page.docx\" }}"
```

{{< /tab >}}
{{< tab "Response" >}}

```javascript
{
  "totalCount": 1,
  "entries": [
    {
      "number": 0,
      "link": {
        "href": "https://api.groupdocs.cloud/v2.0/annotation/storage/file/one-page_docx/page_0.png",
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
var options = new PreviewOptions {FileInfo = fileInfo};
 
var request = new GetPagesRequest(options);
 
var response = apiInstance.GetPages(request);
Console.WriteLine("GetPages: pages count = " + response.TotalCount);
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
fileInfo.setFilePath("Annotationdocs\\one-page.docx");
 
PreviewOptions options = new PreviewOptions();
options.setFileInfo(fileInfo);        
 
GetPagesRequest request = new GetPagesRequest(options);
 
// Executing api method.
PageImages response = apiInstance.getPages(request);
 
System.out.println("GetPages: pages count = " + response.getTotalCount());
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
$fileInfo->setFilePath("annotationdocs\\one-page.docx");
 
$options = new GroupDocs\Annotation\Model\PreviewOptions();
$options->setFileInfo($fileInfo);
 
$request = new GroupDocs\Annotation\Model\Requests\GetPagesRequest($options);
$response = $apiInstance->getPages($request);
 
echo "GetPages: pages count = ", $response->getTotalCount();
```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");
 
global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(appSid, appKey);
 
let fileInfo = new annotation_cloud.FileInfo();
fileInfo.filePath = "annotationdocs\\one-page.docx";
let options = new annotation_cloud.PreviewOptions();
options.fileInfo = fileInfo;          
 
const response = await previewApi.getPages(new annotation_cloud.GetPagesRequest(options));
 
console.log("GetPages: pages count = " + response.totalCount);
```

{{< /tab >}} {{< tab "Python" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud
 
app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(app_sid, app_key)
 
file_info = FileInfo()
file_info.file_path = "annotationdocs\\one-page.docx"
 
options = PreviewOptions()
options.file_info = file_info
 
request = GetPagesRequest(options)
response = api.get_pages(request)
 
print("GetPages: pages count = " + str(response.total_count))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'
 
$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($app_sid, $app_key)
 
file_info = GroupDocsAnnotationCloud::FileInfo.new()
file_info.file_path = "annotationdocs\\one-page.docx"
options = GroupDocsAnnotationCloud::PreviewOptions.new()
options.file_info = file_info
 
request = GroupDocsAnnotationCloud::GetPagesRequest.new(options)
response = $api.get_pages(request)
 
puts("GetPages: pages count = " + (response.total_count).to_s)
```

{{< /tab >}} {{< /tabs >}}
