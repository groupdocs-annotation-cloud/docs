---
id: "watermark-annotation"
url: "annotation/watermark-annotation"
title: "Watermark Annotation"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---






# Add Area Annotation #

You can add Area annotations to the supported document formats with request body parameters listed in **[AnnotationInfo]({{< ref "annotation/developer-guide/annotationinfo.md" >}}))**.

## Resource ##

The following GroupDocs.Annotation Cloud REST API resource has been used to get an [annotation list from the document](https://apireference.groupdocs.cloud/annotation/#!/Annotation/GetImport).

## cURL REST Example ##





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

### Add Area Annotation ###





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







