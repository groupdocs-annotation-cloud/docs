---
id: "text-strikeout-annotation"
url: "annotation/text-strikeout-annotation"
title: "Text Strikeout Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

Text Strikeout annotation marks text fragment with a strikethrough styling

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
    'Type': 'TextStrikeout',
    'Text': 'This is text strikeout annotation',
    'CreatorName': 'Anonym A.',
    'Points': [ {
      'X': 80,
      'Y': 730
     },
     {
      'X': 240,
      'Y': 730
     },
     {
      'X': 80,
      'Y': 760
     },
     {
      'X': 240,
      'Y': 650
     }
    ],
    'PageNumber': 0,
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
    'CreatedOn': '2020-10-02T06:52:01.376Z'
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
        Points = new List<Point>
        {
            new Point {X = 80, Y = 730}, new Point {X=240, Y=730}, new Point {X=80, Y=650}, new Point {X=240, Y=650}
        },
        FontColor = 65535,
        PageNumber = 0,
        Type = AnnotationInfo.TypeEnum.TextStrikeout,
        Text = "This is text strikeout annotation",
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
Console.WriteLine("AddTextStrikeoutAnnotation: Text Strikeout Annotation added.");

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
annotations[0].setFontColor(1201033);
annotations[0].setType(TypeEnum.TEXTSTRIKEOUT);
annotations[0].setText("This is text strikeout annotation");
annotations[0].setCreatorName("Anonym A.");

// Create request object.
PostAnnotationsRequest request = new PostAnnotationsRequest("Annotationdocs\\one-page.docx", Arrays.asList(annotations));

// Executing api method.
apiInstance.postAnnotations(request);

System.out.println("AddTextStrikeoutAnnotation: TextStrikeout Annotation added.");

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
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_TEXT_STRIKEOUT);
$a->setText("This is text strikeout annotation");
$a->setCreatorName("Anonym A.");

$request = new GroupDocs\Annotation\Model\Requests\postAnnotationsRequest("annotationdocs\\one-page.docx", [$a]);
$apiInstance->postAnnotations($request);

echo "AddTextStrikeoutAnnotation: Text Strikeout Annotation added.";

```

{{< /tab >}} {{< tab tabNum="4" >}}

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
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.Text;
a1.text = "This is text strikeout annotation";
a1.creatorName = "Anonym A.";

var request = new annotation_cloud.PostAnnotationsRequest("Annotationdocs\\one-page.docx", [a1]);
await annotateApi.postAnnotations(request);
console.log("AddTextStrikeoutAnnotation: Text Strikeout Annotation added.");

```

{{< /tab >}} {{< tab tabNum="5" >}}

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
a1.opacity = 0.7
a1.type = "TextStrikeout"
a1.text = "This is text strikeout annotation"
a1.creator_name = "Anonym A."

request = PostAnnotationsRequest("annotationdocs\\one-page.docx", [a1])
api.post_annotations(request)

print("AddTextStrikeoutAnnotation: Text Strikeout Annotation added.")
```

{{< /tab >}} {{< tab tabNum="6" >}}

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
$a1.type = "TextStrikeout"
$a1.text = "This is text strikeout annotation"
$a1.creator_name = "Anonym A."

$request = GroupDocsAnnotationCloud::PostAnnotationsRequest.new("Annotationdocs\\one-page.docx", [$a1])

# Executing an API.
$api.post_annotations($request)

puts("AddTextStrikeoutAnnotation: Text Strikeout Annotation added.")

```

{{< /tab >}} {{< /tabs >}}
