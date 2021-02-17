---
id: "fileinfo"
url: "annotation/fileinfo"
title: "FileInfo"
productName: "GroupDocs.Annotation Cloud"
weight: 5
description: ""
keywords: ""
---
FileInfo data structure describes input file

## FileInfo example ##

```html
{
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
}
```

## FileInfo fields ###

|Name|Description
|---|---
|FilePath|File path in storage
|StorageName|Storage name. Default storage used if not specified
|VersionId|Version ID. Not required.
|Password|Password to open password-protected file
