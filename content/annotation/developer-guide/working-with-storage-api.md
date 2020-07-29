---
id: "working-with-storage-api"
url: "annotation/working-with-storage-api"
title: "Working with Storage API"
productName: "GroupDocs.Annotation Cloud"
weight: 6
description: ""
keywords: ""
---






# Storage existence API #

This API intended for checking existence of cloud storage with given name from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).
|---|---

## API Explorer ##

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Storage existence API](https://apireference.groupdocs.cloud/annotation/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**storageName**|Storage name


## cURL Example ##





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/MyStorage/exist" -H  "accept: application/json" -H  "authorization: Bearer  [Access Token]"
    
 ```




 Response

```html 
{
  "exists": true
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Storage existence](https://apireference.groupdocs.cloud/annotation/#/Storage/StorageExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Storage_Exist.cs >}}







 Java




{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Storage_Exist.java >}}







 PHP




{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Storage_Exist.php >}}







 Node.Js




{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Storage_Exist.js >}}







 Ruby




{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Storage_Exist.rb >}}







 Python




{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Storage_Exist.py >}}









# Storage object existence API #

This API intended for checking existence of file or folder in [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).
|---|---

## API Explorer ##

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Storage existence API](https://apireference.groupdocs.cloud/annotation/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file or folder

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id


## cURL Example ##





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/exist/annotationdocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```




 Response

```html 
{
  "exists": true,
  "isFolder": true
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Storage Object existence](https://apireference.groupdocs.cloud/annotation/#/Storage/ObjectExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Object_Exists.cs >}}







 Java




{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Object_Exists.java >}}







 PHP




{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Object_Exists.php >}}







 Node.Js




{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Object_Exists.js >}}







 Ruby




{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Object_Exists.rb >}}







 Python




{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Object_Exists.py >}}









# Storage Space Usage API #

This API intended for getting total and used space of the[ GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)
|---|---

## API Explorer ##

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [storage space usage API](https://apireference.groupdocs.cloud/annotation/#/Storage/GetDiscUsage) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/disc?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```




 Response

```html 
{
  "usedSize": 31032368,
  "totalSize": 3221225472
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [storage space usage API](https://apireference.groupdocs.cloud/annotation/#/Storage/GetDiscUsage) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





 C#




{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Disc_Usage.cs >}}







 Java




{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Disc_Usage.java >}}







 PHP




{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Disc_Usage.php >}}







 Node.Js




{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Disc_Usage.js >}}







 Ruby




{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Disc_Usage.rb >}}







 Python




{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_Disc_Usage.py >}}









# Storage File Versions API #

This API intended for getting the list of file versions, stored in the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)
|---|---

## API Explorer ##

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Storage File Versions API](https://apireference.groupdocs.cloud/annotation/#/Storage/GetFileVersions) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


 

## cURL Example ##





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/version/one-page.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
 ```




 Response

```html 
{
  "value": [
    {
      "versionId": "null",
      "isLatest": true,
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2018-08-16T19:45:05+00:00",
      "size": 347612,
      "path": "/one-page.docx"
    }
  ]
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Storage File Versions API](https://apireference.groupdocs.cloud/annotation/#/Storage/GetFileVersions) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###

 





 C#




{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_File_Versions.cs >}}







 Java




{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_File_Versions.java >}}







 PHP




{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_File_Versions.php >}}







 Node.Js




{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_File_Versions.js >}}







 Ruby




{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_File_Versions.rb >}}







 Python




{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_File_Versions.py >}}







