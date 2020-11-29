---
id: "resource-redaction-annotation"
url: "annotation/resource-redaction-annotation"
title: "Resource redaction Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

Resource redaction annotation fills black rectangle with fixed position (used if you want to hide some text)

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
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in the "client_id" and Client Secret in the "client_secret" arguments.
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
    'Type': 'ResourcesRedaction',
    'Text': 'This is resource redaction annotation',
    'CreatorName': 'Anonym A.',
    'Box': {
      'X': 100,
      'Y': 100,
      'Width': 100,
      'Height': 100
    },
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
string MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);

var apiInstance = new AnnotateApi(configuration);

var request = new PostAnnotationsRequest();
request.filePath = "one-page.docx";
AnnotationInfo[] annotations =
{
    new AnnotationInfo
    {
        Box = new Rectangle { X = 100, Y = 100, Width = 100, Height = 100 },
        PageNumber = 0,
        Type = AnnotationInfo.TypeEnum.ResourcesRedaction,
        Text = "This is resource redaction annotation",
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
Console.WriteLine("AddResourcesRedactionAnnotation: resources redaction Annotation added.");

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);

AnnotateApi apiInstance = new AnnotateApi(configuration);

// Create annotation/s.
AnnotationInfo[] annotations = new AnnotationInfo[1];
annotations[0] = new AnnotationInfo();

Rectangle r = new Rectangle();
r.setX(100.0);
r.setY(100.0);
r.setWidth(200.0);
r.setHeight(100.0);

annotations[0].setBox(r);

annotations[0].setPageNumber(0);
annotations[0].setType(TypeEnum.RESOURCESREDACTION);
annotations[0].setText("This is resources redaction annotation");
annotations[0].setCreatorName("Anonym A.");

// Create request object.
PostAnnotationsRequest request = new PostAnnotationsRequest("Annotationdocs\\one-page.docx", Arrays.asList(annotations));

// Executing api method.
apiInstance.postAnnotations(request);

System.out.println("AddResourcesRedactionAnnotation: Resources redaction Annotation added.");
```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;

$ClientId = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

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
$a->setType(GroupDocs\Annotation\Model\AnnotationInfo::TYPE_RESOURCES_REDACTION);
$a->setText("This is resource redaction annotation");
$a->setCreatorName("Anonym A.");

$request = new GroupDocs\Annotation\Model\Requests\postAnnotationsRequest("annotationdocs\\one-page.docx", [$a]);
$apiInstance->postAnnotations($request);

echo "AddResourcesRedactionAnnotation: Resource redaction Annotation added.";
```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

global.annotateApi = annotation_cloud.AnnotateApi.fromKeys(clientId, clientSecret);

let a1 = new annotation_cloud.AnnotationInfo();
a1.box = new annotation_cloud.Rectangle();
a1.box.x = 100;
a1.box.y = 100;
a1.box.width = 200;
a1.box.height = 100;
a1.pageNumber = 0;
a1.type = annotation_cloud.AnnotationInfo.TypeEnum.ResourcesRedaction;
a1.text = "This is Resources Redaction annotation";
a1.creatorName = "Anonym A.";

var request = new annotation_cloud.PostAnnotationsRequest("Annotationdocs\\one-page.docx", [a1]);
await annotateApi.postAnnotations(request);
console.log("AddResourcesRedactionAnnotation: Resources Redaction Annotation added.");

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

api = groupdocs_annotation_cloud.AnnotateApi.from_keys(client_id, client_secret)

a1 = groupdocs_annotation_cloud.AnnotationInfo()
a1.box = groupdocs_annotation_cloud.Rectangle()
a1.box.x = 100
a1.box.y = 100
a1.box.width = 200
a1.box.height = 100
a1.page_number = 0
a1.type = "ResourcesRedaction"
a1.text = "This is resource redaction annotation"
a1.creator_name = "Anonym A."

request = PostAnnotationsRequest("annotationdocs\\one-page.docx", [a1])
api.post_annotations(request)

print("AddResourcesRedactionAnnotation: resource redaction Annotation added.")
```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get Client Id and Client Secret from https://dashboard.groupdocs.cloud

$api = GroupDocsAnnotationCloud::AnnotateApi.from_keys($client_id, $client_secret)

$a1 = GroupDocsAnnotationCloud::AnnotationInfo.new
$a1.box = GroupDocsAnnotationCloud::Rectangle.new
$a1.box.x = 100
$a1.box.y = 100
$a1.box.width = 200
$a1.box.height = 100
$a1.page_number = 0
$a1.font_color = 1201033
$a1.font_size = 12
$a1.opacity = 0.7
$a1.type = "ResourcesRedaction"
$a1.text = "This is resource redaction annotatio"
$a1.creator_name = "Anonym A."

$request = GroupDocsAnnotationCloud::PostAnnotationsRequest.new("Annotationdocs\\one-page.docx", [$a1])

# Executing an API.
$api.post_annotations($request)

puts("AddResourcesRedactionAnnotation: resource redaction Annotation added.")

```

{{< /tab >}} {{< /tabs >}}
