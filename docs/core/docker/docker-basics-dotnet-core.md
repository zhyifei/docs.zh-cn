---
title: "了解 Docker 使用.NET Core 的基础知识"
description: "Docker 和.NET 核心基本教程"
keywords: ".NET，.NET 核心、 Docker 教程"
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
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>了解 Docker 使用.NET Core 的基础知识

本教程教的 Docker 容器生成和部署.NET 核心应用程序的任务。 在本教程过程中，你学习：

> [!div class="checklist"]
> * 如何创建 Dockerfile
> * 如何创建.NET Core 应用。
> * 如何将您的应用程序部署到 Docker 容器。

[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用[Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成并打包应用程序作为[Docker 映像](https://docs.docker.com/glossary/?term=image)。 这些映像用[Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)格式来部署和运行在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)。

## <a name="net-core-easiest-way-to-get-started"></a>.NET 核心： 若要开始的最简单方法

在创建之前的 Docker 映像，你需要应用程序化。 你可以在 Linux、 MacOS 或 Windows 上创建它。 执行此操作的最快和最简单方法是使用.NET 核心。

如果熟悉 .NET Core CLI 工具集，请阅读 [.NET Core SDK 概述](../tools/index.md)。

你可以生成使用的 Windows 和 Linux 容器[多体系结构基于标记](https://github.com/dotnet/announcements/issues/14)。

## <a name="your-first-net-core-docker-app"></a>第一个.NET 核心 Docker 应用

### <a name="prerequisites"></a>先决条件

若要完成本教程：

#### <a name="net-core-20-sdk"></a>.NET 核心 2.0 SDK

* 安装[.NET 核心 SDK 2.0](https://www.microsoft.com/net/core)。

有关支持 .NET Core 2.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。

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

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>为 Dockerization 创建.NET 核心 2.0 控制台应用程序

打开命令提示符，创建一个名为“Hello”的文件夹。 导航到你创建的文件夹，并键入以下命令：

```console
dotnet new console
dotnet run
```

让我们进行快速演练：

1. `$ dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) 会创建一个最新的 `Hello.csproj` 项目文件，其中包含生成控制台应用所必需的依赖项。  它还将创建 `Program.cs`，这是包含应用程序的入口点的基本文件。
   
   `Hello.csproj`：

   项目文件指定还原依赖项和生成程序所需的一切。

   * `OutputType` 标记指定我们要生成的可执行文件，即控制台应用程序。
   * `TargetFramework` 标记指定要定位的 .NET 实现代码。 在高级方案中，你可以指定多个目标框架，并生成到单个操作中指定的框架。 在本教程中，我们生成 for.NET 核心 2.0。

   `Program.cs`：

   程序的启动方式`using System`。 此声明表示，"将所有内容放`System`到此文件的作用域的命名空间。" `System` 命名空间包括基本结构，如 `string` 或数值类型。

   接着定义一个名为 `Hello` 的命名空间。 可以将命名空间更改为任何需要的内容。 在该命名空间中定义了一个名为 `Program` 的类，其中 `Main` 方法将字符串数组作为其参数。 此数组包含在调用编译的程序时所传递的参数列表。 在我们的示例，该程序只会写入"Hello World ！" “Hello World!”。

2. `$ dotnet restore`

   在.NET 核心 2.x， **dotnet 新**运行[ `dotnet restore` ](../tools/dotnet-restore.md)命令。 **Dotnet 还原**还原依赖关系的树[NuGet](https://www.nuget.org/)（.NET 程序包管理器） 调用。
   NuGet 将执行下列任务：
   * 分析*Hello.csproj*文件 
   * 下载文件依赖关系 （或从你计算机的缓存 grabs）
   * 写入*obj/project.assets.json*文件

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   *Project.assets.json*文件是一组完整的 NuGet 依赖项关系图、 绑定分辨率和其他应用程序元数据。 这所必需的文件由其他工具，如使用[ `dotnet build` ](../tools/dotnet-build.md)和[ `dotnet run` ](../tools/dotnet-run.md)，若要正确处理的源代码。
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)调用[ `dotnet build` ](../tools/dotnet-build.md)以确认成功生成，然后调用`dotnet <assembly.dll>`运行该应用程序。
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    对于高级方案，请参阅[.NET 核心应用程序部署](../deploying/index.md)有关详细信息。

## <a name="dockerize-the-net-core-application"></a>Dockerize.NET 核心应用程序

Hello.NET Core 控制台应用程序已成功将本地运行。 现在让我们进一步它和生成和运行应用程序在 Docker 中。

### <a name="your-first-dockerfile"></a>第一个 Dockerfile

打开文本编辑器，并让我们开始吧 ！ 我们仍正在从我们生成应用程序中的 Hello 目录。

添加下列 Docker 指导来帮助任一 Linux 或[Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/)到新文件。 完成后，将其保存在作为你 Hello 目录的根目录**Dockerfile**，不带扩展名 (可能需要将你的文件类型设置为`All types (*.*)`或类似的内容)。

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile 包含按顺序运行的 Docker 生成说明。

第一个指令必须为[ **FROM**](https://docs.docker.com/engine/reference/builder/#from)。 此指令初始化新的生成阶段，并设置其余说明进行操作基础映像。 多 arch 标记提取 Windows 或 Linux 容器，具体取决于 Windows 的 Docker[容器模式](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)。 我们的示例基础映像是从 microsoft/dotnet 存储库，2.0 sdk 映像

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

[ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir)指令设置工作目录的任何剩余运行、 CMD、 入口点、 复制和添加 Dockerfile 指令。 如果目录不存在，则创建它。 在这种情况下，WORKDIR 设置为应用程序目录。

```Dockerfile
WORKDIR /app
```

[**复制**](https://docs.docker.com/engine/reference/builder/#copy)指令从源路径复制新文件或目录，并将它们添加到目标容器文件系统。 使用此指令中，我们要复制到容器的 C# 项目文件。

```Dockerfile
COPY *.csproj ./
```

[**运行**](https://docs.docker.com/engine/reference/builder/#run)指令在当前映像的一个新层中执行任何命令，并提交结果。 生成的提交的映像用于 Dockerfile 的下一步。 我们正在运行**dotnet 还原**获取 C# 项目文件的所需依赖关系。 

```Dockerfile
RUN dotnet restore
```

这**复制**指令文件的其余部分将复制到复制到我们容器新[层](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)。

```Dockerfile
COPY . ./
```

我们正在发布应用程序与此**运行**指令。 [ **Dotnet 发布**](../tools/dotnet-publish.md)的命令编译应用程序、 读取通过在项目文件中，指定其依赖项并将结果集的文件发布到一个目录。 我们的应用程序发布与**版本**配置和输出到默认目录。

```Dockerfile
RUN dotnet publish -c Release -o out
```

[**入口点**](https://docs.docker.com/engine/reference/builder/#entrypoint)指令允许要为可执行文件运行的容器。

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

现在你拥有 Dockerfile 的：

* 将你的应用程序复制到映像
* 对图像的应用程序的依赖关系
* 生成应用程序以运行为可执行文件

### <a name="build-and-run-the-hello-net-core-20-app"></a>生成并运行 Hello.NET 核心 2.0 应用

#### <a name="essential-docker-commands"></a>基本 Docker 命令

这些 Docker 命令至关重要：

* [docker 生成](https://docs.docker.com/engine/reference/commandline/build/)
* [运行的 docker](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker 停止](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker 映像](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>生成并运行

你编写 dockerfile;现在 Docker 生成你的应用程序，然后运行容器。

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

从输出`docker build`命令应类似于下面的控制台输出：

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

正如您可以看到输出中，Docker 引擎将使用 Dockerfile 生成我们容器。

从输出`docker run`命令应类似于下面的控制台输出：

```console
Hello World!
```

祝贺你！ 正好有：
> [!div class="checklist"]
> * 创建本地.NET Core 应用
> * 创建 Dockerfile 生成第一个容器
> * 生成并运行您 Dockerized 的应用程序



## <a name="next-steps"></a>后续步骤

下面是一些您可以采取的后续步骤：

* [.NET Docker 映像视频简介](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio、 Docker 和 Azure 容器实例最好一起使用 ！](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Azure 快速入门的 docker](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [部署 Azure 的 Docker 上的应用程序](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> 如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。

## <a name="docker-images-used-in-this-sample"></a>此示例中使用的 docker 映像

在此示例中使用以下的 Docker 映像

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>相关资源

* [.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Windows 容器上的 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET framework Docker 示例](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET 核心上 DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Dockerize.NET 核心应用程序-Docker 教程](https://docs.docker.com/engine/examples/dotnetcore/)
* [使用 Visual Studio Docker 工具](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)