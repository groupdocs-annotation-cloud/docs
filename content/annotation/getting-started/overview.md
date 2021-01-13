---
id: "overview"
url: "annotation/overview"
title: "Overview"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---
The GroupDocs.Annotation Cloud is a REST API and universal document annotator that supports almost all common business document and image file formats. It gives developers an API for creating advanced online document annotation tools. With GroupDocs.Annotation Cloud API developers can deliver advanced annotation features to their users quickly. It provides features for export/import annotations into/from files, additionally to possibility to save files in supported formats.

{{< alert style="info" >}}
GroupDocs.Annotation Cloud REST API supports following type of Annotations:

**Area** – add notes to an area highlighted with a rectangle.\
**Arrow** – The annotation type that draws an arrow on the document page.\
**Distance** – measure the distance between any objects in a document.\
**Ellipse** – The annotation of elliptic form that marks parts of document content.\
**Link** – The annotation type that represents a hyperlink to a remote resource.\
**Point** – add notes to any point in the document.\
**Polyline** – draw freehand lines and shapes.\
**ResourcesRedaction** – The annotation type that hides textual content behind black rectangle.\
**TextField** – The text field annotation type represents textual comment inside colored frame.\
**TextHighlight** – The annotation type that highlights and comments selected text.\
**TextRedaction** – The annotation type that fills part of selected text with black rectangle.\
**TextReplacement** –  The annotation type that replaces original text with other provided text fragment.\
**TextStrikeout** –  The annotation type that marks text fragment with a strike through styling.\
**TextUnderline** –  The annotation type that marks text with a underline styling.\
**Watermark** –   The annotation type that adds textual watermark over document page.\
**Image** –  The annotation type that adds image overlay over document page content.

{{< /alert >}}

## Supported Formats ##

|Format|Description|Annotate
|---|---|---
|[DOC](https://wiki.fileformat.com/word-processing/doc/)|Microsoft Word 97-2003 Document|![ ](annotation/images/check.png)
|[DOCM](https://wiki.fileformat.com/word-processing/docm/)|Microsoft Word Macro-Enabled Document|![ ](annotation/images/check.png)
|[DOCX](https://wiki.fileformat.com/word-processing/docx/)|Microsoft Word Document|![ ](annotation/images/check.png)
|[DOT](https://wiki.fileformat.com/word-processing/dot/)|Microsoft Word 97-2003 Template|![ ](annotation/images/check.png)
|[DOTM](https://wiki.fileformat.com/word-processing/dotm/)|Microsoft Word Macro-Enabled Template|![ ](annotation/images/check.png)
|[DOTX](https://wiki.fileformat.com/word-processing/dotx/)|Microsoft Word Template|![ ](annotation/images/check.png)
|[RTF](https://wiki.fileformat.com/word-processing/rtf/)|Rich Text Document|![ ](annotation/images/check.png)
|[ODT](https://wiki.fileformat.com/word-processing/odt/)|OpenDocument Text|![ ](annotation/images/check.png)
|[XLS](https://wiki.fileformat.com/spreadsheet/xls/)|Microsoft Excel 97-2003 Worksheet|![ ](annotation/images/check.png)
|[XLSB](https://wiki.fileformat.com/spreadsheet/xlsb/)|Microsoft Excel Binary Worksheet|![ ](annotation/images/check.png)
|[XLSM](https://wiki.fileformat.com/spreadsheet/xlsm/)|Microsoft Excel Macro-Enabled Worksheet|![ ](annotation/images/check.png)
|[XLSX](https://wiki.fileformat.com/spreadsheet/xlsx/)|Microsoft Excel Worksheet|![ ](annotation/images/check.png)
|[ODS](https://wiki.fileformat.com/spreadsheet/ods/)|OpenDocument Spreadsheet|![ ](annotation/images/check.png)
|[PPT](https://wiki.fileformat.com/presentation/ppt/)|Microsoft PowerPoint 97-2003 Presentation|![ ](annotation/images/check.png)
|[PPTX](https://wiki.fileformat.com/presentation/pptx/)|Microsoft PowerPoint Presentation|![ ](annotation/images/check.png)
|[PPSX](https://wiki.fileformat.com/presentation/ppsx/)|Microsoft PowerPoint Slide Show|![ ](annotation/images/check.png)
|[ODP](https://wiki.fileformat.com/presentation/odp/)|OpenDocument Presentation|![ ](annotation/images/check.png)
|[PPS](https://wiki.fileformat.com/presentation/pps/)|Microsoft PowerPoint 97-2003 Slide Show|![ ](annotation/images/check.png)
|[TIF](https://wiki.fileformat.com/image/tiff/), [TIFF](https://wiki.fileformat.com/image/tiff/)|Tagged Image File Format (TIFF)|![ ](annotation/images/check.png)
|[JPG](https://wiki.fileformat.com/image/jpeg), [JPEG](https://wiki.fileformat.com/image/jpeg)|Joint Photographic Experts Group (JPEG)|![ ](annotation/images/check.png)
|[PNG](https://wiki.fileformat.com/image/png/)|Portable Network Graphics (PNG)|![ ](annotation/images/check.png)
|[BMP](https://wiki.fileformat.com/image/bmp/)|Bitmap Picture (BMP)|![ ](annotation/images/check.png)
|[PDF](https://wiki.fileformat.com/pdf/)|Adobe Portable Document Format (PDF)|![ ](annotation/images/check.png)
|[HTML](https://wiki.fileformat.com/web/html/)|HyperText Markup Language (HTML)|![ ](annotation/images/check.png)
|[EML](https://wiki.fileformat.com/email/eml/)|E-mail Message|![ ](annotation/images/check.png)
|[VSD](https://wiki.fileformat.com/image/vsd/)|Microsoft Visio 2003-2010 Drawing|![ ](annotation/images/check.png)
|[VSDX](https://wiki.fileformat.com/image/vsdx/)|Microsoft Visio Drawing|![ ](annotation/images/check.png)
|[VSS](https://wiki.fileformat.com/image/vss/)|Microsoft Visio 2003-2010 Stencil|![ ](annotation/images/check.png)
|[VST](https://wiki.fileformat.com/image/vst/)|Microsoft Visio 2013 Stencil|![ ](annotation/images/check.png)
|[DWG](https://wiki.fileformat.com/cad/dwg/)|Autodesk Design Data Formats|![ ](annotation/images/check.png)
|[DXF](https://wiki.fileformat.com/cad/dxf/)|Drawing Interchange Format|![ ](annotation/images/check.png)
|[DCM](https://wiki.fileformat.com/image/dcm/)|Digital Imaging and Communications in Medicine (DICOM)|![ ](annotation/images/check.png)

## Security and Authentication ##

The GroupDocs.Annotation Cloud API is secured and requires authentication. Developers can [generate]({{< ref "total/getting-started/ui-topics/creating-and-managing-application.md" >}}) a new application with an unique Client Id and Client Secret combination after [registering]({{< ref "total/getting-started/ui-topics/creating-and-managing-account.md" >}}) to our [dashboard](https://dashboard.groupdocs.cloud). Authenticated requests require a Bearer authorization header with a JWT Token obtained by using the previously specified Cliend Id + Client Secret credentials. You can check complete details about authenticating your calls to our API [here]({{< ref "total/getting-started/overview-rest-api/authenticating-api-requests.md" >}}).

## SDKs ##

GroupDocs.Annotation Cloud comes with SDKs for different platforms to use this REST API in your specific project effortlessly. Checkout our GitHub [repository](https://github.com/groupdocs-annotation-cloud) for a complete list of GroupDocs.Annotation SDKs along with working examples, to get you started in no time.

## API Explorer ##

The easiest way to try out our API right away in your browser! With the [GroupDocs.Cloud Web API Explorer](https://apireference.groupdocs.cloud/annotation/).\
This is a collection of Swagger documentation for the GroupDocs.Cloud APIs. You can get information about all the resources in the API. It also provides testing and interactivity to our API endpoint documentation.
