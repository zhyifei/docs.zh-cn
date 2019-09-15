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
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="13bb5-103">教程：.NET for Apache Spark 入门</span><span class="sxs-lookup"><span data-stu-id="13bb5-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="13bb5-104">本教程介绍如何在 Windows 上使用 .NET Core 运行 .NET for Apache Spark 应用。</span><span class="sxs-lookup"><span data-stu-id="13bb5-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="13bb5-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="13bb5-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="13bb5-106">为 .NET for Apache Spark 准备 Windows 环境</span><span class="sxs-lookup"><span data-stu-id="13bb5-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="13bb5-107">下载 Microsoft.Spark.Worker </span><span class="sxs-lookup"><span data-stu-id="13bb5-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="13bb5-108">生成和运行简单的 .NET for Apache Spark 应用程序</span><span class="sxs-lookup"><span data-stu-id="13bb5-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="13bb5-109">准备环境</span><span class="sxs-lookup"><span data-stu-id="13bb5-109">Prepare your environment</span></span>

<span data-ttu-id="13bb5-110">开始之前，请确保可以从命令行运行 `dotnet`、`java`、`mvn`、`spark-shell`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="13bb5-111">如果环境已准备好，则可跳至下一部分。</span><span class="sxs-lookup"><span data-stu-id="13bb5-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="13bb5-112">如果无法运行任何或所有命令，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="13bb5-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="13bb5-113">下载并安装 [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="13bb5-114">安装 SDK 会将 `dotnet` 工具链添加到路径。</span><span class="sxs-lookup"><span data-stu-id="13bb5-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="13bb5-115">使用 PowerShell 命令 `dotnet --version` 以验证安装。</span><span class="sxs-lookup"><span data-stu-id="13bb5-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="13bb5-116">安装包含最新更新的 [Visual Studio 2017](https://www.visualstudio.com/downloads/) 或 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="13bb5-117">可以使用 Community、Professional 或 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="13bb5-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="13bb5-118">Community 版本免费。</span><span class="sxs-lookup"><span data-stu-id="13bb5-118">The Community version is free.</span></span>

   <span data-ttu-id="13bb5-119">在安装过程中选择以下工作负载：</span><span class="sxs-lookup"><span data-stu-id="13bb5-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="13bb5-120">.NET 桌面开发</span><span class="sxs-lookup"><span data-stu-id="13bb5-120">.NET desktop development</span></span>
          * <span data-ttu-id="13bb5-121">所有必需的组件</span><span class="sxs-lookup"><span data-stu-id="13bb5-121">All required components</span></span>
          * <span data-ttu-id="13bb5-122">.NET Framework 4.6.1 开发工具</span><span class="sxs-lookup"><span data-stu-id="13bb5-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="13bb5-123">.NET Core 跨平台开发</span><span class="sxs-lookup"><span data-stu-id="13bb5-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="13bb5-124">所有必需的组件</span><span class="sxs-lookup"><span data-stu-id="13bb5-124">All required components</span></span>

3. <span data-ttu-id="13bb5-125">安装 [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="13bb5-126">选择适用于操作系统的合适版本。</span><span class="sxs-lookup"><span data-stu-id="13bb5-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="13bb5-127">例如，为 Windows x64 计算机选择 jdk-8u201-windows-x64.exe  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="13bb5-128">使用 PowerShell 命令 `java -version` 以验证安装。</span><span class="sxs-lookup"><span data-stu-id="13bb5-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="13bb5-129">安装 [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="13bb5-130">下载 [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="13bb5-131">提取到本地目录。</span><span class="sxs-lookup"><span data-stu-id="13bb5-131">Extract to a local directory.</span></span> <span data-ttu-id="13bb5-132">例如 `c:\bin\apache-maven-3.6.0\`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="13bb5-133">将 Apache Maven 添加到 [PATH 环境变量](https://www.java.com/en/download/help/path.xml)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="13bb5-134">如果已提取到 `c:\bin\apache-maven-3.6.0\`，则需将 `c:\bin\apache-maven-3.6.0\bin` 添加到路径。</span><span class="sxs-lookup"><span data-stu-id="13bb5-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="13bb5-135">使用 PowerShell 命令 `mvn -version` 以验证安装。</span><span class="sxs-lookup"><span data-stu-id="13bb5-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="13bb5-136">安装 [Apache Spark 2.3+](https://spark.apache.org/downloads.html)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="13bb5-137">不支持 Apache Spark 2.4 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="13bb5-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="13bb5-138">下载 [Apache Spark 2.3+](https://spark.apache.org/downloads.html) 并使用 [7-zip](https://www.7-zip.org/) 或 [WinZip](https://www.winzip.com/) 等工具将其提取到本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="13bb5-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="13bb5-139">例如，可以将其提取到 `c:\bin\spark-2.3.2-bin-hadoop2.7\`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="13bb5-140">将 Apache Spark 添加到 [PATH 环境变量](https://www.java.com/en/download/help/path.xml)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="13bb5-141">如果已提取到 `c:\bin\spark-2.3.2-bin-hadoop2.7\`，则需将 `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` 添加到路径。</span><span class="sxs-lookup"><span data-stu-id="13bb5-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="13bb5-142">添加名为 `SPARK_HOME` 的[新环境变量](https://www.java.com/en/download/help/path.xml)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="13bb5-143">如果已提取到 `C:\bin\spark-2.3.2-bin-hadoop2.7\`，则使用 `C:\bin\spark-2.3.2-bin-hadoop2.7\` 存储变量值  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="13bb5-144">验证是否能够从命令行运行 `spark-shell`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="13bb5-145">设置 [WinUtils](https://github.com/steveloughran/winutils)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="13bb5-146">从 [WinUtils 存储库](https://github.com/steveloughran/winutils)下载 winutils.exe 二进制文件  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="13bb5-147">选择编译 Spark 发行版时使用的 Hadoop 版本。</span><span class="sxs-lookup"><span data-stu-id="13bb5-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="13bb5-148">例如，将 hadoop-2.7.1 用于 Spark 2.3.2   。</span><span class="sxs-lookup"><span data-stu-id="13bb5-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="13bb5-149">Hadoop 版本批注在 Spark 安装文件夹名称的末尾。</span><span class="sxs-lookup"><span data-stu-id="13bb5-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="13bb5-150">将 winutils.exe 二进制文件保存到所选的目录  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="13bb5-151">例如 `c:\hadoop\bin`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="13bb5-152">设置 `HADOOP_HOME` 以反映包含不带 `bin` 的 winutils.exe 的目录  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="13bb5-153">例如 `c:\hadoop`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="13bb5-154">设置 PATH 环境变量以包含 `%HADOOP_HOME%\bin`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="13bb5-155">再次确认可以从命令行运行 `dotnet`、`java`、`mvn`、`spark-shell`，然后再转到下一部分。</span><span class="sxs-lookup"><span data-stu-id="13bb5-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="13bb5-156">下载 Microsoft.Spark.Worker 版本</span><span class="sxs-lookup"><span data-stu-id="13bb5-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="13bb5-157">从本地计算机的 .NET for Apache Spark GitHub 版本页下载 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="13bb5-158">例如，可以将其下载到路径 `c:\bin\Microsoft.Spark.Worker\`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="13bb5-159">创建名为 `DotnetWorkerPath` 的[新环境变量](https://www.java.com/en/download/help/path.xml)，并将其设置到已下载和已提取 Microsoft.Spark.Worker 的目录  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="13bb5-160">例如 `c:\bin\Microsoft.Spark.Worker`。</span><span class="sxs-lookup"><span data-stu-id="13bb5-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="13bb5-161">克隆 .NET for Apache Spark GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="13bb5-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="13bb5-162">使用以下 [GitBash](https://gitforwindows.org/) 命令将 .NET for Apache Spark 存储库克隆到计算机。</span><span class="sxs-lookup"><span data-stu-id="13bb5-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="13bb5-163">编写 .NET for Apache Spark 应用</span><span class="sxs-lookup"><span data-stu-id="13bb5-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="13bb5-164">打开“Visual Studio”并导航到“文件”>“创建新项目”>“控制台应用 (.NET Core)”   。</span><span class="sxs-lookup"><span data-stu-id="13bb5-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="13bb5-165">将应用程序命名为 HelloSpark  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="13bb5-166">安装 [Microsoft.Spark NuGet 包](https://www.nuget.org/profiles/spark)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="13bb5-167">有关安装 NuGet 包的详细信息，请参阅[安装 NuGet 包的不同方式](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)。</span><span class="sxs-lookup"><span data-stu-id="13bb5-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="13bb5-168">在“解决方案资源管理器”中，打开“Program.cs”并编写以下 C# 代码   ：</span><span class="sxs-lookup"><span data-stu-id="13bb5-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="13bb5-169">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="13bb5-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="13bb5-170">运行 .NET for Apache Spark 应用</span><span class="sxs-lookup"><span data-stu-id="13bb5-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="13bb5-171">打开“PowerShell”并将目录更改为存储应用的文件夹  。</span><span class="sxs-lookup"><span data-stu-id="13bb5-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="13bb5-172">创建名为 people.json 且包含以下内容的文件  ：</span><span class="sxs-lookup"><span data-stu-id="13bb5-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="13bb5-173">使用以下 PowerShell 命令运行应用：</span><span class="sxs-lookup"><span data-stu-id="13bb5-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="13bb5-174">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="13bb5-174">Congratulations!</span></span> <span data-ttu-id="13bb5-175">你已成功创建并运行 .NET for Apache Spark 应用。</span><span class="sxs-lookup"><span data-stu-id="13bb5-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13bb5-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="13bb5-176">Next steps</span></span>

<span data-ttu-id="13bb5-177">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="13bb5-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="13bb5-178">为 .NET for Apache Spark 准备 Windows 环境</span><span class="sxs-lookup"><span data-stu-id="13bb5-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="13bb5-179">下载 Microsoft.Spark.Worker </span><span class="sxs-lookup"><span data-stu-id="13bb5-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="13bb5-180">生成和运行简单的 .NET for Apache Spark 应用程序</span><span class="sxs-lookup"><span data-stu-id="13bb5-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="13bb5-181">查看资源页以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="13bb5-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="13bb5-182">.NET for Apache Spark 资源</span><span class="sxs-lookup"><span data-stu-id="13bb5-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
