---
id: "multiple-annotations"
url: "annotation/multiple-annotations"
title: "Multiple Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

This REST API allows to add multiple annotations to the document

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
    'PenStyle': 'Solid',
    'PenColor': 65535,
    'PenWidth': 3
  },
  {
    'Type': 'Point',
    'CreatorName': 'Anonym A.',
    'Box': {
      'X': 375,
      'Y': 59,
      'Width': 88,
      'Height': 37
    },
    'PageNumber': 2,
    'AnnotationPosition': {
      'X': 852,
      'Y': 59
    },
    'PenStyle': 'Solid',
    'PenColor': 65535,
    'PenWidth': 3
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
request.filePath = "ten-pages.pdf";
AnnotationInfo[] annotations =
{
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 1, Y = 1 },
        Box = new Rectangle { X = 100, Y = 100, Width = 100, Height = 100 },
        PageNumber = 1,
        BackgroundColor=65535,
        PenColor = 65535,
        PenStyle = AnnotationInfo.PenStyleEnum.Solid,
        PenWidth = 3,
        Opacity = 0.7,
        Type = AnnotationInfo.TypeEnum.Area,
        Text="This is area annotation",
        CreatorName = "Anonym A.",
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
        } },
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 852, Y = 59.388262910798119 },
        Box = new Rectangle { X = 375.89276123046875, Y = 59.388263702392578, Width = 88.7330551147461, Height = 37.7290153503418 },
        PageNumber = 2,
        PenColor = 1201033,
        PenStyle = 0,
        PenWidth = 1,
        Type = AnnotationInfo.TypeEnum.Area,
        CreatorName = "Anonym A."
    },
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 852, Y = 59.388262910798119 },
        Box = new Rectangle { X = 375.89276123046875, Y = 59.388263702392578, Width = 88.7330551147461, Height = 37.7290153503418 },
        PageNumber = 4,
        Type = AnnotationInfo.TypeEnum.Point,
        CreatorName = "Anonym A."
    },
    new AnnotationInfo
    {
        AnnotationPosition = new Point { X = 852, Y = 59.388262910798119 },
        Box = new Rectangle { X = 375.89276123046875, Y = 59.388263702392578, Width = 88.7330551147461, Height = 37.7290153503418 },
        PageNumber = 5,
        PenColor = 1201033,
        PenStyle = 0,
        PenWidth = 1,
        Type = AnnotationInfo.TypeEnum.Arrow,
        CreatorName = "Anonym A."
    }
};
request.annotations = annotations.ToList();
apiInstance.PostAnnotations(request);
Console.WriteLine("AddMultipleAnnotations: Multiple Annotation added.");

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyAppSid, MyAppKey);

AnnotateApi apiInstance = new AnnotateApi(configuration);

// Create annotation/s.
AnnotationInfo[] annotations = new AnnotationInfo[4];
annotations[0] = new AnnotationInfo();

Point pt = new Point();
pt.setX(852.0);
pt.setY(59.388262910798119);
annotations[0].setAnnotationPosition(pt);

Rectangle r = new Rectangle();
r.setX(375.89276123046875);
r.setY(59.388262910798119);
r.setWidth(88.7330551147461);
r.setHeight(37.7290153503418);

annotations[0].setBox(r);

annotations[0].setPageNumber(1);
annotations[0].setPenColor(1201033);
annotations[0].setPenStyle(PenStyleEnum.SOLID);
annotations[0].setPenWidth(1);
annotations[0].setOpacity(0.7);
annotations[0].setType(TypeEnum.DISTANCE);
annotations[0].setText("This is distance annotation");
annotations[0].setCreatorName("Anonym A.");

annotations[1] = new AnnotationInfo();

annotations[1].setAnnotationPosition(pt);
annotations[1].setBox(r);
annotations[1].setPageNumber(2);
annotations[1].setPenColor(1201033);
annotations[1].setPenStyle(PenStyleEnum.SOLID);
annotations[1].setPenWidth(1);
annotations[0].setOpacity(0.7);
annotations[1].setType(TypeEnum.AREA);
annotations[1].setText("This is area annotation");
annotations[1].setCreatorName("Anonym A.");

annotations[2] = new AnnotationInfo();
annotations[2].setAnnotationPosition(pt);
annotations[2].setBox(r);
annotations[2].setPageNumber(4);
annotations[0].setOpacity(0.7);
annotations[2].setType(TypeEnum.POINT);
annotations[0].setText("This is point annotation");
annotations[2].setCreatorName("Anonym A.");

annotations[3] = new AnnotationInfo();
annotations[3].setAnnotationPosition(pt);
annotations[3].setBox(r);
annotations[3].setPageNumber(5);
annotations[3].setPenColor(1201033);
annotations[3].setPenStyle(PenStyleEnum.SOLID);
annotations[3].setPenWidth(1);
annotations[0].setOpacity(0.7);
annotations[3].setType(TypeEnum.ARROW);
annotations[0].setText("This is arrow annotation");
annotations[3].setCreatorName("Anonym A.");

// Create request object.
PostAnnotationsRequest request = new PostAnnotationsRequest("Annotationdocs\\ten-pages.docx", Arrays.asList(annotations));

// Executing api method.
apiInstance.postAnnotations(request);

System.out.println("AddMultipleAnnotations: Multiple Annotation added.");

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
$pt->setX(852);
$pt->setY(59.388262910798119);
$a->setAnnotationPosition($pt);
$box = new GroupDocs\Annotation\Model\Rectangle();
$box->setX(375.89276123046875);
$box->setY(59.388263702392578);
$box->setWidth(88.7330551147461);
$box->setHeight(37.7290153503418);
$a->setBox($box);
$a->setPageNumber(1);
$a->setPenColor(1201033);
$a->setPenStyle(GroupDocs\Annotation\Model\AnnotationInfo::PEN_STYLE_SOLID);
$a->setPenWidth(1);
$a->setOpacity(0.7);
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_DISTANCE);
$a->setText("This is distance annotation");
$a->setCreatorName("Anonym A.");

$a1 = new GroupDocs\Annotation\Model\AnnotationInfo();
$pt = new GroupDocs\Annotation\Model\Point();
$pt->setX(852);
$pt->setY(59.388262910798119);
$a1->setAnnotationPosition($pt);
$box = new GroupDocs\Annotation\Model\Rectangle();
$box->setX(375.89276123046875);
$box->setY(59.388263702392578);
$box->setWidth(88.7330551147461);
$box->setHeight(37.7290153503418);
$a1->setBox($box);
$a1->setPageNumber(2);
$a1->setPenColor(1201033);
$a1->setPenStyle(0);
$a1->setPenWidth(1);
$a1->setOpacity(0.7);
$a1->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_AREA);
$a1->setText("This is area annotation");
$a1->setCreatorName("Anonym A.");

$a2 = new GroupDocs\Annotation\Model\AnnotationInfo();
$pt = new GroupDocs\Annotation\Model\Point();
$pt->setX(852);
$pt->setY(59.388262910798119);
$a2->setAnnotationPosition($pt);
$box = new GroupDocs\Annotation\Model\Rectangle();
$box->setX(375.89276123046875);
$box->setY(59.388263702392578);
$box->setWidth(88.7330551147461);
$box->setHeight(37.7290153503418);
$a2->setBox($box);
$a2->setPageNumber(4);
$a2->setOpacity(0.7);
$a2->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_POINT);
$a2->setText("This is point annotation");
$a2->setCreatorName("Anonym A.");

$a3 = new GroupDocs\Annotation\Model\AnnotationInfo();
$pt = new GroupDocs\Annotation\Model\Point();
$pt->setX(852);
$pt->setY(59.388262910798119);
$a3->setAnnotationPosition($pt);
$box = new GroupDocs\Annotation\Model\Rectangle();
$box->setX(375.89276123046875);
$box->setY(59.388263702392578);
$box->setWidth(88.7330551147461);
$box->setHeight(37.7290153503418);
$a3->setBox($box);
$a1->setPageNumber(5);
$a1->setPenColor(1201033);
$a1->setPenStyle(0);
$a1->setPenWidth(1);
$a3->setOpacity(0.7);
$a3->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_ARROW);
$a3->setText("This is arrow annotation");
$a3->setCreatorName("Anonym A.");

$request = new GroupDocs\Annotation\Model\Requests\postAnnotationsRequest("annotationdocs\\ten-pages.docx", [$a, $a1, $a2, $a3]);
$apiInstance->postAnnotations($request);

echo "AddMultipleAnnotations: Multiple Annotations added.";

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
a1.annotationPosition.x = 852;
a1.annotationPosition.y = 59.388262910798119;
a1.box = new annotation_cloud.Rectangle();
a1.box.x = 375.89276123046875;
a1.box.y = 59.388263702392578;
a1.box.width = 88.7330551147461;
a1.box.height = 37.7290153503418;
a1.pageNumber = 1;
a1.penColor = 1201033;
a1.penStyle = annotation_cloud.AnnotationInfo.PenStyleEnum.Solid;
a1.penWidth = 1;
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.Distance;
a1.text = "This is distance annotation";
a1.creatorName = "Anonym A.";

let a2 = new annotation_cloud.AnnotationInfo();
a2.annotationPosition = new annotation_cloud.Point();
a2.annotationPosition.x = 852;
a2.annotationPosition.y = 59.388262910798119;
a2.box = new annotation_cloud.Rectangle();
a2.box.x = 375.89276123046875;
a2.box.y = 59.388263702392578;
a2.box.width = 88.7330551147461;
a2.box.height = 37.7290153503418;
a2.pageNumber = 2;
a2.penColor = 1201033;
a2.penStyle = 0;
a2.penWidth = 1;
a2.type = annotation_cloud.AnnotationInfo.TypeEnum.Area;
a1.text = "This is area annotation";
a2.creatorName = "Anonym A.";

let a3 = new annotation_cloud.AnnotationInfo();
a3.annotationPosition = new annotation_cloud.Point();
a3.annotationPosition.x = 852;
a3.annotationPosition.y = 59.388262910798119;
a3.box = new annotation_cloud.Rectangle();
a3.box.x = 375.89276123046875;
a3.box.y = 59.388263702392578;
a3.box.width = 88.7330551147461;
a3.box.height = 37.7290153503418;
a3.pageNumber = 4;
a3.type = annotation_cloud.AnnotationInfo.TypeEnum.Point;
a1.text = "This is point annotation";
a3.creatorName = "Anonym A.";

let a4 = new annotation_cloud.AnnotationInfo();
a4.annotationPosition = new annotation_cloud.Point();
a4.annotationPosition.x = 852;
a4.annotationPosition.y = 59.388262910798119;
a4.box = new annotation_cloud.Rectangle();
a4.box.x = 375.89276123046875;
a4.box.y = 59.388263702392578;
a4.box.width = 88.7330551147461;
a4.box.height = 37.7290153503418;
a4.pageNumber = 5;
a4.penColor = 1201033;
a4.penStyle = 0;
a4.penWidth = 1;
a4.type = annotation_cloud.AnnotationInfo.TypeEnum.Arrow;
a1.text = "This is arrow annotation";
a4.creatorName = "Anonym A.";

var request = new annotation_cloud.PostAnnotationsRequest("Annotationdocs\\one-page.docx", [a1, a2, a3, a4]);
await annotateApi.postAnnotations(request);
console.log("AddMultipleAnnotations: Multiple Annotations added.");

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
a1.annotation_position.x = 852
a1.annotation_position.y = 59.388262910798119
a1.box = groupdocs_annotation_cloud.Rectangle()
a1.box.x = 375.89276123046875
a1.box.y = 59.388263702392578
a1.box.width = 88.7330551147461
a1.box.height = 37.7290153503418
a1.page_number = 1
a1.pen_color = 1201033
a1.pen_style = "Solid"
a1.pen_width = 1
a1.opacity = 0.7
a1.type = "Distance"
a1.text = "This is distance annotation"
a1.creator_name = "Anonym A."

a2 = groupdocs_annotation_cloud.AnnotationInfo()
a2.annotation_position = groupdocs_annotation_cloud.Point()
a2.annotation_position.x = 852
a2.annotation_position.y = 59.388262910798119
a2.box = groupdocs_annotation_cloud.Rectangle()
a2.box.x = 375.89276123046875
a2.box.y = 59.388263702392578
a2.box.width = 88.7330551147461
a2.box.height = 37.7290153503418
a2.page_number = 2
a2.pen_color = 1201033
a2.pen_style = 0
a2.pen_width = 1
a2.opacity = 0.7
a2.type = "Area"
a2.text = "This is area annotation"
a2.creator_name = "Anonym A."

a3 = groupdocs_annotation_cloud.AnnotationInfo()
a3.annotation_position = groupdocs_annotation_cloud.Point()
a3.annotation_position.x = 852
a3.annotation_position.y = 59.388262910798119
a3.box = groupdocs_annotation_cloud.Rectangle()
a3.box.x = 375.89276123046875
a3.box.y = 59.388263702392578
a3.box.width = 88.7330551147461
a3.box.height = 37.7290153503418
a3.page_number = 4
a3.opacity = 0.7
a3.type = "Point"
a3.text = "This is point annotation"
a3.creator_name = "Anonym A."

a4 = groupdocs_annotation_cloud.AnnotationInfo()
a4.annotation_position = groupdocs_annotation_cloud.Point()
a4.annotation_position.x = 852
a4.annotation_position.y = 59.388262910798119
a4.box = groupdocs_annotation_cloud.Rectangle()
a4.box.x = 375.89276123046875
a4.box.y = 59.388263702392578
a4.box.width = 88.7330551147461
a4.box.height = 37.7290153503418
a4.page_number = 5
a4.pen_color = 1201033
a4.pen_style = 0
a4.pen_width = 1
a4.opacity = 0.7
a4.type = "Arrow"
a4.text = "This is arrow annotation"
a4.creator_name = "Anonym A."

request = PostAnnotationsRequest("annotationdocs\\ten-pages.docx", [a1, a2, a3, a4])
api.post_annotations(request)

print("AddMultipleAnnotations: Multiple Annotations added.")
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
$a1.annotation_position.x = 852
$a1.annotation_position.y = 59.388262910798119
$a1.box = GroupDocsAnnotationCloud::Rectangle.new
$a1.box.x = 375.89276123046875
$a1.box.y = 59.388263702392578
$a1.box.width = 88.7330551147461
$a1.box.height = 37.7290153503418
$a1.page_number = 1
$a1.pen_color = 1201033
$a1.pen_style = "Solid"
$a1.pen_width = 1
$a1.opacity = 0.7
$a1.type = "Distance"
$a1.text = "This is distance annotation"
$a1.creator_name = "Anonym A."

$a2 = GroupDocsAnnotationCloud::AnnotationInfo.new
$a2.annotation_position = GroupDocsAnnotationCloud::Point.new
$a2.annotation_position.x = 852
$a2.annotation_position.y = 59.388262910798119
$a2.box = GroupDocsAnnotationCloud::Rectangle.new
$a2.box.x = 375.89276123046875
$a2.box.y = 59.388263702392578
$a2.box.width = 88.7330551147461
$a2.box.height = 37.7290153503418
$a2.page_number = 2
$a2.pen_color = 1201033
$a2.pen_style = "Solid"
$a2.pen_width = 1
$a2.opacity = 0.7
$a2.type = "Area"
$a2.text = "This is area annotation"
$a2.creator_name = "Anonym A."

$a3 = GroupDocsAnnotationCloud::AnnotationInfo.new
$a3.annotation_position = GroupDocsAnnotationCloud::Point.new
$a3.annotation_position.x = 852
$a3.annotation_position.y = 59.388262910798119
$a3.box = GroupDocsAnnotationCloud::Rectangle.new
$a3.box.x = 375.89276123046875
$a3.box.y = 59.388263702392578
$a3.box.width = 88.7330551147461
$a3.box.height = 37.7290153503418
$a3.page_number = 4
$a3.opacity = 0.7
$a3.type = "Point"
$a3.text = "This is point annotation"
$a3.creator_name = "Anonym A."

$a4 = GroupDocsAnnotationCloud::AnnotationInfo.new
$a4.annotation_position = GroupDocsAnnotationCloud::Point.new
$a4.annotation_position.x = 852
$a4.annotation_position.y = 59.388262910798119
$a4.box = GroupDocsAnnotationCloud::Rectangle.new
$a4.box.x = 375.89276123046875
$a4.box.y = 59.388263702392578
$a4.box.width = 88.7330551147461
$a4.box.height = 37.7290153503418
$a4.page_number = 5
$a4.pen_color = 1201033
$a4.pen_style = "Solid"
$a4.pen_width = 1
$a4.opacity = 0.7
$a4.type = "Arrow"
$a4.text = "This is arrow annotation"
$a4.creator_name = "Anonym A."

$request = GroupDocsAnnotationCloud::PostAnnotationsRequest.new("Annotationdocs\\ten-pages.docx", [$a1, $a2, $a3, $a4])

# Executing an API.
$api.post_annotations($request)

puts("AddMultipleAnnotations: Multiple Annotations added.")

```

{{< /tab >}} {{< /tabs >}}
