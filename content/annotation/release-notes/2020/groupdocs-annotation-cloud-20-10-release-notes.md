---
id: "groupdocs-annotation-cloud-20-10-release-notes"
url: "annotation/groupdocs-annotation-cloud-20-10-release-notes"
title: "GroupDocs.Annotation Cloud 20.10 Release Notes"
productName: "GroupDocs.Annotation Cloud"
weight: 1
description: ""
keywords: ""
---
{{< alert style="info" >}}
This page contains release notes for GroupDocs.Annotation Cloud 20.10
{{< /alert >}}

## Major Features ##

* Added several new annotation types, including image annotation
* Created docker version

## Full List of Issues Covering all Changes in this Release ##

|Key|Summary|Category
|---|---|---
ANNOTATIONCLOUD-104|Add new annotation types|Feature
ANNOTATIONCLOUD-101|Change parameters of method /annotation/pages|Task
ANNOTATIONCLOUD-102|Remove /annotation/pdf method|Task
ANNOTATIONCLOUD-103|Add/rename/remove annotation properties|Task

## Public API and Backward Incompatible Changes ##

### Removed /annotation/pdf method ###

The Method /annotation/pdf was removed.

### Changed parameters of method /annotation/pages ###

#### Removed parameters ####

countPagesToConvert,
pageNumber,
enableCaching,
cacheStoragePath

#### Added parameters #####

format,
width,
height,
renderComments

### Changed annotation properties ###

#### Changed some properties in AnnotationInfo structure ####

*Guid* property renamed to *Id*
Removed *DocumentGuid* property
*CreatorGuid* property renamed to *CreatorId*
Added *HorizontalAlignment* property
Added *VerticalAlignment* property
Added *Points* property
Changed type of *PenStyle* property from *integer* to *enum*
Removed *FieldText* property
Added *Url* property

#### Changed some properties in AnnotationReplyInfo structure #####

*Guid* property renamed to *Id*
*UserGuid* property renamed to *UserId*
*ParentReplyGuid* property renamed to *ParentReplyId*
*Message* property renamed to *Comment*

#### Changed PageInfo structure ####

Removed *IsVisible* property
Removed *Row*s property
