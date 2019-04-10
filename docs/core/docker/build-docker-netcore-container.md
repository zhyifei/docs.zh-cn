---
title: 通过 Docker 使应用程序容器化的教程
description: 在本教程中，你将学习如何通过 Docker 使 .NET Core 应用程序容器化。
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8255a901c706e55e143cdf23dda0eb9bc79d245d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58844958"
---
# <a name="tutorial-containerize-a-net-core-app"></a>教程：使 .NET Core 应用程序容器化

本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。 此映像可用于为本地开发环境、私有云或公有云创建容器。

在本教程中，你将了解如何：

> [!div class="checklist"]
> * 创建 Dockerfile
> * 拉取 Microsoft .NET Core Docker 基本映像
> * 自定义应用程序并将应用部署到映像
> * 创建并运行容器
> * 部署到 Azure

本教程介绍了 .NET Core 应用程序的 Docker 容器生成和部署任务。 [Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用 [Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成应用，并将其打包为 [Docker 映像](https://docs.docker.com/glossary/?term=image)。 这些映像以 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 格式编写，可在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)中部署和运行。



## <a name="net-core-easiest-way-to-get-started"></a>.NET Core：最简单的入门方式

在创建 Docker 映像之前，需要容器化应用程序。 可在 Linux、MacOS 或 Windows 上创建该映像。 完成该操作最快、最简单的方法是使用 .NET Core。

如果熟悉 .NET Core CLI 工具集，请阅读 [.NET Core SDK 概述](../tools/index.md)。

可使用[基于多拱形的标记](https://github.com/dotnet/announcements/issues/14)生成 Windows 和 Linux 容器。

## <a name="your-first-net-core-docker-app"></a>第一个 .NET Core Docker 应用

### <a name="prerequisites"></a>系统必备

完成本教程：

#### <a name="net-core-sdk"></a>.NET Core SDK

* 安装 [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) 或更高版本。

有关支持 .NET Core 2.1 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。

* 安装常用的代码编辑器（如果尚未安装）。

> [!TIP]
> 需要安装代码编辑器？ 试用 [Visual Studio Code](https://code.visualstudio.com/download)！

#### <a name="installing-docker-client"></a>安装 Docker 客户端

安装 [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) 或更高版本的 Docker 客户端。

可在以下位置安装 Docker 客户端：

* Linux 分布

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/)。

### <a name="create-a-net-core-21-console-app-for-dockerization"></a>创建 .NET Core 2.1 控制台应用进行 Docker 化

打开命令提示符，创建一个名为“Hello”的文件夹。 导航到创建的文件夹，并键入以下内容：

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
   * `TargetFramework` 标记指定要定位的 .NET 实现代码。 在高级方案中，可以指定多个目标框架，并在单个操作中生成到指定框架。 在本教程中，针对 .NET Core 2.1 进行生成。

   `Program.cs`：

   程序通过 `using System` 启动。 此语句的意思是“将 `System` 命名空间中的所有内容都纳入此文件的作用域”。 `System` 命名空间包括基本结构，如 `string` 或数值类型。

   接着定义一个名为 `Hello` 的命名空间。 可以将命名空间更改为任何喜欢的名称。 在该命名空间中定义了一个名为 `Program` 的类，其中 `Main` 方法将字符串数组作为其参数。 此数组包含在调用编译的程序时所传递的参数列表。 在我们的示例中，该程序只会在控制台中写入 “Hello World!”。

   dotnet new 运行 [`dotnet restore`](../tools/dotnet-restore.md) 命令。 Dotnet restore 通过 [NuGet](https://www.nuget.org/)（.NET 包管理器）调用还原依赖项树。
   NuGet 执行下列任务：
   * 分析 Hello.csproj 文件。
   * 下载文件依赖项（或从计算机缓存中获取）。
   * 写入 obj/project.assets.json 文件。

   project.assets.json 文件是一组完整的 NuGet 依赖项关系图、绑定解决方法及其他应用元数据。 此必需文件由其他工具（如 [`dotnet build`](../tools/dotnet-build.md) 和 [`dotnet run`](../tools/dotnet-run.md)）用于正确处理源代码。

2. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) 调用 [`dotnet build`](../tools/dotnet-build.md) 来确认生成成功，然后调用 `dotnet <assembly.dll>` 来运行应用程序。

    ```console
    $ dotnet run

    Hello World!
    ```

    有关高级方案的详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。

## <a name="dockerize-the-net-core-application"></a>使 .NET Core 应用程序 Docker 化

Hello .NET Core 控制台应用已成功在本地运行。 现在，可进一步在 Docker 中生成和运行应用。

### <a name="your-first-dockerfile"></a>第一个 Dockerfile

打开文本编辑器并开始操作！ 仍从生成了应用的 Hello 目录中进行操作。

为 Linux 或 [Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/) 向新文件添加以下 Docker 指令。 完成后，将其保存在 Hello 目录的根目录中作为 Dockerfile，并且不使用扩展名（可能需要将文件类型设置为 `All types (*.*)` 或类似的类型）。

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile 包含按顺序运行的 Docker build 指令。

第一个指令必须为 [FROM](https://docs.docker.com/engine/reference/builder/#from)。 此指令用于初始化新的生成阶段，并为剩余指令设置基础映像。 多拱形标记跟根据 Docker for Windows [容器模式](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) 请求 Windows 或 Linux 容器。 本示例的基础映像是 microsoft/dotnet 存储库中的 2.1-sdk 映像，

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

[WORKDIR](https://docs.docker.com/engine/reference/builder/#workdir) 指令为剩余的任意 RUN、CMD、ENTRYPOINT、COPY 和 ADD Dockerfile 指令设置工作目录。 如果不存在，则会创建该目录。 在本例中，WORKDIR 设置为应用目录。

```Dockerfile
WORKDIR /app
```

[COPY](https://docs.docker.com/engine/reference/builder/#copy) 指令从源路径复制新文件或目录，并将它们添加到目标容器文件系统。 使用此指令中，可将 C# 项目文件复制到容器。

```Dockerfile
COPY *.csproj ./
```

[RUN](https://docs.docker.com/engine/reference/builder/#run) 指令在当前映像之上的一个新层中执行任何命令，并提交结果。 最终提交的映像用于 Dockerfile 中的后续步骤。 本例运行 dotnet restore 来获取 C# 项目文件所需的依赖项。

```Dockerfile
RUN dotnet restore
```

此 COPY 指令将剩余文件复制到新[层](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)中的容器。

```Dockerfile
COPY . ./
```

本例使用 RUN 指令发布应用。 [dotnet publish](../tools/dotnet-publish.md) 命令用于编译应用程序、读取项目文件中指定的所有依赖项并将生成的文件集发布到目录。 此处使用 Release 配置和到默认目录的输出来发布应用。

```Dockerfile
RUN dotnet publish -c Release -o out
```

[ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) 指令支持以可执行文件的形式运行容器。

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

现在，生成的 Dockerfile 可：

* 将应用复制到映像
* 作为应用对映像的依赖项
* 生成作为可执行文件运行的应用

### <a name="build-and-run-the-hello-net-core-app"></a>生成并运行 Hello .NET Core 应用

#### <a name="essential-docker-commands"></a>重要的 Docker 命令

以下 Docker 命令非常重要：

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>生成和运行

已编写 dockerfile；现在 Docker 可生成应用，然后运行容器。

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

`docker build` 命令的输出应类似于以下控制台输出：

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

可在输出中看到，Docker 引擎使用 Dockerfile 生成容器。

`docker run` 命令的输出应类似于以下控制台输出：

```console
Hello World!
```

祝贺你！ 你刚才已完成：
> [!div class="checklist"]
> * 创建本地 .NET Core 应用
> * 创建 Dockerfile 以生成第一个容器
> * 生成并运行已 Docker 化的应用

## <a name="next-steps"></a>后续步骤

下面是一些可以采取的后续步骤：

* [.NET Docker 映像视频简介](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio、Docker 和 Azure 容器实例结合使用效果更佳！](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [Docker for Azure 快速入门](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [在 Docker for Azure 上部署应用](https://docs.docker.com/docker-for-azure/deploy/)

> [!NOTE]
> 如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。

## <a name="docker-images-used-in-this-sample"></a>此示例中使用的 Docker 映像

此示例中使用了以下 Docker 映像

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>相关资源

* [.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [Windows 容器上的 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET Framework Docker 示例](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [DockerHub 上的 ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/)
* [使 .NET Core 应用程序 Docker 化 - Docker 教程](https://docs.docker.com/engine/examples/dotnetcore/)
* [使用 Visual Studio Docker 工具](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)