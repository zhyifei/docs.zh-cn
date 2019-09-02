---
title: 将 .NET for Apache Spark 应用程序部署到 Databricks
description: 了解如何将 .NET for Apache Spark 应用程序部署到 Databricks。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77c2d93ae324b6acbf8fc8dc25cd3e4d1a652f48
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107349"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>将 .NET for Apache Spark 应用程序部署到 Databricks

本教程介绍如何将 .NET for Apache Spark 应用程序部署到 Databricks。

在本教程中，你将了解：

> [!div class="checklist"]
> - 准备 Microsoft.Spark.Worker
> - 发布 Spark .NET 应用
> - 将应用部署到 Databricks
> - 运行你的应用

## <a name="prerequisites"></a>系统必备

开始之前，请执行以下操作：

- 下载 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)。
- 将 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 下载到本地计算机。 这是稍后用于将 .NET for Apache Spark 依赖文件复制到 Spark 群集的工作器节点的帮助程序脚本。

## <a name="prepare-worker-dependencies"></a>准备辅助角色依赖项

Microsoft.Spark.Worker 是后端组件，位于 Spark 群集的单个工作器节点上  。 想要执行 C# UDF（用户定义的函数），Spark 需要了解如何启动 .NET CLR 以执行 UDF。 Microsoft.Spark.Worker 向 Spark 提供启用此功能的类集合  。

1. 选择要在群集上部署的 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 版本。

   例如，如果需要使用 `netcoreapp2.1` 的 `.NET for Apache Spark v0.1.0`，则下载 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)。

2. 将 `Microsoft.Spark.Worker.<release>.tar.gz` 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 上传到群集具有访问权限的分布式文件系统（如 DBFS）。

## <a name="prepare-your-net-for-apache-spark-app"></a>准备 .NET for Apache Spark 应用

1. 按照[入门](get-started.md)教程来生成应用。

2. 发布独立的 Spark .NET 应用。

   可在 Linux 上运行以下命令。

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. 为已发布的文件生成 `<your app>.zip`。

   可使用 `zip` 在 Linux 上运行以下命令。

   ```bash
   zip -r <your app>.zip .
   ```

4. 将以下内容上传到群集具有访问权限的分布式文件系统（如 DBFS）：

   - `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`：此 jar 作为 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 包的一部分包含在内，并且并置在应用的生成输出目录中。
   - `<your app>.zip`
   - 要放在每个执行程序的工作目录中的文件（如每位工作人员都可以访问的依赖文件或公共数据）或程序集（如包含应用所依赖的用户定义的函数或库的 DLL）。

## <a name="deploy-to-databricks"></a>部署到 Databricks

[Databricks](https://databricks.com) 是一个使用 Apache Spark 提供基于云的大数据处理的平台。

> [!Note] 
> [Azure Databricks](https://azure.microsoft.com/services/databricks/) 和 [AWS Databricks](https://databricks.com/aws) 都基于 Linux。 因此，如果要将应用部署到 Databricks，请确保应用与 .NET Standard 兼容，并且使用 [.NET Core 编译器](https://dotnet.microsoft.com/download)编译应用。

通过 Databricks，可以将 .NET for Apache Spark 应用提交到现有的有效群集，或在每次启动作业时创建新群集。 这就需要先安装 Microsoft.Spark.Worker  再提交 .NET for Apache Spark 应用。

### <a name="deploy-microsoftsparkworker"></a>部署 Microsoft.Spark.Worker

对于群集，此步骤只需执行一次。

1. 将 [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) 下载到本地计算机。

2. 将 db-init.sh 修改为指向要下载并安装在群集上的 Microsoft.Spark.Worker 版本   。

3. 安装 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)。

4. [设置 Databricks CLI 的身份验证](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication)详细信息。

5. 使用以下命令将文件上传到 Databricks 群集：

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. 转到该 Databricks 工作区。 选择左侧菜单的“群集”，然后选择“创建群集”   。

7. 正确配置群集之后，设置“Init 脚本”并创建群集  。

   ![脚本操作图像](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>运行你的应用 

可使用 `set JAR` 或 `spark-submit` 将作业提交到 Databricks。

### <a name="use-set-jar"></a>使用 Set JAR

通过 [Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job)，可将作业提交到现有的有效群集。

#### <a name="one-time-setup"></a>一次性设置

1. 转到 Databricks 群集并选择左侧菜单的“作业”  。 然后选择“Set JAR”  。

2. 上传正确的 `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` 文件。

3. 正确设置参数。

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. 将“群集”配置为指向上一部分中为其创建“Init 脚本”的现有群集   。

#### <a name="publish-and-run-your-app"></a>发布并运行应用

1. 使用 [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) 将应用程序上传到 Databricks 群集。

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. 只有当应用程序集（例如包含用户定义的函数及其依赖项的 DLL）需要放置在每个 Microsoft.Spark.Worker 的工作目录中时，才需要执行此步骤  。

   - 将应用程序集上传到 Databricks 群集
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - 取消评论并将 [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 中的应用依赖项部分修改为指向应用依赖项路径，并上传到 Databricks 群集。
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - 重启群集。

3. 在 Databricks 工作区中转到 Databricks 群集。 在“作业”下，选择作业，然后选择“立即运行”以运行作业   。

### <a name="use-spark-submit"></a>使用 spark-submit

使用 [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 命令，可将作业提交到新群集。

1. [创建作业](https://docs.databricks.com/user-guide/jobs.html)并选择“配置 spark-submit”  。

2. 使用以下参数配置 `spark-submit`：

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. 在 Databricks 工作区中转到 Databricks 群集。 在“作业”下，选择作业，然后选择“立即运行”以运行作业   。

## <a name="next-steps"></a>后续步骤

在本教程中，你已将 .NET for Apache Spark 应用程序部署到 Databricks。 要了解有关 Databricks 的详细信息，请继续阅读 Azure Databricks 文档。

> [!div class="nextstepaction"]
> [Azure Databricks 文档](https://docs.microsoft.com/azure/azure-databricks/)
