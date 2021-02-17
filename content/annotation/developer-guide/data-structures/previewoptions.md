---
id: "previewoptions"
url: "annotation/previewoptions"
title: "PreviewOptions"
productName: "GroupDocs.Annotation Cloud"
weight: 5
description: ""
keywords: ""
---
PreviewOptions structure defines options for creating documents preview

## FileInfo example ##

```html
{
  "FileInfo": {
    "FilePath": "string",
    "Password": "string"
  },
  "Format": "PNG",
  "PageNumbers": [
    0
  ],
  "Width": 0,
  "Height": 0,
  "RenderComments": true
}
```

## FileInfo fields ###

|Name|Description
|---|---
|FileInfo|Input file path and password. See [FileInfo](annotation/fileinfo) structure
|AnnotationIds|Array of IDs of annotations to remove from the document.
|Format|Preview format. Supported values are: PNG, JPEG or BMP. Default value is PNG.
|PageNumbers|Page numbers to create preview for
|Width|Preview image width
|Height|Preview image height
|RenderComments|Show comments in preview
