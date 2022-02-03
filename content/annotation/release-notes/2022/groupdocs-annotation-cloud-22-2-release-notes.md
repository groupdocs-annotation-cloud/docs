---
id: "groupdocs-annotation-cloud-22-2-release-notes"
url: "annotation/groupdocs-annotation-cloud-22-2-release-notes"
title: "GroupDocs.Annotation Cloud 22.2 Release Notes"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: "GroupDocs.Annotation Cloud 22.2 Release Notes"
keywords: "GroupDocs Annotation Cloud Release Notes"
---
{{< alert style="info" >}}
This page contains release notes for GroupDocs.Annotation Cloud 22.2
{{< /alert >}}

## Major Features ##

* Add an ability to get consumption of metered license (this feature is for Docker version only)
* Introduced support of Google Cloud Storage (this feature is for Docker version only)
* Added squiggly annotation support
* Added some new options

## List of issues covering changes in this release ##

|Key|Summary|Category
|---|---|---
ANNOTATIONCLOUD-149|Watermark string to auto scale depending on the length of the string|Improvement
ANNOTATIONCLOUD-160|Add Background color option to Link,Underline, Strikeout Annotations|Feature
ANNOTATIONCLOUD-161|Add squiggly annotation support|Feature
ANNOTATIONCLOUD-162|Add method to get consumption of metered license|Improvement

## Public API and Backward Incompatible Changes ##

There is not backward incompatible changes in this release. Only new options were added:

|Property|Type|Description
|---|---|---
AnnotationInfo.AutoScale|boolean|Sets auto scale for watermark annotation
AnnotationType.TextSquiggly|enum|The annotation type that squiggly comments selected text
AnnotationInfo.SquigglyColor|int|Squiggly annotation color
AnnotationInfo.BackgroundColor|int|Added support of background color to Link, Underline, Strikeout Annotations

The License API was introduced in this release, which allows to get metered license consumption information.
See [Getting metered license consumption]({{< ref "annotation/developer-guide/metered-consumption.md" >}})
