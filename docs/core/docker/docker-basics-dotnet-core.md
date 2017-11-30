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
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="bd286-104">了解 Docker 使用.NET Core 的基础知识</span><span class="sxs-lookup"><span data-stu-id="bd286-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="bd286-105">本教程教的 Docker 容器生成和部署.NET 核心应用程序的任务。</span><span class="sxs-lookup"><span data-stu-id="bd286-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="bd286-106">在本教程过程中，你学习：</span><span class="sxs-lookup"><span data-stu-id="bd286-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="bd286-107">如何创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="bd286-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="bd286-108">如何创建.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="bd286-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="bd286-109">如何将您的应用程序部署到 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="bd286-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="bd286-110">[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用[Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成并打包应用程序作为[Docker 映像](https://docs.docker.com/glossary/?term=image)。</span><span class="sxs-lookup"><span data-stu-id="bd286-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="bd286-111">这些映像用[Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)格式来部署和运行在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)。</span><span class="sxs-lookup"><span data-stu-id="bd286-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="bd286-112">.NET 核心： 若要开始的最简单方法</span><span class="sxs-lookup"><span data-stu-id="bd286-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="bd286-113">在创建之前的 Docker 映像，你需要应用程序化。</span><span class="sxs-lookup"><span data-stu-id="bd286-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="bd286-114">你可以在 Linux、 MacOS 或 Windows 上创建它。</span><span class="sxs-lookup"><span data-stu-id="bd286-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="bd286-115">执行此操作的最快和最简单方法是使用.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="bd286-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="bd286-116">如果熟悉 .NET Core CLI 工具集，请阅读 [.NET Core SDK 概述](../tools/index.md)。</span><span class="sxs-lookup"><span data-stu-id="bd286-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="bd286-117">你可以生成使用的 Windows 和 Linux 容器[多体系结构基于标记](https://github.com/dotnet/announcements/issues/14)。</span><span class="sxs-lookup"><span data-stu-id="bd286-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="bd286-118">第一个.NET 核心 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="bd286-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="bd286-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="bd286-119">Prerequisites</span></span>

<span data-ttu-id="bd286-120">若要完成本教程：</span><span class="sxs-lookup"><span data-stu-id="bd286-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="bd286-121">.NET 核心 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="bd286-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="bd286-122">安装[.NET 核心 SDK 2.0](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="bd286-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="bd286-123">有关支持 .NET Core 2.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。</span><span class="sxs-lookup"><span data-stu-id="bd286-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="bd286-124">如果你尚未，安装最喜欢的代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="bd286-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="bd286-125">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="bd286-125">Need to install a code editor?</span></span> <span data-ttu-id="bd286-126">请尝试[Visual Studio](https://visualstudio.com/downloads)！</span><span class="sxs-lookup"><span data-stu-id="bd286-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="bd286-127">安装 Docker 客户端</span><span class="sxs-lookup"><span data-stu-id="bd286-127">Installing Docker Client</span></span>

<span data-ttu-id="bd286-128">安装[Docker 17.06](https://docs.docker.com/release-notes/docker-ce/)或更高版本的 Docker 客户端。</span><span class="sxs-lookup"><span data-stu-id="bd286-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="bd286-129">可以在安装 Docker 客户端：</span><span class="sxs-lookup"><span data-stu-id="bd286-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="bd286-130">Linux 分发</span><span class="sxs-lookup"><span data-stu-id="bd286-130">Linux distributions</span></span>

   * [<span data-ttu-id="bd286-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="bd286-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="bd286-132">Debian</span><span class="sxs-lookup"><span data-stu-id="bd286-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="bd286-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="bd286-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="bd286-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="bd286-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="bd286-135">macOS</span><span class="sxs-lookup"><span data-stu-id="bd286-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="bd286-136">[Windows](https://docs.docker.com/docker-for-windows/)。</span><span class="sxs-lookup"><span data-stu-id="bd286-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="bd286-137">为 Dockerization 创建.NET 核心 2.0 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bd286-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="bd286-138">打开命令提示符，创建一个名为“Hello”的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd286-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="bd286-139">导航到你创建的文件夹，并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="bd286-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="bd286-140">让我们进行快速演练：</span><span class="sxs-lookup"><span data-stu-id="bd286-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="bd286-141">[`dotnet new`](../tools/dotnet-new.md) 会创建一个最新的 `Hello.csproj` 项目文件，其中包含生成控制台应用所必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bd286-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="bd286-142">它还将创建 `Program.cs`，这是包含应用程序的入口点的基本文件。</span><span class="sxs-lookup"><span data-stu-id="bd286-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="bd286-143">`Hello.csproj`：</span><span class="sxs-lookup"><span data-stu-id="bd286-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="bd286-144">项目文件指定还原依赖项和生成程序所需的一切。</span><span class="sxs-lookup"><span data-stu-id="bd286-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="bd286-145">`OutputType` 标记指定我们要生成的可执行文件，即控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd286-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="bd286-146">`TargetFramework` 标记指定要定位的 .NET 实现代码。</span><span class="sxs-lookup"><span data-stu-id="bd286-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="bd286-147">在高级方案中，你可以指定多个目标框架，并生成到单个操作中指定的框架。</span><span class="sxs-lookup"><span data-stu-id="bd286-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="bd286-148">在本教程中，我们生成 for.NET 核心 2.0。</span><span class="sxs-lookup"><span data-stu-id="bd286-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="bd286-149">`Program.cs`：</span><span class="sxs-lookup"><span data-stu-id="bd286-149">`Program.cs`:</span></span>

   <span data-ttu-id="bd286-150">程序的启动方式`using System`。</span><span class="sxs-lookup"><span data-stu-id="bd286-150">The program starts by `using System`.</span></span> <span data-ttu-id="bd286-151">此声明表示，"将所有内容放`System`到此文件的作用域的命名空间。"</span><span class="sxs-lookup"><span data-stu-id="bd286-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="bd286-152">`System` 命名空间包括基本结构，如 `string` 或数值类型。</span><span class="sxs-lookup"><span data-stu-id="bd286-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="bd286-153">接着定义一个名为 `Hello` 的命名空间。</span><span class="sxs-lookup"><span data-stu-id="bd286-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="bd286-154">可以将命名空间更改为任何需要的内容。</span><span class="sxs-lookup"><span data-stu-id="bd286-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="bd286-155">在该命名空间中定义了一个名为 `Program` 的类，其中 `Main` 方法将字符串数组作为其参数。</span><span class="sxs-lookup"><span data-stu-id="bd286-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="bd286-156">此数组包含在调用编译的程序时所传递的参数列表。</span><span class="sxs-lookup"><span data-stu-id="bd286-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="bd286-157">在我们的示例，该程序只会写入"Hello World ！"</span><span class="sxs-lookup"><span data-stu-id="bd286-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="bd286-158">“Hello World!”。</span><span class="sxs-lookup"><span data-stu-id="bd286-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="bd286-159">在.NET 核心 2.x， **dotnet 新**运行[ `dotnet restore` ](../tools/dotnet-restore.md)命令。</span><span class="sxs-lookup"><span data-stu-id="bd286-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="bd286-160">**Dotnet 还原**还原依赖关系的树[NuGet](https://www.nuget.org/)（.NET 程序包管理器） 调用。</span><span class="sxs-lookup"><span data-stu-id="bd286-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="bd286-161">NuGet 将执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="bd286-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="bd286-162">分析*Hello.csproj*文件</span><span class="sxs-lookup"><span data-stu-id="bd286-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="bd286-163">下载文件依赖关系 （或从你计算机的缓存 grabs）</span><span class="sxs-lookup"><span data-stu-id="bd286-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="bd286-164">写入*obj/project.assets.json*文件</span><span class="sxs-lookup"><span data-stu-id="bd286-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="bd286-165">*Project.assets.json*文件是一组完整的 NuGet 依赖项关系图、 绑定分辨率和其他应用程序元数据。</span><span class="sxs-lookup"><span data-stu-id="bd286-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="bd286-166">这所必需的文件由其他工具，如使用[ `dotnet build` ](../tools/dotnet-build.md)和[ `dotnet run` ](../tools/dotnet-run.md)，若要正确处理的源代码。</span><span class="sxs-lookup"><span data-stu-id="bd286-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="bd286-167">[`dotnet run`](../tools/dotnet-run.md)调用[ `dotnet build` ](../tools/dotnet-build.md)以确认成功生成，然后调用`dotnet <assembly.dll>`运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd286-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="bd286-168">对于高级方案，请参阅[.NET 核心应用程序部署](../deploying/index.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd286-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="bd286-169">Dockerize.NET 核心应用程序</span><span class="sxs-lookup"><span data-stu-id="bd286-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="bd286-170">Hello.NET Core 控制台应用程序已成功将本地运行。</span><span class="sxs-lookup"><span data-stu-id="bd286-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="bd286-171">现在让我们进一步它和生成和运行应用程序在 Docker 中。</span><span class="sxs-lookup"><span data-stu-id="bd286-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="bd286-172">第一个 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="bd286-172">Your first Dockerfile</span></span>

<span data-ttu-id="bd286-173">打开文本编辑器，并让我们开始吧 ！</span><span class="sxs-lookup"><span data-stu-id="bd286-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="bd286-174">我们仍正在从我们生成应用程序中的 Hello 目录。</span><span class="sxs-lookup"><span data-stu-id="bd286-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="bd286-175">添加下列 Docker 指导来帮助任一 Linux 或[Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/)到新文件。</span><span class="sxs-lookup"><span data-stu-id="bd286-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="bd286-176">完成后，将其保存在作为你 Hello 目录的根目录**Dockerfile**，不带扩展名 (可能需要将你的文件类型设置为`All types (*.*)`或类似的内容)。</span><span class="sxs-lookup"><span data-stu-id="bd286-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

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

<span data-ttu-id="bd286-177">Dockerfile 包含按顺序运行的 Docker 生成说明。</span><span class="sxs-lookup"><span data-stu-id="bd286-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="bd286-178">第一个指令必须为[ **FROM**](https://docs.docker.com/engine/reference/builder/#from)。</span><span class="sxs-lookup"><span data-stu-id="bd286-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="bd286-179">此指令初始化新的生成阶段，并设置其余说明进行操作基础映像。</span><span class="sxs-lookup"><span data-stu-id="bd286-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="bd286-180">多 arch 标记提取 Windows 或 Linux 容器，具体取决于 Windows 的 Docker[容器模式](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)。</span><span class="sxs-lookup"><span data-stu-id="bd286-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="bd286-181">我们的示例基础映像是从 microsoft/dotnet 存储库，2.0 sdk 映像</span><span class="sxs-lookup"><span data-stu-id="bd286-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="bd286-182">[ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir)指令设置工作目录的任何剩余运行、 CMD、 入口点、 复制和添加 Dockerfile 指令。</span><span class="sxs-lookup"><span data-stu-id="bd286-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="bd286-183">如果目录不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="bd286-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="bd286-184">在这种情况下，WORKDIR 设置为应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="bd286-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="bd286-185">[**复制**](https://docs.docker.com/engine/reference/builder/#copy)指令从源路径复制新文件或目录，并将它们添加到目标容器文件系统。</span><span class="sxs-lookup"><span data-stu-id="bd286-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="bd286-186">使用此指令中，我们要复制到容器的 C# 项目文件。</span><span class="sxs-lookup"><span data-stu-id="bd286-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="bd286-187">[**运行**](https://docs.docker.com/engine/reference/builder/#run)指令在当前映像的一个新层中执行任何命令，并提交结果。</span><span class="sxs-lookup"><span data-stu-id="bd286-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="bd286-188">生成的提交的映像用于 Dockerfile 的下一步。</span><span class="sxs-lookup"><span data-stu-id="bd286-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="bd286-189">我们正在运行**dotnet 还原**获取 C# 项目文件的所需依赖关系。</span><span class="sxs-lookup"><span data-stu-id="bd286-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="bd286-190">这**复制**指令文件的其余部分将复制到复制到我们容器新[层](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)。</span><span class="sxs-lookup"><span data-stu-id="bd286-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="bd286-191">我们正在发布应用程序与此**运行**指令。</span><span class="sxs-lookup"><span data-stu-id="bd286-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="bd286-192">[ **Dotnet 发布**](../tools/dotnet-publish.md)的命令编译应用程序、 读取通过在项目文件中，指定其依赖项并将结果集的文件发布到一个目录。</span><span class="sxs-lookup"><span data-stu-id="bd286-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="bd286-193">我们的应用程序发布与**版本**配置和输出到默认目录。</span><span class="sxs-lookup"><span data-stu-id="bd286-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="bd286-194">[**入口点**](https://docs.docker.com/engine/reference/builder/#entrypoint)指令允许要为可执行文件运行的容器。</span><span class="sxs-lookup"><span data-stu-id="bd286-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="bd286-195">现在你拥有 Dockerfile 的：</span><span class="sxs-lookup"><span data-stu-id="bd286-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="bd286-196">将你的应用程序复制到映像</span><span class="sxs-lookup"><span data-stu-id="bd286-196">copies your app to the image</span></span>
* <span data-ttu-id="bd286-197">对图像的应用程序的依赖关系</span><span class="sxs-lookup"><span data-stu-id="bd286-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="bd286-198">生成应用程序以运行为可执行文件</span><span class="sxs-lookup"><span data-stu-id="bd286-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="bd286-199">生成并运行 Hello.NET 核心 2.0 应用</span><span class="sxs-lookup"><span data-stu-id="bd286-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="bd286-200">基本 Docker 命令</span><span class="sxs-lookup"><span data-stu-id="bd286-200">Essential Docker commands</span></span>

<span data-ttu-id="bd286-201">这些 Docker 命令至关重要：</span><span class="sxs-lookup"><span data-stu-id="bd286-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="bd286-202">docker 生成</span><span class="sxs-lookup"><span data-stu-id="bd286-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="bd286-203">运行的 docker</span><span class="sxs-lookup"><span data-stu-id="bd286-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="bd286-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="bd286-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="bd286-205">docker 停止</span><span class="sxs-lookup"><span data-stu-id="bd286-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="bd286-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="bd286-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="bd286-207">docker rmi</span><span class="sxs-lookup"><span data-stu-id="bd286-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="bd286-208">docker 映像</span><span class="sxs-lookup"><span data-stu-id="bd286-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="bd286-209">生成并运行</span><span class="sxs-lookup"><span data-stu-id="bd286-209">Build and run</span></span>

<span data-ttu-id="bd286-210">你编写 dockerfile;现在 Docker 生成你的应用程序，然后运行容器。</span><span class="sxs-lookup"><span data-stu-id="bd286-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="bd286-211">从输出`docker build`命令应类似于下面的控制台输出：</span><span class="sxs-lookup"><span data-stu-id="bd286-211">The output from the `docker build` command should be similar to the following console output:</span></span>

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

<span data-ttu-id="bd286-212">正如您可以看到输出中，Docker 引擎将使用 Dockerfile 生成我们容器。</span><span class="sxs-lookup"><span data-stu-id="bd286-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="bd286-213">从输出`docker run`命令应类似于下面的控制台输出：</span><span class="sxs-lookup"><span data-stu-id="bd286-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="bd286-214">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="bd286-214">Congratulations!</span></span> <span data-ttu-id="bd286-215">正好有：</span><span class="sxs-lookup"><span data-stu-id="bd286-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="bd286-216">创建本地.NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="bd286-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="bd286-217">创建 Dockerfile 生成第一个容器</span><span class="sxs-lookup"><span data-stu-id="bd286-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="bd286-218">生成并运行您 Dockerized 的应用程序</span><span class="sxs-lookup"><span data-stu-id="bd286-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="bd286-219">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bd286-219">Next Steps</span></span>

<span data-ttu-id="bd286-220">下面是一些您可以采取的后续步骤：</span><span class="sxs-lookup"><span data-stu-id="bd286-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="bd286-221">.NET Docker 映像视频简介</span><span class="sxs-lookup"><span data-stu-id="bd286-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="bd286-222">Visual Studio、 Docker 和 Azure 容器实例最好一起使用 ！</span><span class="sxs-lookup"><span data-stu-id="bd286-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="bd286-223">Azure 快速入门的 docker</span><span class="sxs-lookup"><span data-stu-id="bd286-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="bd286-224">部署 Azure 的 Docker 上的应用程序</span><span class="sxs-lookup"><span data-stu-id="bd286-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="bd286-225">如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="bd286-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="bd286-226">此示例中使用的 docker 映像</span><span class="sxs-lookup"><span data-stu-id="bd286-226">Docker Images used in this sample</span></span>

<span data-ttu-id="bd286-227">在此示例中使用以下的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="bd286-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="bd286-228">相关资源</span><span class="sxs-lookup"><span data-stu-id="bd286-228">Related Resources</span></span>

* [<span data-ttu-id="bd286-229">.NET 核心 Docker 示例</span><span class="sxs-lookup"><span data-stu-id="bd286-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="bd286-230">Windows 容器上的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="bd286-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="bd286-231">.NET framework Docker 示例</span><span class="sxs-lookup"><span data-stu-id="bd286-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="bd286-232">ASP.NET 核心上 DockerHub</span><span class="sxs-lookup"><span data-stu-id="bd286-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="bd286-233">Dockerize.NET 核心应用程序-Docker 教程</span><span class="sxs-lookup"><span data-stu-id="bd286-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="bd286-234">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="bd286-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="bd286-235">部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="bd286-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)