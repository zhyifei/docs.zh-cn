---
title: 将 .NET for Apache Spark 应用程序部署到 Azure HDInsight
description: 了解如何将 .NET for Apache Spark 应用程序部署到 HDInsight。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 81d1af1fd4e3329c4a289eea388edf8af57d7c4e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70243951"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="23f3d-103">将 .NET for Apache Spark 应用程序部署到 Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="23f3d-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="23f3d-104">本教程介绍如何将 .NET for Apache Spark 应用程序部署到 Azure HDInsight。</span><span class="sxs-lookup"><span data-stu-id="23f3d-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="23f3d-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="23f3d-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="23f3d-106">准备 Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="23f3d-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="23f3d-107">发布 Spark .NET 应用</span><span class="sxs-lookup"><span data-stu-id="23f3d-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="23f3d-108">将应用部署到 Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="23f3d-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="23f3d-109">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="23f3d-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23f3d-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="23f3d-110">Prerequisites</span></span>

<span data-ttu-id="23f3d-111">开始之前，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="23f3d-111">Before you start, do the following:</span></span>

* <span data-ttu-id="23f3d-112">下载 [Azure 存储资源管理器](https://azure.microsoft.com/features/storage-explorer/)。</span><span class="sxs-lookup"><span data-stu-id="23f3d-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="23f3d-113">将 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="23f3d-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="23f3d-114">这是稍后用于将 .NET for Apache Spark 依赖文件复制到 Spark 群集的工作器节点的帮助程序脚本。</span><span class="sxs-lookup"><span data-stu-id="23f3d-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="23f3d-115">准备辅助角色依赖项</span><span class="sxs-lookup"><span data-stu-id="23f3d-115">Prepare worker dependencies</span></span>

<span data-ttu-id="23f3d-116">Microsoft.Spark.Worker 是后端组件，位于 Spark 群集的单个工作器节点上  。</span><span class="sxs-lookup"><span data-stu-id="23f3d-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="23f3d-117">想要执行 C# UDF（用户定义的函数），Spark 需要了解如何启动 .NET CLR 以执行 UDF。</span><span class="sxs-lookup"><span data-stu-id="23f3d-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="23f3d-118">Microsoft.Spark.Worker 向 Spark 提供启用此功能的类集合  。</span><span class="sxs-lookup"><span data-stu-id="23f3d-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="23f3d-119">选择要在群集上部署的 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 版本。</span><span class="sxs-lookup"><span data-stu-id="23f3d-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="23f3d-120">例如，如果需要使用 `netcoreapp2.1` 的 `.NET for Apache Spark v0.1.0`，则下载 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)。</span><span class="sxs-lookup"><span data-stu-id="23f3d-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="23f3d-121">将 `Microsoft.Spark.Worker.<release>.tar.gz` 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 上传到群集具有访问权限的分布式文件系统（如 HDFS、WASB、ADLS）。</span><span class="sxs-lookup"><span data-stu-id="23f3d-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="23f3d-122">准备 .NET for Apache Spark 应用</span><span class="sxs-lookup"><span data-stu-id="23f3d-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="23f3d-123">按照[入门](get-started.md)教程来生成应用。</span><span class="sxs-lookup"><span data-stu-id="23f3d-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="23f3d-124">发布独立的 Spark .NET 应用。</span><span class="sxs-lookup"><span data-stu-id="23f3d-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="23f3d-125">可在 Linux 上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="23f3d-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="23f3d-126">为已发布的文件生成 `<your app>.zip`。</span><span class="sxs-lookup"><span data-stu-id="23f3d-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="23f3d-127">可使用 `zip` 在 Linux 上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="23f3d-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="23f3d-128">将以下内容上传到群集具有访问权限的分布式文件系统（如 HDFS、WASB、ADLS）：</span><span class="sxs-lookup"><span data-stu-id="23f3d-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="23f3d-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`：此 jar 作为 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 包的一部分包含在内，并且并置在应用的生成输出目录中。</span><span class="sxs-lookup"><span data-stu-id="23f3d-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="23f3d-130">要放在每个执行程序的工作目录中的文件（如每位工作人员都可以访问的依赖文件或公共数据）或程序集（如包含 `app` 所依赖的用户定义的函数或库的 DLL）。</span><span class="sxs-lookup"><span data-stu-id="23f3d-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="23f3d-131">部署到 Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="23f3d-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="23f3d-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) 是允许用户在 Azure 中启动和配置 Spark 群集的云中 Apache Spark 的 Microsoft 实现。</span><span class="sxs-lookup"><span data-stu-id="23f3d-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="23f3d-133">可以使用 HDInsight Spark 群集来处理存储在 [Azure 存储](https://azure.microsoft.com/services/storage/)或 [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2) 中的数据。</span><span class="sxs-lookup"><span data-stu-id="23f3d-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="23f3d-134">Azure HDInsight Spark 基于 Linux。</span><span class="sxs-lookup"><span data-stu-id="23f3d-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="23f3d-135">如果要将应用部署到 Azure HDInsight Spark，请确保应用与 .NET Standard 兼容，并且使用 [.NET Core 编译器](https://dotnet.microsoft.com/download)编译应用。</span><span class="sxs-lookup"><span data-stu-id="23f3d-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="23f3d-136">部署 Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="23f3d-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="23f3d-137">对于群集，此步骤只需执行一次。</span><span class="sxs-lookup"><span data-stu-id="23f3d-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="23f3d-138">使用 [HDInsight 脚本操作](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)运行群集上的 `install-worker.sh`。</span><span class="sxs-lookup"><span data-stu-id="23f3d-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="23f3d-139">设置</span><span class="sxs-lookup"><span data-stu-id="23f3d-139">Setting</span></span>|<span data-ttu-id="23f3d-140">值</span><span class="sxs-lookup"><span data-stu-id="23f3d-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="23f3d-141">脚本类型</span><span class="sxs-lookup"><span data-stu-id="23f3d-141">Script type</span></span>|<span data-ttu-id="23f3d-142">自定义</span><span class="sxs-lookup"><span data-stu-id="23f3d-142">Custom</span></span>|
|<span data-ttu-id="23f3d-143">name</span><span class="sxs-lookup"><span data-stu-id="23f3d-143">Name</span></span>|<span data-ttu-id="23f3d-144">安装 Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="23f3d-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="23f3d-145">Bash 脚本 URI</span><span class="sxs-lookup"><span data-stu-id="23f3d-145">Bash script URI</span></span>|<span data-ttu-id="23f3d-146">向其上传 `install-worker.sh` 的 URI。</span><span class="sxs-lookup"><span data-stu-id="23f3d-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="23f3d-147">例如，`abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="23f3d-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="23f3d-148">节点类型</span><span class="sxs-lookup"><span data-stu-id="23f3d-148">Node type(s)</span></span>|<span data-ttu-id="23f3d-149">辅助角色</span><span class="sxs-lookup"><span data-stu-id="23f3d-149">Worker</span></span>|
|<span data-ttu-id="23f3d-150">参数</span><span class="sxs-lookup"><span data-stu-id="23f3d-150">Parameters</span></span>|<span data-ttu-id="23f3d-151">`install-worker.sh` 的参数。</span><span class="sxs-lookup"><span data-stu-id="23f3d-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="23f3d-152">例如，如果已将 `install-worker.sh` 上传到 Azure Data Lake Gen 2，那么它将为 `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`。</span><span class="sxs-lookup"><span data-stu-id="23f3d-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![脚本操作图像](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="23f3d-154">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="23f3d-154">Run your app</span></span>

<span data-ttu-id="23f3d-155">可以使用 `spark-submit` 或 Apache Livy 将作业提交到 Azure HDInsight。</span><span class="sxs-lookup"><span data-stu-id="23f3d-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="23f3d-156">使用 spark-submit</span><span class="sxs-lookup"><span data-stu-id="23f3d-156">Use spark-submit</span></span>

<span data-ttu-id="23f3d-157">可以使用 [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 命令将 .NET for Apache Spark 作业提交到 Azure HDInsight。</span><span class="sxs-lookup"><span data-stu-id="23f3d-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="23f3d-158">群集中的某个头节点的 `ssh`。</span><span class="sxs-lookup"><span data-stu-id="23f3d-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="23f3d-159">运行 `spark-submit`：</span><span class="sxs-lookup"><span data-stu-id="23f3d-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="23f3d-160">使用 Apache Livy</span><span class="sxs-lookup"><span data-stu-id="23f3d-160">Use Apache Livy</span></span>

<span data-ttu-id="23f3d-161">可以使用 [Apache Livy](https://livy.incubator.apache.org/)（即 Apache Spark REST API）将 .NET for Apache Spark 作业提交到 Azure HDInsight Spark 群集。</span><span class="sxs-lookup"><span data-stu-id="23f3d-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="23f3d-162">有关详细信息，请参阅[使用 Apache Livy 提交远程作业](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface)。</span><span class="sxs-lookup"><span data-stu-id="23f3d-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="23f3d-163">可使用 `curl` 在 Linux 上运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="23f3d-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="23f3d-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23f3d-164">Next steps</span></span>

<span data-ttu-id="23f3d-165">在本教程中，你已将 .NET for Apache Spark 应用程序部署到 Azure HDInsight。</span><span class="sxs-lookup"><span data-stu-id="23f3d-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="23f3d-166">要了解有关 HDInsight 的详细信息，请继续阅读 Azure HDInsight 文档。</span><span class="sxs-lookup"><span data-stu-id="23f3d-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="23f3d-167">Azure HDInsight 文档</span><span class="sxs-lookup"><span data-stu-id="23f3d-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
