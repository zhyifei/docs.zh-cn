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
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="7247a-104">为 .NET Core 应用程序生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="7247a-105">在本教程中，我们重点说明如何在 Docker 上使用.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="7247a-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="7247a-106">首先，我们探讨不同的 Docker 映像由 Microsoft 和使用情况下维护和提供。</span><span class="sxs-lookup"><span data-stu-id="7247a-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="7247a-107">我们然后了解如何构建和 dockerize ASP.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="7247a-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="7247a-108">在本教程过程中，你学习：</span><span class="sxs-lookup"><span data-stu-id="7247a-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="7247a-109">了解有关 Microsoft.NET 核心 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="7247a-110">获取 ASP.NET Core Dockerize 到示例应用程序</span><span class="sxs-lookup"><span data-stu-id="7247a-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="7247a-111">本地运行 ASP.NET 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="7247a-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="7247a-112">生成并运行该示例使用 Docker 的 Linux 容器</span><span class="sxs-lookup"><span data-stu-id="7247a-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="7247a-113">生成并使用用于 Windows 的 Docker 容器运行示例</span><span class="sxs-lookup"><span data-stu-id="7247a-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="7247a-114">Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="7247a-114">Docker Image Optimizations</span></span>

<span data-ttu-id="7247a-115">为开发人员生成 Docker 映像时，侧重于以下三种主要方案：</span><span class="sxs-lookup"><span data-stu-id="7247a-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="7247a-116">用于开发 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="7247a-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="7247a-117">用于生成 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="7247a-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="7247a-118">用于运行 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="7247a-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="7247a-119">为什么是三个映像？</span><span class="sxs-lookup"><span data-stu-id="7247a-119">Why three images?</span></span>
<span data-ttu-id="7247a-120">当开发、 构建和运行容器化应用程序时，我们具有不同的优先级别。</span><span class="sxs-lookup"><span data-stu-id="7247a-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="7247a-121">**开发：**优先级主要是为了快速循环更改和调试所做的更改的能力。</span><span class="sxs-lookup"><span data-stu-id="7247a-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="7247a-122">图像的大小不为重要，而是你可以对代码进行更改并快速查看它们？</span><span class="sxs-lookup"><span data-stu-id="7247a-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="7247a-123">**生成中：**此映像包含将应用程序，其中包括编译器和任何其他依赖项以优化的二进制文件编译所需的一切。</span><span class="sxs-lookup"><span data-stu-id="7247a-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="7247a-124">生成映像用于创建你将放入生产映像的资产。</span><span class="sxs-lookup"><span data-stu-id="7247a-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="7247a-125">将用于构建映像，持续集成，或在生成环境中。</span><span class="sxs-lookup"><span data-stu-id="7247a-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="7247a-126">此方法允许用于编译和生成中生成映像实例应用程序 （具有所有必需的依赖项） 的生成代理。</span><span class="sxs-lookup"><span data-stu-id="7247a-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="7247a-127">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="7247a-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="7247a-128">**生产：**速度可以部署和启动你的映像？</span><span class="sxs-lookup"><span data-stu-id="7247a-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="7247a-129">此映像很小，因此从 Docker 注册表到 Docker 主机的网络性能进行了优化。</span><span class="sxs-lookup"><span data-stu-id="7247a-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="7247a-130">已准备运行内容，以此实现从 Docker 运行到处理结果的最快时间。</span><span class="sxs-lookup"><span data-stu-id="7247a-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="7247a-131">Docker 模型中不需要动态代码编译。</span><span class="sxs-lookup"><span data-stu-id="7247a-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="7247a-132">放置在此映像中的内容将限制为运行应用程序所需的二进制文件和内容。</span><span class="sxs-lookup"><span data-stu-id="7247a-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="7247a-133">例如，`dotnet publish`输出包含：</span><span class="sxs-lookup"><span data-stu-id="7247a-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="7247a-134">已编译的二进制文件</span><span class="sxs-lookup"><span data-stu-id="7247a-134">the compiled binaries</span></span>
    * <span data-ttu-id="7247a-135">.js 和.css 文件</span><span class="sxs-lookup"><span data-stu-id="7247a-135">.js and .css files</span></span>


<span data-ttu-id="7247a-136">原因包括`dotnet publish`你生产的映像中的命令输出是保持其最小大小。</span><span class="sxs-lookup"><span data-stu-id="7247a-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="7247a-137">一些.NET Core 映像共享不同标记，因此下载最新的标记是相对轻量的过程之间的层。</span><span class="sxs-lookup"><span data-stu-id="7247a-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="7247a-138">如果您的计算机上已有较旧版本，此体系结构会降低所需的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="7247a-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="7247a-139">当多个应用程序相同的计算机上使用公共映像时，常见的映像之间共享内存。</span><span class="sxs-lookup"><span data-stu-id="7247a-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="7247a-140">图像必须为相同共享。</span><span class="sxs-lookup"><span data-stu-id="7247a-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="7247a-141">Docker 映像变体</span><span class="sxs-lookup"><span data-stu-id="7247a-141">Docker image variations</span></span>

<span data-ttu-id="7247a-142">若要实现上述目标，我们提供映像下的变体[ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="7247a-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="7247a-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) 此映像包含.NET 核心 SDK，其中包含.NET 核心和命令行工具 (CLI)。</span><span class="sxs-lookup"><span data-stu-id="7247a-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="7247a-144">此映像将映射到**开发方案**。</span><span class="sxs-lookup"><span data-stu-id="7247a-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="7247a-145">此映像用于本地开发、 调试和单元测试。</span><span class="sxs-lookup"><span data-stu-id="7247a-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="7247a-146">此映像还可用于**生成**方案。</span><span class="sxs-lookup"><span data-stu-id="7247a-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="7247a-147">使用`microsoft/dotnet:sdk`始终为你提供最新版本。</span><span class="sxs-lookup"><span data-stu-id="7247a-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="7247a-148">如果您不确定你的需求，你想要使用`microsoft/dotnet:<version>-sdk`映像。</span><span class="sxs-lookup"><span data-stu-id="7247a-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="7247a-149">作为"事实上"图像，它旨在用作 throw 远容器 （装入你的源代码和启动容器启动你的应用程序），并作为基本映像，以生成从其他映像。</span><span class="sxs-lookup"><span data-stu-id="7247a-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="7247a-150">`microsoft/dotnet:<version>-runtime`： 此映像包含.NET 核心 （运行时和库），非常适合运行.NET Core 应用**生产**。</span><span class="sxs-lookup"><span data-stu-id="7247a-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="7247a-151">备用映像</span><span class="sxs-lookup"><span data-stu-id="7247a-151">Alternative images</span></span>

<span data-ttu-id="7247a-152">除了开发、生成和生产的优化方案外，我们还提供了其他映像：</span><span class="sxs-lookup"><span data-stu-id="7247a-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="7247a-153">`microsoft/dotnet:<version>-runtime-deps`:**运行时 deps**映像包含操作系统所有所需的.NET 核心的本机依赖项。</span><span class="sxs-lookup"><span data-stu-id="7247a-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="7247a-154">此映像适用[自包含的应用程序](https://docs.microsoft.com/dotnet/core/deploying/index)。</span><span class="sxs-lookup"><span data-stu-id="7247a-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="7247a-155">每个变体的最新版本：</span><span class="sxs-lookup"><span data-stu-id="7247a-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="7247a-156">`microsoft/dotnet`或`microsoft/dotnet:latest`（别名 SDK 映像）</span><span class="sxs-lookup"><span data-stu-id="7247a-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="7247a-157">若要浏览的示例</span><span class="sxs-lookup"><span data-stu-id="7247a-157">Samples to explore</span></span>

* <span data-ttu-id="7247a-158">[此 ASP.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。</span><span class="sxs-lookup"><span data-stu-id="7247a-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="7247a-159">示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="7247a-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="7247a-160">.NET 核心 Docker 演示的最佳做法模式[构建的生产.NET 核心应用程序的 Docker 映像。](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="7247a-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="7247a-161">第一个 ASP.NET 核心 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="7247a-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="7247a-162">对于本教程中，可让我们想要 dockerize 应用使用的 ASP.NET 核心 Docker 示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="7247a-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="7247a-163">此 ASP.NET 核心 Docker 示例应用程序演示了针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。</span><span class="sxs-lookup"><span data-stu-id="7247a-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="7247a-164">示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="7247a-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="7247a-165">示例 Dockerfile 创建基于 ASP.NET 核心运行时 Docker 基本映像的 ASP.NET Core 应用程序 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="7247a-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="7247a-166">它使用[Docker 多阶段生成功能](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)到：</span><span class="sxs-lookup"><span data-stu-id="7247a-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="7247a-167">生成基于容器中的示例**更大**ASP.NET 核心生成 Docker 的基本映像</span><span class="sxs-lookup"><span data-stu-id="7247a-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="7247a-168">将最终生成结果复制到 Docker 映像基于**较小**ASP.NET Core Docker 运行时的基本映像</span><span class="sxs-lookup"><span data-stu-id="7247a-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="7247a-169">生成映像包含所需的工具，而运行时映像则不生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="7247a-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7247a-170">先决条件</span><span class="sxs-lookup"><span data-stu-id="7247a-170">Prerequisites</span></span>

<span data-ttu-id="7247a-171">若要生成并运行，请安装以下各项：</span><span class="sxs-lookup"><span data-stu-id="7247a-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="7247a-172">.NET 核心 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="7247a-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="7247a-173">安装[.NET 核心 SDK 2.0](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="7247a-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="7247a-174">如果你尚未，安装最喜欢的代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="7247a-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="7247a-175">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="7247a-175">Need to install a code editor?</span></span> <span data-ttu-id="7247a-176">请尝试[Visual Studio](https://visualstudio.com/downloads)！</span><span class="sxs-lookup"><span data-stu-id="7247a-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="7247a-177">安装 Docker 客户端</span><span class="sxs-lookup"><span data-stu-id="7247a-177">Installing Docker Client</span></span>

<span data-ttu-id="7247a-178">安装[Docker 17.06](https://docs.docker.com/release-notes/docker-ce/)或更高版本的 Docker 客户端。</span><span class="sxs-lookup"><span data-stu-id="7247a-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="7247a-179">可以在安装 Docker 客户端：</span><span class="sxs-lookup"><span data-stu-id="7247a-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="7247a-180">Linux 分发</span><span class="sxs-lookup"><span data-stu-id="7247a-180">Linux distributions</span></span>

   * [<span data-ttu-id="7247a-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="7247a-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="7247a-182">Debian</span><span class="sxs-lookup"><span data-stu-id="7247a-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="7247a-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="7247a-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="7247a-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7247a-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="7247a-185">macOS</span><span class="sxs-lookup"><span data-stu-id="7247a-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="7247a-186">[Windows](https://docs.docker.com/docker-for-windows/)。</span><span class="sxs-lookup"><span data-stu-id="7247a-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="7247a-187">为示例存储库安装 Git</span><span class="sxs-lookup"><span data-stu-id="7247a-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="7247a-188">安装[git](https://git-scm.com/download)如果你想要克隆存储库。</span><span class="sxs-lookup"><span data-stu-id="7247a-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="7247a-189">获取示例应用程序</span><span class="sxs-lookup"><span data-stu-id="7247a-189">Getting the sample application</span></span>

<span data-ttu-id="7247a-190">获取该示例的最简单方法是通过克隆[示例存储库](https://github.com/dotnet/dotnet-docker-samples)使用 git，使用以下说明：</span><span class="sxs-lookup"><span data-stu-id="7247a-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="7247a-191">你也可以作为.NET 核心 Docker 示例存储库从 zip 下载 （它位于小） 的存储库。</span><span class="sxs-lookup"><span data-stu-id="7247a-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="7247a-192">本地运行 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="7247a-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="7247a-193">对于引用点，在容器化应用程序之前，请先在本地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="7247a-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="7247a-194">你可以本地生成并运行应用程序使用.NET 核心 2.0 SDK 使用以下命令 （的说明假定存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="7247a-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="7247a-195">在应用程序启动后，请访问**http://localhost:5000/**在 web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="7247a-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="7247a-196">生成并运行该示例使用 Docker 的 Linux 容器</span><span class="sxs-lookup"><span data-stu-id="7247a-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="7247a-197">你可以生成并运行在 Docker 使用 Linux 容器使用以下命令 （的说明假定存储库的根目录） 中的示例：</span><span class="sxs-lookup"><span data-stu-id="7247a-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="7247a-198">`docker run` -P 地图端口 5000 上你本地计算机添加到端口 80 容器中的自变量 (该端口映射窗体是`host:container`)。</span><span class="sxs-lookup"><span data-stu-id="7247a-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="7247a-199">有关详细信息，请参阅[docker 运行](https://docs.docker.com/engine/reference/commandline/exec/)命令行参数的引用。</span><span class="sxs-lookup"><span data-stu-id="7247a-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="7247a-200">在应用程序启动后，请访问**http://localhost:5000/**在 web 浏览器中。</span><span class="sxs-lookup"><span data-stu-id="7247a-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="7247a-201">生成并使用用于 Windows 的 Docker 容器运行示例</span><span class="sxs-lookup"><span data-stu-id="7247a-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="7247a-202">你可以生成并运行在 Docker 使用 Windows 容器使用以下命令 （的说明假定存储库的根目录） 中的示例：</span><span class="sxs-lookup"><span data-stu-id="7247a-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="7247a-203">必须导航到**容器 IP 地址**（而不是 http://localhost) 在浏览器中直接使用 Windows 容器时。</span><span class="sxs-lookup"><span data-stu-id="7247a-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="7247a-204">你可以通过以下步骤将容器的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="7247a-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="7247a-205">打开另一个命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7247a-205">Open up another command prompt.</span></span>
* <span data-ttu-id="7247a-206">运行`docker ps`以查看你正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="7247a-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="7247a-207">"Aspnetcore_sample"容器应在那里。</span><span class="sxs-lookup"><span data-stu-id="7247a-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="7247a-208">运行 `docker exec aspnetcore_sample ipconfig`。</span><span class="sxs-lookup"><span data-stu-id="7247a-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="7247a-209">将容器 IP 地址复制并粘贴到你的浏览器 (例如，172.29.245.43)。</span><span class="sxs-lookup"><span data-stu-id="7247a-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="7247a-210">Docker exec 支持标识容器名称或哈希。</span><span class="sxs-lookup"><span data-stu-id="7247a-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="7247a-211">我们示例中使用的名称 (aspnetcore_sample)。</span><span class="sxs-lookup"><span data-stu-id="7247a-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="7247a-212">请参阅如何获取正在运行的 Windows 容器的 IP 地址的下面的示例。</span><span class="sxs-lookup"><span data-stu-id="7247a-212">See the following example of how to get the IP address of a running Windows container.</span></span>

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
> <span data-ttu-id="7247a-213">Docker exec 在正在运行的容器中运行新的命令。</span><span class="sxs-lookup"><span data-stu-id="7247a-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="7247a-214">有关详细信息，请参阅[docker exec 参考](https://docs.docker.com/engine/reference/commandline/exec/)命令行参数。</span><span class="sxs-lookup"><span data-stu-id="7247a-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="7247a-215">您可以生成的应用程序已准备好部署到生产环境使用本地[dotnet 发布](../tools/dotnet-publish.md)命令。</span><span class="sxs-lookup"><span data-stu-id="7247a-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="7247a-216">-C 版本自变量生成应用程序在发布模式下 （默认值为调试模式下）。</span><span class="sxs-lookup"><span data-stu-id="7247a-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="7247a-217">有关详细信息，请参阅[dotnet run 参考](../tools/dotnet-run.md)命令行参数。</span><span class="sxs-lookup"><span data-stu-id="7247a-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="7247a-218">你可以上运行应用程序**Windows**使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="7247a-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="7247a-219">你可以上运行应用程序**Linux**或**macOS**使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="7247a-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="7247a-220">此示例中使用的 docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-220">Docker Images used in this sample</span></span>

<span data-ttu-id="7247a-221">在此示例中使用以下的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="7247a-222">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="7247a-222">Congratulations!</span></span> <span data-ttu-id="7247a-223">正好有：</span><span class="sxs-lookup"><span data-stu-id="7247a-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="7247a-224">所了解的有关 Microsoft.NET 核心 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="7247a-225">有 Dockerize 到示例应用程序的 ASP.NET 核心</span><span class="sxs-lookup"><span data-stu-id="7247a-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="7247a-226">本地运行 ASP.NET 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="7247a-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="7247a-227">构建并使用 Docker 的 Linux 容器运行示例</span><span class="sxs-lookup"><span data-stu-id="7247a-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="7247a-228">生成并与用于 Windows 的 Docker 容器中运行示例</span><span class="sxs-lookup"><span data-stu-id="7247a-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="7247a-229">**后续步骤**</span><span class="sxs-lookup"><span data-stu-id="7247a-229">**Next Steps**</span></span>

<span data-ttu-id="7247a-230">下面是一些您可以采取的后续步骤：</span><span class="sxs-lookup"><span data-stu-id="7247a-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="7247a-231">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="7247a-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="7247a-232">部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="7247a-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="7247a-233">使用 Visual Studio 代码进行调试</span><span class="sxs-lookup"><span data-stu-id="7247a-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="7247a-234">获取之手使用 Visual Studio Mac、 容器和无服务器代码在云中</span><span class="sxs-lookup"><span data-stu-id="7247a-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="7247a-235">开始使用 Docker 和 Visual Studio Mac 实验室</span><span class="sxs-lookup"><span data-stu-id="7247a-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="7247a-236">如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="7247a-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
