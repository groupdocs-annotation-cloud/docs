---
id: "working-with-file-api"
url: "annotation/working-with-file-api"
title: "Working with File Api"
productName: "GroupDocs.Annotation Cloud"
weight: 7
description: ""
keywords: ""
toc: True
---
## Download File API

This API allows you to download a file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Download a File API](https://apireference.groupdocs.cloud/annotation/#/File/DownloadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|File version id

### cURL example

{{< tabs "example1">}}
{{< tab "Request" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/file/one-page.docx?storageName#MyStorage" -H  "accept: multipart/form-data" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Download_File.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Download_File.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Download_File.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Download_File.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Download_File.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Download_File.rb >}}

{{< /tab >}}
{{< /tabs >}}

##  Upload File API

This API allows you to upload files to the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you try out [Upload a File API](https://apireference.groupdocs.cloud/conversion/#/File/UploadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request Body parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|File|File content

### cURL example

{{< tabs "example3">}}
{{< tab "Request" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation/storage/file/annotationdocs/Fone-page2.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
Http status code: 200 (Returns OK and list of errors, which is empty if success.)
{
  "Uploaded": [
    "string"
  ],
  "Errors": [
    {
      "Code": "string",
      "Message": "string",
      "Description": "string",
      "InnerError": {
        "RequestId": "string",
        "Date": "2019-02-27T06:10:08.884Z"
      }
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example4">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Upload_File.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Upload_File.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Upload_File.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Upload_File.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Upload_File.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Upload_File.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Delete File API

This API allows you to delete specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Delete a File](https://apireference.groupdocs.cloud/annotation/#/File/DeleteFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.


### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|File version id

### cURL example

{{< tabs "example5">}}
{{< tab "Request" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation/storage/file/annotationdocs%2Fone-page1.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.



{{< tabs "example6">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Delete_File.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Delete_File.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Delete_File.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Delete_File.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Delete_File.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Delete_File.rb >}}

{{< /tab >}}
{{< /tabs >}}

## File Copy API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Copy File](https://apireference.groupdocs.cloud/annotation/#/File/CopyFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination file. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|Source file version id

### cURL example

{{< tabs "example7">}}
{{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/file/copy/annotationdocs%2Fone-page1.docx?destPath#conversiondocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}


### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.



{{< tabs "example8">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Copy_File.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Copy_File.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Copy_File.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Copy_File.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Copy_File.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Copy_File.rb >}}

{{< /tab >}}
{{< /tabs >}}

## File Move API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Move File](https://apireference.groupdocs.cloud/annotation/#/File/MoveFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination file. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|Source file version id

### cURL example

{{< tabs "example9">}}
{{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/file/move/annotationdocs%2Fone-page1.docx?destPath#conversiondocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example10">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Move_File.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Move_File.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Move_File.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Move_File.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Move_File.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Move_File.rb >}}

{{< /tab >}}
{{< /tabs >}}
