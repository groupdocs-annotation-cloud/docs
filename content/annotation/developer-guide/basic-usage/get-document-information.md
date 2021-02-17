---
id: "get-document-information"
url: "annotation/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Annotation Cloud"
weight: 10
description: ""
keywords: ""
---
This API retrieves document information. It returns an object that contains the document description with metadata and coordinates of text on pages.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get [document information](https://apireference.groupdocs.cloud/annotation/#/Info/GetInfo).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -v "https://api.groupdocs.cloud/v2.0/annotation/info" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>" \
-d "{ 'FilePath': 'annotationdocs/one-page.docx'}
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
{
  "name": "one-page.docx",
  "path": "annotationdocs/one-page.docx",
  "extension": ".docx",
  "fileFormat": "Microsoft Word Open XML format",
  "size": 16646,
  "dateModified": "2021-02-05T05:17:10Z",
  "pages": [
    {
      "number": 1,
      "width": 595,
      "height": 841
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](annotation/available-sdks).

## Get Document Information In Code ##

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java  & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
var configuration = new Configuration(MyAppSid, MyAppKey);
  
var apiInstance = new InfoApi(configuration);
var response = apiInstance.GetSupportedFileFormats();
```

{{< /tab >}} {{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyAppSid, MyAppKey);
  
InfoApi apiInstance = new InfoApi(configuration); 
FormatsResult response = apiInstance.getSupportedFileFormats();
```

{{< /tab >}} {{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;
 
$AppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);
 
$infoApi= new GroupDocs\Annotation\InfoApi($configuration);
 
$response = $infoApi->getSupportedFileFormats();
```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");
 
global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.infoApi = annotation_cloud.InfoApi.fromKeys(appSid, appKey);
 
let response = await infoApi.getSupportedFileFormats();
```

{{< /tab >}} {{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud
 
app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
infoApi = groupdocs_annotation_cloud.InfoApi.from_keys(app_sid, app_key)
 
result = infoApi.get_supported_file_formats()
```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'
 
$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
infoApi = GroupDocsAnnotationCloud::InfoApi.from_keys($app_sid, $app_key)
 
result = infoApi.get_supported_file_formats()
```

{{< /tab >}} {{< /tabs >}}
