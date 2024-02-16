---
id: "get-supported-file-formats"
url: "annotation/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Annotation Cloud"
weight: 9
description: ""
keywords: ""
toc: True
---
GroupDocs.Annotation Cloud is a REST API provides methods to apply Text and Figure based annotations to documents & images of all popular formats.

## Resource

The following GroupDocs.Comparison Cloud REST API resource has been used in the [Supported File Formats](https://apireference.groupdocs.cloud/annotation/#/Info/GetSupportedFileFormats) example.

## cURL example

{{< tabs "example1">}}
{{< tab "Request" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/formats" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "formats": [
    {
      "extension": ".doc",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docx",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docm",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dot",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dotx",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".dotm",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".rtf",
      "fileFormat": "Rich Text Format"
    },
    {
      "extension": ".odt",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ott",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".xls",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsx",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsm",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsb",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".ods",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ppt",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pptx",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pps",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".ppsx",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pot",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".odp",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".tif",
      "fileFormat": "Image files"
    },
    {
      "extension": ".tiff",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpeg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".png",
      "fileFormat": "Image files"
    },
    {
      "extension": ".bmp",
      "fileFormat": "Image files"
    },
    {
      "extension": ".gif",
      "fileFormat": "Image files"
    },
    {
      "extension": ".pdf",
      "fileFormat": "Portable Document Format"
    },
    {
      "extension": ".htm",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".html",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".eml",
      "fileFormat": "Microsoft Outlook Mail Message"
    },
    {
      "extension": ".vsd",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".vsdx",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".vss",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".vsdm",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".dwg",
      "fileFormat": "CAD Drawing File Format"
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here]({{< ref "/annotation/getting-started/available-sdks.md" >}}).

{{< tabs "example2">}}
{{< tab "C#" >}}

{{< gist groupdocscloud 9cff9e42173d5964e88b2ee989ce4a83 Annotation_CSharp_Get_Supported_Formats.cs >}}

{{< /tab >}}
{{< tab "Java" >}}

{{< gist groupdocscloud 7e00ab6ab1a8faab84ca2edd2edc30db Annotation_Java_Get_Supported_Formats.java >}}

{{< /tab >}}
{{< tab "PHP" >}}

{{< gist groupdocscloud 9d23670221e0b7b3882f3f3bab9baf9e Annotation_Php_Get_Supported_Formats.php >}}

{{< /tab >}}
{{< tab "Node.Js" >}}

{{< gist groupdocscloud 18dbfb11660d5c7555df9b7886856763 Annotation_Node_Get_All_Supported_Formats.js >}}

{{< /tab >}}
{{< tab "Python" >}}

{{< gist groupdocscloud adf9db2b064fbf397457fa83429d9efa Annotation_Python_Get_All_Supported_Formats.py >}}

{{< /tab >}}
{{< tab "Ruby" >}}

{{< gist groupdocscloud 13003090505393ddeb57a01bf8b5a823 Annotation_Ruby_Get_Supported_Formats.rb >}}

{{< /tab >}}
{{< /tabs >}}
