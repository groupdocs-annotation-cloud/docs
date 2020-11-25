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

Creating an account is very simple. Go to [Dashboard](https://dashboard.groupdocs.cloud) to create a free account.\
We're using Single Sign On across our websites, therefore, if you already have an account with our services, you can use it to also acccess the [Dashboard](https://dashboard.groupdocs.cloud).

## Create an API client app ##

Before you can make any requests to GroupDocs Cloud API you need to get a **Client Id** and a **Client Secret**.
This will will be used to invoke GroupDocs Cloud API. You can get it by creating a new [Application](https://dashboard.groupdocs.cloud/applications).

## Install the SDK of your choice ##

GroupDocs Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "annotation/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice ##

Use the **Client Id** and the **Client Secret** from the API app client you have created previously and replace in the corresponding code. Below is an example demonstrating using Formats API to get all supported file formats in GroupDocs.Annotation Cloud using SDKs for supported languages.

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(ClientId, ClientSecret);

var apiInstance = new InfoApi(configuration);
var response = apiInstance.GetSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(ClientId, ClientSecret);

InfoApi apiInstance = new InfoApi(configuration);
FormatsResult response = apiInstance.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$infoApi= new GroupDocs\Annotation\InfoApi($configuration);

$response = $infoApi->getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.infoApi = annotation_cloud.InfoApi.fromKeys(clientId, clientSecret);

let response = await infoApi.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = groupdocs_annotation_cloud.InfoApi.from_keys(client_id, client_secret)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = GroupDocsAnnotationCloud::InfoApi.from_keys($client_id, $client_secret)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< /tabs >}}
