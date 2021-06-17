---
id: "groupdocs-annotation-cloud-21-2-release-notes"
url: "annotation/groupdocs-annotation-cloud-21-2-release-notes"
title: "GroupDocs.Annotation Cloud 21.2 Release Notes"
productName: "GroupDocs.Annotation Cloud"
weight: 2
description: "GroupDocs.Annotation Cloud 21.2 Release Notes"
keywords: ""
---
{{< alert style="info" >}}
This page contains release notes for GroupDocs.Annotation Cloud 21.2
{{< /alert >}}

## Major Features ##

* Changed API methods so that all parameters are passed through request body instead of query string. This was necessary because of security reasons.
* Annotations are now added directly to the document itself. So, export method was removed, and two new add methods was added.

## List of issues covering changes in this release ##

|Key|Summary|Category
|---|---|---
ANNOTATIONCLOUD-118|Remove passwords from query string|Improvement

## Public API and Backward Incompatible Changes ##

### Changed methods table ###

|Verb|Method before v21.2|Verb|Method since v21.2|Description
|---|---|---|---|---
GET|/annotation|POST|/annotation/extract|Extracts annotations from document
DELETE|/annotation|POST|/annotation/remove|Removes annotations from document
POST|/annotation|POST|/annotation/add|Adds annotations to document and saves output file into cloud storage
-|-|PUT|/annotation/add|Adds annotations to document and returns output file
GET|/annotation/result|-|*method removed*|Export annotations
GET|/annotation/formats|GET|/annotation/formats|Retrieves supported file formats list
GET|/annotation/info|POST|/annotation/info|Retrieves basic document info - path, extension, formats, size etc
GET|/annotation/pages|POST|/annotation/preview/create|Generates image representations from documents pages
DELETE|/annotation/pages|POST|/annotation/preview/remove|Removes document's pages image representations
