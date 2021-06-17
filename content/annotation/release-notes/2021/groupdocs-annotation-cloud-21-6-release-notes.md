---
id: "groupdocs-annotation-cloud-21-6-release-notes"
url: "annotation/groupdocs-annotation-cloud-21-6-release-notes"
title: "GroupDocs.Annotation Cloud 21.6 Release Notes"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: "GroupDocs.Annotation Cloud 21.6 Release Notes"
keywords: "GroupDocs Annotation Cloud Release Notes"
---
{{< alert style="info" >}}
This page contains release notes for GroupDocs.Annotation Cloud 21.6
{{< /alert >}}

## Major Features ##

* Add an ability to load custom fonts for documents int add annotations and preview methods
* Added new ZIndex option that allows to add annotation over page content
* Added some new Preview method options

## List of issues covering changes in this release ##

|Key|Summary|Category
|---|---|---
ANNOTATIONCLOUD-131|Support to add Rectangle Annotation over page content|Improvement
ANNOTATIONCLOUD-146|Add an ability to load custom fonts for documents|Feature
ANNOTATIONCLOUD-147|Implement ability to set up image of document quality|Feature
ANNOTATIONCLOUD-148|Generate preview without annotations|Improvement

## Public API and Backward Incompatible Changes ##

There is not backward incompatible changes in this release. Only new options were added:

|Property|Type|Description
|---|---|---
AnnotationInfo.ZIndex|int|Specifies the stack order of an annotation
PreviewOptions.FontsPath|string|The path to directory containing custom fonts in storage
AnnotateOptions.FontsPath|string|The path to directory containing custom fonts in storage
PreviewOptions.Resolution|int|The resolution for generated images, in dots per inch.
PreviewOptions.RenderAnnotations|bool|Controls whether annotations will be generated on the preview
