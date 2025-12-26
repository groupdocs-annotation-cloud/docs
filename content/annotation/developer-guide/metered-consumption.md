---
id: "metered-consumption"
url: "annotation/metered-consumption"
title: "Getting metered license consumption"
productName: "GroupDocs.Annotation Cloud"
description: ""
keywords: ""
toc: True
---
{{< alert style="info" >}}
This example related to Docker version of GroupDocs.Annotation-Cloud only
{{< /alert >}}

The metered license can be used in Docker version of GroupDocs.Annotation-Cloud.
Here is an example how to retrieve metered license consumption.

You can find more information about Docker version at [How to self-host GroupDocs.Annotation Cloud with Docker]({{< ref "annotation/getting-started/self-host-with-docker.md" >}})

## Note about credits consumption when using metered license in docker version

+ Storage calls are not charged
+ Annotation API calls charge is based on document size: 1 credit per call per 20MB

### Resource URI

```HTTP GET ~/annotation/consumption```

### cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
# cURL example to get metered license consumption
curl -v "https://api.groupdocs.cloud/v2.0/annotation/consumption" \
  -X GET \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}
{{< tab "Windows PowerShell" >}}

```powershell
# cURL example to get metered license consumption
curl.exe -v "https://api.groupdocs.cloud/v2.0/annotation/consumption" `
  -X GET `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}
{{< tab "Windows CMD" >}}

```cmd
:: cURL example to get metered license consumption
curl -v "https://api.groupdocs.cloud/v2.0/annotation/consumption" ^
  -X GET ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "credit": 487848,
  "quantity": 6061570985.37938
}
```
{{< /tab >}} {{< /tabs >}}

### Response

The response structure contains metered license consumption information:

| Name | Type | Comment
|---|---|---
|Credit|decimal|Amount of used credits.
|Quantity|decimal|Amount of MBs processed.

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us.



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
var configuration = new Configuration(MyClientId, MyClientSecret);
  
// Create necessary API instances
var apiInstance = new LicenseApi(configuration);

var response = apiInstance.GetConsumptionCredit();

Console.WriteLine($"Credits: {response.Credit}");
Console.WriteLine($"Quantity: {response.Quantity}");
```

{{< /tab >}} {{< tab "Java" >}}

```java
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
Configuration configuration = new Configuration(MyClientId, MyClientSecret);
  
// Create API instance
LicenseApi apiInstance = new LicenseApi(configuration);

ConsumptionResult response = apiInstance.getConsumptionCredit();
System.out.println("Credit: " + response.getCredit());
System.out.println("Quantity: " + response.getQuantity());
```

{{< /tab >}} {{< tab "PHP" >}}

```php
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php-samples
use GroupDocs\Annotation\Model;
use GroupDocs\Annotation\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
$configuration = new GroupDocs\Annotation\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance = new GroupDocs\Annotation\LicenseApi($configuration);

// Prepare request
$filePath = dirname(realpath(__DIR__)) . '\Resources\WordProcessing\four-pages.docx';
$request = new Requests\ConvertDocumentDirectRequest("pdf", $filePath);

// Get consumption
$result = $apiInstance->getConsumptionCredit();

// Done
echo "Credit: " . $result->getCredit();
```

{{< /tab >}} {{< tab "Node.js" >}}

```node
// For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-node-samples
global.annotation_cloud = require("groupdocs-annotation-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
global.licenseApi = annotation_cloud.LicenseApi.fromKeys(clientId, clientSecret);

let response = await licenseApi.getConsumptionCredit();
console.log("GetLicenseConsumption: Credit = " + response.credit);
```

{{< /tab >}} {{< tab "Python" >}}

```python
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-python-samples
import groupdocs_annotation_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
# Create necessary API instances
apiInstance = groupdocs_annotation_cloud.LicenseApi.from_keys(Common.client_id, Common.client_secret)

# Get consumption
result = apiInstance.get_consumption_credit()

print("Credit: " + result.credit)
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# For complete examples and data files, please go to https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby-samples
require 'groupdocs_annotation_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
  
# Create necessary API instances
apiInstance = GroupDocsAnnotationCloud::LicenseApi.from_keys($client_id, $client_secret)

# Get consumption
result = apiInstance.get_consumption_credit()

puts("Credit: " + result.credit)
```

{{< /tab >}} {{< /tabs >}}
