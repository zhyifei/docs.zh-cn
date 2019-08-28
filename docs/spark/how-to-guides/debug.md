---
title: 在 Windows 上部署 .NET for Apache Spark 应用程序
description: 了解如何在 Windows 上部署 .NET for Apache Spark 应用程序。
ms.date: 08/15/2019
ms.topic: how-to
ms.custom: mvc
ms.openlocfilehash: 08142bd45c475ddd131053213ebdea5f843fa736
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69667665"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="5bb81-103">部署 .NET for Apache Spark 应用程序</span><span class="sxs-lookup"><span data-stu-id="5bb81-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="5bb81-104">此操作说明提供需要运行的命令，以在 Windows 上调试 .NET for Apache Spark 应用程序和 Scala 代码。</span><span class="sxs-lookup"><span data-stu-id="5bb81-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="5bb81-105">调试应用程序</span><span class="sxs-lookup"><span data-stu-id="5bb81-105">Debug your application</span></span>

<span data-ttu-id="5bb81-106">打开新的命令提示符窗口，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="5bb81-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="5bb81-107">运行命令时，会看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="5bb81-107">When you run the command, you see the following output:</span></span>

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="5bb81-108">在此调试模式中，`DotnetRunner` 不启动 .NET 应用程序，但它会等待应用程序连接。</span><span class="sxs-lookup"><span data-stu-id="5bb81-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="5bb81-109">将此命令提示符窗口保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="5bb81-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="5bb81-110">现在可以使用任何调试程序来运行 .NET 应用程序，以调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="5bb81-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="5bb81-111">调试 Scala 代码</span><span class="sxs-lookup"><span data-stu-id="5bb81-111">Debug Scala code</span></span>

<span data-ttu-id="5bb81-112">如果需要调试 Scala 端代码（如 `DotnetRunner` 或 `DotnetBackendHandler`），请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5bb81-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="5bb81-113">运行命令后，使用 [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) 将调试程序附加到正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="5bb81-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5bb81-114">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5bb81-114">Next steps</span></span>

* [<span data-ttu-id="5bb81-115">.NET for Apache Spark 入门</span><span class="sxs-lookup"><span data-stu-id="5bb81-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="5bb81-116">将 .NET for Apache Spark 应用程序部署到 Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="5bb81-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="5bb81-117">将 .NET for Apache Spark 应用程序部署到 Databricks</span><span class="sxs-lookup"><span data-stu-id="5bb81-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="5bb81-118">将 .NET for Apache Spark 应用程序部署到 Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="5bb81-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)