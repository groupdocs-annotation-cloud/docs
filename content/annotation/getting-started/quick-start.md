---
id: "quick-start"
url: "annotation/quick-start"
title: "Quick Start"
productName: "GroupDocs.Annotation Cloud"
weight: 2
description: ""
keywords: ""
---
## Create an account ##

Creating an account is very simple. Go to [Dashboard](https://dashboard.groupdocs.cloud/#/) to create a free account.

## Create an API client app ##

Before you can make any requests to GroupDocs for Cloud API you need to get APP SID and APP key (secret key). This will will be used to invoke GroupDocs for Cloud API. You can get it from default Application or create new Application from My Apps tab of [GroupDocs for Cloud Dashboard](https://dashboard.groupdocs.cloud).

## Install the SDK of your choice ##

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "annotation/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice ##

Use the **App SID** and **App key (secret key)** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating using Formats API to get all supported file formats in GroupDocs.Annotation Cloud using SDKs for supported languages.

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyAppSid, MyAppKey);

var apiInstance = new InfoApi(configuration);
var response = apiInstance.GetSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyAppSid, MyAppKey);

InfoApi apiInstance = new InfoApi(configuration);
FormatsResult response = apiInstance.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;

$AppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);

$infoApi= new GroupDocs\Annotation\InfoApi($configuration);

$response = $infoApi->getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

global.infoApi = annotation_cloud.InfoApi.fromKeys(appSid, appKey);

let response = await infoApi.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

infoApi = groupdocs_annotation_cloud.InfoApi.from_keys(app_sid, app_key)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

infoApi = GroupDocsAnnotationCloud::InfoApi.from_keys($app_sid, $app_key)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< /tabs >}}
