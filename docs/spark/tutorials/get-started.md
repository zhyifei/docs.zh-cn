---
title: .NET for Apache Spark 入门
description: 了解如何在 Windows 上使用 .NET Core 运行 .NET for Apache Spark 应用。
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 004256a2fe369b026b15151dfc72ae379da0be8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928486"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>教程：.NET for Apache Spark 入门

本教程介绍如何在 Windows 上使用 .NET Core 运行 .NET for Apache Spark 应用。

在本教程中，你将了解：

> [!div class="checklist"]
>
> * 为 .NET for Apache Spark 准备 Windows 环境
> * 下载 Microsoft.Spark.Worker 
> * 生成和运行简单的 .NET for Apache Spark 应用程序

## <a name="prepare-your-environment"></a>准备环境

开始之前，请确保可以从命令行运行 `dotnet`、`java`、`mvn`、`spark-shell`。 如果环境已准备好，则可跳至下一部分。 如果无法运行任何或所有命令，请按照以下步骤操作。

1. 下载并安装 [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)。 安装 SDK 会将 `dotnet` 工具链添加到路径。 使用 PowerShell 命令 `dotnet --version` 以验证安装。

2. 安装包含最新更新的 [Visual Studio 2017](https://www.visualstudio.com/downloads/) 或 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/)。 可以使用 Community、Professional 或 Enterprise。 Community 版本免费。

   在安装过程中选择以下工作负载：
      * .NET 桌面开发
          * 所有必需的组件
          * .NET Framework 4.6.1 开发工具
      * .NET Core 跨平台开发
          * 所有必需的组件

3. 安装 [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)。

    * 选择适用于操作系统的合适版本。 例如，为 Windows x64 计算机选择 jdk-8u201-windows-x64.exe  。
    * 使用 PowerShell 命令 `java -version` 以验证安装。

4. 安装 [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)。
    * 下载 [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)。
    * 提取到本地目录。 例如 `c:\bin\apache-maven-3.6.0\`。
    * 将 Apache Maven 添加到 [PATH 环境变量](https://www.java.com/en/download/help/path.xml)。 如果已提取到 `c:\bin\apache-maven-3.6.0\`，则需将 `c:\bin\apache-maven-3.6.0\bin` 添加到路径。
    * 使用 PowerShell 命令 `mvn -version` 以验证安装。

5. 安装 [Apache Spark 2.3+](https://spark.apache.org/downloads.html)。 不支持 Apache Spark 2.4 及以上版本。
    * 下载 [Apache Spark 2.3+](https://spark.apache.org/downloads.html) 并使用 [7-zip](https://www.7-zip.org/) 或 [WinZip](https://www.winzip.com/) 等工具将其提取到本地文件夹。 例如，可以将其提取到 `c:\bin\spark-2.3.2-bin-hadoop2.7\`。
    * 将 Apache Spark 添加到 [PATH 环境变量](https://www.java.com/en/download/help/path.xml)。 如果已提取到 `c:\bin\spark-2.3.2-bin-hadoop2.7\`，则需将 `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` 添加到路径。
    * 添加名为 `SPARK_HOME` 的[新环境变量](https://www.java.com/en/download/help/path.xml)。 如果已提取到 `C:\bin\spark-2.3.2-bin-hadoop2.7\`，则使用 `C:\bin\spark-2.3.2-bin-hadoop2.7\` 存储变量值  。
    * 验证是否能够从命令行运行 `spark-shell`。

6. 设置 [WinUtils](https://github.com/steveloughran/winutils)。
    * 从 [WinUtils 存储库](https://github.com/steveloughran/winutils)下载 winutils.exe 二进制文件  。 选择编译 Spark 发行版时使用的 Hadoop 版本。 例如，将 hadoop-2.7.1 用于 Spark 2.3.2   。 Hadoop 版本批注在 Spark 安装文件夹名称的末尾。
    * 将 winutils.exe 二进制文件保存到所选的目录  。 例如 `c:\hadoop\bin`。
    * 设置 `HADOOP_HOME` 以反映包含不带 `bin` 的 winutils.exe 的目录  。 例如 `c:\hadoop`。
    * 设置 PATH 环境变量以包含 `%HADOOP_HOME%\bin`。

再次确认可以从命令行运行 `dotnet`、`java`、`mvn`、`spark-shell`，然后再转到下一部分。

## <a name="download-the-microsoftsparkworker-release"></a>下载 Microsoft.Spark.Worker 版本

1. 从本地计算机的 .NET for Apache Spark GitHub 版本页下载 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)。 例如，可以将其下载到路径 `c:\bin\Microsoft.Spark.Worker\`。

2. 创建名为 `DotnetWorkerPath` 的[新环境变量](https://www.java.com/en/download/help/path.xml)，并将其设置到已下载和已提取 Microsoft.Spark.Worker 的目录  。 例如 `c:\bin\Microsoft.Spark.Worker`。

## <a name="clone-the-net-for-apache-spark-github-repo"></a>克隆 .NET for Apache Spark GitHub 存储库

使用以下 [GitBash](https://gitforwindows.org/) 命令将 .NET for Apache Spark 存储库克隆到计算机。

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>编写 .NET for Apache Spark 应用

1. 打开“Visual Studio”并导航到“文件”>“创建新项目”>“控制台应用 (.NET Core)”   。 将应用程序命名为 HelloSpark  。

2. 安装 [Microsoft.Spark NuGet 包](https://www.nuget.org/profiles/spark)。 有关安装 NuGet 包的详细信息，请参阅[安装 NuGet 包的不同方式](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)。

3. 在“解决方案资源管理器”中，打开“Program.cs”并编写以下 C# 代码   ：

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. 生成解决方案。

## <a name="run-your-net-for-apache-spark-app"></a>运行 .NET for Apache Spark 应用

1. 打开“PowerShell”并将目录更改为存储应用的文件夹  。

   ```powershell
   cd <your-app-output-directory>
   ```

2. 创建名为 people.json 且包含以下内容的文件  ：

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. 使用以下 PowerShell 命令运行应用：

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

祝贺你！ 你已成功创建并运行 .NET for Apache Spark 应用。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
>
> * 为 .NET for Apache Spark 准备 Windows 环境
> * 下载 Microsoft.Spark.Worker 
> * 生成和运行简单的 .NET for Apache Spark 应用程序

查看资源页以了解详细信息。
> [!div class="nextstepaction"]
> [.NET for Apache Spark 资源](../resources/index.md)
