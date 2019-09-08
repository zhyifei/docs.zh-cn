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
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>将 .NET for Apache Spark 应用程序部署到 Azure HDInsight

本教程介绍如何将 .NET for Apache Spark 应用程序部署到 Azure HDInsight。

在本教程中，你将了解：

> [!div class="checklist"]
> * 准备 Microsoft.Spark.Worker
> * 发布 Spark .NET 应用
> * 将应用部署到 Azure HDInsight
> * 运行你的应用

## <a name="prerequisites"></a>系统必备

开始之前，请执行以下操作：

* 下载 [Azure 存储资源管理器](https://azure.microsoft.com/features/storage-explorer/)。
* 将 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 下载到本地计算机。 这是稍后用于将 .NET for Apache Spark 依赖文件复制到 Spark 群集的工作器节点的帮助程序脚本。

## <a name="prepare-worker-dependencies"></a>准备辅助角色依赖项

Microsoft.Spark.Worker 是后端组件，位于 Spark 群集的单个工作器节点上  。 想要执行 C# UDF（用户定义的函数），Spark 需要了解如何启动 .NET CLR 以执行 UDF。 Microsoft.Spark.Worker 向 Spark 提供启用此功能的类集合  。

1. 选择要在群集上部署的 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp 版本。

   例如，如果需要使用 `netcoreapp2.1` 的 `.NET for Apache Spark v0.1.0`，则下载 [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)。

2. 将 `Microsoft.Spark.Worker.<release>.tar.gz` 和 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 上传到群集具有访问权限的分布式文件系统（如 HDFS、WASB、ADLS）。

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

4. 将以下内容上传到群集具有访问权限的分布式文件系统（如 HDFS、WASB、ADLS）：

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`：此 jar 作为 [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 包的一部分包含在内，并且并置在应用的生成输出目录中。
   * `<your app>.zip`
   * 要放在每个执行程序的工作目录中的文件（如每位工作人员都可以访问的依赖文件或公共数据）或程序集（如包含 `app` 所依赖的用户定义的函数或库的 DLL）。

## <a name="deploy-to-azure-hdinsight-spark"></a>部署到 Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) 是允许用户在 Azure 中启动和配置 Spark 群集的云中 Apache Spark 的 Microsoft 实现。 可以使用 HDInsight Spark 群集来处理存储在 [Azure 存储](https://azure.microsoft.com/services/storage/)或 [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2) 中的数据。

> [!NOTE]
> Azure HDInsight Spark 基于 Linux。 如果要将应用部署到 Azure HDInsight Spark，请确保应用与 .NET Standard 兼容，并且使用 [.NET Core 编译器](https://dotnet.microsoft.com/download)编译应用。

### <a name="deploy-microsoftsparkworker"></a>部署 Microsoft.Spark.Worker

对于群集，此步骤只需执行一次。

使用 [HDInsight 脚本操作](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)运行群集上的 `install-worker.sh`。

|设置|值|
|-------|-----|
|脚本类型|自定义|
|name|安装 Microsoft.Spark.Worker|
|Bash 脚本 URI|向其上传 `install-worker.sh` 的 URI。 例如，`abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|节点类型|辅助角色|
|参数|`install-worker.sh` 的参数。 例如，如果已将 `install-worker.sh` 上传到 Azure Data Lake Gen 2，那么它将为 `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`。|

![脚本操作图像](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>运行你的应用

可以使用 `spark-submit` 或 Apache Livy 将作业提交到 Azure HDInsight。

### <a name="use-spark-submit"></a>使用 spark-submit

可以使用 [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) 命令将 .NET for Apache Spark 作业提交到 Azure HDInsight。
 
1. 群集中的某个头节点的 `ssh`。

1. 运行 `spark-submit`：

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>使用 Apache Livy

可以使用 [Apache Livy](https://livy.incubator.apache.org/)（即 Apache Spark REST API）将 .NET for Apache Spark 作业提交到 Azure HDInsight Spark 群集。 有关详细信息，请参阅[使用 Apache Livy 提交远程作业](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface)。

可使用 `curl` 在 Linux 上运行以下命令：

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

## <a name="next-steps"></a>后续步骤

在本教程中，你已将 .NET for Apache Spark 应用程序部署到 Azure HDInsight。 要了解有关 HDInsight 的详细信息，请继续阅读 Azure HDInsight 文档。

> [!div class="nextstepaction"]
> [Azure HDInsight 文档](https://docs.microsoft.com/azure/hdinsight/)
