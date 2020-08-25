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

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation?filePath#annotationdocs%2F" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" -H  "Content-Type: application/json" -d "[  {    \"guid\": null,    \"documentGuid\": 0,    \"text\": null,    \"creatorGuid\": null,    \"creatorName\": \"Anonym A.\",    \"creatorEmail\": null,    \"box\": {      \"x\": 375.892761,      \"y\": 59.3882637,      \"width\": 88.7330551,      \"height\": 37.7290154    },    \"pageNumber\": 0,    \"annotationPosition\": {      \"x\": 852,      \"y\": 59.38826291079812    },    \"svgPath\": null,    \"type\": 1,    \"access\": null,    \"replies\": null,    \"createdOn\": \"0001-01-01T00:00:00\",    \"fontColor\": null,    \"penColor\": 1201033,    \"penWidth\": 1,    \"penStyle\": 0,    \"backgroundColor\": null,    \"fieldText\": null,    \"fontFamily\": null,    \"fontSize\": null,    \"opacity\": null,    \"angle\": null  }]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
code 200
Adds annotations to document
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Add Annotation ###

{{< tabs tabTotal="6" tabID="2" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.Js" tabName5="Python" tabName6="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Add_Area_Annotation.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Add_Area_Annotation.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Add_Area_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Add_Area_Annotation.js >}}

{{< /tab >}}
{{< tab tabNum="5" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Add_Area_Annotation.py >}}

{{< /tab >}}
{{< tab tabNum="6" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Add_Area_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Delete Annotation ##

You can delete annotations to the supported document formats with request body parameters listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [Delete Annotation](https://apireference.groupdocs.cloud/annotation/#/Annotate/DeleteAnnotations).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -X Delete "https://api.groupdocs.cloud/v2.0/annotation?filePath#annotationdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Http status code: 200  
<Binary file stream>
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Delete Annotation ###

{{< tabs tabTotal="6" tabID="4" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.Js" tabName5="Python" tabName6="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Delete_Annotation.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Delete_Annotation.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Delete_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Delete_Annotation.js >}}

{{< /tab >}}
{{< tab tabNum="5" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Delete_Annotation.py >}}

{{< /tab >}}
{{< tab tabNum="6" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Delete_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Get Annotations with Result as File Path ##

This API gets an annotated document and retrieves the resultant document as a file.Request body parameters are  listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [get annotated documents as a file path](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Http status code: 204
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Annotations with Result as File ###

{{< tabs tabTotal="6" tabID="6" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.Js" tabName5="Python" tabName6="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Annotation.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Annotation.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Annotation.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Annotation.js >}}

{{< /tab >}}
{{< tab tabNum="5" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_Annotation.py >}}

{{< /tab >}}
{{< tab tabNum="6" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Annotation.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Get Annotations with Result as Stream ##

This API gets an annotated document and retrieves the resultant document as a stream. The request body parameter is listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to [get the annotated document as a stream](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="7" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Http status code: 204
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Annotations with Result as Stream ###

{{< tabs tabTotal="6" tabID="8" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.Js" tabName5="Python" tabName6="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Export_Document.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Export_Document.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Export_Document.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Export_Document.js >}}

{{< /tab >}}
{{< tab tabNum="5" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_Export_Document.py >}}

{{< /tab >}}
{{< tab tabNum="6" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Export_Document.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Get Document as PDF with Annotation Result as Stream ##

This API gets an annotated PDF document and retrieves the resultant document as a stream.Request body parameters listed are in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get [resultant documents as PDF files](https://apireference.groupdocs.cloud/annotation/#/Annotate/GetExport).

### cURL REST Example ###

{{< tabs tabTotal="2" tabID="9" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation?filePath#viewerdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```html
Http status code: 204
```

{{< /tab >}}
{{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Document as PDF with Annotation Result as Stream ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.Js" tabName5="Python" tabName6="Ruby" >}}
{{< tab tabNum="1" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_PDF.cs >}}

{{< /tab >}}
{{< tab tabNum="2" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_PDF.java >}}

{{< /tab >}}
{{< tab tabNum="3" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_PDF.php >}}

{{< /tab >}}
{{< tab tabNum="4" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_PDF.js >}}

{{< /tab >}}
{{< tab tabNum="5" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_PDF.py >}}

{{< /tab >}}
{{< tab tabNum="6" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_PDF.rb >}}

{{< /tab >}}
{{< /tabs >}}
