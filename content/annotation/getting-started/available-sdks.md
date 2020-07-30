---
id: "available-sdks"
url: "annotation/available-sdks"
title: "GroupDocs.Annotation Cloud SDKs"
productName: "GroupDocs.Annotation Cloud"
weight: 3
description: ""
keywords: ""
---
GroupDocs.Annotation Cloud is a modern REST oriented API, that allows easy integration into existing systems.

## Why use an SDK? ##

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project.

## SDK benefits ##

Our supported SDKs are 100% tested and out of the box running. These SDKs are open source and have an MIT license. You can use them, and even customize them for absolutely free of charge.

## Supported SDKs ##

**GroupDocs.Annotation Cloud SDK for .NET** allows you to incorporate GroupDocs.Annotation Cloud services in your .NET applications quickly and easily. Install [GroupDocs.Annotation-Cloud](https://www.nuget.org/packages/GroupDocs.Annotation-Cloud/) via NuGet from Package Manager:

```bash  
PM> Install-Package GroupDocs.Annotation-Cloud
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Annotation Cloud SDK for .Net is freely available on the [GitHub](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet). Please see the GroupDocs.Annotation Cloud SDK for .NET [Examples here](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-dotnet/tree/master/GroupDocs.Annotation.Cloud.Sdk.Test/Api).{{< /alert >}}  

**GroupDocs.Annotation Cloud SDK for PHP** allows you to incorporate GroupDocs.Annotation Cloud services in your PHP applications quickly and easily. It is available on Packagist as the [groupdocs-annotation-cloud](https://packagist.org/packages/groupdocscloud/groupdocs-annotation-cloud) package. Run the following command:

```bash
composer require groupdocscloud/groupdocs-annotation-cloud
```

To use the SDK, use Composer's [autoload](https://getcomposer.org/doc/00-intro.md#autoloading):

```bash
require_once('vendor/autoload.php');
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Annotation Cloud SDK for PHP is freely available on [GitHub](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php). Please see the GroupDocs.Annotation Cloud SDK for PHP [Examples here](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-php/tree/master/tests/GroupDocs/Annotation/ApiTests).{{< /alert >}}

**GroupDocs.Annotation Cloud SDK for Java** allows you to incorporate GroupDocs.Annotation Cloud services in your Java applications quickly and easily. You can directly include the source code of GroupDocs.Annotation Cloud SDK for Java in your own project, the source code is available from [here](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java).

Alternatively, you can use [**Maven**](https://repository.groupdocs.cloud/webapp/#/artifacts/browse/tree/General/repo/com/groupdocs/groupdocs-annotation-cloud) to include in your Java project. Below are the steps for Maven.

### GroupDocs Maven Repository ###

```bash
<repository>  
    <id>groupdocs-artifact-repository</id>  
    <name>GroupDocs Artifact Repository</name>  
    <url>http://repository.groupdocs.cloud/repo</url>
</repository>
```

### Maven Dependency ###

```bash
<dependency>  
    <groupId>com.groupdocs</groupId>  
    <artifactId>groupdocs-annotation-cloud</artifactId>  
    <version>18.4</version>  
    <scope>compile</scope>
</dependency>
```

### Get Sources and Javadocs ###

#### Maven ####

```bash
$ mvn dependency:sources
$ mvn dependency:resolve -Dclassifier#javadoc
```

#### Eclipse IDE ####

```bash
$ mvn eclipse:eclipse -DdownloadSources#true
$ mvn eclipse:eclipse -DdownloadSources#true -DdownloadJavadocs#false
```

#### pom.xml ####

```bash
<build>  
    <plugins>  
        <plugin>  
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-eclipse-plugin</artifactId>
            <configuration>
                <downloadSources>true</downloadSources>
                <downloadJavadocs>false</downloadJavadocs>
            </configuration>
        </plugin>  
    </plugins>
</build>
```

#### Direct Download ####

{{< alert style="info" >}}
Complete source code of GroupDocs.Annotation Cloud SDK for Java is freely available on the [GitHub](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java). Please see the GroupDocs.Annotation Cloud SDK for Java [Examples here](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-java/tree/master/src/test/java/com/groupdocs/cloud/annotation/api).{{< /alert >}}

**GroupDocs.Annotation Cloud SDK for Ruby** allows you to incorporate GroupDocs.Annotation Cloud services in your Ruby applications quickly and easily. It is available on **[RubyGem distribution](https://rubygems.org/gems/groupdocs_annotation_cloud)** package. Run the following command::

```bash
gem install groupdocs_cloud_annotation
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Annotation Cloud SDK for Ruby is freely available on the [GitHub](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby). Please see the GroupDocs.Annotation Cloud SDK for Ruby [Examples here](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-ruby/tree/master/test/api).{{< /alert >}}