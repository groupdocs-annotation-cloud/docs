---
id: "text-field-annotation"
url: "annotation/text-field-annotation"
title: "Text field Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---
Text field annotation adds rectangle with a text inside

## API usage

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation (using File API)
1. Add annotation(s)
1. Download document with annotations (using File API)

```html
HTTP POST ~/annotation/add
```

[Swagger UI](https://apireference.groupdocs.cloud/annotation/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# Get JSON Web Token
# Place your Client Id and Client Secret in the CLIENT_ID and CLIENT_SECRET environment variables.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# Add annotation into document
curl -v "https://api.groupdocs.cloud/v2.0/annotation/add" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "FileInfo": {
      "FilePath": "annotationdocs/one-page.docx"
    },
    "OutputPath": "Output/output.docx",
    "Annotations": [
      {
        "Type": "TextField",
        "Text": "This is text field annotation",
        "CreatorName": "Anonym A.",
        "Box": {
          "X": 100,
          "Y": 100,
          "Width": 100,
          "Height": 100
        },
        "PageNumber": 0,
        "AnnotationPosition": {
          "X": 1,
          "Y": 1
        },
        "Replies": [
          {
            "Comment": "First comment",
            "RepliedOn": "2020-10-02T06:52:01.376Z"
          },
          {
            "Comment": "Second comment",
            "RepliedOn": "2020-10-02T06:52:01.376Z"
          }
        ],
        "CreatedOn": "2020-10-02T06:52:01.376Z",
        "PenStyle": "Solid",
        "PenColor": 65535,
        "PenWidth": 3,
        "BackgroundColor": 65535,
        "Opacity": 0.7
      }
    ]
  }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# Get JSON Web Token
# Set your Client Id and Client Secret in the $env:CLIENT_ID and $env:CLIENT_SECRET environment variables.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# Add annotation into document
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/add" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'FileInfo': {
      'FilePath': 'annotationdocs/one-page.docx'
    },
    'OutputPath': 'Output/output.docx',
    'Annotations': [
      {
        'Type': 'TextField',
        'Text': 'This is text field annotation',
        'CreatorName': 'Anonym A.',
        'Box': {
          'X': 100,
          'Y': 100,
          'Width': 100,
          'Height': 100
        },
        'PageNumber': 0,
        'AnnotationPosition': {
          'X': 1,
          'Y': 1
        },
        'Replies': [
          {
            'Comment': 'First comment',
            'RepliedOn': '2020-10-02T06:52:01.376Z'
          },
          {
            'Comment': 'Second comment',
            'RepliedOn': '2020-10-02T06:52:01.376Z'
          }
        ],
        'CreatedOn': '2020-10-02T06:52:01.376Z',
        'PenStyle': 'Solid',
        'PenColor': 65535,
        'PenWidth': 3,
        'BackgroundColor': 65535,
        'Opacity': 0.7
      }
    ]
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: Get JSON Web Token
:: Set your Client Id and Client Secret in the CLIENT_ID and CLIENT_SECRET environment variables.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: Add annotation into document
curl -v "https://api.groupdocs.cloud/v2.0/annotation/add" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"annotationdocs/one-page.docx\"},\"OutputPath\":\"Output/output.docx\",\"Annotations\":[{\"Type\":\"TextField\",\"Text\":\"This is text field annotation\",\"CreatorName\":\"Anonym A.\",\"Box\":{\"X\":100,\"Y\":100,\"Width\":100,\"Height\":100},\"PageNumber\":0,\"AnnotationPosition\":{\"X\":1,\"Y\":1},\"Replies\":[{\"Comment\":\"First comment\",\"RepliedOn\":\"2020-10-02T06:52:01.376Z\"},{\"Comment\":\"Second comment\",\"RepliedOn\":\"2020-10-02T06:52:01.376Z\"}],\"CreatedOn\":\"2020-10-02T06:52:01.376Z\",\"PenStyle\":\"Solid\",\"PenColor\":65535,\"PenWidth\":3,\"BackgroundColor\":65535,\"Opacity\":0.7}]}"
```

{{< /tab >}}
{{< tab "Response" >}}

```bash
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
 
AnnotationInfo[] annotations =
{
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 1, Y = 1 },
        Box = new Rectangle { X = 100, Y = 100, Width = 100, Height = 100 },
        FontColor = 65535,
        FontSize = 12,
        PageNumber = 0,
        Opacity = 0.7,
        Type = AnnotationInfo.TypeEnum.TextField,
        Text = "This is text field annotation",
        CreatorName = "Anonym A.",
        CreatedOn = DateTime.Now,
        Replies = new List<AnnotationReplyInfo>
        {
            new AnnotationReplyInfo
            {
                Comment = "First comment",
                RepliedOn = DateTime.Now
            },
            new AnnotationReplyInfo
            {
                Comment = "Second comment",
                RepliedOn = DateTime.Now
            }
        }
    },
};
 
var options = new AnnotateOptions
{
    FileInfo = fileInfo,
    Annotations = annotations.ToList(),
    OutputPath = "Output/output.docx"
};
 
var link = apiInstance.Annotate(new AnnotateRequest(options));
Console.WriteLine("AddTextFieldAnnotation: TextField Annotation added: " + link.Title);
```

{{< /tab >}} {{< tab "Java  & Android" >}}

```java
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyAppSid, MyAppKey);
  
AnnotateApi apiInstance = new AnnotateApi(configuration); 
 
// Create annotation/s.
AnnotationInfo[] annotations = new AnnotationInfo[1];
annotations[0] = new AnnotationInfo();
 
Point pt = new Point();
pt.setX(1.0);
pt.setY(1.0);
annotations[0].setAnnotationPosition(pt);
 
Rectangle r = new Rectangle();
r.setX(100.0);
r.setY(100.0);
r.setWidth(200.0);
r.setHeight(100.0);
 
annotations[0].setBox(r);
annotations[0].setPageNumber(0);
annotations[0].setFontColor(1201033);
annotations[0].setFontSize(12.0);
annotations[0].setOpacity(0.7);
annotations[0].setType(TypeEnum.TEXTFIELD);
annotations[0].setText("Text field text");
annotations[0].setCreatorName("Anonym A.");
 
// Create request object.
FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Annotationdocs\\one-page.docx");
 
AnnotateOptions options = new AnnotateOptions();
options.setFileInfo(fileInfo);
options.setAnnotations(Arrays.asList(annotations));
options.setOutputPath("Output/one-page-annotated.docx");
 
AnnotateRequest request = new AnnotateRequest(options);
 
// Executing api method.
AnnotationApiLink result = apiInstance.annotate(request);
 
System.out.println("AddTextFieldAnnotation: TextField Annotation added: " + result.getTitle());
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
 
$a = new GroupDocs\Annotation\Model\AnnotationInfo();
$pt = new GroupDocs\Annotation\Model\Point();
$pt->setX(1);
$pt->setY(1);
$a->setAnnotationPosition($pt);
$box = new GroupDocs\Annotation\Model\Rectangle();
$box->setX(100);
$box->setY(100);
$box->setWidth(200);
$box->setHeight(100);
$a->setBox($box);
$a->setPageNumber(0);
$a->setFontColor(1201033);
$a->setFontSize(12);
$a->setOpacity(0.7);
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_TEXT_FIELD);
$a->setText("Text field text");
$a->setCreatorName("Anonym A.");   
 
$fileInfo = new GroupDocs\Annotation\Model\FileInfo();
$fileInfo->setFilePath("annotationdocs\\one-page.docx");
 
$options = new GroupDocs\Annotation\Model\AnnotateOptions();
$options->setFileInfo($fileInfo);
$options->setAnnotations([$a]);
$options->setOutputPath("Output\\output.docx");
 
$request = new GroupDocs\Annotation\Model\Requests\annotateRequest($options);
$result = $apiInstance->annotate($request);
 
echo "AddTextFieldAnnotation: Text Field Annotation added: " . $result->getHref();
```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");
 
global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(appSid, appKey);
 
let a1 = new annotation_cloud.AnnotationInfo();
a1.annotationPosition = new annotation_cloud.Point();
a1.annotationPosition.x = 1;
a1.annotationPosition.y = 1;
a1.box = new annotation_cloud.Rectangle();
a1.box.x = 100;
a1.box.y = 100;
a1.box.width = 200;
a1.box.height = 100;
a1.pageNumber = 0;
a1.fontColor = 65535;
a1.fontSize = 12;
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.TextField;       
a1.text = "Text field text";
a1.creatorName = "Anonym A.";
 
let fileInfo = new annotation_cloud.FileInfo();
fileInfo.filePath = "annotationdocs\\one-page.docx";
let options = new annotation_cloud.AnnotateOptions();
options.fileInfo = fileInfo;
options.annotations = [a1];
options.outputPath = "Output/output.docx";
let result = await annotateApi.annotate(new annotation_cloud.AnnotateRequest(options));
 
console.log("AddTextFieldAnnotation: Text Field Annotation added: " + result.href);
```

{{< /tab >}} {{< tab "Python" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud
 
app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(app_sid, app_key)
 
a1 = groupdocs_annotation_cloud.AnnotationInfo()
a1.annotation_position = groupdocs_annotation_cloud.Point()
a1.annotation_position.x = 1
a1.annotation_position.y = 1
a1.box = groupdocs_annotation_cloud.Rectangle()
a1.box.x = 100
a1.box.y = 100
a1.box.width = 200
a1.box.height = 100
a1.page_number = 0
a1.font_color = 1201033
a1.font_size = 12
a1.opacity = 0.7
a1.type = "TextField"           
a1.text = "Text field text"
a1.creator_name = "Anonym A."
 
file_info = FileInfo()
file_info.file_path = "annotationdocs\\one-page.docx"
options = AnnotateOptions()
options.file_info = file_info
options.annotations = [a1]
options.output_path = "Output\\output.docx"
 
request = AnnotateRequest(options)
result = api.annotate(request)         
 
print("AddTextFieldAnnotation: Text Field Annotation added: " + result['href'])
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'
 
$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($app_sid, $app_key)
 
$a1 = GroupDocsAnnotationCloud::AnnotationInfo.new
$a1.annotation_position = GroupDocsAnnotationCloud::Point.new
$a1.annotation_position.x = 1
$a1.annotation_position.y = 1
$a1.box = GroupDocsAnnotationCloud::Rectangle.new
$a1.box.x = 100
$a1.box.y = 100
$a1.box.width = 200
$a1.box.height = 100
$a1.page_number = 0
$a1.font_color = 1201033
$a1.font_size = 12
$a1.opacity = 0.7
$a1.type = "TextField"   
$a1.text = "Text field text"
$a1.creator_name = "Anonym A."     
 
file_info = GroupDocsAnnotationCloud::FileInfo.new()
file_info.file_path = "annotationdocs\\one-page.docx"
 
options = GroupDocsAnnotationCloud::AnnotateOptions.new()
options.file_info = file_info
options.annotations = [$a1]
options.output_path = "Output/output.docx"
 
$request = GroupDocsAnnotationCloud::AnnotateRequest.new(options)
 
# Executing an API.
result = $api.annotate($request)
 
puts("AddTextFieldAnnotation: Text Field Annotation added: " + result.href)
```

{{< /tab >}} {{< /tabs >}}
