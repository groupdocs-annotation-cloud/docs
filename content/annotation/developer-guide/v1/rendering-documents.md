---
id: "rendering-documents"
url: "annotation/rendering-documents"
title: "Rendering Documents"
productName: "GroupDocs.Annotation Cloud"
weight: 4
description: ""
keywords: ""
toc: True
---{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Annotation Cloud V1
{{< /alert >}}

GroupDocs.Annotation Cloud API supports to render documents to PDF and saves output to storage or stream.

## Render Document to PDF with Storage URL Output

This API renders document to PDF and saves resulted document to storage. It also returns the link of rendered document.

### Resource

The following GroupDocs.Annotation Cloud REST API resource has been used to render [document to PDF and save to storage](https://apireference.groupdocs.cloud/annotation/#!/PdfFile/GetPdf).

### cURL example

{{< tabs "example1">}}
{{< tab "Request" >}}

```bash
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated.pdf/pdf" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "fileName": "Annotated.pdf.pdf",
  "link": {
    "href": "http://api.groupdocs.cloud/storage/file/Annotated.pdf.pdf/Annotated_pdf/p",
    "rel": "self",
    "type": null,
    "title": null
  }
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here]({{< ref "/annotation/getting-started/available-sdks.md" >}}).

### Render Document to PDF with Storage URL Ouput

{{< tabs "example2">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Get_Render_PDF_Storage.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Get_Render_PDF_Storage.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Get_Render_PDF_Storage.php >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Render_Storage.rb >}}

{{< /tab >}}
{{< /tabs >}}

## Render Document to PDF with Stream Output

This API renders document to PDF and save resulted document to storage.

### Resource

The following GroupDocs.Annotation Cloud REST API resource has been used to render [document to PDF with stream output](https://apireference.groupdocs.cloud/annotation/#!/PdfFile/GetPdfStream).

### cURL example

{{< tabs "example3">}}
{{< tab "Request" >}}

```bash
curl -v "https://api.groupdocs.cloud/v1/annotation/Annotated.pdf/pdf/stream" \
-X GET \
-H "Content-Type: application/json" \
-H "authorization: Bearer 0v7TK3UGYjVBEcEIS9aaO0dsXAlt-KriIDnJGkDIPktFmuu6xIuou2-eVUD4-Td9TcToDvShk9w02pWIXvyEdstxDqjSa8L2K4Pk2zgNkAoEDgDeFlpWf0k7lZ8guqUm43eAKQf43MVNyr3L6P3w1e2l9j-RJx-btpPorcZ90xY8S_b1vySsKsUxOlnwYtWc01JEXlO7TNrmfD3Eek4ch-xzi-qe4V8nofmy7RbqwHNczeP7O_9bMi1eQ68b3Rprqd4UvDCj3gqTMyAaqd-I58lJzZsHRnbZoM7icIjVQyu02bRgx7meoXB8fIWmOkUfUkiGTT3IjI4NSmARxrPPwgp2LAv-N_9H0q3nxxfZDV1vHZQP--I6vgC2UHo-YPw-mB4WRVHsUKqq04L4pdR4pCIWuluus_ydjVH_ndJlqP843eL3glt1XJez3DgXQIbHiAnqBBDqZqSZZDVUYhLDq1jN9eM"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
Binary Data
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here]({{< ref "/annotation/getting-started/available-sdks.md" >}}).

{{< tabs "example4">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 024c8d6fda257f009f47dd55141c959f Annotation_CSharp_Get_Render_PDF_Stream.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud dd069ea3659b158b48e2239356aea189 Annotation_Java_Get_Render_PDF_Stream.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 91cf9bb641d8b967c65ee1f2eb626f2e Annotation_PHP_Get_Render_PDF_Stream.php >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 6a14ecd45b4278c014689b688ec34d21 Annotation_Ruby_Get_Render_Stream.rb >}}

{{< /tab >}}
{{< /tabs >}}
