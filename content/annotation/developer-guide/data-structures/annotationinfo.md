---
id: "annotationinfo"
url: "annotation/annotationinfo"
title: "AnnotationInfo"
productName: "GroupDocs.Annotation Cloud"
weight: 5
description: ""
keywords: ""
---
AnnotationInfo data structure describes annotation properties.

## AnnotationInfo example ##

```html
{
    "Id": 0,
    "Type": "string",
    "Text": "string",
    "TextToReplace": "string",
    "CreatorId": 0,
    "CreatorName": "string",
    "CreatorEmail": "string",
    "Box": {
      "X": 0,
      "Y": 0,
      "Width": 0,
      "Height": 0
    },
    "Points": [
      {
        "X": 0,
        "Y": 0
      }
    ],
    "PageNumber": 0,
    "AnnotationPosition": {
      "X": 0,
      "Y": 0
    },
    "SvgPath": "string",
    "Replies": [
      {
        "Id": 0,
        "UserId": 0,
        "UserName": "string",
        "UserEmail": "string",
        "Comment": "string",
        "RepliedOn": "2020-10-08T08:26:41.865Z",
        "ParentReplyId": 0
      }
    ],
    "CreatedOn": "2020-10-08T08:26:41.865Z",
    "FontColor": 0,
    "PenColor": 0,
    "PenWidth": 0,
    "BackgroundColor": 0,
    "FontFamily": "string",
    "FontSize": 0,
    "Opacity": 0,
    "Angle": 0,
    "Url": "string",
    "ImagePath": "string"
  }
```

## AnnotationInfo fields ###

|Name|Description
|---|---
|Angle|Gets or sets the watermark annotation's rotation angle
|AnnotationPosition|Gets or sets the annotation position
|BackgroundColor|Gets or sets the annotation's background color
|Box|Gets or sets the box where annotation will be placed
|CreatedOn|Gets or sets the annotation created on date
|CreatorEmail|Gets or sets the creator's email
|CreatorId|Gets or sets the creator unique identifier
|CreatorName|Gets or sets the name of the creator
|FieldText|Gets or sets the annotation's field text
|FontColor|Gets or sets the annotation's font color
|FontFamily|Gets or sets the annotation's font family
|FontSize|Gets or sets the annotation's font size
|Id|Gets or sets the unique identifier
|Opacity|Gets or sets the annotation's opacity
|PageNumber|Gets or sets the number of page where annotation will be placed
|PenColor|Gets or sets the annotation's pen color
|PenStyle|Gets or sets the annotation's pen style
|PenWidth|Gets or sets the annotation's pen width
|Replies|Gets or sets the array of annotation replies
|SvgPath|Gets or sets the annotation SVG path
|Text|Gets or sets the annotation text
|Type|Gets or sets the annotation type

## AnnotationReplyInfo ##

AnnotationReplyInfo data structure describes annotation reply properties.

```html

{
  "Id": "string",
  "UserId": "string",
  "UserName": "string",
  "UserEmail": "string",
  "Comment": "string",
  "RepliedOn": "2019-05-02T08:07:33.447Z",
  "ParentReplyId": "string"
}
```

## AnnotationReplyInfo fields ##

|Name|Description
|---|---
|Id|Gets or sets the unique identifier
|Comment|Gets or sets the message
|ParentReplyId|Gets or sets the parent reply unique identifier
|RepliedOn|Gets or sets the reply time
|UserEmail|Gets or sets the user email
|UserId|Gets or sets the user's unique identifier
|UserName|Gets or sets the user's name
