---
title: ".NET 和 Docker 简介"
description: "了解 Docker 和.NET 核心"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="617b1-104">.NET 和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="617b1-104">Introduction to .NET and Docker</span></span>

 <span data-ttu-id="617b1-105">本文提供了简介和概念与使用 Docker 上的.NET 的背景。</span><span class="sxs-lookup"><span data-stu-id="617b1-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span> 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="617b1-106">Docker： 打包你的应用部署并运行任何位置</span><span class="sxs-lookup"><span data-stu-id="617b1-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="617b1-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined)是使开发人员和管理员可生成一个开放平台[映像](https://docs.docker.com/glossary/?term=image)，提供，并调用松散隔离环境中运行分布式应用程序[容器](https://www.docker.com/what-container).</span><span class="sxs-lookup"><span data-stu-id="617b1-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="617b1-108">此方法支持开发、 QA 和生产环境之间的有效的应用程序生命周期管理。</span><span class="sxs-lookup"><span data-stu-id="617b1-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="617b1-109">[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用[Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速生成并打包应用程序作为[Docker 映像](https://docs.docker.com/glossary/?term=image)使用编写的文件创建[Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)格式，然后是部署和运行在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)。</span><span class="sxs-lookup"><span data-stu-id="617b1-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="617b1-110">你可以创建你自己[分层映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)为 dockerfile 或使用现有的从[注册表](https://docs.docker.com/glossary/?term=registry)、 like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub)。</span><span class="sxs-lookup"><span data-stu-id="617b1-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="617b1-111">[Docker 容器、 图像和注册表之间的关系](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries)是一个重要概念时[构建和生成容器化应用程序或微服务](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/)。</span><span class="sxs-lookup"><span data-stu-id="617b1-111">The [relationship between Docker containers, images, and registries](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) is an important concept when [architecting and building containerized applications or microservices](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span></span> <span data-ttu-id="617b1-112">此方法大大缩短了开发和部署之间的时间。</span><span class="sxs-lookup"><span data-stu-id="617b1-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="617b1-113">其他阅读材料 （和监视）</span><span class="sxs-lookup"><span data-stu-id="617b1-113">Further reading (and watching)</span></span>

* [<span data-ttu-id="617b1-114">基于 Windows 的容器： 使用企业级控制的现代应用开发。</span><span class="sxs-lookup"><span data-stu-id="617b1-114">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="617b1-115">Docker 概述</span><span class="sxs-lookup"><span data-stu-id="617b1-115">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="617b1-116">Windows 容器上的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="617b1-116">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="617b1-117">编写 Dockerfile 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="617b1-117">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="617b1-118">.NET 核心应用程序的构建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="617b1-119">获取.NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-119">Getting .NET Docker Images</span></span>

<span data-ttu-id="617b1-120">创建和优化由 Microsoft 的官方.NET Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="617b1-121">在 Docker Hub 上的 Microsoft 存储库中，公开提供。</span><span class="sxs-lookup"><span data-stu-id="617b1-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="617b1-122">每个存储库可以包含多个映像，具体取决于.NET 版本和操作系统版本上。</span><span class="sxs-lookup"><span data-stu-id="617b1-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="617b1-123">大多数映像存储库提供广泛的标记，以帮助你选择特定的 framework 版本和操作系统 （Linux 发行版或 Windows 版本）。</span><span class="sxs-lookup"><span data-stu-id="617b1-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="617b1-124">基于方案的指南</span><span class="sxs-lookup"><span data-stu-id="617b1-124">Scenario Based Guidance</span></span>

<span data-ttu-id="617b1-125">.NET 存储库的 Microsoft 的意图是具有精确的专注于存储库，它表示特定方案或工作负荷。</span><span class="sxs-lookup"><span data-stu-id="617b1-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="617b1-126">`microsoft/aspnetcore`映像进行优化 ASP.NET Core 上的应用程序 Docker，以便可以更快地启动容器。</span><span class="sxs-lookup"><span data-stu-id="617b1-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="617b1-127">.NET Core 映像 (`microsoft/dotnet`) 适用于基于.NET 核心的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="617b1-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="617b1-128">例如，批处理、 Azure WebJobs 和其他控制台方案应使用优化的.NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="617b1-129">使用 Docker 和.NET 应用程序的最明显的水平方案适用于生产部署和托管。</span><span class="sxs-lookup"><span data-stu-id="617b1-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="617b1-130">事实证明生产是一个方案和其他哪些是同样有用。</span><span class="sxs-lookup"><span data-stu-id="617b1-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="617b1-131">这些方案并不特定于.NET 中，但应适用于大多数开发人员平台。</span><span class="sxs-lookup"><span data-stu-id="617b1-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="617b1-132">**低摩擦安装**-你可以尝试.NET 而无需本地安装。</span><span class="sxs-lookup"><span data-stu-id="617b1-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="617b1-133">只下载使用.NET 中它的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="617b1-134">**在容器中进行开发**-你可以开发在一致环境中，使开发和生产环境类似 （避免如开发人员计算机上的全局状态的问题）。</span><span class="sxs-lookup"><span data-stu-id="617b1-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="617b1-135">Visual Studio Tools for Docker 甚至可以直接从 Visual Studio 启动容器。</span><span class="sxs-lookup"><span data-stu-id="617b1-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="617b1-136">**测试容器中**-你可以在测试容器，减少由于配置不正确的环境的故障或留在原地从最后一次测试其他更改。</span><span class="sxs-lookup"><span data-stu-id="617b1-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="617b1-137">**容器中生成**-你可以构建在容器中，代码避免需要正确配置为多个环境的共享的生成计算机但而将移动到"BYOC"（自带你自己的容器） 的方法。</span><span class="sxs-lookup"><span data-stu-id="617b1-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="617b1-138">**在所有环境中的部署**— 您可以通过你的环境的所有部署映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="617b1-139">此方法可以降低由于配置的不同，通常会更改通过外部配置 （例如，插入的环境变量） 的映像行为的故障。</span><span class="sxs-lookup"><span data-stu-id="617b1-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="617b1-140">[一般性指导原则](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance)的 Docker 容器开发的.NET 核心和.NET Framework 之间做出决定。</span><span class="sxs-lookup"><span data-stu-id="617b1-140">[General guidance](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="617b1-141">常见的 Docker 开发方案</span><span class="sxs-lookup"><span data-stu-id="617b1-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="617b1-142">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="617b1-142">.NET Core</span></span>

<span data-ttu-id="617b1-143">**.NET 核心资源**</span><span class="sxs-lookup"><span data-stu-id="617b1-143">**.NET Core resources**</span></span>

 <span data-ttu-id="617b1-144">选择适合您感兴趣的方案的.NET 核心示例。</span><span class="sxs-lookup"><span data-stu-id="617b1-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="617b1-145">所有的示例说明介绍如何面向 Windows、 Linux 或 macOS 主机中的 Windows 或 Linux 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="617b1-146">这些示例使用.NET 核心 2.0。</span><span class="sxs-lookup"><span data-stu-id="617b1-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="617b1-147">它们使用 Docker[多阶段生成](https://github.com/dotnet/announcements/issues/18)和[多 arch 标记](https://github.com/dotnet/announcements/issues/14)在适当的位置。</span><span class="sxs-lookup"><span data-stu-id="617b1-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="617b1-148">.NET core 映像上 DockerHub</span><span class="sxs-lookup"><span data-stu-id="617b1-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="617b1-149">Dockerize.NET 核心应用程序</span><span class="sxs-lookup"><span data-stu-id="617b1-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="617b1-150">此.NET 核心 Docker 示例演示如何[在.NET 核心开发过程中使用 Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)。</span><span class="sxs-lookup"><span data-stu-id="617b1-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="617b1-151">示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="617b1-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="617b1-152">.NET 核心 Docker 演示的最佳做法模式[构建的生产.NET 核心应用程序的 Docker 映像。](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="617b1-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="617b1-153">示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="617b1-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="617b1-154">这[.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)演示生成的 Docker 映像的最佳做法模式[自包含的.NET Core 应用](https://docs.microsoft.com/dotnet/core/deploying/)。</span><span class="sxs-lookup"><span data-stu-id="617b1-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](https://docs.microsoft.com/dotnet/core/deploying/).</span></span> <span data-ttu-id="617b1-155">用于最小的生产容器，而无需受益于[共享容器之间的基础映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)。</span><span class="sxs-lookup"><span data-stu-id="617b1-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="617b1-156">但是，无法共享较低的 Docker 层。</span><span class="sxs-lookup"><span data-stu-id="617b1-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="617b1-157">ARM32 / Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="617b1-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="617b1-158">.NET 核心运行时 ARM32 生成公告</span><span class="sxs-lookup"><span data-stu-id="617b1-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="617b1-159">ARM32 / Raspberry Pi.NET Core 映像上 DockerHub</span><span class="sxs-lookup"><span data-stu-id="617b1-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="617b1-160">ARM32 / 树莓 Pi.NET 核心 Docker 示例 GitHub 上</span><span class="sxs-lookup"><span data-stu-id="617b1-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="617b1-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="617b1-161">.NET Framework</span></span>

* <span data-ttu-id="617b1-162">[.NET framework 映像上 DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/)此存储库包含演示各种.NET Framework Docker 配置的示例。</span><span class="sxs-lookup"><span data-stu-id="617b1-162">[.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="617b1-163">作为你自己的 Docker 映像的基础，可使用这些映像。</span><span class="sxs-lookup"><span data-stu-id="617b1-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="617b1-164">**.NET framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="617b1-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="617b1-165">[ [Dotnet-framework: 4.7 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)演示基本"你好 world"用法的[.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47)。</span><span class="sxs-lookup"><span data-stu-id="617b1-165">[The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span></span> <span data-ttu-id="617b1-166">它演示如何生成并部署应用程序依赖于[.NET Framework 4.7 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)。</span><span class="sxs-lookup"><span data-stu-id="617b1-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span></span>

<span data-ttu-id="617b1-167">**.NET framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="617b1-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="617b1-168">[Dotnet-framework: 4.6.2 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)演示基本"你好 world"用法的[.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462)。</span><span class="sxs-lookup"><span data-stu-id="617b1-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span></span> <span data-ttu-id="617b1-169">它演示如何生成并部署应用程序依赖于[.NET Framework 4.6.2 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)。</span><span class="sxs-lookup"><span data-stu-id="617b1-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span></span>

<span data-ttu-id="617b1-170">**.NET framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="617b1-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="617b1-171">[Dotnet-framework: 3.5 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)演示基本"你好 world"用法的[.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5)。</span><span class="sxs-lookup"><span data-stu-id="617b1-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span></span> <span data-ttu-id="617b1-172">它演示如何生成并部署依赖于在 Docker 中的.NET Framework 3.5 的项目。</span><span class="sxs-lookup"><span data-stu-id="617b1-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="617b1-173">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="617b1-173">ASP.NET Core</span></span>

* <span data-ttu-id="617b1-174">[此 ASP.NET 核心 Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示针对适用于生产应用的 ASP.NET Core 构建 Docker 映像的最佳做法模式。</span><span class="sxs-lookup"><span data-stu-id="617b1-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="617b1-175">示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="617b1-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="617b1-176">DockerHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="617b1-177">在 GitHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="617b1-178">ASP.NET Framework</span><span class="sxs-lookup"><span data-stu-id="617b1-178">ASP.NET Framework</span></span> 

* [<span data-ttu-id="617b1-179">DockerHub 上的 ASP.NET 框架映像</span><span class="sxs-lookup"><span data-stu-id="617b1-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="617b1-180">在.NET Framework 4.6.2 示例上的 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="617b1-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="617b1-181">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="617b1-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="617b1-182">DockerHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="617b1-183">在 GitHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

* [<span data-ttu-id="617b1-184">使用.NET Full Framework 4.6.2 Windows Communication Framework (WCF) Docker 示例</span><span class="sxs-lookup"><span data-stu-id="617b1-184">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="617b1-185">Internet 信息服务器 (IIS)</span><span class="sxs-lookup"><span data-stu-id="617b1-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="617b1-186">DockerHub 上的 Internet 信息服务器 (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="617b1-187">在 GitHub 上的 Internet 信息服务器 (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="617b1-188">与其他 Microsoft 堆栈容器映像进行交互</span><span class="sxs-lookup"><span data-stu-id="617b1-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="617b1-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="617b1-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="617b1-190">使用 Docker 快速入门中运行 Microsoft SQL Server 并执行自 2017 年 Linux 容器映像</span><span class="sxs-lookup"><span data-stu-id="617b1-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="617b1-191">DockerHub 上的 Linux 映像的 Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="617b1-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="617b1-192">DockerHub 上的 Microsoft SQL Server 的 Windows 容器映像</span><span class="sxs-lookup"><span data-stu-id="617b1-192">Microsoft SQL Server for Windows Containers images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="617b1-193">Microsoft SQL Server Express Edition DockerHub 上的 Windows 容器映像</span><span class="sxs-lookup"><span data-stu-id="617b1-193">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="617b1-194">Microsoft SQL Server Developer Edition DockerHub 上的 Windows 容器映像</span><span class="sxs-lookup"><span data-stu-id="617b1-194">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="617b1-195">Visual Studio Team Services (VSTS) 代理</span><span class="sxs-lookup"><span data-stu-id="617b1-195">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="617b1-196">DockerHub 上的 visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="617b1-196">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="617b1-197">在 GitHub 上的 visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="617b1-197">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="617b1-198">Operations Management Suite (OMS) Linux 代理</span><span class="sxs-lookup"><span data-stu-id="617b1-198">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="617b1-199">Operations Management Suite (OMS) Linux 代理概述</span><span class="sxs-lookup"><span data-stu-id="617b1-199">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [<span data-ttu-id="617b1-200">DockerHub 上的 operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-200">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [<span data-ttu-id="617b1-201">在 GitHub 上的 operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-201">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="617b1-202">Microsoft Azure 命令行界面 (CLI)</span><span class="sxs-lookup"><span data-stu-id="617b1-202">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="617b1-203">DockerHub 上的 Microsoft Azure 命令行界面 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-203">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](Docker image for Microsoft Azure Command Line Interface) 

* [<span data-ttu-id="617b1-204">在 GitHub 上的 Microsoft Azure 命令行界面 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-204">Microsoft Azure Command Line Interface (CLI) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

> [!Note]
> <span data-ttu-id="617b1-205">如果你没有 Azure 订阅，[现在注册](https://azure.microsoft.com/free/?b=16.48)免费的 30 天帐户和 get 200 美元的 Azure 信用额度来试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="617b1-205">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="617b1-206">Microsoft Azure Cosmos DB 模拟器 （仅适用于 Windows 容器）</span><span class="sxs-lookup"><span data-stu-id="617b1-206">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="617b1-207">DockerHub 上的 Microsoft Azure Cosmos DB 仿真程序映像</span><span class="sxs-lookup"><span data-stu-id="617b1-207">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="617b1-208">使用 Azure Cosmos DB 仿真程序用于本地开发和测试</span><span class="sxs-lookup"><span data-stu-id="617b1-208">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="617b1-209">浏览丰富的 Docker 开发生态系统</span><span class="sxs-lookup"><span data-stu-id="617b1-209">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="617b1-210">现在，你已了解有关 Docker 平台和不同的 Docker 映像下, 一步是浏览丰富 Docker 生态系统。</span><span class="sxs-lookup"><span data-stu-id="617b1-210">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="617b1-211">以下链接将显示 Microsoft 工具对容器开发的补充。</span><span class="sxs-lookup"><span data-stu-id="617b1-211">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="617b1-212">将.NET 与 Docker 一起使用</span><span class="sxs-lookup"><span data-stu-id="617b1-212">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [<span data-ttu-id="617b1-213">设计和开发多容器和基于微服务的.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="617b1-213">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [<span data-ttu-id="617b1-214">Visual Studio 代码 Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="617b1-214">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile) 
* [<span data-ttu-id="617b1-215">了解如何使用 Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="617b1-215">Learn how to use Azure Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/) 
* [<span data-ttu-id="617b1-216">Service Fabric 获取启动示例</span><span class="sxs-lookup"><span data-stu-id="617b1-216">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="617b1-217">Windows 容器的优点</span><span class="sxs-lookup"><span data-stu-id="617b1-217">Benefits of Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="617b1-218">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="617b1-218">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="617b1-219">部署到 Azure 容器实例中 Azure 容器注册表的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-219">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="617b1-220">使用 Visual Studio 代码进行调试</span><span class="sxs-lookup"><span data-stu-id="617b1-220">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="617b1-221">获取之手使用 Visual Studio Mac、 容器和无服务器代码在云中</span><span class="sxs-lookup"><span data-stu-id="617b1-221">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="617b1-222">开始使用 Docker 和 Visual Studio Mac 实验室</span><span class="sxs-lookup"><span data-stu-id="617b1-222">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="617b1-223">后续步骤</span><span class="sxs-lookup"><span data-stu-id="617b1-223">Next Steps</span></span>

* [<span data-ttu-id="617b1-224">了解 Docker 使用.NET Core 的基础知识</span><span class="sxs-lookup"><span data-stu-id="617b1-224">Learn Docker Basics with .NET Core</span></span>](../docker/docker-basics-dotnet-core.md)
* [<span data-ttu-id="617b1-225">构建.NET 核心 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="617b1-225">Building .NET Core Docker Images</span></span>](../docker/building-net-docker-images)