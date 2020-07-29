---
id: "get-document-information"
url: "annotation/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Annotation Cloud"
weight: 10
description: ""
keywords: ""
---






# Get Document Information #

This API retrieves document information. It returns an object that contains the document description with metadata and coordinates of text on pages.

## Resource ##

The following GroupDocs.Annotation Cloud REST API resource has been used to get [document information](https://apireference.groupdocs.cloud/annotation/#/Info/GetInfo).

# cURL REST Example #





 Request

```html 
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/info?filePath#annotationdocs%2Fone-page.docx" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]" 
 ```




 Response

```html 
{
  "name": "one-page.docx",
  "path": "annotationdocs/one-page.docx",
  "extension": null,
  "fileFormat": null,
  "size": 0,
  "dateModified": "0001-01-01T00:00:00",
  "pages": [
    {
      "number": 1,
      "width": 612,
      "height": 792,
      "isVisible": false,
      "rows": [
        {
          "characterCoordinates": [
            85.05,
            90.099,
            92.629,
            96.468,
            100.769,
            106.94,
            112.616,
            117.885,
            123.066
          ],
          "lineHeight": 12.1,
          "lineLeft": 85.05,
          "lineTop": 58.033,
          "lineWidth": 43.494,
          "text": "First Page",
          "textCoordinates": [
            85.05,
            19.404,
            106.94,
            21.604
          ]
        }
      ]
    },
    {
      "number": 2,
      "width": 612,
      "height": 792,
      "isVisible": false,
      "rows": [
        {
          "characterCoordinates": [
            85.05,
            90.099,
            95.577,
            100.23,
            106.027,
            111.813,
            120.074,
            125.849,
            131.118,
            136.299
          ],
          "lineHeight": 12.1,
          "lineLeft": 85.05,
          "lineTop": 58.033,
          "lineWidth": 56.727,
          "text": "Second page",
          "textCoordinates": [
            85.05,
            32.538,
            120.074,
            21.703
          ]
        }
      ]
    }
  ]
}
 ```






# SDKs #

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

## Get Document Information ##





 C#




{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_DocumentInfo_File.cs >}}







 Java




{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Document_Information.java >}}







 PHP




{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Document_Information.php >}}







 Node.Js




{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_Document_Information.js >}}







 Ruby




{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Document_Information.rb >}}







 Python




{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_DocumentInfo_File.py >}}







