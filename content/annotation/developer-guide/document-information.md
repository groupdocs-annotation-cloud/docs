---
id: "document-information"
url: "annotation/document-information"
title: "Document Information"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---
{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Annotation Cloud V1
{{< /alert >}}

This API retrieves document information. It returns an object that contains the document description with meta data and coordinates of text on pages.

### DocumentInfo object fields ###

|Field Name|Type|Description
|---|---|---
|name|string|The document name.
|folder|string|The document folder.
|extension|string|The file extension.
|fileFormat|string|The file type.
|size|long|The file size.
|dateModified|DateTime|The file last modification date.
|pages|List\<PageInfo\>|The file pages list.

### PageInfo object fields ###

|Field Name|Type|Description
|---|---|---
|number|int|The page number.
|width|int|The page width.
|height|int|The page height.
|visible|bool|If page is visible.
|rows|List\<RowInfo\>|The page rows list.

### RowInfo object fields ###

|Field Name|Type|Description
|---|---|---
|characterCoordinates|List\<double\>|Coordinates of row characters.
|lineHeight|double|The height of the row.
|lineLeft|double|The left position of the row.
|lineTop|double|The top position of the row.
|linewidth|double|The width of the row.
|text|string|The row text.
|texCoordinates|List\<double\>|The text line coordinates.

### Resource ###

The following GroupDocs.Annotation Cloud REST API resource has been used to get [document information(Image representation)](https://apireference.groupdocs.cloud/annotation/#!/ImageInfo/GetInfo).

### cURL REST Example ###

Request

```html
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated_docx.docx/image/info" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

Response

```html
{  
   "name":"Annotated_docx.docx",
   "folder":null,
   "extension":"docx",
   "fileFormat":"Docx",
   "size":11590,
   "dateModified":"2017-03-21T14:51:06.8720237Z",
   "pages":[  
      {  
         "number":1,
         "width":612,
         "height":792,
         "visible":false,
         "rows":[  
            {  
               "characterCoordinates":[  
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
               "lineHeight":12.1,
               "lineLeft":85.05,
               "lineTop":58.033,
               "lineWidth":43.494,
               "text":"First Page",
               "textCoordinates":[  
                  85.05,
                  19.404,
                  106.94,
                  21.604
               ]
            }
         ]
      },
      {  
         "number":2,
         "width":612,
         "height":792,
         "visible":false,
         "rows":[  
            {  
               "characterCoordinates":[  
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
               "lineHeight":12.1,
               "lineLeft":85.05,
               "lineTop":58.033,
               "lineWidth":56.727,
               "text":"Second page",
               "textCoordinates":[  
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

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-annotation-cloud).

### Get Document Information ###

C#  
{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Get_Document_Info.cs >}}

PHP  
{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Get_Document_Info.php >}}

Java  
{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Get_Document_Info.java >}}

Ruby  
{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Info.rb >}}