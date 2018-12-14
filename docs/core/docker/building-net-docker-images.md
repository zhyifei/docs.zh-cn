---
title: Docker 映像概述 - .NET Core
description: 了解如何使用 Docker 注册表中发布的 .NET Core Docker 映像。 你还将了解如何拉取映像和生成自己的映像。
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 34ff6ce7d990412fa0ac4896d1e2e39b307681f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145827"
---
# <a name="learn-about-docker-images-for-net-core"></a><span data-ttu-id="49729-104">了解适用于 .NET Core 的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="49729-104">Learn about Docker images for .NET Core</span></span>

<span data-ttu-id="49729-105">本教程重点介绍了如何在 Docker 上使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="49729-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="49729-106">首先，我们探讨 Microsoft 维护和提供的各种不同的 Docker 映像，及其使用情况。</span><span class="sxs-lookup"><span data-stu-id="49729-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="49729-107">然后讲解了如何生成和 Docker 化 ASP.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="49729-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="49729-108">在本教程中可学习：</span><span class="sxs-lookup"><span data-stu-id="49729-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="49729-109">了解 Microsoft.NET 核心 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="49729-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="49729-110">获取用于 dockerize 的 ASP.NET Core 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="49729-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="49729-111">在本地运行 ASP.NET 示例应用</span><span class="sxs-lookup"><span data-stu-id="49729-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="49729-112">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="49729-113">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="49729-114">Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="49729-114">Docker Image Optimizations</span></span>

<span data-ttu-id="49729-115">为开发人员生成 Docker 映像时，侧重于以下三种主要方案：</span><span class="sxs-lookup"><span data-stu-id="49729-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="49729-116">用于开发 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="49729-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="49729-117">用于生成 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="49729-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="49729-118">用于运行 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="49729-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="49729-119">为什么是三个映像？</span><span class="sxs-lookup"><span data-stu-id="49729-119">Why three images?</span></span>
<span data-ttu-id="49729-120">因为在开发、生成和运行容器化应用程序时，具有不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="49729-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="49729-121">**开发：** 优先级注重循环访问更改的速度以及调试更改的能力。</span><span class="sxs-lookup"><span data-stu-id="49729-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="49729-122">与更改代码并且快速查看相比，映像的大小是否不是那么重要？</span><span class="sxs-lookup"><span data-stu-id="49729-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="49729-123">**生成：** 此映像包含编译应用所需的所有内容，其中包括编译器和任何其他用于优化二进制文件的依赖项。</span><span class="sxs-lookup"><span data-stu-id="49729-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="49729-124">可使用生成映像创建置于生产映像中的资产。</span><span class="sxs-lookup"><span data-stu-id="49729-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="49729-125">生成映像用于持续集成或用于生成环境中。</span><span class="sxs-lookup"><span data-stu-id="49729-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="49729-126">此方法允许生成代理在生成映像实例中编译和生成应用程序（包括所有必需的依赖项）。</span><span class="sxs-lookup"><span data-stu-id="49729-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="49729-127">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="49729-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="49729-128">**生产：** 部署和启动映像的速度可以有多快？</span><span class="sxs-lookup"><span data-stu-id="49729-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="49729-129">此映像很小，因此从 Docker 注册表到 Docker 主机的网络性能得到了优化。</span><span class="sxs-lookup"><span data-stu-id="49729-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="49729-130">已准备运行内容，以此实现从 Docker 运行到处理结果的最快时间。</span><span class="sxs-lookup"><span data-stu-id="49729-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="49729-131">Docker 模型中不需要动态代码编译。</span><span class="sxs-lookup"><span data-stu-id="49729-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="49729-132">放置在此映像中的内容将限制为运行应用程序所需的二进制文件和内容。</span><span class="sxs-lookup"><span data-stu-id="49729-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="49729-133">例如，`dotnet publish` 输出包含：</span><span class="sxs-lookup"><span data-stu-id="49729-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="49729-134">已编译的二进制文件</span><span class="sxs-lookup"><span data-stu-id="49729-134">the compiled binaries</span></span>
    * <span data-ttu-id="49729-135">.js 和 .css 文件</span><span class="sxs-lookup"><span data-stu-id="49729-135">.js and .css files</span></span>


<span data-ttu-id="49729-136">在生产映像中包括 `dotnet publish` 命令输出的原因是使生产映像保持最小大小。</span><span class="sxs-lookup"><span data-stu-id="49729-136">The reason to include the `dotnet publish` command output in your production image is to keep its size to a minimum.</span></span>

<span data-ttu-id="49729-137">某些 .NET Core 映像共享不同标记之间的层，因此下载最新标记是一个相对轻量的过程。</span><span class="sxs-lookup"><span data-stu-id="49729-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="49729-138">如果计算机上已有较早版本，此体系结构会降低所需的磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="49729-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="49729-139">当多个应用程序在同一计算机上使用公共映像时，在公共映像之间共享内存。</span><span class="sxs-lookup"><span data-stu-id="49729-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="49729-140">映像必须相同才可共享。</span><span class="sxs-lookup"><span data-stu-id="49729-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="49729-141">Docker 映像变体</span><span class="sxs-lookup"><span data-stu-id="49729-141">Docker image variations</span></span>

<span data-ttu-id="49729-142">为了实现上述目标，我们在 [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) 下提供了映像变体。</span><span class="sxs-lookup"><span data-stu-id="49729-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="49729-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) 此映像包含带有 .NET Core 和命令行工具 (CLI) 的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="49729-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="49729-144">此映像将映射到**开发方案**。</span><span class="sxs-lookup"><span data-stu-id="49729-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="49729-145">可使用此映像进行本地开发、调试和单元测试。</span><span class="sxs-lookup"><span data-stu-id="49729-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="49729-146">此映像还可用于**生成**方案。</span><span class="sxs-lookup"><span data-stu-id="49729-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="49729-147">使用 `microsoft/dotnet:sdk` 始终都提供最新版本。</span><span class="sxs-lookup"><span data-stu-id="49729-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="49729-148">如果不确定自己的需求，需使用 `microsoft/dotnet:<version>-sdk` 映像。</span><span class="sxs-lookup"><span data-stu-id="49729-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="49729-149">作为“实际”映像，它旨在用作一次性容器（装载源代码并启动容器以启动应用）以及生成其他映像的基础映像。</span><span class="sxs-lookup"><span data-stu-id="49729-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="49729-150">`microsoft/dotnet:<version>-runtime`：此映像包含 .NET Core（运行时和库），并且针对在生产环境中运行 .NET Core 应用进行了优化。</span><span class="sxs-lookup"><span data-stu-id="49729-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="49729-151">备用映像</span><span class="sxs-lookup"><span data-stu-id="49729-151">Alternative images</span></span>

<span data-ttu-id="49729-152">除了开发、生成和生产的优化方案外，我们还提供了其他映像：</span><span class="sxs-lookup"><span data-stu-id="49729-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="49729-153">`microsoft/dotnet:<version>-runtime-deps`：runtime-deps 映像包括具有 .NET Core 所需的所有本机依赖项的操作系统。</span><span class="sxs-lookup"><span data-stu-id="49729-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="49729-154">此映像适用于[独立应用程序](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="49729-154">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="49729-155">每个变体的最新版本：</span><span class="sxs-lookup"><span data-stu-id="49729-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="49729-156">`microsoft/dotnet` 或 `microsoft/dotnet:latest`（SDK 映像的别名）</span><span class="sxs-lookup"><span data-stu-id="49729-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="49729-157">要了解的示例</span><span class="sxs-lookup"><span data-stu-id="49729-157">Samples to explore</span></span>

* <span data-ttu-id="49729-158">[此 ASP.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp)演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="49729-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="49729-159">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="49729-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="49729-160">此 .NET Core Docker 示例演示了[生成 .NET Core 应用程序的 Docker 映像以用于生产](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="49729-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span></span>

## <a name="forward-the-request-scheme-and-original-ip-address"></a><span data-ttu-id="49729-161">转发请求方案和原始 IP 地址</span><span class="sxs-lookup"><span data-stu-id="49729-161">Forward the request scheme and original IP address</span></span>

<span data-ttu-id="49729-162">代理服务器、负载均衡器和其他网络设备通常会在请求到达容器化应用之前隐藏有关请求的信息：</span><span class="sxs-lookup"><span data-stu-id="49729-162">Proxy servers, load balancers, and other network appliances often obscure information about a request before it reaches the containerized app:</span></span>

* <span data-ttu-id="49729-163">当通过 HTTP 代理 HTTPS 请求时，原方案 (HTTPS) 将丢失，并且必须在标头中转接。</span><span class="sxs-lookup"><span data-stu-id="49729-163">When HTTPS requests are proxied over HTTP, the original scheme (HTTPS) is lost and must be forwarded in a header.</span></span>
* <span data-ttu-id="49729-164">由于应用收到来自代理的请求，而不是 Internet 或公司网络上请求的真实源，因此原始客户端 IP 地址也必须在标头中转接。</span><span class="sxs-lookup"><span data-stu-id="49729-164">Because an app receives a request from the proxy and not its true source on the Internet or corporate network, the original client IP address must also be forwarded in a header.</span></span>

<span data-ttu-id="49729-165">此信息在请求处理中可能很重要，例如在重定向、身份验证、链接生成、策略评估和客户端地理位置中。</span><span class="sxs-lookup"><span data-stu-id="49729-165">This information may be important in request processing, for example in redirects, authentication, link generation, policy evaluation, and client geolocation.</span></span>

<span data-ttu-id="49729-166">要将方案和原始 IP 地址转发到 ASP.NET Core 容器化应用，请使用 Forwarded Headers 中间件。</span><span class="sxs-lookup"><span data-stu-id="49729-166">To forward the scheme and original IP address to a containerized ASP.NET Core app, use Forwarded Headers Middleware.</span></span> <span data-ttu-id="49729-167">有关详细信息，请参阅[配置 ASP.NET Core 以使用代理服务器和负载均衡器](/aspnet/core/host-and-deploy/proxy-load-balancer)。</span><span class="sxs-lookup"><span data-stu-id="49729-167">For more information, see [Configure ASP.NET Core to work with proxy servers and load balancers](/aspnet/core/host-and-deploy/proxy-load-balancer).</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="49729-168">第一个 ASP.NET Core Docker 应用</span><span class="sxs-lookup"><span data-stu-id="49729-168">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="49729-169">本教程对要 Docker 化的应用使用 ASP.NET Core Docker 示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-169">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="49729-170">此 ASP.NET Core Docker 示例应用程序演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳做法模式。</span><span class="sxs-lookup"><span data-stu-id="49729-170">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="49729-171">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="49729-171">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="49729-172">该示例 Dockerfile 基于 ASP.NET Core 运行时 Docker 基础映像创建 ASP.NET Core 应用程序 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="49729-172">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="49729-173">它使用 [Docker 多阶段生成功能](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="49729-173">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="49729-174">基于较大的 ASP.NET Core 生成 Docker 基础映像在容器中生成示例</span><span class="sxs-lookup"><span data-stu-id="49729-174">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="49729-175">基于较小的 ASP.NET Core Docker 运行时基础映像将最终生成结果复制到 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="49729-175">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="49729-176">生成映像包含生成应用程序所需的工具，而运行时映像不包括这些工具。</span><span class="sxs-lookup"><span data-stu-id="49729-176">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="49729-177">系统必备</span><span class="sxs-lookup"><span data-stu-id="49729-177">Prerequisites</span></span>

<span data-ttu-id="49729-178">要进行生成并运行，请安装以下各项：</span><span class="sxs-lookup"><span data-stu-id="49729-178">To build and run, install the following items:</span></span>

#### <a name="net-core-21-sdk"></a><span data-ttu-id="49729-179">.NET Core 2.1 SDK</span><span class="sxs-lookup"><span data-stu-id="49729-179">.NET Core 2.1 SDK</span></span>

* <span data-ttu-id="49729-180">安装 [.NET Core 2.1 SDK](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="49729-180">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="49729-181">安装常用的代码编辑器（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="49729-181">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="49729-182">需要安装代码编辑器？</span><span class="sxs-lookup"><span data-stu-id="49729-182">Need to install a code editor?</span></span> <span data-ttu-id="49729-183">试用 [Visual Studio](https://visualstudio.com/downloads)！</span><span class="sxs-lookup"><span data-stu-id="49729-183">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="49729-184">安装 Docker 客户端</span><span class="sxs-lookup"><span data-stu-id="49729-184">Installing Docker Client</span></span>

<span data-ttu-id="49729-185">安装 [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) 或更高版本的 Docker 客户端。</span><span class="sxs-lookup"><span data-stu-id="49729-185">Install [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="49729-186">可在以下位置安装 Docker 客户端：</span><span class="sxs-lookup"><span data-stu-id="49729-186">The Docker client can be installed in:</span></span>

* <span data-ttu-id="49729-187">Linux 分布</span><span class="sxs-lookup"><span data-stu-id="49729-187">Linux distributions</span></span>

   * [<span data-ttu-id="49729-188">CentOS</span><span class="sxs-lookup"><span data-stu-id="49729-188">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="49729-189">Debian</span><span class="sxs-lookup"><span data-stu-id="49729-189">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="49729-190">Fedora</span><span class="sxs-lookup"><span data-stu-id="49729-190">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="49729-191">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="49729-191">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="49729-192">macOS</span><span class="sxs-lookup"><span data-stu-id="49729-192">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="49729-193">[Windows](https://docs.docker.com/docker-for-windows/install/)。</span><span class="sxs-lookup"><span data-stu-id="49729-193">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="49729-194">为示例存储库安装 Git</span><span class="sxs-lookup"><span data-stu-id="49729-194">Installing Git for sample repository</span></span>

* <span data-ttu-id="49729-195">如果要克隆存储库，请安装 [git](https://git-scm.com/download)。</span><span class="sxs-lookup"><span data-stu-id="49729-195">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="49729-196">获取示例应用程序</span><span class="sxs-lookup"><span data-stu-id="49729-196">Getting the sample application</span></span>

<span data-ttu-id="49729-197">获取该示例的最简单方法是使用以下指令克隆包含 git 的 [.NET Core Docker 存储库](https://github.com/dotnet/dotnet-docker)：</span><span class="sxs-lookup"><span data-stu-id="49729-197">The easiest way to get the sample is by cloning the [.NET Core Docker repository](https://github.com/dotnet/dotnet-docker) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker
```

<span data-ttu-id="49729-198">也可以从 .NET Core Docker 存储库中下载 zip 格式的存储库（其大小较小）。</span><span class="sxs-lookup"><span data-stu-id="49729-198">You can also download the repository (it is small) as a zip from the .NET Core Docker repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="49729-199">在本地运行 ASP.NET 应用</span><span class="sxs-lookup"><span data-stu-id="49729-199">Run the ASP.NET app locally</span></span>

<span data-ttu-id="49729-200">对于引用点，在容器化应用程序之前，请先在本地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-200">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="49729-201">可使用以下命令，通过 .NET Core 2.1 SDK 在本地生成和运行应用程序（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="49729-201">You can build and run the application locally with the .NET Core 2.1 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

<span data-ttu-id="49729-202">应用程序启动后，在 Web 浏览器中访问 **http://localhost:5000**。</span><span class="sxs-lookup"><span data-stu-id="49729-202">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="49729-203">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-203">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="49729-204">可使用以下命令，通过 Linux 容器在 Docker 中生成和运行示例（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="49729-204">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="49729-205">`docker run` 的“-p”参数将本地计算机上的端口 5000 映射到容器中的端口 80（该端口映射形式为 `host:container`）。</span><span class="sxs-lookup"><span data-stu-id="49729-205">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="49729-206">有关详细信息，请参阅命令行参数中的 [docker run](https://docs.docker.com/engine/reference/commandline/exec/) 引用。</span><span class="sxs-lookup"><span data-stu-id="49729-206">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="49729-207">应用程序启动后，在 Web 浏览器中访问 **http://localhost:5000**。</span><span class="sxs-lookup"><span data-stu-id="49729-207">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="49729-208">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-208">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="49729-209">可使用以下命令，通过 Windows 容器在 Docker 中生成和运行示例（这些指令假定使用存储库的根目录）：</span><span class="sxs-lookup"><span data-stu-id="49729-209">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="49729-210">使用 Windows 容器时，必须直接在浏览器中转到容器 IP 地址（而不是 `http://localhost`）。</span><span class="sxs-lookup"><span data-stu-id="49729-210">You must navigate to the **container IP address** (as opposed to `http://localhost`) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="49729-211">可通过以下步骤获取容器的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="49729-211">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="49729-212">打开另一个命令提示符。</span><span class="sxs-lookup"><span data-stu-id="49729-212">Open up another command prompt.</span></span>
* <span data-ttu-id="49729-213">运行 `docker ps`，查看正在运行的容器。</span><span class="sxs-lookup"><span data-stu-id="49729-213">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="49729-214">其中应包含“Aspnetcore_sample”。</span><span class="sxs-lookup"><span data-stu-id="49729-214">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="49729-215">运行 `docker exec aspnetcore_sample ipconfig`。</span><span class="sxs-lookup"><span data-stu-id="49729-215">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="49729-216">将容器 IP 地址复制并粘贴到浏览器中（例如，172.29.245.43）。</span><span class="sxs-lookup"><span data-stu-id="49729-216">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="49729-217">Docker exec 支持通过名称或哈希标识容器。</span><span class="sxs-lookup"><span data-stu-id="49729-217">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="49729-218">示例中使用了名称 (aspnetcore_sample)。</span><span class="sxs-lookup"><span data-stu-id="49729-218">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="49729-219">请查看以下示例，了解如何获取正在运行的 Windows 容器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="49729-219">See the following example of how to get the IP address of a running Windows container.</span></span>

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
> <span data-ttu-id="49729-220">Docker exec 在正在运行的容器中运行新命令。</span><span class="sxs-lookup"><span data-stu-id="49729-220">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="49729-221">有关详细信息，请参阅命令行参数中的 [docker exec 引用](https://docs.docker.com/engine/reference/commandline/exec/)。</span><span class="sxs-lookup"><span data-stu-id="49729-221">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="49729-222">可使用 [dotnet publish](../tools/dotnet-publish.md) 命令生成已准备好在本地部署到生产环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-222">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> <span data-ttu-id="49729-223">-c Release 参数用于在发布模式（默认为调试模式）下生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-223">The -c Release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="49729-224">有关详细信息，请参阅命令行参数中的 [dotnet run 引用](../tools/dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="49729-224">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="49729-225">可使用以下命令在 Windows 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-225">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="49729-226">可使用以下命令在 Linux 或 macOS 中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="49729-226">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="49729-227">此示例中使用的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="49729-227">Docker Images used in this sample</span></span>

<span data-ttu-id="49729-228">此示例的 dockerfile 中使用了以下 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="49729-228">The following Docker images are used in this sample's dockerfile.</span></span>

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

<span data-ttu-id="49729-229">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="49729-229">Congratulations!</span></span> <span data-ttu-id="49729-230">你刚才已：</span><span class="sxs-lookup"><span data-stu-id="49729-230">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="49729-231">了解 Microsoft .NET Core Docker 映像</span><span class="sxs-lookup"><span data-stu-id="49729-231">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="49729-232">获取要 Docker 化的 ASP.NET Core 示例应用</span><span class="sxs-lookup"><span data-stu-id="49729-232">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="49729-233">在本地运行 ASP.NET 示例应用</span><span class="sxs-lookup"><span data-stu-id="49729-233">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="49729-234">使用 Docker for Linux 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-234">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="49729-235">使用 Docker for Windows 容器生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="49729-235">Built and ran the sample with Docker for Windows containers</span></span>

<span data-ttu-id="49729-236">**后续步骤**</span><span class="sxs-lookup"><span data-stu-id="49729-236">**Next Steps**</span></span>

<span data-ttu-id="49729-237">下面是一些可以采取的后续步骤：</span><span class="sxs-lookup"><span data-stu-id="49729-237">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="49729-238">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="49729-238">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="49729-239">将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="49729-239">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="49729-240">使用 Visual Studio Code 进行调试</span><span class="sxs-lookup"><span data-stu-id="49729-240">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="49729-241">在云中使用 Visual Studio for Mac、容器和无服务器代码</span><span class="sxs-lookup"><span data-stu-id="49729-241">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="49729-242">Docker 和 Visual Studio for Mac Lab 入门</span><span class="sxs-lookup"><span data-stu-id="49729-242">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!NOTE]
> <span data-ttu-id="49729-243">如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="49729-243">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
