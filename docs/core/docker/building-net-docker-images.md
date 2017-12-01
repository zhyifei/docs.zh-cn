---
title: "生成 .NET Core Docker 映像"
description: "了解 Docker 映像和 .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>为 .NET Core 应用程序生成 Docker 映像

 在本教程中，我们重点说明如何在 Docker 上使用.NET 核心。 首先，我们探讨不同的 Docker 映像由 Microsoft 和使用情况下维护和提供。 我们然后了解如何构建和 dockerize ASP.NET Core 应用。

在本教程过程中，你学习：
> [!div class="checklist"]
> * 了解有关 Microsoft.NET 核心 Docker 映像 
> * 获取 ASP.NET Core Dockerize 到示例应用程序
> * 本地运行 ASP.NET 示例应用程序
> * 生成并运行该示例使用 Docker 的 Linux 容器
> * 生成并使用用于 Windows 的 Docker 容器运行示例

## <a name="docker-image-optimizations"></a>Docker 映像优化

为开发人员生成 Docker 映像时，侧重于以下三种主要方案：

* 用于开发 .NET Core 应用的映像
* 用于生成 .NET Core 应用的映像
* 用于运行 .NET Core 应用的映像

为什么是三个映像？
当开发、 构建和运行容器化应用程序时，我们具有不同的优先级别。

* **开发：**优先级主要是为了快速循环更改和调试所做的更改的能力。 图像的大小不为重要，而是你可以对代码进行更改并快速查看它们？

* **生成中：**此映像包含将应用程序，其中包括编译器和任何其他依赖项以优化的二进制文件编译所需的一切。  生成映像用于创建你将放入生产映像的资产。 将用于构建映像，持续集成，或在生成环境中。 此方法允许用于编译和生成中生成映像实例应用程序 （具有所有必需的依赖项） 的生成代理。 生成代理只需要了解如何运行此 Docker 映像即可。

* **生产：**速度可以部署和启动你的映像？ 此映像很小，因此从 Docker 注册表到 Docker 主机的网络性能进行了优化。 已准备运行内容，以此实现从 Docker 运行到处理结果的最快时间。 Docker 模型中不需要动态代码编译。 放置在此映像中的内容将限制为运行应用程序所需的二进制文件和内容。

    例如，`dotnet publish`输出包含：

    * 已编译的二进制文件
    * .js 和.css 文件


原因包括`dotnet publish`你生产的映像中的命令输出是保持其最小大小。

一些.NET Core 映像共享不同标记，因此下载最新的标记是相对轻量的过程之间的层。 如果您的计算机上已有较旧版本，此体系结构会降低所需的磁盘空间。

当多个应用程序相同的计算机上使用公共映像时，常见的映像之间共享内存。 图像必须为相同共享。

## <a name="docker-image-variations"></a>Docker 映像变体

若要实现上述目标，我们提供映像下的变体[ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/)。

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) 此映像包含.NET 核心 SDK，其中包含.NET 核心和命令行工具 (CLI)。 此映像将映射到**开发方案**。 此映像用于本地开发、 调试和单元测试。 此映像还可用于**生成**方案。 使用`microsoft/dotnet:sdk`始终为你提供最新版本。

> [!TIP]
> 如果您不确定你的需求，你想要使用`microsoft/dotnet:<version>-sdk`映像。 作为"事实上"图像，它旨在用作 throw 远容器 （装入你的源代码和启动容器启动你的应用程序），并作为基本映像，以生成从其他映像。

* `microsoft/dotnet:<version>-runtime`： 此映像包含.NET 核心 （运行时和库），非常适合运行.NET Core 应用**生产**。

## <a name="alternative-images"></a>备用映像

除了开发、生成和生产的优化方案外，我们还提供了其他映像：

* `microsoft/dotnet:<version>-runtime-deps`:**运行时 deps**映像包含操作系统所有所需的.NET 核心的本机依赖项。 此映像适用[自包含的应用程序](https://docs.microsoft.com/dotnet/core/deploying/index)。

每个变体的最新版本：

* `microsoft/dotnet`或`microsoft/dotnet:latest`（别名 SDK 映像）
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>若要浏览的示例

* [此 ASP.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。 示例适用于 Linux 和 Windows 容器。

* .NET 核心 Docker 演示的最佳做法模式[构建的生产.NET 核心应用程序的 Docker 映像。](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>第一个 ASP.NET 核心 Docker 应用

对于本教程中，可让我们想要 dockerize 应用使用的 ASP.NET 核心 Docker 示例应用程序。 此 ASP.NET 核心 Docker 示例应用程序演示了针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。 示例适用于 Linux 和 Windows 容器。

示例 Dockerfile 创建基于 ASP.NET 核心运行时 Docker 基本映像的 ASP.NET Core 应用程序 Docker 映像。

它使用[Docker 多阶段生成功能](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)到：

* 生成基于容器中的示例**更大**ASP.NET 核心生成 Docker 的基本映像 
* 将最终生成结果复制到 Docker 映像基于**较小**ASP.NET Core Docker 运行时的基本映像

> [!Note]
> 生成映像包含所需的工具，而运行时映像则不生成应用程序。

### <a name="prerequisites"></a>先决条件

若要生成并运行，请安装以下各项：

#### <a name="net-core-20-sdk"></a>.NET 核心 2.0 SDK

* 安装[.NET 核心 SDK 2.0](https://www.microsoft.com/net/core)。

* 如果你尚未，安装最喜欢的代码编辑器中。

> [!TIP]
> 需要安装代码编辑器？ 请尝试[Visual Studio](https://visualstudio.com/downloads)！

#### <a name="installing-docker-client"></a>安装 Docker 客户端

安装[Docker 17.06](https://docs.docker.com/release-notes/docker-ce/)或更高版本的 Docker 客户端。

可以在安装 Docker 客户端：

* Linux 分发

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/)。

#### <a name="installing-git-for-sample-repository"></a>为示例存储库安装 Git

* 安装[git](https://git-scm.com/download)如果你想要克隆存储库。

### <a name="getting-the-sample-application"></a>获取示例应用程序

获取该示例的最简单方法是通过克隆[示例存储库](https://github.com/dotnet/dotnet-docker-samples)使用 git，使用以下说明： 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

你也可以作为.NET 核心 Docker 示例存储库从 zip 下载 （它位于小） 的存储库。

### <a name="run-the-aspnet-app-locally"></a>本地运行 ASP.NET 应用程序

对于引用点，在容器化应用程序之前，请先在本地运行应用程序。

你可以本地生成并运行应用程序使用.NET 核心 2.0 SDK 使用以下命令 （的说明假定存储库的根目录）：

```console
cd aspnetapp
dotnet run
```

在应用程序启动后，请访问**http://localhost:5000/**在 web 浏览器中。

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>生成并运行该示例使用 Docker 的 Linux 容器

你可以生成并运行在 Docker 使用 Linux 容器使用以下命令 （的说明假定存储库的根目录） 中的示例：

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] `docker run` -P 地图端口 5000 上你本地计算机添加到端口 80 容器中的自变量 (该端口映射窗体是`host:container`)。 有关详细信息，请参阅[docker 运行](https://docs.docker.com/engine/reference/commandline/exec/)命令行参数的引用。

在应用程序启动后，请访问**http://localhost:5000/**在 web 浏览器中。

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>生成并使用用于 Windows 的 Docker 容器运行示例

你可以生成并运行在 Docker 使用 Windows 容器使用以下命令 （的说明假定存储库的根目录） 中的示例：

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> 必须导航到**容器 IP 地址**（而不是 http://localhost) 在浏览器中直接使用 Windows 容器时。 你可以通过以下步骤将容器的 IP 地址：

* 打开另一个命令提示符。
* 运行`docker ps`以查看你正在运行的容器。 "Aspnetcore_sample"容器应在那里。
* 运行 `docker exec aspnetcore_sample ipconfig`。
* 将容器 IP 地址复制并粘贴到你的浏览器 (例如，172.29.245.43)。

> [!Note]
> Docker exec 支持标识容器名称或哈希。 我们示例中使用的名称 (aspnetcore_sample)。

请参阅如何获取正在运行的 Windows 容器的 IP 地址的下面的示例。

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> Docker exec 在正在运行的容器中运行新的命令。 有关详细信息，请参阅[docker exec 参考](https://docs.docker.com/engine/reference/commandline/exec/)命令行参数。

您可以生成的应用程序已准备好部署到生产环境使用本地[dotnet 发布](../tools/dotnet-publish.md)命令。

```console
dotnet publish -c release -o published
```

> [!Note]
> -C 版本自变量生成应用程序在发布模式下 （默认值为调试模式下）。 有关详细信息，请参阅[dotnet run 参考](../tools/dotnet-run.md)命令行参数。

你可以上运行应用程序**Windows**使用以下命令。

```console
dotnet published\aspnetapp.dll
```

你可以上运行应用程序**Linux**或**macOS**使用以下命令。

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>此示例中使用的 docker 映像

在此示例中使用以下的 Docker 映像

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

祝贺你！ 正好有：
> [!div class="checklist"]
> * 所了解的有关 Microsoft.NET 核心 Docker 映像
> * 有 Dockerize 到示例应用程序的 ASP.NET 核心
> * 本地运行 ASP.NET 示例应用程序
> * 构建并使用 Docker 的 Linux 容器运行示例
> * 生成并与用于 Windows 的 Docker 容器中运行示例


**后续步骤**

下面是一些您可以采取的后续步骤：

* [使用 Visual Studio Docker 工具](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [使用 Visual Studio 代码进行调试](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [获取之手使用 Visual Studio Mac、 容器和无服务器代码在云中](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [开始使用 Docker 和 Visual Studio Mac 实验室](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> 如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。
