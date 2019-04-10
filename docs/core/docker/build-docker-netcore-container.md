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
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="fd306-103">教程：使 .NET Core 应用程序容器化</span><span class="sxs-lookup"><span data-stu-id="fd306-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="fd306-104">本教程介绍如何生成包含 .NET Core 应用程序的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="fd306-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="fd306-105">此映像可用于为本地开发环境、私有云或公有云创建容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="fd306-106">在本教程中，你将了解如何：</span><span class="sxs-lookup"><span data-stu-id="fd306-106">In this tutorial you will learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fd306-107">创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="fd306-107">Create a Dockerfile</span></span>
> * <span data-ttu-id="fd306-108">拉取 Microsoft .NET Core Docker 基本映像</span><span class="sxs-lookup"><span data-stu-id="fd306-108">Pull a Microsoft .NET Core Docker base image</span></span>
> * <span data-ttu-id="fd306-109">自定义应用程序并将应用部署到映像</span><span class="sxs-lookup"><span data-stu-id="fd306-109">Customize and deploy your app to the image</span></span>
> * <span data-ttu-id="fd306-110">创建并运行容器</span><span class="sxs-lookup"><span data-stu-id="fd306-110">Create and run a container</span></span>
> * <span data-ttu-id="fd306-111">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="fd306-111">Deploy to Azure</span></span>

<span data-ttu-id="fd306-112">本教程介绍了 .NET Core 应用程序的 Docker 容器生成和部署任务。</span><span class="sxs-lookup"><span data-stu-id="fd306-112">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="fd306-113">[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用 [Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成应用，并将其打包为 [Docker 映像](https://docs.docker.com/glossary/?term=image)。</span><span class="sxs-lookup"><span data-stu-id="fd306-113">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="fd306-114">这些映像以 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 格式编写，可在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="fd306-114">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>



## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="fd306-115">.NET Core：最简单的入门方式</span><span class="sxs-lookup"><span data-stu-id="fd306-115">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="fd306-116">在创建 Docker 映像之前，需要容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd306-116">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="fd306-117">可在 Linux、MacOS 或 Windows 上创建该映像。</span><span class="sxs-lookup"><span data-stu-id="fd306-117">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="fd306-118">完成该操作最快、最简单的方法是使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="fd306-118">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="fd306-119">如果熟悉 .NET Core CLI 工具集，请阅读 [.NET Core SDK 概述](../tools/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fd306-119">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="fd306-120">可使用[基于多拱形的标记](https://github.com/dotnet/announcements/issues/14)生成 Windows 和 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-120">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="fd306-121">第一个 .NET Core Docker 应用</span><span class="sxs-lookup"><span data-stu-id="fd306-121">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="fd306-122">系统必备</span><span class="sxs-lookup"><span data-stu-id="fd306-122">Prerequisites</span></span>

<span data-ttu-id="fd306-123">完成本教程：</span><span class="sxs-lookup"><span data-stu-id="fd306-123">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="fd306-124">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="fd306-124">.NET Core SDK</span></span>

* <span data-ttu-id="fd306-125">安装 [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fd306-125">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="fd306-126">有关支持 .NET Core 2.1 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="fd306-126">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="fd306-127">安装常用的代码编辑器（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="fd306-127">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="fd306-128">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="fd306-128">Need to install a code editor?</span></span> <span data-ttu-id="fd306-129">试用 [Visual Studio Code](https://code.visualstudio.com/download)！</span><span class="sxs-lookup"><span data-stu-id="fd306-129">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="fd306-130">安装 Docker 客户端</span><span class="sxs-lookup"><span data-stu-id="fd306-130">Installing Docker Client</span></span>

<span data-ttu-id="fd306-131">安装 [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) 或更高版本的 Docker 客户端。</span><span class="sxs-lookup"><span data-stu-id="fd306-131">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="fd306-132">可在以下位置安装 Docker 客户端：</span><span class="sxs-lookup"><span data-stu-id="fd306-132">The Docker client can be installed in:</span></span>

* <span data-ttu-id="fd306-133">Linux 分布</span><span class="sxs-lookup"><span data-stu-id="fd306-133">Linux distributions</span></span>

   * [<span data-ttu-id="fd306-134">CentOS</span><span class="sxs-lookup"><span data-stu-id="fd306-134">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="fd306-135">Debian</span><span class="sxs-lookup"><span data-stu-id="fd306-135">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="fd306-136">Fedora</span><span class="sxs-lookup"><span data-stu-id="fd306-136">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="fd306-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="fd306-137">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="fd306-138">macOS</span><span class="sxs-lookup"><span data-stu-id="fd306-138">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="fd306-139">[Windows](https://docs.docker.com/docker-for-windows/install/)。</span><span class="sxs-lookup"><span data-stu-id="fd306-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="fd306-140">创建 .NET Core 2.1 控制台应用进行 Docker 化</span><span class="sxs-lookup"><span data-stu-id="fd306-140">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="fd306-141">打开命令提示符，创建一个名为“Hello”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fd306-141">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="fd306-142">导航到创建的文件夹，并键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="fd306-142">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="fd306-143">让我们进行快速演练：</span><span class="sxs-lookup"><span data-stu-id="fd306-143">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="fd306-144">[`dotnet new`](../tools/dotnet-new.md) 会创建一个最新的 `Hello.csproj` 项目文件，其中包含生成控制台应用所必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fd306-144">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="fd306-145">它还将创建 `Program.cs`，这是包含应用程序的入口点的基本文件。</span><span class="sxs-lookup"><span data-stu-id="fd306-145">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="fd306-146">`Hello.csproj`：</span><span class="sxs-lookup"><span data-stu-id="fd306-146">`Hello.csproj`:</span></span>

   <span data-ttu-id="fd306-147">项目文件指定还原依赖项和生成程序所需的一切。</span><span class="sxs-lookup"><span data-stu-id="fd306-147">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="fd306-148">`OutputType` 标记指定我们要生成的可执行文件，即控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd306-148">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="fd306-149">`TargetFramework` 标记指定要定位的 .NET 实现代码。</span><span class="sxs-lookup"><span data-stu-id="fd306-149">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="fd306-150">在高级方案中，可以指定多个目标框架，并在单个操作中生成到指定框架。</span><span class="sxs-lookup"><span data-stu-id="fd306-150">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="fd306-151">在本教程中，针对 .NET Core 2.1 进行生成。</span><span class="sxs-lookup"><span data-stu-id="fd306-151">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="fd306-152">`Program.cs`：</span><span class="sxs-lookup"><span data-stu-id="fd306-152">`Program.cs`:</span></span>

   <span data-ttu-id="fd306-153">程序通过 `using System` 启动。</span><span class="sxs-lookup"><span data-stu-id="fd306-153">The program starts by `using System`.</span></span> <span data-ttu-id="fd306-154">此语句的意思是“将 `System` 命名空间中的所有内容都纳入此文件的作用域”。</span><span class="sxs-lookup"><span data-stu-id="fd306-154">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="fd306-155">`System` 命名空间包括基本结构，如 `string` 或数值类型。</span><span class="sxs-lookup"><span data-stu-id="fd306-155">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="fd306-156">接着定义一个名为 `Hello` 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fd306-156">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="fd306-157">可以将命名空间更改为任何喜欢的名称。</span><span class="sxs-lookup"><span data-stu-id="fd306-157">You can change namespace to anything you want.</span></span> <span data-ttu-id="fd306-158">在该命名空间中定义了一个名为 `Program` 的类，其中 `Main` 方法将字符串数组作为其参数。</span><span class="sxs-lookup"><span data-stu-id="fd306-158">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="fd306-159">此数组包含在调用编译的程序时所传递的参数列表。</span><span class="sxs-lookup"><span data-stu-id="fd306-159">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="fd306-160">在我们的示例中，该程序只会在控制台中写入</span><span class="sxs-lookup"><span data-stu-id="fd306-160">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="fd306-161">“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="fd306-161">to the console.</span></span>

   <span data-ttu-id="fd306-162">dotnet new 运行 [`dotnet restore`](../tools/dotnet-restore.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="fd306-162">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="fd306-163">Dotnet restore 通过 [NuGet](https://www.nuget.org/)（.NET 包管理器）调用还原依赖项树。</span><span class="sxs-lookup"><span data-stu-id="fd306-163">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="fd306-164">NuGet 执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="fd306-164">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="fd306-165">分析 Hello.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="fd306-165">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="fd306-166">下载文件依赖项（或从计算机缓存中获取）。</span><span class="sxs-lookup"><span data-stu-id="fd306-166">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="fd306-167">写入 obj/project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="fd306-167">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="fd306-168">project.assets.json 文件是一组完整的 NuGet 依赖项关系图、绑定解决方法及其他应用元数据。</span><span class="sxs-lookup"><span data-stu-id="fd306-168">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="fd306-169">此必需文件由其他工具（如 [`dotnet build`](../tools/dotnet-build.md) 和 [`dotnet run`](../tools/dotnet-run.md)）用于正确处理源代码。</span><span class="sxs-lookup"><span data-stu-id="fd306-169">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="fd306-170">[`dotnet run`](../tools/dotnet-run.md) 调用 [`dotnet build`](../tools/dotnet-build.md) 来确认生成成功，然后调用 `dotnet <assembly.dll>` 来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="fd306-170">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="fd306-171">有关高级方案的详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fd306-171">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="fd306-172">使 .NET Core 应用程序 Docker 化</span><span class="sxs-lookup"><span data-stu-id="fd306-172">Dockerize the .NET Core application</span></span>

<span data-ttu-id="fd306-173">Hello .NET Core 控制台应用已成功在本地运行。</span><span class="sxs-lookup"><span data-stu-id="fd306-173">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="fd306-174">现在，可进一步在 Docker 中生成和运行应用。</span><span class="sxs-lookup"><span data-stu-id="fd306-174">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="fd306-175">第一个 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="fd306-175">Your first Dockerfile</span></span>

<span data-ttu-id="fd306-176">打开文本编辑器并开始操作！</span><span class="sxs-lookup"><span data-stu-id="fd306-176">Open your text editor and let's get started!</span></span> <span data-ttu-id="fd306-177">仍从生成了应用的 Hello 目录中进行操作。</span><span class="sxs-lookup"><span data-stu-id="fd306-177">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="fd306-178">为 Linux 或 [Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/) 向新文件添加以下 Docker 指令。</span><span class="sxs-lookup"><span data-stu-id="fd306-178">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="fd306-179">完成后，将其保存在 Hello 目录的根目录中作为 Dockerfile，并且不使用扩展名（可能需要将文件类型设置为 `All types (*.*)` 或类似的类型）。</span><span class="sxs-lookup"><span data-stu-id="fd306-179">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

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

<span data-ttu-id="fd306-180">Dockerfile 包含按顺序运行的 Docker build 指令。</span><span class="sxs-lookup"><span data-stu-id="fd306-180">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="fd306-181">第一个指令必须为 [FROM](https://docs.docker.com/engine/reference/builder/#from)。</span><span class="sxs-lookup"><span data-stu-id="fd306-181">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="fd306-182">此指令用于初始化新的生成阶段，并为剩余指令设置基础映像。</span><span class="sxs-lookup"><span data-stu-id="fd306-182">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="fd306-183">多拱形标记跟根据 Docker for Windows [容器模式](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) 请求 Windows 或 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-183">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="fd306-184">本示例的基础映像是 microsoft/dotnet 存储库中的 2.1-sdk 映像，</span><span class="sxs-lookup"><span data-stu-id="fd306-184">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="fd306-185">[WORKDIR](https://docs.docker.com/engine/reference/builder/#workdir) 指令为剩余的任意 RUN、CMD、ENTRYPOINT、COPY 和 ADD Dockerfile 指令设置工作目录。</span><span class="sxs-lookup"><span data-stu-id="fd306-185">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="fd306-186">如果不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="fd306-186">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="fd306-187">在本例中，WORKDIR 设置为应用目录。</span><span class="sxs-lookup"><span data-stu-id="fd306-187">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="fd306-188">[COPY](https://docs.docker.com/engine/reference/builder/#copy) 指令从源路径复制新文件或目录，并将它们添加到目标容器文件系统。</span><span class="sxs-lookup"><span data-stu-id="fd306-188">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="fd306-189">使用此指令中，可将 C# 项目文件复制到容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-189">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="fd306-190">[RUN](https://docs.docker.com/engine/reference/builder/#run) 指令在当前映像之上的一个新层中执行任何命令，并提交结果。</span><span class="sxs-lookup"><span data-stu-id="fd306-190">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="fd306-191">最终提交的映像用于 Dockerfile 中的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="fd306-191">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="fd306-192">本例运行 dotnet restore 来获取 C# 项目文件所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fd306-192">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="fd306-193">此 COPY 指令将剩余文件复制到新[层](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)中的容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-193">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="fd306-194">本例使用 RUN 指令发布应用。</span><span class="sxs-lookup"><span data-stu-id="fd306-194">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="fd306-195">[dotnet publish](../tools/dotnet-publish.md) 命令用于编译应用程序、读取项目文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="fd306-195">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="fd306-196">此处使用 Release 配置和到默认目录的输出来发布应用。</span><span class="sxs-lookup"><span data-stu-id="fd306-196">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="fd306-197">[ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) 指令支持以可执行文件的形式运行容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-197">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="fd306-198">现在，生成的 Dockerfile 可：</span><span class="sxs-lookup"><span data-stu-id="fd306-198">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="fd306-199">将应用复制到映像</span><span class="sxs-lookup"><span data-stu-id="fd306-199">copies your app to the image</span></span>
* <span data-ttu-id="fd306-200">作为应用对映像的依赖项</span><span class="sxs-lookup"><span data-stu-id="fd306-200">your app's dependencies to the image</span></span>
* <span data-ttu-id="fd306-201">生成作为可执行文件运行的应用</span><span class="sxs-lookup"><span data-stu-id="fd306-201">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="fd306-202">生成并运行 Hello .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="fd306-202">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="fd306-203">重要的 Docker 命令</span><span class="sxs-lookup"><span data-stu-id="fd306-203">Essential Docker commands</span></span>

<span data-ttu-id="fd306-204">以下 Docker 命令非常重要：</span><span class="sxs-lookup"><span data-stu-id="fd306-204">These Docker commands are essential:</span></span>

* [<span data-ttu-id="fd306-205">docker build</span><span class="sxs-lookup"><span data-stu-id="fd306-205">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="fd306-206">docker run</span><span class="sxs-lookup"><span data-stu-id="fd306-206">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="fd306-207">docker ps</span><span class="sxs-lookup"><span data-stu-id="fd306-207">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="fd306-208">docker stop</span><span class="sxs-lookup"><span data-stu-id="fd306-208">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="fd306-209">docker rm</span><span class="sxs-lookup"><span data-stu-id="fd306-209">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="fd306-210">docker rmi</span><span class="sxs-lookup"><span data-stu-id="fd306-210">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="fd306-211">docker image</span><span class="sxs-lookup"><span data-stu-id="fd306-211">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="fd306-212">生成和运行</span><span class="sxs-lookup"><span data-stu-id="fd306-212">Build and run</span></span>

<span data-ttu-id="fd306-213">已编写 dockerfile；现在 Docker 可生成应用，然后运行容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-213">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="fd306-214">`docker build` 命令的输出应类似于以下控制台输出：</span><span class="sxs-lookup"><span data-stu-id="fd306-214">The output from the `docker build` command should be similar to the following console output:</span></span>

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

<span data-ttu-id="fd306-215">可在输出中看到，Docker 引擎使用 Dockerfile 生成容器。</span><span class="sxs-lookup"><span data-stu-id="fd306-215">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="fd306-216">`docker run` 命令的输出应类似于以下控制台输出：</span><span class="sxs-lookup"><span data-stu-id="fd306-216">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="fd306-217">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="fd306-217">Congratulations!</span></span> <span data-ttu-id="fd306-218">你刚才已完成：</span><span class="sxs-lookup"><span data-stu-id="fd306-218">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="fd306-219">创建本地 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="fd306-219">Created a local .NET Core app</span></span>
> * <span data-ttu-id="fd306-220">创建 Dockerfile 以生成第一个容器</span><span class="sxs-lookup"><span data-stu-id="fd306-220">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="fd306-221">生成并运行已 Docker 化的应用</span><span class="sxs-lookup"><span data-stu-id="fd306-221">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd306-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd306-222">Next steps</span></span>

<span data-ttu-id="fd306-223">下面是一些可以采取的后续步骤：</span><span class="sxs-lookup"><span data-stu-id="fd306-223">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="fd306-224">.NET Docker 映像视频简介</span><span class="sxs-lookup"><span data-stu-id="fd306-224">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="fd306-225">Visual Studio、Docker 和 Azure 容器实例结合使用效果更佳！</span><span class="sxs-lookup"><span data-stu-id="fd306-225">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [<span data-ttu-id="fd306-226">Docker for Azure 快速入门</span><span class="sxs-lookup"><span data-stu-id="fd306-226">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="fd306-227">在 Docker for Azure 上部署应用</span><span class="sxs-lookup"><span data-stu-id="fd306-227">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!NOTE]
> <span data-ttu-id="fd306-228">如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="fd306-228">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="fd306-229">此示例中使用的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="fd306-229">Docker Images used in this sample</span></span>

<span data-ttu-id="fd306-230">此示例中使用了以下 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="fd306-230">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="fd306-231">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd306-231">Related resources</span></span>

* [<span data-ttu-id="fd306-232">.NET Core Docker 示例</span><span class="sxs-lookup"><span data-stu-id="fd306-232">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [<span data-ttu-id="fd306-233">Windows 容器上的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="fd306-233">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="fd306-234">.NET Framework Docker 示例</span><span class="sxs-lookup"><span data-stu-id="fd306-234">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="fd306-235">DockerHub 上的 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fd306-235">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="fd306-236">使 .NET Core 应用程序 Docker 化 - Docker 教程</span><span class="sxs-lookup"><span data-stu-id="fd306-236">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="fd306-237">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="fd306-237">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="fd306-238">将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="fd306-238">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)