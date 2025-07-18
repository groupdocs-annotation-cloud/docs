---
id: "working-with-file-api"
url: "annotation/working-with-file-api"
title: "Working with File Api"
productName: "GroupDocs.Annotation Cloud"
weight: 7
description: ""
keywords: ""
toc: True
---
## Download File API

This API allows you to download a file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Download a File API](https://apireference.groupdocs.cloud/annotation/#/File/DownloadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|File version id

### cURL example

{{< tabs "example1">}}
{{< tab "Request" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/annotation/storage/file/one-page.docx?storageName#MyStorage" -H  "accept: multipart/form-data" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;
using System;
using System.IO;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Download_File
	class Download_File
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FileApi(configuration);

			try
			{
				var request = new DownloadFileRequest("Annotationdocs/ten-pages.pdf", Common.MyStorage);

				Stream response = apiInstance.DownloadFile(request);
				using (var fileStream = File.Create("D:\\tenpages.pdf"))
				{
					response.Seek(0, SeekOrigin.Begin);
					response.CopyTo(fileStream);
				}
				Console.WriteLine("Expected response type is Stream: " + response.Length.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FileApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Files;

import java.io.File;
import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Download_File {

	public static void main(String[] args) {

		FileApi apiInstance = new FileApi(Utils.AppSID, Utils.AppKey);
		try {

			DownloadFileRequest request = new DownloadFileRequest("Annotationdocs\\two-page.docx", Utils.MYStorage, null);
			File response = apiInstance.downloadFile(request);
			System.err.println("Expected response type is File: " + response.length());
		} catch (ApiException e) {
			System.err.println("Exception while calling FileApi:");
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
		$apiInstance = CommonUtils::GetFileApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\DownloadFileRequest("annotationdocs\one-page.docx", CommonUtils::$MyStorage, null);
		$response = $apiInstance->downloadFile($request);
		
		echo "Expected response type is File: ", strlen($response);
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Download_File {
	static Run() {
		var request = new groupdocs_annotation_cloud_1.DownloadFileRequest("Annotationdocs/one-page.docx", myStorage);
		fileApi.downloadFile(request)
			.then(function (response) {
				console.log("Expected response type is Stream: " + response.length);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Download_File;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Download_File:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FileApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.DownloadFileRequest("annotationdocs\\one-page.docx", Common_Utilities.myStorage)
            response = api.download_file(request)
            
            print("Expected response type is Stream: " + str(len(response)))
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Files
  def self.Annotation_Ruby_Download_File()

    # Getting instance of the API
    $api = Common_Utilities.Get_FileApi_Instance()

    $request = GroupDocsAnnotationCloud::DownloadFileRequest.new("annotationdocs/one-page.docx", $myStorage)
    $response = $api.download_file($request)
    
    puts("Expected response type is Stream: " + ($response).to_s)
  end
end
```

{{< /tab >}}
{{< /tabs >}}

##  Upload File API

This API allows you to upload files to the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you try out [Upload a File API](https://apireference.groupdocs.cloud/conversion/#/File/UploadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request Body parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|File|File content

### cURL example

{{< tabs "example3">}}
{{< tab "Request" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation/storage/file/annotationdocs/Fone-page2.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
Http status code: 200 (Returns OK and list of errors, which is empty if success.)
{
  "Uploaded": [
    "string"
  ],
  "Errors": [
    {
      "Code": "string",
      "Message": "string",
      "Description": "string",
      "InnerError": {
        "RequestId": "string",
        "Date": "2019-02-27T06:10:08.884Z"
      }
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example4">}}
{{< tab "C#" >}}

```csharp
using System;
using System.IO;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Upload File
	class Upload_File
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FileApi(configuration);

			try
			{
				// Open file in IOStream from local/disc.
				var fileStream = File.Open("..\\..\\..\\Data\\Annotationdocs\\one-page.docx", FileMode.Open);

				var request = new UploadFileRequest("Annotationdocs/one-page1.docx", fileStream, Common.MyStorage);

				var response = apiInstance.UploadFile(request);
				Console.WriteLine("Expected response type is FilesUploadResult: " + response.Uploaded.Count.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FileApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Files;

import java.io.File;
import java.nio.file.Paths;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.*;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Upload_File {

	public static void main(String[] args) {

		FileApi apiInstance = new FileApi(Utils.AppSID, Utils.AppKey);
		try {
			File fileStream = new File(
					Paths.get("src\\main\\resources").toAbsolutePath().toString() + "\\Annotationdocs\\one-page.docx");
			UploadFileRequest request = new UploadFileRequest("Annotationdocs\\one-page1.docx", fileStream,
					Utils.MYStorage);
			FilesUploadResult response = apiInstance.uploadFile(request);
			System.out.println("Expected response type is FilesUploadResult: " + response.getUploaded().size());
		} catch (ApiException e) {
			System.err.println("Exception while calling FileApi:");
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
		$apiInstance = CommonUtils::GetFileApiInstance();
		$filePath = realpath(dirname(__DIR__). '\Resources\annotationdocs\one-page.docx');
		echo "filePath: ". $filePath;

		$fileStream = readfile($filePath);
		$request = new GroupDocs\Annotation\Model\Requests\UploadFileRequest("annotationdocs\one-page1.docx", $fileStream);
		$response = $apiInstance->uploadFile($request);
		
		echo "Expected response type is FilesUploadResult: ", $response;
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Upload_File {
	static Run() {

		// Open file in IOStream from local/disc.
		var resourcesFolder = './Resources/Annotationdocs/one-page.docx';
		fs.readFile(resourcesFolder, (err, fileStream) => {

			var request = new groupdocs_annotation_cloud_1.UploadFileRequest("Annotationdocs/one-page1.docx", fileStream, myStorage);
			fileApi.uploadFile(request)
				.then(function (response) {
					console.log("Expected response type is FilesUploadResult: " + response.uploaded.length);
				})
				.catch(function (error) {
					console.log("Error: " + error.message);
				});
		});
	}
}
module.exports = Annotation_Node_Upload_File;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Upload_File:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FileApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.UploadFileRequest("annotationdocs\\one-page.docx", "D:\\ewspace\\GroupDocs.Annotation.Cloud.Python.Examples\\src\\Resources\\annotationdocs\\one-page.docx", Common_Utilities.myStorage)
            response = api.upload_file(request)
            
            print("Expected response type is FilesUploadResult: " + str(response))
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Files
  def self.Annotation_Ruby_Upload_File()

    # Getting instance of the API
    $api = Common_Utilities.Get_FileApi_Instance()
   
    $fileStream = File.new("..\\Resources\\annotationdocs\\one-page.docx", "r")
    
    $request = GroupDocsAnnotationCloud::UploadFileRequest.new("annotationdocs/one-page1.docx", $fileStream, $myStorage)
    $response = $api.upload_file($request)
    
    $fileStream.close()

    puts("Expected response type is FilesUploadResult: " + ($response).to_s)
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## Delete File API

This API allows you to delete specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Delete a File](https://apireference.groupdocs.cloud/annotation/#/File/DeleteFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.


### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|File version id

### cURL example

{{< tabs "example5">}}
{{< tab "Request" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation/storage/file/annotationdocs%2Fone-page1.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.



{{< tabs "example6">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;
using System;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Delete File
	class Delete_File
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FileApi(configuration);

			try
			{
				var request = new DeleteFileRequest("Annotationdocs1/one-page1.docx", Common.MyStorage);

				apiInstance.DeleteFile(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs1/one-page1.docx' deleted.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FileApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Files;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Delete_File {

	public static void main(String[] args) {

		FileApi apiInstance = new FileApi(Utils.AppSID, Utils.AppKey);
		try {

			DeleteFileRequest request = new DeleteFileRequest("annotations1\\one-page1.docx", Utils.MYStorage, null);
			apiInstance.deleteFile(request);
			System.out.println("Expected response type is Void: 'annotations1/one-page1.docx' deleted.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FileApi:");
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
		$apiInstance = CommonUtils::GetFileApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\DeleteFileRequest("annotationdocs\one-page-copied.docx", CommonUtils::$MyStorage);
		$apiInstance->deleteFile($request);
		
		echo "Expected response type is Void: 'annotationdocs1/one-page-copied.docx' file deleted.";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Delete_File {
	static Run() {
		var request = new groupdocs_annotation_cloud_1.DeleteFileRequest("annotations1/one-page1.docx", myStorage);
		fileApi.deleteFile(request)
			.then(function (response) {
				console.log("Expected response type is Void: 'Annotationdocs1/one-page1.docx' deleted.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Delete_File;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Delete_File:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FileApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.DeleteFileRequest("annotationdocs1\\one-page.docx", Common_Utilities.myStorage)
            api.delete_file(request)
            
            print("Expected response type is Void: 'annotationdocs1/one-page.docx' deleted.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Files
  def self.Annotation_Ruby_Delete_File()

    # Getting instance of the API
    $api = Common_Utilities.Get_FileApi_Instance()

    $request = GroupDocsAnnotationCloud::DeleteFileRequest.new("annotationdocs1/one-page.docx", $myStorage)
    $response = $api.delete_file($request)

    puts("Expected response type is Void: 'annotationdocs1/one-page.docx' deleted.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## File Copy API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Copy File](https://apireference.groupdocs.cloud/annotation/#/File/CopyFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination file. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|Source file version id

### cURL example

{{< tabs "example7">}}
{{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/file/copy/annotationdocs%2Fone-page1.docx?destPath#conversiondocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}


### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.



{{< tabs "example8">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;
using System;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Copy File
	class Copy_File
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FileApi(configuration);

			try
			{
				var request = new CopyFileRequest("Annotationdocs/one-page1.docx", "Annotationdocs/one-page-copied.docx", Common.MyStorage, Common.MyStorage);

				apiInstance.CopyFile(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs/one-page1.docx' file copied as 'Annotationdocs/one-page-copied.docx'.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FileApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Files;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Copy_File {

	public static void main(String[] args) {

		FileApi apiInstance = new FileApi(Utils.AppSID, Utils.AppKey);
		try {

			CopyFileRequest request = new CopyFileRequest("Annotationdocs\\two-page.docx",
					"Annotationdocs\\two-page-copied.docx", Utils.MYStorage, Utils.MYStorage, null);
			apiInstance.copyFile(request);
			System.out.println(
					"Expected response type is Void: 'annotations/one-page1.docx' file copied as 'annotations/one-page-copied.docx'.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FileApi:");
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
		$apiInstance = CommonUtils::GetFileApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\CopyFileRequest("annotationdocs\one-page.docx", "annotationdocs\one-page-copied.docx", CommonUtils::$MyStorage, CommonUtils::$MyStorage);
		$apiInstance->copyFile($request);
		
		echo "Expected response type is Void: 'annotationdocs/one-page.docx' file copied as 'annotationdocs/one-page-copied.docx'.";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Copy_File {
	static Run() {
		var request = new groupdocs_annotation_cloud_1.CopyFileRequest("Annotationdocs/one-page1.docx", "Annotationdocs/one-page-copied.docx", myStorage, myStorage);
		fileApi.copyFile(request)
			.then(function (response) {
				console.log("Expected response type is Void: 'Annotationdocs/one-page1.docx' file copied as 'Annotationdocs/one-page-copied.docx'.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Copy_File;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Copy_File:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FileApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.CopyFileRequest("annotationdocs\\one-page.docx", "annotationdocs\\one-page-copied.docx", Common_Utilities.myStorage, Common_Utilities.myStorage)
            api.copy_file(request)
            
            print("Expected response type is Void: 'annotationdocs/one-page.docx' file copied as 'annotationdocs/one-page-copied.docx'.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Files
  def self.Annotation_Ruby_Copy_File()

    # Getting instance of the API
    $api = Common_Utilities.Get_FileApi_Instance()

    $request = GroupDocsAnnotationCloud::CopyFileRequest.new("annotationdocs/one-page.docx", "annotationdocs/one-page-copied.docx", $myStorage, $myStorage)
    $response = $api.copy_file($request)

    puts("Expected response type is Void: 'annotationdocs/one-page.docx' file copied as 'annotationdocs/one-page-copied.docx'.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## File Move API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Move File](https://apireference.groupdocs.cloud/annotation/#/File/MoveFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination file. If not set, then the API will use the default storage of the Application used to authenticate with
|versionId|Source file version id

### cURL example

{{< tabs "example9">}}
{{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/file/move/annotationdocs%2Fone-page1.docx?destPath#conversiondocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [File API](https://apireference.groupdocs.cloud/annotation/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example10">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;
using System;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Move File
	class Move_File
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FileApi(configuration);

			try
			{
				var request = new MoveFileRequest("Annotationdocs/one-page1.docx", "Annotationdocs1/one-page1.docx", Common.MyStorage, Common.MyStorage);

				apiInstance.MoveFile(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs/one-page1.docx' file moved to 'Annotationdocs1/one-page1.docx'.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FileApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Files;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Move_File {

	public static void main(String[] args) {

		FileApi apiInstance = new FileApi(Utils.AppSID, Utils.AppKey);
		try {

			MoveFileRequest request = new MoveFileRequest("Annotationdocs\\one-page.docx", "Annotationdocs\\one-page1.docx",
					Utils.MYStorage, Utils.MYStorage, null);
			apiInstance.moveFile(request);
			System.out.println(
					"Expected response type is Void: 'Annotationdocs/one-page.docx' file moved to 'Annotationdocs1/one-page1.docx'.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FileApi:");
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
		$apiInstance = CommonUtils::GetFileApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\MoveFileRequest("annotationdocs\one-page.docx", "annotationdocs1\one-page-copied.docx", CommonUtils::$MyStorage, CommonUtils::$MyStorage);
		$apiInstance->moveFile($request);
		
		echo "Expected response type is Void: 'annotationdocs/one-page.docx' file moved as 'annotationdocs1/one-page-copied.docx'.";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Move_File {
	static Run() {
		var request = new groupdocs_annotation_cloud_1.MoveFileRequest("Annotationdocs/one-page1.docx", "annotations1/one-page1.docx", myStorage, myStorage);
		fileApi.moveFile(request)
			.then(function (response) {
				console.log("Expected response type is Void: 'Annotationdocs/one-page1.docx' file moved to 'Annotationdocs1/one-page1.docx'.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Move_File;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Move_File:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FileApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.MoveFileRequest("annotationdocs\\one-page.docx", "annotationdocs1\\one-page.docx", Common_Utilities.myStorage, Common_Utilities.myStorage)
            api.move_file(request)
            
            print("Expected response type is Void: 'annotationdocs/one-page.docx' file moved to 'annotationdocs1/one-page.docx'.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Files
  def self.Annotation_Ruby_Move_File()

    # Getting instance of the API
    $api = Common_Utilities.Get_FileApi_Instance()

    $request = GroupDocsAnnotationCloud::MoveFileRequest.new("annotationdocs/one-page.docx", "annotationdocs1/one-page.docx", $myStorage, $myStorage)
    $response = $api.move_file($request)

    puts("Expected response type is Void: 'annotationdocs/one-page.docx' file moved to 'annotationdocs1/one-page.docx'.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}
