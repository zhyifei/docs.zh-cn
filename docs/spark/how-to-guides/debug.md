---
title: 在 Windows 上部署 .NET for Apache Spark 应用程序
description: 了解如何在 Windows 上部署 .NET for Apache Spark 应用程序。
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281533"
---
# <a name="debug-a-net-for-apache-spark-application"></a>部署 .NET for Apache Spark 应用程序

此操作说明提供需要运行的命令，以在 Windows 上调试 .NET for Apache Spark 应用程序和 Scala 代码。

## <a name="debug-your-application"></a>调试应用程序

打开新的命令提示符窗口，运行以下内容：

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

运行命令时，会看到以下输出：

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

在此调试模式中，`DotnetRunner` 不启动 .NET 应用程序，但它会等待应用程序连接。 将此命令提示符窗口保持打开状态。

现在可以使用任何调试程序来运行 .NET 应用程序，以调试应用程序。

## <a name="debug-scala-code"></a>调试 Scala 代码

如果需要调试 Scala 端代码（如 `DotnetRunner` 或 `DotnetBackendHandler`），请运行以下命令：

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

运行命令后，使用 [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) 将调试程序附加到正在运行的进程。

## <a name="next-steps"></a>后续步骤

* [.NET for Apache Spark 入门](../tutorials/get-started.md)
* [将 .NET for Apache Spark 应用程序部署到 Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [将 .NET for Apache Spark 应用程序部署到 Databricks](../tutorials/databricks-deployment.md)
* [将 .NET for Apache Spark 应用程序部署到 Amazon EMR Spark](../tutorials/amazon-emr-spark-deployment.md)
