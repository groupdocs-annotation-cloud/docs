---
id: "annotation-api"
url: "annotation/annotation-api"
title: "Working with Annotation API"
productName: "GroupDocs.Annotation Cloud"
weight: 2
description: ""
keywords: ""
hideChildren: true
---
## Introduction ##

GroupDocs.Annotation Cloud is a REST API that provides methods to apply Text and Figure based annotations to documents & images of all popular formats.

The difference between the V2 version from V1 is a more simplified API with fewer methods and options. Also, it has a more optimized and refined internal architecture. In this version, the API includes methods for working with cloud storage, which is an important part: main annotation API methods take input documents from storage and put results there.

## Add Annotation ##

You can add arrow annotations to the supported document formats with request body parameters listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get an [annotation list from the document](https://apireference.groupdocs.cloud/annotation/#!/Annotation/GetImport).

### cURL REST Example ###

Request

```html
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation?filePath#annotationdocs%2F" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "[  {    \"guid\": null,    \"documentGuid\": 0,    \"text\": null,    \"creatorGuid\": null,    \"creatorName\": \"Anonym A.\",    \"creatorEmail\": null,    \"box\": {      \"x\": 375.892761,      \"y\": 59.3882637,      \"width\": 88.7330551,      \"height\": 37.7290154    },    \"pageNumber\": 0,    \"annotationPosition\": {      \"x\": 852,      \"y\": 59.38826291079812    },    \"svgPath\": null,    \"type\": 1,    \"access\": null,    \"replies\": null,    \"createdOn\": \"0001-01-01T00:00:00\",    \"fontColor\": null,    \"penColor\": 1201033,    \"penWidth\": 1,    \"penStyle\": 0,    \"backgroundColor\": null,    \"fieldText\": null,    \"fontFamily\": null,    \"fontSize\": null,    \"opacity\": null,    \"angle\": null  }]"
```

Response

```html
code 200
Adds annotations to document
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Add Annotation ###

C#  
{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Add_Area_Annotation.cs >}}

Java  
{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Add_Area_Annotation.java >}}

PHP  
{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Add_Area_Annotation.php >}}

Node.Js  
{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Add_Area_Annotation.js >}}

Ruby  
{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Add_Area_Annotation.rb >}}

Python  
{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Add_Area_Annotation.py >}}

## Delete Annotation ##

You can delete annotations to the supported document formats with request body parameters listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [Delete Annotation](https://apireference.groupdocs.cloud/annotation/#/Annotate/DeleteAnnotations).

### cURL REST Example ###

Request

```html
curl -X Delete "https://api.groupdocs.cloud/v2.0/annotation?filePath#annotationdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access token]"
```

Response

```html
Http status code: 200  
<Binary file stream>
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Delete Annotation ###

C#  
{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Delete_Annotation.cs >}}

Java  
{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Delete_Annotation.java >}}

PHP  
{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Delete_Annotation.php >}}

Node.Js  
{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Delete_Annotation.js >}}

Ruby  
{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Delete_Annotation.rb >}}

Python  
{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Delete_Annotation.py >}}

## Get Annotations with Result as File Path ##

This API gets an annotated document and retrieves the resultant document as a file.Request body parameters are  listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [get annotated documents as a file path](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

Request

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

Response

```html
Http status code: 204
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Annotations with Result as File ###

C#  
{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Annotation.cs >}}

Java  
{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Annotation.java >}}

PHP  
{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Annotation.php >}}

Node.Js  
{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Annotation.js >}}

Ruby  
{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Annotation.rb >}}

Python  
{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_Annotation.py >}}

## Get Annotations with Result as Stream ##

This API gets an annotated document and retrieves the resultant document as a stream. The request body parameter is listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [get the annotated document as a stream](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

Request

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

Response

```html
Http status code: 204
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Annotations with Result as Stream ###

C#  
{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Export_Document.cs >}}

Java  
{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Export_Document.java >}}

PHP  
{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Export_Document.php >}}

Node.Js  
{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Export_Document.js >}}

Ruby  
{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Export_Document.rb >}}

Python  
{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_Export_Document.py >}}

## Get Document as PDF with Annotation Result as Stream ##

This API gets an annotated PDF document and retrieves the resultant document as a stream.Request body parameters listed are in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get [resultant documents as PDF files](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

Request

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

Response

```html
Http status code: 204
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Document as PDF with Annotation Result as Stream ###

C#  
{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_PDF.cs >}}

Java  
{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_PDF.java >}}

PHP  
{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_PDF.php >}}

Node.Js  
{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_PDF.js >}}

Ruby  
{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_PDF.rb >}}

Python  
{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_PDF.py >}}
