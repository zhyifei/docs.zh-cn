---
title: 生成 .NET Core Docker 映像
description: 了解 Docker 映像和 .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: dotnet-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.custom: mvc
manager: wpickett
ms.workload:
- dotnetcore
ms.openlocfilehash: c1983be59b4a961cabd94915852e0cab7811682c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="9c8a4-103">为 .NET Core 应用程序生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="9c8a4-104">本教程重点介绍了如何在 Docker 上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="9c8a4-105">首先，我们探讨 Microsoft 维护和提供的各种不同的 Docker 映像，及其使用情况。
</span><span class="sxs-lookup"><span data-stu-id="9c8a4-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="9c8a4-106">然后讲解了如何生成和 Docker 化 ASP.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="9c8a4-107">在本教程中可学习：
</span><span class="sxs-lookup"><span data-stu-id="9c8a4-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9c8a4-108">了解 Microsoft.NET 核心 Docker 映像
</span><span class="sxs-lookup"><span data-stu-id="9c8a4-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="9c8a4-109">获取用于 dockerize 的 ASP.NET Core 示例应用程序
</span><span class="sxs-lookup"><span data-stu-id="9c8a4-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="9c8a4-110">在本地运行 ASP.NET 示例应用</span><span class="sxs-lookup"><span data-stu-id="9c8a4-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="9c8a4-111">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="9c8a4-112">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="9c8a4-113">Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="9c8a4-113">Docker Image Optimizations</span></span>

<span data-ttu-id="9c8a4-114">为开发人员生成 Docker 映像时，侧重于以下三种主要方案：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="9c8a4-115">用于开发 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="9c8a4-116">用于生成 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="9c8a4-117">用于运行 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="9c8a4-118">为什么是三个映像？</span><span class="sxs-lookup"><span data-stu-id="9c8a4-118">Why three images?</span></span>
<span data-ttu-id="9c8a4-119">因为在开发、生成和运行容器化应用程序时，具有不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="9c8a4-120">**开发：**优先级注重循环访问更改的速度以及调试更改的能力。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="9c8a4-121">与更改代码并且快速查看相比，映像的大小是否不是那么重要？</span><span class="sxs-lookup"><span data-stu-id="9c8a4-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="9c8a4-122">**生成：**此映像包含编译应用所需的所有内容，其中包括编译器和任何其他用于优化二进制文件的依赖项。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="9c8a4-123">可使用生成映像创建置于生产映像中的资产。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="9c8a4-124">生成映像用于持续集成或用于生成环境中。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="9c8a4-125">此方法允许生成代理在生成映像实例中编译和生成应用程序（包括所有必需的依赖项）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="9c8a4-126">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="9c8a4-127">**生产：**部署和启动映像的速度可以有多快？</span><span class="sxs-lookup"><span data-stu-id="9c8a4-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="9c8a4-128">此映像很小，因此从 Docker 注册表到 Docker 主机的网络性能得到了优化。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="9c8a4-129">已准备运行内容，以此实现从 Docker 运行到处理结果的最快时间。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="9c8a4-130">Docker 模型中不需要动态代码编译。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="9c8a4-131">放置在此映像中的内容将限制为运行应用程序所需的二进制文件和内容。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="9c8a4-132">例如，`dotnet publish` 输出包含：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="9c8a4-133">已编译的二进制文件</span><span class="sxs-lookup"><span data-stu-id="9c8a4-133">the compiled binaries</span></span>
    * <span data-ttu-id="9c8a4-134">.js 和 .css 文件</span><span class="sxs-lookup"><span data-stu-id="9c8a4-134">.js and .css files</span></span>


<span data-ttu-id="9c8a4-135">在生产映像中包括 `dotnet publish` 命令输出的原因是使生产映像保持最小大小。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-135">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="9c8a4-136">某些 .NET Core 映像共享不同标记之间的层，因此下载最新标记是一个相对轻量的过程。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="9c8a4-137">如果计算机上已有较早版本，此体系结构会降低所需的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="9c8a4-138">当多个应用程序在同一计算机上使用公共映像时，在公共映像之间共享内存。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="9c8a4-139">映像必须相同才可共享。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="9c8a4-140">Docker 映像变体</span><span class="sxs-lookup"><span data-stu-id="9c8a4-140">Docker image variations</span></span>

<span data-ttu-id="9c8a4-141">为了实现上述目标，我们在 [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) 下提供了映像变体。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="9c8a4-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) 此映像包含带有 .NET Core 和命令行工具 (CLI) 的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="9c8a4-143">此映像将映射到**开发方案**。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="9c8a4-144">可使用此映像进行本地开发、调试和单元测试。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="9c8a4-145">此映像还可用于**生成**方案。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="9c8a4-146">使用 `microsoft/dotnet:sdk` 始终都提供最新版本。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="9c8a4-147">如果不确定自己的需求，需使用 `microsoft/dotnet:<version>-sdk` 映像。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="9c8a4-148">作为“实际”映像，它旨在用作一次性容器（装载源代码并启动容器以启动应用）以及生成其他映像的基础映像。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="9c8a4-149">`microsoft/dotnet:<version>-runtime`：此映像包含 .NET Core（运行时和库），并且针对在生产环境中运行 .NET Core 应用进行了优化。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="9c8a4-150">备用映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-150">Alternative images</span></span>

<span data-ttu-id="9c8a4-151">除了开发、生成和生产的优化方案外，我们还提供了其他映像：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="9c8a4-152">`microsoft/dotnet:<version>-runtime-deps`：runtime-deps 映像包括具有 .NET Core 所需的所有本机依赖项的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="9c8a4-153">此映像适用于[独立应用程序](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="9c8a4-154">每个变体的最新版本：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="9c8a4-155">`microsoft/dotnet` 或 `microsoft/dotnet:latest`（SDK 映像的别名）</span><span class="sxs-lookup"><span data-stu-id="9c8a4-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="9c8a4-156">要了解的示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-156">Samples to explore</span></span>

* <span data-ttu-id="9c8a4-157">[此 ASP.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="9c8a4-158">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="9c8a4-159">此 .NET Core Docker 示例演示了[生成 .NET Core 应用程序的 Docker 映像以用于生产](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="9c8a4-160">第一个 ASP.NET Core Docker 应用</span><span class="sxs-lookup"><span data-stu-id="9c8a4-160">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="9c8a4-161">本教程对要 Docker 化的应用使用 ASP.NET Core Docker 示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-161">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="9c8a4-162">此 ASP.NET Core Docker 示例应用程序演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳做法模式。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-162">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="9c8a4-163">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-163">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="9c8a4-164">该示例 Dockerfile 基于 ASP.NET Core 运行时 Docker 基础映像创建 ASP.NET Core 应用程序 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-164">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="9c8a4-165">它使用 [Docker 多阶段生成功能](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-165">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="9c8a4-166">基于较大的 ASP.NET Core 生成 Docker 基础映像在容器中生成示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-166">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="9c8a4-167">基于较小的 ASP.NET Core Docker 运行时基础映像将最终生成结果复制到 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-167">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="9c8a4-168">生成映像包含生成应用程序所需的工具，而运行时映像不包括这些工具。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-168">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9c8a4-169">系统必备</span><span class="sxs-lookup"><span data-stu-id="9c8a4-169">Prerequisites</span></span>

<span data-ttu-id="9c8a4-170">要进行生成并运行，请安装以下各项：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-170">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="9c8a4-171">.NET Core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="9c8a4-171">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="9c8a4-172">安装 [.NET Core SDK 2.0](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-172">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="9c8a4-173">安装常用的代码编辑器（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-173">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="9c8a4-174">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="9c8a4-174">Need to install a code editor?</span></span> <span data-ttu-id="9c8a4-175">试用 [Visual Studio](https://visualstudio.com/downloads)！</span><span class="sxs-lookup"><span data-stu-id="9c8a4-175">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="9c8a4-176">安装 Docker 客户端</span><span class="sxs-lookup"><span data-stu-id="9c8a4-176">Installing Docker Client</span></span>

<span data-ttu-id="9c8a4-177">安装 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) 或更高版本的 Docker 客户端。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-177">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="9c8a4-178">可在以下位置安装 Docker 客户端：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-178">The Docker client can be installed in:</span></span>

* <span data-ttu-id="9c8a4-179">Linux 分布</span><span class="sxs-lookup"><span data-stu-id="9c8a4-179">Linux distributions</span></span>

   * [<span data-ttu-id="9c8a4-180">CentOS</span><span class="sxs-lookup"><span data-stu-id="9c8a4-180">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="9c8a4-181">Debian</span><span class="sxs-lookup"><span data-stu-id="9c8a4-181">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="9c8a4-182">Fedora</span><span class="sxs-lookup"><span data-stu-id="9c8a4-182">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="9c8a4-183">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="9c8a4-183">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="9c8a4-184">macOS</span><span class="sxs-lookup"><span data-stu-id="9c8a4-184">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="9c8a4-185">[Windows](https://docs.docker.com/docker-for-windows/)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-185">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="9c8a4-186">为示例存储库安装 Git</span><span class="sxs-lookup"><span data-stu-id="9c8a4-186">Installing Git for sample repository</span></span>

* <span data-ttu-id="9c8a4-187">如果要克隆存储库，请安装 [git](https://git-scm.com/download)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-187">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="9c8a4-188">获取示例应用程序</span><span class="sxs-lookup"><span data-stu-id="9c8a4-188">Getting the sample application</span></span>

<span data-ttu-id="9c8a4-189">获取该示例的最简单方法是使用以下指令克隆包含 git 的[示例存储库](https://github.com/dotnet/dotnet-docker-samples)：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-189">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="9c8a4-190">也可以从 .NET Core Docker 示例存储库中下载 zip 格式的存储库（其大小较小）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-190">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="9c8a4-191">在本地运行 ASP.NET 应用</span><span class="sxs-lookup"><span data-stu-id="9c8a4-191">Run the ASP.NET app locally</span></span>

<span data-ttu-id="9c8a4-192">对于引用点，在容器化应用程序之前，请先在本地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-192">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="9c8a4-193">可使用以下命令，通过 .NET Core 2.0 SDK 在本地生成和运行应用程序（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-193">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="9c8a4-194">应用程序启动后，在 Web 浏览器中访问 **http://localhost:5000**。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-194">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="9c8a4-195">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-195">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="9c8a4-196">可使用以下命令，通过 Linux 容器在 Docker 中生成和运行示例（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-196">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="9c8a4-197">`docker run` 的“-p”参数将本地计算机上的端口 5000 映射到容器中的端口 80（该端口映射形式为 `host:container`）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-197">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="9c8a4-198">有关详细信息，请参阅命令行参数中的 [docker run](https://docs.docker.com/engine/reference/commandline/exec/) 引用。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-198">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="9c8a4-199">应用程序启动后，在 Web 浏览器中访问 **http://localhost:5000**。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-199">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="9c8a4-200">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-200">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="9c8a4-201">可使用以下命令，通过 Windows 容器在 Docker 中生成和运行示例（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-201">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="9c8a4-202">使用 Windows 容器时，必须直接在浏览器中转到容器 IP 地址（而不是 http://localhost)）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-202">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="9c8a4-203">可通过以下步骤获取容器的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-203">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="9c8a4-204">打开另一个命令提示符。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-204">Open up another command prompt.</span></span>
* <span data-ttu-id="9c8a4-205">运行 `docker ps`，查看正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-205">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="9c8a4-206">其中应包含“Aspnetcore_sample”。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-206">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="9c8a4-207">运行 `docker exec aspnetcore_sample ipconfig`。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-207">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="9c8a4-208">将容器 IP 地址复制并粘贴到浏览器中（例如，172.29.245.43）。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-208">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="9c8a4-209">Docker exec 支持通过名称或哈希标识容器。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-209">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="9c8a4-210">示例中使用了名称 (aspnetcore_sample)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-210">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="9c8a4-211">请查看以下示例，了解如何获取正在运行的 Windows 容器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-211">See the following example of how to get the IP address of a running Windows container.</span></span>

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

> [!NOTE]
> <span data-ttu-id="9c8a4-212">Docker exec 在正在运行的容器中运行新命令。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-212">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="9c8a4-213">有关详细信息，请参阅命令行参数中的 [docker exec 引用](https://docs.docker.com/engine/reference/commandline/exec/)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-213">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="9c8a4-214">可使用 [dotnet publish](../tools/dotnet-publish.md) 命令生成已准备好在本地部署到生产环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-214">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!NOTE]
> <span data-ttu-id="9c8a4-215">-c release 参数用于在发布模式（默认为调试模式）下生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-215">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="9c8a4-216">有关详细信息，请参阅命令行参数中的 [dotnet run 引用](../tools/dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-216">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="9c8a4-217">可使用以下命令在 Windows 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-217">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="9c8a4-218">可使用以下命令在 Linux 或 macOS 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-218">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="9c8a4-219">此示例中使用的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-219">Docker Images used in this sample</span></span>

<span data-ttu-id="9c8a4-220">此示例中使用了以下 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-220">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="9c8a4-221">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="9c8a4-221">Congratulations!</span></span> <span data-ttu-id="9c8a4-222">你刚才已：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-222">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="9c8a4-223">了解 Microsoft .NET Core Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9c8a4-223">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="9c8a4-224">获取要 Docker 化的 ASP.NET Core 示例应用</span><span class="sxs-lookup"><span data-stu-id="9c8a4-224">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="9c8a4-225">在本地运行 ASP.NET 示例应用</span><span class="sxs-lookup"><span data-stu-id="9c8a4-225">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="9c8a4-226">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-226">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="9c8a4-227">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-227">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="9c8a4-228">**后续步骤**</span><span class="sxs-lookup"><span data-stu-id="9c8a4-228">**Next Steps**</span></span>

<span data-ttu-id="9c8a4-229">下面是一些可以采取的后续步骤：</span><span class="sxs-lookup"><span data-stu-id="9c8a4-229">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="9c8a4-230">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="9c8a4-230">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="9c8a4-231">将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="9c8a4-231">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="9c8a4-232">使用 Visual Studio Code 进行调试</span><span class="sxs-lookup"><span data-stu-id="9c8a4-232">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="9c8a4-233">在云中使用 Visual Studio for Mac、容器和无服务器代码</span><span class="sxs-lookup"><span data-stu-id="9c8a4-233">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="9c8a4-234">Docker 和 Visual Studio for Mac Lab 入门</span><span class="sxs-lookup"><span data-stu-id="9c8a4-234">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!NOTE]
> <span data-ttu-id="9c8a4-235">如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="9c8a4-235">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
