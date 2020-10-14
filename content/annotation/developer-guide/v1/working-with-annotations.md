---
id: "working-with-annotations"
url: "annotation/working-with-annotations"
title: "Working with Annotations"
productName: "GroupDocs.Annotation Cloud"
weight: 2
description: ""
keywords: ""
---
{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Annotation Cloud V1
{{< /alert >}}

## Introduction ##

GroupDocs.Annotation Cloud API provides annotation data from supported file formats as AnnotationInfo Object.

### AnnotationInfo object fields ###

|Field Name|Type|Description
|---|---|---
|guid|string|The unique identifier of annotation.
|documentGuid|long|The unique identifier of document.
|text|string|The text of the annotation.
|creatorGuid|string|The annotation creator unique identifier.
|creatorName|string|The annotation creator name.
|creatorEmail|string|The annotation creator email.
|box|Rectangle|The frame of the annotation.
|pageNumber|int|The annotation page number.
|annotationPosition|Point|Coordinates of annotation point or row and column for cells document.
|svgPath|string|The annotation svg-path.
|type|AnnotationType|The annotation type.Enum that represents all types of annotations.
|access|AnnotationAccess|The annotation access.
|replies|AnnotationReplyInfo[]|The list of annotation replies.
|createdOn|DateTime|The annotation creation date.
|fontColor|int|The annotaiton text font color.
|penColor|int|The annotaiton pen color.
|penWidth|byte|The annotaiton pen width.
|penStyle|byte|The annotaiton pen style.
|backgroundColor|int|The annotaiton background color.
|fieldText|string|The annotaiton text font color.
|fontFamily|string|The annotaiton text font family.
|fontSize|double|The annotaiton text font size.

## Point object fields ##

|Field Name|Type|Description
|---|---|---
|x|Double|The x coordinate.
|y|Double|The y coordinate.

## AnnotationReplyInfo object fields ##

|Field Name|Type|Description
|---|---|---
|Guid|string|The unique identifier of reply.
|UserGuid|string|The unique identifier of user.
|UserName|string|The user name.
|UserEmail|string|The user email.
|Message|string|The reply message.
|RepliedOn|DateTime|The reply creation date.
|ParentReplyGuid|string|The unique identifier of parent reply.

## Rectangle object fields ##

|Field Name|Type|Description
|---|---|---
|x|float|The x coordinate.
|y|float|The y coordinate.
|width|float|The rectangle width.
|height|float|The rectangle height.

## The emuneration of Annotation types ##

```csharp
public enum AnnotationType : byte
{
   /// The text
   Text = 0,
   /// The area
   Area = 1,
   /// The point
   Point = 2,
   /// The text strikeout
   TextStrikeout = 3,
   /// The polyline
   Polyline = 4,
   /// The text field
   TextField = 5,
   /// The watermark
   Watermark = 6,
   /// The text replacement
   TextReplacement = 7,
   /// The arrow
   Arrow = 8,
   /// The text redaction
   TextRedaction = 9,
   /// The resources redaction
   ResourcesRedaction = 10,
   /// The text underline
   TextUnderline = 11,
   /// The distance
   Distance = 12
}

```

## Import Annotation Information ##

This API retrieves(imports) annotation information from the document. It returns the list of annotations which were imported from the document.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get [annotation list from document](https://apireference.groupdocs.cloud/annotation/#!/Annotation/GetImport).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated.pdf/annotations" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
[
   {
      "guid":null,
      "documentGuid":0,
      "text":null,
      "creatorGuid":null,
      "creatorName":"Anonym A.",
      "creatorEmail":null,
      "box":{
         "x":173.0,
         "y":154.89,
         "width":142.5,
         "height":9.0
      },
      "pageNumber":0,
      "annotationPosition":{
         "x":173.0,
         "y":154.8
      },
      "svgPath":"[
      {
        \"X\":173.298,
        \"Y\":687.575
      },
      {
        \"X\":315.798,
        \"Y\":687.576
      },
      {
        \"X\":173.298,
        \"Y\":678.576
      },
      {
        \"X\":315.793,
        \"Y\":678.875
       }
      ]",
      "type":0,
"access":null,
"replies":[
   {
      "guid":null,
      "userGuid":null,
      "userName":"Admin",
      "userEmail":null,
      "message":"reply text",
      "repliedOn":"2017-03-16T18:19:14",
      "parentReplyGuid":null
   },
   {
      "guid":null,
      "userGuid":null,
      "userName":"Commentator",
      "userEmail":null,
      "message":"reply2 text",
      "repliedOn":"2017-03-16T18:19:14",
      "parentReplyGuid":null
   }
]
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Import Annotation Information ###

{{< tabs tabTotal="6" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Get_Annotation_Info.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Get_Annotation_Info.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Get_Import_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Import_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Export Annotation ##

This API adds(exports) annotation to a document and retrieves the resultant document as stream. It expects AnnotaitonInfo object in request body.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [add Annotation and get resultant document as stream](https://apireference.groupdocs.cloud/annotation/#!/Annotation/PutExport).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated.pdf/annotations" \
-X PUT \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-d "[{"creatorName":"Anonym A.","box":{ "x":173.0, "y":154.89, "width":142.5, "height":9.0 },"pageNumber":0,"annotationPosition":{ "x":173.0, "y":154.88999938964844 },"svgPath":"[{'x':173.2986,'y':687.5769},'x':315.7985,'y':687.5769},{'x':173.2986,'y':678.5769},{'x':315.7985,'y':678.5769}]","type":0,"replies":[{ "userName":"Admin", "message":"reply text", "repliedOn":"2017-03-16T18:19:14" },{ "userName":"Commentator", "message":"reply2 text", "repliedOn":"2017-03-16T18:19:14" }]}]" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Returns Binary data
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Export Annotation and get Document as Stream ###

{{< tabs tabTotal="6" tabID="4" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Put_Annotation.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Put_Annotation.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Get_Export_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Export_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Remove Annotation ##

This API removes annotation from a document and retrieves the resultant document as stream.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [remove Annotation and get resultant document as stream](https://apireference.groupdocs.cloud/annotation/#!/Annotation/DeleteCleanDocument).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated.pdf/annotations" \
-X DELETE \
-H "Content-Type: application/json" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Returns Binary data
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Remove Annotation and get Document as Stream ###

{{< tabs tabTotal="6" tabID="6" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Delete_Remove_Annotation.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Delete_Remove_Annotation.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Delete_Remove_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Delete_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}
