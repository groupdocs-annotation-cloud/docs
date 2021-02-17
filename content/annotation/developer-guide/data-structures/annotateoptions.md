---
id: "annotateoptions"
url: "annotation/annotateoptions"
title: "AnnotateOptions"
productName: "GroupDocs.Annotation Cloud"
weight: 5
description: ""
keywords: ""
---
AnnotateOptions structure defines options for annotating documents

## FileInfo example ##

```html
{
  "FileInfo": {
    "FilePath": "string",
    "Password": "string"
  },
  "Annotations": [],
  "FirstPage": 0,
  "LastPage": 0,
  "OnlyAnnotatedPages": true,
  "OutputPath": "string"
}
```

## FileInfo fields ###

|Name|Description
|---|---
|FileInfo|Input file path and password. See [FileInfo](annotation/fileinfo) structure
|Annotations|Array of annotations to add to the document. See [AnnotationInfo](annotation/annotationinfo) structure
|FirstPage|Num of first page to annotate
|OnlyAnnotatedPages|Indicates whether to save only annotated pages to output document
|OutputPath|Path of output document
