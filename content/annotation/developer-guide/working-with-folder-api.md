---
id: "working-with-folder-api"
url: "annotation/working-with-folder-api"
title: "Working with Folder API"
productName: "GroupDocs.Annotation Cloud"
weight: 8
description: ""
keywords: ""
toc: True
---
## Get the File Listing of a Specific Folder

This API allows you to get a list of all files of a specific folder from the specified Cloud Storage. If you do not pass storage name API will find folder in GroupDocs Cloud Storage.

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/) lets you to try out [List Files in a Folder API](https://apireference.groupdocs.cloud/conversion/#/Folder/GetFilesList) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. */Folder1/file.ext*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with

### cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/conversion/storage/folder/annotationdocs?storageName#MyStorage" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X GET "https://api.groupdocs.cloud/v2.0/conversion/storage/folder/annotationdocs?storageName#MyStorage" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X GET "https://api.groupdocs.cloud/v2.0/conversion/storage/folder/annotationdocs?storageName#MyStorage" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "value": [
    {
      "name": "four-pages.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:38+00:00",
      "size": 8651,
      "path": "/annotationdocs/four-pages.docx"
    },
    {
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:34+00:00",
      "size": 351348,
      "path": "/annotationdocs/one-page.docx"
    },
    {
      "name": "password-protected.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:40+00:00",
      "size": 10240,
      "path": "/annotationdocs/password-protected.docx"
    },
    {
      "name": "sample.mpp",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:29:10+00:00",
      "size": 289792,
      "path": "/annotationdocs/sample.mpp"
    },
    {
      "name": "three-layouts.dwf",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:26:42+00:00",
      "size": 15433,
      "path": "/annotationdocs/three-layouts.dwf"
    },
    {
      "name": "two-hidden-pages.vsd",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:36+00:00",
      "size": 457728,
      "path": "/annotationdocs/two-hidden-pages.vsd"
    },
    {
      "name": "uses-custom-font.pptx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:32:30+00:00",
      "size": 39823,
      "path": "/annotationdocs/uses-custom-font.pptx"
    },
    {
      "name": "with-hidden-rows-and-columns.xlsx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:37+00:00",
      "size": 15986,
      "path": "/annotationdocs/with-hidden-rows-and-columns.xlsx"
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.



{{< tabs "example2">}}
{{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Get Files List
	class Get_Files_List
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FolderApi(configuration);

			try
			{
				var request = new GetFilesListRequest("Annotationdocs", Common.MyStorage);

				var response = apiInstance.GetFilesList(request);
				Console.WriteLine("Expected response type is FilesList: " + response.Value.Count.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FolderApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Folder;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.FilesList;
import com.groupdocs.cloud.annotation.model.*;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Get_Files_List {

	public static void main(String[] args) {

		FolderApi apiInstance = new FolderApi(Utils.AppSID, Utils.AppKey);
		try {
			GetFilesListRequest request = new GetFilesListRequest("annotations", Utils.MYStorage);
			FilesList response = apiInstance.getFilesList(request);
			System.out.println("Expected response type is FilesList.");
			for (StorageFile storageFile : response.getValue()) {
				System.out.println("Files: " + storageFile.getPath());
			}
		} catch (ApiException e) {
			System.err.println("Exception while calling FolderApi:");
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
		$apiInstance = CommonUtils::GetFolderApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\GetFilesListRequest("annotationdocs", CommonUtils::$MyStorage);
		$response = $apiInstance->getFilesList($request);
		
		echo "Expected response type is FilesList.", "<br />";

		foreach($response->getValue() as $storageFile) {
          echo "Files: ", $storageFile->getPath(), "<br />";
		}
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Get_Files_List {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_annotation_cloud_1.GetFilesListRequest("Annotationdocs/sample.docx", myStorage);
		folderApi.getFilesList(request)
			.then(function (response) {
				console.log("Expected response type is FilesList: " + response.value.length);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Get_Files_List;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Get_Files_List:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FolderApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.GetFilesListRequest("annotationdocs\\sample.docx", Common_Utilities.myStorage)
            response = api.get_files_list(request)
            
            print("Expected response type is FilesList: " + str(response))
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Folder
  def self.Annotation_Ruby_Get_Files_List()

    # Getting instance of the API
    $api = Common_Utilities.Get_FolderApi_Instance()
    
    $request = GroupDocsAnnotationCloud::GetFilesListRequest.new("annotationdocs/sample.docx", $myStorage)
    $response = $api.get_files_list($request)

    puts("Expected response type is FilesList: " + ($response).to_s)
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## Create a New Folder

This API allows you to create a new Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage.

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/) lets you to try out [Create Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/CreateFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Target folder’s path e.g. *Folder1/Folder2/*. The folders will be created recursively. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with

### cURL example

{{< tabs "example3">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X POST "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X POST "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example4">}}
{{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Create Folder
	class Create_Folder
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FolderApi(configuration);

			try
			{
				var request = new CreateFolderRequest("", Common.MyStorage);

				apiInstance.CreateFolder(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs' folder created.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FolderApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Folder;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Create_Folder {

	public static void main(String[] args) {

		FolderApi apiInstance = new FolderApi(Utils.AppSID, Utils.AppKey);
		try {
			CreateFolderRequest request = new CreateFolderRequest("annotations", Utils.MYStorage);
			apiInstance.createFolder(request);
			System.out.println("Expected response type is Void: 'annotations' folder created.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FolderApi:");
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
		$apiInstance = CommonUtils::GetFolderApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\CreateFolderRequest("annotationdocs", CommonUtils::$MyStorage);
		$apiInstance->createFolder($request);
		
		echo "Expected response type is Void: 'annotationdocs' folder created.", "<br />";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Create_Folder {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_annotation_cloud_1.CreateFolderRequest("annotations", myStorage);
		folderApi.createFolder(request)
			.then(function () {
				console.log("Expected response type is Void: 'Annotationdocs' folder created.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Create_Folder;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Create_Folder:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FolderApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.CreateFolderRequest("Assembler", Common_Utilities.myStorage)
            api.create_folder(request)
            
            print("Expected response type is Void: 'Assembler' folder created.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Folder
  def self.Annotation_Ruby_Create_Folder()

    # Getting instance of the API
    $api = Common_Utilities.Get_FolderApi_Instance()
    
    $request = GroupDocsAnnotationCloud::CreateFolderRequest.new("annotationdocs", $myStorage)
    $response = $api.create_folder($request)

    puts("Expected response type is Void: 'annotationdocs' folder created.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## Delete a Particular Folder

This API allows you to delete a particular Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage. To remove recursively inner folder/files you need to pass true value to recursive parameter inRequest. If it is set to false and folder contains data then API throws the exception.

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/conversion/#/) lets you to try out [Delete a Particular Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/DeleteFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Folder path e.g. */Folder1*. Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then the API will use the default storage of the Application used to authenticate with

## cURL example

{{< tabs "example5">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage&#x26;recursive#true" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X DELETE "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage&#x26;recursive#true" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X DELETE "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/annotationdocs?storageName#MyStorage&#x26;recursive#true" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Delete Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/DeleteFolder) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example6">}}
{{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Delete Folder
	class Delete_Folder
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FolderApi(configuration);

			try
			{
				var request = new DeleteFolderRequest("Annotationdocs/Annotationdocs1", Common.MyStorage, true);

				apiInstance.DeleteFolder(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs/Annotationdocs1' folder deleted recusrsively.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FolderApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Folder;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Delete_Folder {

	public static void main(String[] args) {

		FolderApi apiInstance = new FolderApi(Utils.AppSID, Utils.AppKey);
		try {
			DeleteFolderRequest request = new DeleteFolderRequest("annotations\\annotations1", Utils.MYStorage, true);
			apiInstance.deleteFolder(request);
			System.out
					.println("Expected response type is Void: 'annotations/annotations1' folder deleted recusrsively.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FolderApi:");
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
		$apiInstance = CommonUtils::GetFolderApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\DeleteFolderRequest("annotationdocs1\\annotationdocs1", CommonUtils::$MyStorage, true);
		$apiInstance->deleteFolder($request);
		
		echo "Expected response type is Void: 'annotationdocs1/annotationdocs1' folder deleted recursively.", "<br />";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Delete_Folder {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_annotation_cloud_1.DeleteFolderRequest("Annotationdocs/annotations1", myStorage, true);
		folderApi.deleteFolder(request)
			.then(function () {
				console.log("Expected response type is Void: 'Annotationdocs/annotations1' folder deleted recursively.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Delete_Folder;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Delete_Folder:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FolderApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.DeleteFolderRequest("annotationdocs\\annotationdocs1", Common_Utilities.myStorage, True)
            api.delete_folder(request)
            
            print("Expected response type is Void: 'annotationdocs/annotationdocs1' folder deleted recursively.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Folder
  def self.Annotation_Ruby_Delete_Folder()

    # Getting instance of the API
    $api = Common_Utilities.Get_FolderApi_Instance()
    
    $request = GroupDocsAnnotationCloud::DeleteFolderRequest.new("annotationdocs1", $myStorage, true)
    $response = $api.delete_folder($request)

    puts("Expected response type is Void: 'annotationdocs/annotationdocs1' folder deleted recursively.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}

## Copy  Specific Folder

This API allows you to copy a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will copy Folder within default Cloud Storage.

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Copy Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/CopyFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. */Folder1*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination folder. If not set, then the API will use the default storage of the Application used to authenticate with

### cURL example

{{< tabs "example7">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/copy/annotationdocs?destPath#conversiondocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/copy/annotationdocs?destPath#conversiondocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/copy/annotationdocs?destPath#conversiondocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Copy Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/CopyFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example8">}}
{{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Copy Folder
	class Copy_Folder
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FolderApi(configuration);

			try
			{
				var request = new CopyFolderRequest("Annotationdocs", "Annotationdocs1", Common.MyStorage, Common.MyStorage);

				apiInstance.CopyFolder(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs' folder copied as 'Annotationdocs1'.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FolderApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Folder;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Copy_Folder {

	public static void main(String[] args) {

		FolderApi apiInstance = new FolderApi(Utils.AppSID, Utils.AppKey);
		try {
			CopyFolderRequest request = new CopyFolderRequest("annotations", "annotations1", Utils.MYStorage,
					Utils.MYStorage);
			apiInstance.copyFolder(request);
			System.out.println("Expected response type is Void: 'annotations' folder copied as 'annotations1'.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FolderApi:");
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
		$apiInstance = CommonUtils::GetFolderApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\CopyFolderRequest("annotationdocs", "annotationdocs1", CommonUtils::$MyStorage, CommonUtils::$MyStorage);
		$apiInstance->copyFolder($request);
		
		echo "Expected response type is Void: 'annotationdocs' folder copied as 'annotationdocs1'.", "<br />";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Copy_Folder {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_annotation_cloud_1.CopyFolderRequest("annotations", "annotations1", myStorage, myStorage);
		folderApi.copyFolder(request)
			.then(function () {
				console.log("Expected response type is Void: 'Annotationdocs' folder copied as 'Annotationdocs1'.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Copy_Folder;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Copy_Folder:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FolderApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.CopyFolderRequest("annotationdocs", "annotationdocs1", Common_Utilities.myStorage, Common_Utilities.myStorage)
            api.copy_folder(request)
            
            print("Expected response type is Void: 'annotationdocs' folder copied as 'annotationdocs1'.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Folder
  def self.Annotation_Ruby_Copy_Folder()

    # Getting instance of the API
    $api = Common_Utilities.Get_FolderApi_Instance()
    
    $request = GroupDocsAnnotationCloud::CopyFolderRequest.new("annotationdocs", "annotationdocs1", $myStorage, $myStorage)
    $response = $api.copy_folder($request)

    puts("Expected response type is Void: 'annotationdocs' folder copied as 'annotationdocs1'.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}

### Move a Specific Folder

This API allows you to move a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will move Folder within default Cloud Storage.

### API Explorer

[GroupDocs.Annotation Cloud API Reference](https://apireference.groupdocs.cloud/annotation/#/) lets you to try out [Move a Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/MoveFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. */Folder1*. Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then the API will use the default storage of the Application used to authenticate with
|destStorageName|Name of the storage of destination folder. If not set, then the API will use the default storage of the Application used to authenticate with

### cURL example

{{< tabs "example9">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/move/annotationdocs?destPath#annotationdocs&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/move/annotationdocs?destPath#annotationdocs&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X PUT "https://api.groupdocs.cloud/v2.0/annotation/storage/folder/move/annotationdocs?destPath#annotationdocs&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-annotation-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-annotation-cloud), it hides the [Move Folder API](https://apireference.groupdocs.cloud/annotation/#/Folder/MoveFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example10">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Annotation.Cloud.Sdk.Api;
using GroupDocs.Annotation.Cloud.Sdk.Client;
using GroupDocs.Annotation.Cloud.Sdk.Model.Requests;
using System;

namespace GroupDocs.Annotation.Cloud.Examples.CSharp
{
	// Move Folder
	class Move_Folder
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new FolderApi(configuration);

			try
			{
				var request = new MoveFolderRequest("Annotationdocs1", "Annotationdocs\\Annotationdocs1", Common.MyStorage, Common.MyStorage);

				apiInstance.MoveFolder(request);
				Console.WriteLine("Expected response type is Void: 'Annotationdocs1' folder moved to 'Annotationdocs/Annotationdocs1'.");
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling FolderApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
package examples.Working_With_Folder;

import com.groupdocs.cloud.annotation.api.*;
import com.groupdocs.cloud.annotation.client.ApiException;
import com.groupdocs.cloud.annotation.model.requests.*;
import examples.Utils;

public class Annotation_Java_Move_Folder {

	public static void main(String[] args) {

		FolderApi apiInstance = new FolderApi(Utils.AppSID, Utils.AppKey);
		try {
			MoveFolderRequest request = new MoveFolderRequest("annotations1", "annotations\\annotations1",
					Utils.MYStorage, Utils.MYStorage);
			apiInstance.moveFolder(request);
			System.out.println(
					"Expected response type is Void: 'annotations1' folder moved to 'annotations/annotations1'.");
		} catch (ApiException e) {
			System.err.println("Exception while calling FolderApi:");
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
		$apiInstance = CommonUtils::GetFolderApiInstance();

		$request = new GroupDocs\Annotation\Model\Requests\MoveFolderRequest("annotationdocs1", "annotationdocs1\\annotationdocs1", CommonUtils::$MyStorage, CommonUtils::$MyStorage, true);
		$apiInstance->moveFolder($request);
		
		echo "Expected response type is Void: 'annotationdocs1' folder moved to 'annotationdocs1/annotationdocs1'.", "<br />";
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```

{{< /tab >}}
{{< tab "Node.js" >}}

```js
"use strict";
class Annotation_Node_Move_Folder {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_annotation_cloud_1.MoveFolderRequest("annotations1", "Annotationdocs/annotations1", myStorage, myStorage);
		folderApi.moveFolder(request)
			.then(function () {
				console.log("Expected response type is Void: 'Annotationdocs1' folder moved to 'Annotationdocs/annotations1'.");
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Annotation_Node_Move_Folder;

```

{{< /tab >}}
{{< tab "Python" >}}

```python
# Import modules
import groupdocs_annotation_cloud

from Common_Utilities.Utils import Common_Utilities


class Annotation_Python_Move_Folder:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_FolderApi_Instance()
        
        try:
            request = groupdocs_annotation_cloud.MoveFolderRequest("annotationdocs1", "annotationdocs1\\annotationdocs", Common_Utilities.myStorage, Common_Utilities.myStorage)
            api.move_folder(request)
            
            print("Expected response type is Void: 'annotationdocs1' folder moved to 'annotationdocs/annotationdocs1'.")
        except groupdocs_annotation_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}}
{{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_annotation_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Folder
  def self.Annotation_Ruby_Move_Folder()

    # Getting instance of the API
    $api = Common_Utilities.Get_FolderApi_Instance()

    $request = GroupDocsAnnotationCloud::MoveFolderRequest.new("annotationdocs1", "annotationdocs/annotationdocs1", $myStorage, $myStorage)
    $response = $api.move_folder($request)

    puts("Expected response type is Void: 'annotationdocs1' folder moved to 'annotationdocs/annotationdocs1'.")
  end
end
```

{{< /tab >}}
{{< /tabs >}}
