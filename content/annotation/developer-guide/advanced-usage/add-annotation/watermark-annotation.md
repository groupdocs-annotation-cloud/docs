---
id: "watermark-annotation"
url: "annotation/watermark-annotation"
title: "Watermark Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

Watermark annotation adds text watermark

### API Usage ###

There are steps that usage of GroupDocs.Annotation Cloud consists of:

1. Upload input document into cloud storage and other files, like image annotation
1. Add annotation
1. Export document with annotations

```html
HTTP POST ~/annotation
```

[Swagger UI](https://apireference.groupdocs.cloud/annotation/) lets you call this REST API directly from the browser.

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```javascript
// First get JSON Web Token
// Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type=client_credentials&client_id=xxxx&client_secret=xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/annotation/?filePath=annotationdocs%2Fone-page.docx" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>" \
-d "
[
  {
    'Type': 'Watermark',
    'Text': 'This is watermark annotation',
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
"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
code 200 OK
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java  & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyAppSid, MyAppKey);

var apiInstance = new AnnotateApi(configuration);

var request = new PostAnnotationsRequest();
request.filePath = "one-page.docx";
AnnotationInfo[] annotations =
{
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 1, Y = 1 },
        Box = new Rectangle { X = 100, Y = 100, Width = 100, Height = 100 },
        FontColor = 65535,
        FontSize = 12,
        Angle = 75,
        PageNumber = 0,
        Opacity = 0.7,
        Type = AnnotationInfo.TypeEnum.Watermark,
        Text = "This is watermark annotation",
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
request.annotations = annotations.ToList();
apiInstance.PostAnnotations(request);
Console.WriteLine("AddWatermarkAnnotation: Watermark Annotation added.");

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
annotations[0].setFontColor(1201033);
annotations[0].setFontSize(12.0);
annotations[0].setAngle(75.0);
annotations[0].setOpacity(0.7);
annotations[0].setType(TypeEnum.WATERMARK);
annotations[0].setText("This is watermark annotation");
annotations[0].setCreatorName("Anonym A.");

// Create request object.
PostAnnotationsRequest request = new PostAnnotationsRequest("Annotationdocs\\one-page.docx", Arrays.asList(annotations));

// Executing api method.
apiInstance.postAnnotations(request);

System.out.println("AddWatermarkAnnotation: Watermark Annotation added.");

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
$a->setFontColor(1201033);
$a->setFontSize(12);
$a->setOpacity(0.7);
$a->setAngle(75);
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_WATERMARK);
$a->setText("This is text watermark annotation");
$a->setCreatorName("Anonym A.");

$request = new GroupDocs\Annotation\Model\Requests\postAnnotationsRequest("annotationdocs\\one-page.docx", [$a]);
$apiInstance->postAnnotations($request);

echo "AddWatermarkAnnotation: Text Watermark Annotation added.";

```

{{< /tab >}} {{< tab tabNum="4" >}}

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
a1.penColor = 1201033;
a1.penStyle = annotation_cloud.AnnotationInfo.PenStyleEnum.Solid;
a1.penWidth = 1;
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.Watermark;
a1.text = "This is watermark annotation";
a1.angle = 75;
a1.creatorName = "Anonym A.";

var request = new annotation_cloud.PostAnnotationsRequest("Annotationdocs\\one-page.docx", [a1]);
await annotateApi.postAnnotations(request);
console.log("AddWatermarkAnnotation: Watermark Annotation added.");

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
a1.font_color = 1201033
a1.font_size = 12
a1.opacity = 0.7
a1.angle = 75
a1.type = "Watermark"
a1.text = "This is text watermark annotation"
a1.creator_name = "Anonym A."

request = PostAnnotationsRequest("annotationdocs\\one-page.docx", [a1])
api.post_annotations(request)

print("AddWatermarkAnnotation: Text Watermark Annotation added.")
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
$a1.font_color = 1201033
$a1.font_size = 12
$a1.opacity = 0.7
$a1.angle = 75
$a1.type = "Watermark"
$a1.text = "This is text watermark annotation"
$a1.creator_name = "Anonym A."

$request = GroupDocsAnnotationCloud::PostAnnotationsRequest.new("Annotationdocs\\one-page.docx", [$a1])

# Executing an API.
$api.post_annotations($request)

puts("AddWatermarkAnnotation: Text Watermark Annotation added.")
```

{{< /tab >}} {{< /tabs >}}
