---
id: "groupdocs-annotation-cloud-18-4-release-notes"
url: "annotation/groupdocs-annotation-cloud-18-4-release-notes"
title: "GroupDocs.Annotation Cloud 18.4 Release Notes"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---

## Major Features ##

Below the list of the most notable features improvements and fixes for GroupDocs.Annotation Cloud 18.4:

* Introduction of PHP SDK for GroupDocs.Annotation Cloud 
* Improved Replacement annotation for text in different paragraphs
* Fixed import text field for Diagram documents
* Fixed bug with import text annotations from PDF
* Fixed resizing image when user pass width and height
* Fixed creating of Arrow annotation for Diagrams
* Fixed issue with wrong distance structure after export in diagram
* Fixed issue with wrong polyline structure after export in diagram
* Fixed bug with hanging of sample while importing distance annotation for slides
* Fixed bug when importing area annotation
* Fixed bug with importing annotations for diagrams
* Improved export of underline text annotation for PDF
* Improved export strikeout text annotation for PDF was
* Improved  creating annotations from colored or transparent text
* Fixed transparent text for all formats
* Fixed bug when importing text for textfield annotation in Diagrams
* Improved export of text annotations in PDF format
* Implement adding annotations to metadata for Slides and Words formats
* Implement import using metadata for Images
* Improved Images annotating
* Improved using metadata for annotating PDF documents
* Refactored and improved annotating Images
* Fixed issue when images cleanup leaves artifacts after annotations removing
* Fixed wrong annotation range if other annotation has already been created in the same location for Words documents

## Full List of Issues Covering all Changes in this Release ## 

|Key|Summary|Issue Type
|---|---|---
|ANNOTATIONCLOUD-49|[Add PHP SDK for GroupDocs.Annotation Cloud](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php)|New Feature
|ANNOTATIONNET-583|Add text redaction annotation in Slides|New Feature
|ANNOTATIONNET-643|Implement creating annotations in headerfooter in Words document|New Feature
|ANNOTATIONNET-582|Add point with text for text annotation|Improvement
|ANNOTATIONNET-573|Impove export of text annotations in Slides|Improvement
|ANNOTATIONNET-570|Improve annotation export for big font sizes for Slides|Improvement
|ANNOTATIONNET-606|Implement accepting SVG path also with spaces not only with commas|Improvement
|ANNOTATIONNET-602|Improve CleanUp for diagram|Improvement
|ANNOTATIONNET-624|Implement import using metadata in Images|Improvement
|ANNOTATIONNET-621|Add annotations to metadata in Words|Improvement
|ANNOTATIONNET-620|Add annotations to metadata in Slides|Improvement
|ANNOTATIONNET-619|Improve Annotation.Imaging|Improvement
|ANNOTATIONNET-618|Improve export text strikeout annotation for pdf|Improvement
|ANNOTATIONNET-617|Improve export underline text annotation for pdf|Improvement
|ANNOTATIONNET-651|Improve PDF format annotating using metadata|Improvement
|ANNOTATIONNET-650|Refactoring Imaging|Improvement
|ANNOTATIONNET-591|Fix Point annotation in Slides|Bug
|ANNOTATIONNET-589|Fix opacity value for import in Diagrams|Bug
|ANNOTATIONNET-584|Bug with import text field for diagram.|Bug
|ANNOTATIONNET-581|Arrow annotation doesn't create for diagrams.|Bug
|ANNOTATIONNET-578|Fix Slides bug with coordinates of paragraph and portion|Bug
|ANNOTATIONNET-577|Words:Fixed cleanup for text redaction annotation.|Bug
|ANNOTATIONNET-574|Bug with import text annotations from PDF|Bug
|ANNOTATIONNET-572|Wrong distance structure after export in diagram|Bug
|ANNOTATIONNET-571|Wrong polyline structure after export in diagram|Bug
|ANNOTATIONNET-612|Fix transparent color for lines of underline and strikeout annotations for Images|Bug
|ANNOTATIONNET-611|Fix transparent colors in Words|Bug
|ANNOTATIONNET-609|Underline style of annotation doesnt set on text in Words|Bug
|ANNOTATIONNET-608|Annotation of underline doesnt set in table in Words|Bug
|ANNOTATIONNET-607|Export adds extra comment for every shape in diagrams|Bug
|ANNOTATIONNET-605|The align of text for textfield of annotation is wrong in Words|Bug
|ANNOTATIONNET-603|Bug after export strikeout annotation in Words|Bug
|ANNOTATIONNET-601|Bug when importing text for textfield annotation in diagrams|Bug
|ANNOTATIONNET-598|Imported from word document resource redaction annotation does not have color|Bug
|ANNOTATIONNET-597|Bug when importing area annotation from word document|Bug
|ANNOTATIONNET-596|Bug with importing annotations for diagrams|Bug
|ANNOTATIONNET-595|The sample hangs while importing distance annotation for slides.|Bug
|ANNOTATIONNET-648|Wrong annotation range if other annotation has already been created in the same location|Bug
|ANNOTATIONNET-646|Cleanup leaves artifacts after deletion annotations in images|Bug

## Public API and Backward Incompatible Changes ##

No changes in the public API.
