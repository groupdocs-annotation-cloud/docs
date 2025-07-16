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

```csharp
using System;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Get All Supported Formats
	class Get_All_Supported_Formats
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);

			var apiInstance = new InfoApi(configuration);

			try
			{
				// Get supported file formats
				var response = apiInstance.GetSupportedFileFormats();

				foreach (var entry in response.Formats)
				{
					Console.WriteLine(string.Format("{0}: {1}", entry.FileFormat, string.Join(",", entry.Extension)));
				}
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling Annotation InfoApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Supported_File_Formats;

import com.groupdocs.cloud.annotation.client.*;
import com.groupdocs.cloud.annotation.model.*;
import java.util.List;
import com.groupdocs.cloud.annotation.client.Configuration;
import com.groupdocs.cloud.annotation.api.*;
import examples.Utils;

public class Annotation_Java_Get_Supported_Formats {

	public static void main(String[] args) {

		Configuration configuration = new Configuration(Utils.AppSID, Utils.AppKey);
		InfoApi apiInstance = new InfoApi(configuration);
		try {
			FormatsResult response = apiInstance.getSupportedFileFormats();

			for (Format format : response.getFormats()) {
				System.out.println(format.getFileFormat());
			}
		} catch (ApiException e) {
			System.err.println("Exception while calling InfoApi:");
			e.printStackTrace();
		}
	}
}

```

{{< /tab >}}
{{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

try {
    $apiInstance = CommonUtils::GetInfoApiInstance();

    $response = $apiInstance->getSupportedFileFormats();

    echo '<b>Supported file formats<br /></b>';
	foreach($response->getFormats() as $key => $format) {
	  echo $format->getFileFormat(), "(", $format->getExtension(), ")<br />";
	}
} catch (Exception $e) {
    echo "Something went wrong: ", $e->getMessage(), "\n";
}
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Get_All_Supported_Formats {
	static Run() {
		// retrieve supported file-formats
		infoApi.getSupportedFileFormats()
			.then(function (response) {
				console.log("Supported file-formats:");
				response.formats.forEach(function (format) {
					console.log(format.fileFormat + "(" + format.extension + ")" + "\n");
				});
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Get_All_Supported_Formats;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities;


class Annotation_Python_Get_All_Supported_Formats:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_InfoApi_Instance()
        
        try:
            # Retrieve supported file-formats
            response = api.get_supported_file_formats()
    
            # Print out supported file-formats
            print("Supported file-formats:")
            for fileformat in response.formats:
                print('{0} ({1})'.format(fileformat.file_format, fileformat.extension))
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception when calling get_supported_annotation_types: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class File_Formats
  def self.Annotation_Ruby_Get_Supported_Formats()

    # Getting instance of the API
    api = Common_Utilities.Get_InfoApi_Instance()
    
    # Retrieve supported file-formats
    $response = api.get_supported_file_formats()

    # Print out supported file-formats
    puts("Supported file-formats:")
    $response.formats.each do |format|
      puts("#{format.file_format} (#{format.extension})") 
    end
  end
end
```

{{< /tab >}}
{{< /tabs >}}
