---
title: 将 .NET for Apache Spark 应用程序部署到 Databricks
description: 了解如何将 .NET for Apache Spark 应用程序部署到 Databricks。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: ca9e93a413622c84325ca9fc8bac17268b990c5a
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "69576964"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="bf816-103">将 .NET for Apache Spark 应用程序部署到 Databricks</span><span class="sxs-lookup"><span data-stu-id="bf816-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="bf816-104">本教程介绍如何将 .NET for Apache Spark 应用程序部署到 Databricks。</span><span class="sxs-lookup"><span data-stu-id="bf816-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="bf816-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="bf816-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bf816-106">准备 Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="bf816-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="bf816-107">发布 Spark .NET 应用</span><span class="sxs-lookup"><span data-stu-id="bf816-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="bf816-108">将应用部署到 Databricks</span><span class="sxs-lookup"><span data-stu-id="bf816-108">Deploy your app to Databricks</span></span>
> * <span data-ttu-id="bf816-109">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="bf816-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf816-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="bf816-110">Prerequisites</span></span>

<span data-ttu-id="bf816-111">开始之前，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf816-111">Before you start, do the following:</span></span>

* <span data-ttu-id="bf816-112">下载 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)。</span><span class="sxs-lookup"><span data-stu-id="bf816-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
* <span data-ttu-id="bf816-113">将 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="bf816-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="bf816-114">这是稍后用于将 .NET for Apache Spark 依赖文件复制到 Spark 群集的工作器节点的帮助程序脚本。</span><span class="sxs-lookup"><span data-stu-id="bf816-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="bf816-115">准备辅助角色依赖项</span><span class="sxs-lookup"><span data-stu-id="bf816-115">Prepare worker dependencies</span></span>

<span data-ttu-id="bf816-116">Microsoft.Spark.Worker 是后端组件，位于 Spark 群集的单个工作器节点上  。</span><span class="sxs-lookup"><span data-stu-id="bf816-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="bf816-117">想要执行 C# UDF（用户定义的函数），Spark 需要了解如何启动 .NET CLR 以执行 UDF。</span><span class="sxs-lookup"><span data-stu-id="bf816-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="bf816-118">Microsoft.Spark.Worker 向 Spark 提供启用此功能的类集合  。</span><span class="sxs-lookup"><span data-stu-id="bf816-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="bf816-119">选择要在群集上部署的 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 版本。</span><span class="sxs-lookup"><span data-stu-id="bf816-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="bf816-120">例如，如果需要使用 `netcoreapp2.1` 的 `.NET for Apache Spark v0.1.0`，则下载 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)。</span><span class="sxs-lookup"><span data-stu-id="bf816-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="bf816-121">将 `Microsoft.Spark.Worker.<release>.tar.gz` 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 上传到群集具有访问权限的分布式文件系统（如 DBFS）。</span><span class="sxs-lookup"><span data-stu-id="bf816-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="bf816-122">准备 .NET for Apache Spark 应用</span><span class="sxs-lookup"><span data-stu-id="bf816-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="bf816-123">按照[入门](get-started.md)教程来生成应用。</span><span class="sxs-lookup"><span data-stu-id="bf816-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="bf816-124">发布独立的 Spark .NET 应用。</span><span class="sxs-lookup"><span data-stu-id="bf816-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="bf816-125">可在 Linux 上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="bf816-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="bf816-126">为已发布的文件生成 `<your app>.zip`。</span><span class="sxs-lookup"><span data-stu-id="bf816-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="bf816-127">可使用 `zip` 在 Linux 上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="bf816-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="bf816-128">将以下内容上传到群集具有访问权限的分布式文件系统（如 DBFS）：</span><span class="sxs-lookup"><span data-stu-id="bf816-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   * <span data-ttu-id="bf816-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`：此 jar 作为 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 包的一部分包含在内，并且并置在应用的生成输出目录中。</span><span class="sxs-lookup"><span data-stu-id="bf816-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="bf816-130">要放在每个执行程序的工作目录中的文件（如每位工作人员都可以访问的依赖文件或公共数据）或程序集（如包含应用所依赖的用户定义的函数或库的 DLL）。</span><span class="sxs-lookup"><span data-stu-id="bf816-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="bf816-131">部署到 Databricks</span><span class="sxs-lookup"><span data-stu-id="bf816-131">Deploy to Databricks</span></span>

<span data-ttu-id="bf816-132">[Databricks](https://databricks.com) 是一个使用 Apache Spark 提供基于云的大数据处理的平台。</span><span class="sxs-lookup"><span data-stu-id="bf816-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="bf816-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) 和 [AWS Databricks](https://databricks.com/aws) 都基于 Linux。</span><span class="sxs-lookup"><span data-stu-id="bf816-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="bf816-134">因此，如果要将应用部署到 Databricks，请确保应用与 .NET Standard 兼容，并且使用 [.NET Core 编译器](https://dotnet.microsoft.com/download)编译应用。</span><span class="sxs-lookup"><span data-stu-id="bf816-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="bf816-135">通过 Databricks，可以将 .NET for Apache Spark 应用提交到现有的有效群集，或在每次启动作业时创建新群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="bf816-136">这就需要先安装 Microsoft.Spark.Worker  再提交 .NET for Apache Spark 应用。</span><span class="sxs-lookup"><span data-stu-id="bf816-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="bf816-137">部署 Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="bf816-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="bf816-138">对于群集，此步骤只需执行一次。</span><span class="sxs-lookup"><span data-stu-id="bf816-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="bf816-139">将 [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) 下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="bf816-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="bf816-140">将 db-init.sh 修改为指向要下载并安装在群集上的 Microsoft.Spark.Worker 版本   。</span><span class="sxs-lookup"><span data-stu-id="bf816-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="bf816-141">安装 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)。</span><span class="sxs-lookup"><span data-stu-id="bf816-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="bf816-142">[设置 Databricks CLI 的身份验证](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication)详细信息。</span><span class="sxs-lookup"><span data-stu-id="bf816-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="bf816-143">使用以下命令将文件上传到 Databricks 群集：</span><span class="sxs-lookup"><span data-stu-id="bf816-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="bf816-144">转到该 Databricks 工作区。</span><span class="sxs-lookup"><span data-stu-id="bf816-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="bf816-145">选择左侧菜单的“群集”，然后选择“创建群集”   。</span><span class="sxs-lookup"><span data-stu-id="bf816-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="bf816-146">正确配置群集之后，设置“Init 脚本”并创建群集  。</span><span class="sxs-lookup"><span data-stu-id="bf816-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![脚本操作图像](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="bf816-148">运行你的应用</span><span class="sxs-lookup"><span data-stu-id="bf816-148">Run your app</span></span> 

<span data-ttu-id="bf816-149">可使用 `set JAR` 或 `spark-submit` 将作业提交到 Databricks。</span><span class="sxs-lookup"><span data-stu-id="bf816-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="bf816-150">使用 Set JAR</span><span class="sxs-lookup"><span data-stu-id="bf816-150">Use Set JAR</span></span>

<span data-ttu-id="bf816-151">通过 [Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job)，可将作业提交到现有的有效群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="bf816-152">一次性设置</span><span class="sxs-lookup"><span data-stu-id="bf816-152">One-time setup</span></span>

1. <span data-ttu-id="bf816-153">转到 Databricks 群集并选择左侧菜单的“作业”  。</span><span class="sxs-lookup"><span data-stu-id="bf816-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="bf816-154">然后选择“Set JAR”  。</span><span class="sxs-lookup"><span data-stu-id="bf816-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="bf816-155">上传正确的 `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` 文件。</span><span class="sxs-lookup"><span data-stu-id="bf816-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="bf816-156">正确设置参数。</span><span class="sxs-lookup"><span data-stu-id="bf816-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="bf816-157">将“群集”配置为指向上一部分中为其创建“Init 脚本”的现有群集   。</span><span class="sxs-lookup"><span data-stu-id="bf816-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="bf816-158">发布并运行应用</span><span class="sxs-lookup"><span data-stu-id="bf816-158">Publish and run your app</span></span>

1. <span data-ttu-id="bf816-159">使用 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) 将应用程序上传到 Databricks 群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="bf816-160">只有当应用程序集（例如包含用户定义的函数及其依赖项的 DLL）需要放置在每个 Microsoft.Spark.Worker 的工作目录中时，才需要执行此步骤  。</span><span class="sxs-lookup"><span data-stu-id="bf816-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="bf816-161">将应用程序集上传到 Databricks 群集</span><span class="sxs-lookup"><span data-stu-id="bf816-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="bf816-162">取消评论并将 [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 中的应用依赖项部分修改为指向应用依赖项路径，并上传到 Databricks 群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="bf816-163">重启群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-163">Restart your cluster.</span></span>

3. <span data-ttu-id="bf816-164">在 Databricks 工作区中转到 Databricks 群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="bf816-165">在“作业”下，选择作业，然后选择“立即运行”以运行作业   。</span><span class="sxs-lookup"><span data-stu-id="bf816-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="bf816-166">使用 spark-submit</span><span class="sxs-lookup"><span data-stu-id="bf816-166">Use spark-submit</span></span>

<span data-ttu-id="bf816-167">使用 [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 命令，可将作业提交到新群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="bf816-168">[创建作业](https://docs.databricks.com/user-guide/jobs.html)并选择“配置 spark-submit”  。</span><span class="sxs-lookup"><span data-stu-id="bf816-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="bf816-169">使用以下参数配置 `spark-submit`：</span><span class="sxs-lookup"><span data-stu-id="bf816-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="bf816-170">在 Databricks 工作区中转到 Databricks 群集。</span><span class="sxs-lookup"><span data-stu-id="bf816-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="bf816-171">在“作业”下，选择作业，然后选择“立即运行”以运行作业   。</span><span class="sxs-lookup"><span data-stu-id="bf816-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf816-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bf816-172">Next steps</span></span>

<span data-ttu-id="bf816-173">在本教程中，你已将 .NET for Apache Spark 应用程序部署到 Databricks。</span><span class="sxs-lookup"><span data-stu-id="bf816-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="bf816-174">要了解有关 Databricks 的详细信息，请继续阅读 Azure Databricks 文档。</span><span class="sxs-lookup"><span data-stu-id="bf816-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf816-175">Azure Databricks 文档</span><span class="sxs-lookup"><span data-stu-id="bf816-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
