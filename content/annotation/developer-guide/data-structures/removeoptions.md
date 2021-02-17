---
id: "removeoptions"
url: "annotation/removeoptions"
title: "RemoveOptions"
productName: "GroupDocs.Annotation Cloud"
weight: 5
description: ""
keywords: ""
---
RemoveOptions structure defines options for removing document annotations

## FileInfo example ##

```html
{
  "FileInfo": {
    "FilePath": "string",
    "Password": "string"
  },
  "AnnotationIds": [
    0
  ],
  "OutputPath": "string"
}
```

## FileInfo fields ###

|Name|Description
|---|---
|FileInfo|Input file path and password. See [FileInfo](annotation/fileinfo) structure
|AnnotationIds|Array of IDs of annotations to remove from the document. 
|FirstPage|Num of first page to annotate
|OnlyAnnotatedPages|Indicates whether to save only annotated pages to output document
|OutputPath|Path of output document
