---
id: "text-replacement-annotation"
url: "annotation/text-replacement-annotation"
title: "Text Replacement Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---
Text Replacement annotation replaces original text with other provided text fragment

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
# 1. Get JSON Web Token
#    Replace $CLIENT_ID and $CLIENT_SECRET with your actual credentials (or set them as environment variables).
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# 2. Add annotation into a document
#    $JWT_TOKEN should contain the token obtained from the previous request.
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
        "Type": "TextReplacement",
        "Text": "This is text replacement annotation",
        "TextToReplace": "replaced text",
        "CreatorName": "Anonym A.",
        "Points": [
          { "X": 80,  "Y": 730 },
          { "X": 240, "Y": 730 },
          { "X": 80,  "Y": 760 },
          { "X": 240, "Y": 650 }
        ],
        "PageNumber": 0,
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
        "CreatedOn": "2020-10-02T06:52:01.376Z"
      }
    ]
  }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# 1. Get JSON Web Token
#    Ensure $env:CLIENT_ID and $env:CLIENT_SECRET are set in your environment.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# 2. Add annotation into a document
#    $env:JWT_TOKEN must contain the JWT returned from the previous call.
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/add" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{ 
    'FileInfo': { 'FilePath': 'annotationdocs/one-page.docx' }, 
    'OutputPath': 'Output/output.docx', 
    'Annotations': [ 
      { 
        'Type': 'TextReplacement', 
        'Text': 'This is text replacement annotation', 
        'TextToReplace': 'replaced text', 
        'CreatorName': 'Anonym A.', 
        'Points': [ 
          { 'X': 80, 'Y': 730 }, 
          { 'X': 240, 'Y': 730 }, 
          { 'X': 80, 'Y': 760 }, 
          { 'X': 240, 'Y': 650 } 
        ], 
        'PageNumber': 0, 
        'Replies': [ 
          { 'Comment': 'First comment', 'RepliedOn': '2020-10-02T06:52:01.376Z' }, 
          { 'Comment': 'Second comment', 'RepliedOn': '2020-10-02T06:52:01.376Z' } 
        ], 
        'CreatedOn': '2020-10-02T06:52:01.376Z' 
      } 
    ] 
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
rem 1. Get JSON Web Token
rem    Set CLIENT_ID, CLIENT_SECRET and JWT_TOKEN in the CMD environment before running.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

rem 2. Add annotation into a document
rem    Use %JWT_TOKEN% obtained from the previous request.
curl -v "https://api.groupdocs.cloud/v2.0/annotation/add" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"annotationdocs/one-page.docx\"},\"OutputPath\":\"Output/output.docx\",\"Annotations\":[{\"Type\":\"TextReplacement\",\"Text\":\"This is text replacement annotation\",\"TextToReplace\":\"replaced text\",\"CreatorName\":\"Anonym A.\",\"Points\":[{\"X\":80,\"Y\":730},{\"X\":240,\"Y\":730},{\"X\":80,\"Y\":760},{\"X\":240,\"Y\":650}],\"PageNumber\":0,\"Replies\":[{\"Comment\":\"First comment\",\"RepliedOn\":\"2020-10-02T06:52:01.376Z\"},{\"Comment\":\"Second comment\",\"RepliedOn\":\"2020-10-02T06:52:01.376Z\"}],\"CreatedOn\":\"2020-10-02T06:52:01.376Z\"}]}"
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
        Points = new List<Point>
        {
            new Point {X = 80, Y = 730}, new Point {X=240, Y=730}, new Point {X=80, Y=650}, new Point {X=240, Y=650}
        },
        FontColor = 65535,
        PageNumber = 0,
        Opacity = 0.7,
        Type = AnnotationInfo.TypeEnum.TextReplacement,
        Text = "This is text replacement annotation",
        TextToReplace = "replaced text",
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
Console.WriteLine("AddTextReplacementAnnotation: Text Replacement Annotation added: " + link.Title);
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
 
Point[] pt = new Point[4];
pt[0] = new Point();
pt[0].setX(80.0);
pt[0].setY(730.0);
pt[1] = new Point();
pt[1].setX(240.0);
pt[1].setY(730.0);
pt[2] = new Point();
pt[2].setX(80.0);
pt[2].setY(650.0);                          
pt[3] = new Point();
pt[3].setX(240.0);
pt[3].setY(650.0);              
annotations[0].setPoints(Arrays.asList(pt));
 
annotations[0].setPageNumber(0);
annotations[0].setOpacity(0.7);
annotations[0].setType(TypeEnum.TEXTREPLACEMENT);
annotations[0].setText("This is text replacement annotation");
annotations[0].setTextToReplace("Text to replace");
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
 
System.out.println("AddTextReplacementAnnotation: TextReplacement Annotation added: " + result.getTitle());
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
$pt1 = new GroupDocs\Annotation\Model\Point();
$pt1->setX(80);
$pt1->setY(730);
$pt2 = new GroupDocs\Annotation\Model\Point();
$pt2->setX(80);
$pt2->setY(730);        
$pt3 = new GroupDocs\Annotation\Model\Point();
$pt3->setX(80);
$pt3->setY(730);        
$pt4 = new GroupDocs\Annotation\Model\Point();
$pt4->setX(80);
$pt4->setY(730);        
$a->setPoints([$pt1, $pt2, $pt3, $pt4]);
 
$a->setPageNumber(0);
$a->setFontColor(1201033);
$a->setFontSize(12);
$a->setOpacity(0.7);
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_TEXT_REPLACEMENT);
$a->setText("This is text replacement annotation");
$a->setTextToReplace("Text to replace");
$a->setCreatorName("Anonym A.");   
 
$fileInfo = new GroupDocs\Annotation\Model\FileInfo();
$fileInfo->setFilePath("annotationdocs\\one-page.docx");
 
$options = new GroupDocs\Annotation\Model\AnnotateOptions();
$options->setFileInfo($fileInfo);
$options->setAnnotations([$a]);
$options->setOutputPath("Output\\output.docx");
 
$request = new GroupDocs\Annotation\Model\Requests\annotateRequest($options);
$result = $apiInstance->annotate($request);
 
echo "AddTextReplacementAnnotation: Text Replacement Annotation added: " . $result->getHref();
```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");
 
global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(appSid, appKey);
 
let a1 = new annotation_cloud.AnnotationInfo();
let p1 = new annotation_cloud.Point();
p1.x = 80;
p1.y = 730;
let p2 = new annotation_cloud.Point();
p2.x = 240;
p2.y = 730;
let p3 = new annotation_cloud.Point();
p3.x = 80;
p3.y = 650;
let p4 = new annotation_cloud.Point();
p4.x = 240;
p4.y = 650;
a1.points = [p1, p2, p3, p4];
a1.pageNumber = 0;
a1.fontColor = 65535;
a1.fontSize = 12;
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.TextReplacement; 
a1.text = "This is text replacement annotation";    
a1.textToReplace = "Text to replace";
a1.creatorName = "Anonym A.";
 
let fileInfo = new annotation_cloud.FileInfo();
fileInfo.filePath = "annotationdocs\\one-page.docx";
let options = new annotation_cloud.AnnotateOptions();
options.fileInfo = fileInfo;
options.annotations = [a1];
options.outputPath = "Output/output.docx";
let result = await annotateApi.annotate(new annotation_cloud.AnnotateRequest(options));
 
console.log("AddTextReplacementAnnotation: Text Replacement Annotation added: " + result.href);
```

{{< /tab >}} {{< tab "Python" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud
 
app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api = groupdocs_annotation_cloud.AnnotateApi.from_keys(app_sid, app_key)
 
a1 = groupdocs_annotation_cloud.AnnotationInfo()
p1 = groupdocs_annotation_cloud.Point()
p1.x = 80
p1.y = 730
p2 = groupdocs_annotation_cloud.Point()
p2.x = 240
p2.y = 730
p3 = groupdocs_annotation_cloud.Point()
p3.x = 80
p3.y = 650
p4 = groupdocs_annotation_cloud.Point()
p4.x = 240
p4.y = 650
a1.points = [p1, p2, p3, p4]
a1.page_number = 0
a1.font_color = 1201033
a1.font_size = 12
a1.opacity = 0.7
a1.type = "TextReplacement"  
a1.text = "This is text replacement annotation"        
a1.text_to_replace = "Text to replace"
a1.creator_name = "Anonym A."
 
file_info = FileInfo()
file_info.file_path = "annotationdocs\\one-page.docx"
options = AnnotateOptions()
options.file_info = file_info
options.annotations = [a1]
options.output_path = "Output\\output.docx"
 
request = AnnotateRequest(options)
result = api.annotate(request)         
 
print("AddTextReplacementAnnotation: Text Replacement Annotation added: " + result['href'])
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'
 
$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($app_sid, $app_key)
 
$a1 = GroupDocsAnnotationCloud::AnnotationInfo.new
$p1 = GroupDocsAnnotationCloud::Point.new
$p1.x = 1
$p1.y = 1
$p2 = GroupDocsAnnotationCloud::Point.new
$p2.x = 1
$p2.y = 1
$p3 = GroupDocsAnnotationCloud::Point.new
$p3.x = 1
$p3.y = 1
$p4 = GroupDocsAnnotationCloud::Point.new
$p4.x = 1
$p4.y = 1
$a1.points = [$p1, $p2, $p3, $p4]
$a1.page_number = 0
$a1.font_color = 1201033
$a1.font_size = 12
$a1.opacity = 0.7
$a1.type = "TextReplacement"
$a1.text = "This is text replacement annotation"  
$a1.text_to_replace = "Text to replace"
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
 
puts("AddTextReplacementAnnotation: Text Replacement Annotation added: " + result.href)
```

{{< /tab >}} {{< /tabs >}}
