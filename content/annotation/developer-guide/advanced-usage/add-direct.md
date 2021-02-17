---
id: "add-direct"
url: "annotation/add-direct"
title: "Add annotation with downloading output document at once"
productName: "GroupDocs.Annotation Cloud"
weight: 2
description: ""
keywords: ""
---

AnnotateDirect method allows to add annotations to the document and returns output document.

### API Usage ###

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation and get the result immediately

```html
HTTP PUT ~/annotation/add
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
  
// cURL example to add annotation into document with downloading output document
curl -v "https://api.groupdocs.cloud/v2.0/annotation/add" \
-X PUT \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>" \
-d "
{
  'FileInfo': {
    'FilePath': 'annotationdocs/one-page.docx'
  },
  'Annotations': [
  {
    'Type': 'Area',
    'Text': 'This is area annotation',
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
}
"

```javascript
200 OK
<File stream>
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](annotation/available-sdks).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java  & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

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
        PageNumber = 0,
        BackgroundColor = 65535,
        PenColor = 65535,
        PenStyle = AnnotationInfo.PenStyleEnum.Solid,
        PenWidth = 3,
        Type = AnnotationInfo.TypeEnum.Area,
        Text = "This is area annotation",
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
    Annotations = annotations.ToList()
};
 
var stream = apiInstance.AnnotateDirect(new AnnotateDirectRequest(options));
Console.WriteLine("AddAnnotationDirect: Area Annotation added. Stream size: " + stream.Length);
```

{{< /tab >}} {{< tab tabNum="2" >}}

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
annotations[0].setPenColor(1201033);
annotations[0].setPenStyle(PenStyleEnum.SOLID);         
annotations[0].setPenWidth(1);
annotations[0].setBackgroundColor(65535);
annotations[0].setOpacity(0.7);
annotations[0].setType(TypeEnum.AREA);
annotations[0].setText("This is area annotation");
annotations[0].setCreatorName("Anonym A.");
 
// Create request object.
FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Annotationdocs\\one-page.docx");
 
AnnotateOptions options = new AnnotateOptions();
options.setFileInfo(fileInfo);
options.setAnnotations(Arrays.asList(annotations));
 
AnnotateDirectRequest request = new AnnotateDirectRequest(options);
 
// Executing api method.
File response = apiInstance.annotateDirect(request);
 
System.out.println("AddAnnotationsDirect: Document Length: " + response.getTotalSpace());
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
$a->setPenColor(1201033);
$a->setPenStyle(GroupDocs\Annotation\Model\AnnotationInfo::PEN_STYLE_SOLID);
$a->setPenWidth(1);
$a->setOpacity(0.7);
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_AREA);
$a->setText("This is area annotation");
$a->setCreatorName("Anonym A.");   
 
$fileInfo = new GroupDocs\Annotation\Model\FileInfo();
$fileInfo->setFilePath("annotationdocs\\one-page.docx");
 
$options = new GroupDocs\Annotation\Model\AnnotateOptions();
$options->setFileInfo($fileInfo);
$options->setAnnotations([$a]);
 
$request = new GroupDocs\Annotation\Model\Requests\annotateDirectRequest($options);
$result = $apiInstance->annotateDirect($request);
 
echo "AddAnnotationDirect: File size: " . $result->getSize();
```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

```

{{< /tab >}} {{< tab tabNum="5" >}}

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
a1.pen_color = 1201033
a1.pen_style = "Solid"
a1.pen_width = 1
a1.opacity = 0.7
a1.type = "Area"
a1.text = "This is area annotation"
a1.creator_name = "Anonym A."
 
file_info = FileInfo()
file_info.file_path = "annotationdocs\\one-page.docx"
options = AnnotateOptions()
options.file_info = file_info
options.annotations = [a1]
 
request = AnnotateDirectRequest(options)
result = api.annotate_direct(request)         
 
print("AddAnnotationDirect: Document Length: " + str(os.path.getsize(result)))
```

{{< /tab >}} {{< tab tabNum="6" >}}

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
$a1.pen_color = 1201033
$a1.pen_style = "Solid"
$a1.pen_width = 1
$a1.opacity = 0.7
$a1.type = "Area"
$a1.text = "This is area annotation"
$a1.creator_name = "Anonym A."     
 
file_info = GroupDocsAnnotationCloud::FileInfo.new()
file_info.file_path = "annotationdocs\\one-page.docx"
 
options = GroupDocsAnnotationCloud::AnnotateOptions.new()
options.file_info = file_info
options.annotations = [$a1]
 
$request = GroupDocsAnnotationCloud::AnnotateDirectRequest.new(options)
 
# Executing an API.
result = $api.annotate_direct($request)
 
puts("AddAnnotationsDirect: file size = " + result.length.to_s)
```

{{< /tab >}} {{< /tabs >}}
