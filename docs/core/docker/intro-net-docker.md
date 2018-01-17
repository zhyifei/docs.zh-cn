---
title: ".NET 和 Docker 简介"
description: "了解 Docker 和 .NET Core"
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
ms.workload: dotnetcore
ms.openlocfilehash: 8c6daabb3040998d3376ad022790c16b9629233f
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2018
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="0366d-104">.NET 和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="0366d-104">Introduction to .NET and Docker</span></span>

<span data-ttu-id="0366d-105">本文提供了如何在 Docker 上使用 .NET 的简介和概念背景。</span><span class="sxs-lookup"><span data-stu-id="0366d-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span>

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="0366d-106">Docker：打包应用程序以在任何位置部署和运行</span><span class="sxs-lookup"><span data-stu-id="0366d-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="0366d-107">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) 是一个开放平台，使开发人员和管理员可以在称为[容器](https://www.docker.com/what-container)的松散隔离的环境中构建[映像](https://docs.docker.com/glossary/?term=image)、交付和运行分布式应用程序。</span><span class="sxs-lookup"><span data-stu-id="0366d-107">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="0366d-108">此方法可以在开发、QA 和生产环境之间进行高效的应用程序生命周期管理。</span><span class="sxs-lookup"><span data-stu-id="0366d-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="0366d-109">[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用 [Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速构建应用程序，并将其打包为使用以 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 格式编写的文件创建的 [Docker 映像](https://docs.docker.com/glossary/?term=image)，然后在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="0366d-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="0366d-110">你可以创建自己的[分层映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)作为 dockerfiles，或使用[注册表](https://docs.docker.com/glossary/?term=registry)中的现有映像，例如 [Docker 中心](https://docs.docker.com/glossary/?term=Docker%20Hub)。</span><span class="sxs-lookup"><span data-stu-id="0366d-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="0366d-111">[Docker 容器、映像和注册表之间的关系](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md)是[构建和生成容器化应用程序或微服务](../../standard/microservices-architecture/architect-microservice-container-applications/index.md)时的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="0366d-111">The [relationship between Docker containers, images, and registries](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) is an important concept when [architecting and building containerized applications or microservices](../../standard/microservices-architecture/architect-microservice-container-applications/index.md).</span></span> <span data-ttu-id="0366d-112">此方法大大缩短了开发和部署之间的时间。</span><span class="sxs-lookup"><span data-stu-id="0366d-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="0366d-113">其他阅读材料（和视频）</span><span class="sxs-lookup"><span data-stu-id="0366d-113">Further reading (and watching)</span></span>

* [<span data-ttu-id="0366d-114">基于 Windows 的容器：使用企业级控件的新式应用开发。</span><span class="sxs-lookup"><span data-stu-id="0366d-114">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="0366d-115">Docker 概述</span><span class="sxs-lookup"><span data-stu-id="0366d-115">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="0366d-116">Windows 容器上的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="0366d-116">Dockerfile on Windows Containers</span></span>](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile.md)
* [<span data-ttu-id="0366d-117">编写 Dockerfile 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0366d-117">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="0366d-118">为 .NET Core 应用程序生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="0366d-119">获取 .NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-119">Getting .NET Docker images</span></span>

<span data-ttu-id="0366d-120">由 Microsoft 创建和优化官方 .NET Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="0366d-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="0366d-121">这些映像在 Docker 中心的 Microsoft 存储库中公开提供。</span><span class="sxs-lookup"><span data-stu-id="0366d-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="0366d-122">每个存储库可以包含多个映像，具体取决于 .NET 和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="0366d-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="0366d-123">大多数映像存储库提供广泛的标记，以帮助选择特定的框架版本和 OS（Linux 发行版或 Windows 版本）。</span><span class="sxs-lookup"><span data-stu-id="0366d-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="0366d-124">基于方案的指南</span><span class="sxs-lookup"><span data-stu-id="0366d-124">Scenario based guidance</span></span>

<span data-ttu-id="0366d-125">Microsoft 对 .NET 存储库的打算是要有细化和集中存储库，表示特定方案或工作负载。</span><span class="sxs-lookup"><span data-stu-id="0366d-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="0366d-126">`microsoft/aspnetcore` 映像针对 Docker 上的 ASP.NET Core 应用进行了优化，因此容器可以更快启动。</span><span class="sxs-lookup"><span data-stu-id="0366d-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="0366d-127">.NET Core 映像 (`microsoft/dotnet`) 适用于基于 .NET Core 的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="0366d-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="0366d-128">例如，批处理、Azure WebJobs 和其他控制台方案应该使用优化的 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="0366d-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="0366d-129">使用 Docker 和 .NET 应用程序最显而易见的水平方案是用于生产部署和托管。</span><span class="sxs-lookup"><span data-stu-id="0366d-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="0366d-130">事实证明，生产只是一种方案，其他方案同样有用。</span><span class="sxs-lookup"><span data-stu-id="0366d-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="0366d-131">这些方案不是特定于 .NET，但应该适用于大多数开发人员平台。</span><span class="sxs-lookup"><span data-stu-id="0366d-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="0366d-132">**低摩擦安装** — 你可以尝试使用 .NET，无需本地安装。</span><span class="sxs-lookup"><span data-stu-id="0366d-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="0366d-133">只下载 Docker 映像，其中包含 .NET。</span><span class="sxs-lookup"><span data-stu-id="0366d-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="0366d-134">**在容器中开发**你可以在一致的环境中开发，使开发和生产环境类似（可避免一些问题，例如开发人员计算机上的全局状态）。</span><span class="sxs-lookup"><span data-stu-id="0366d-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="0366d-135">通过 Visual Studio Tools for Docker，你甚至可以直接从 Visual Studio 启动容器。</span><span class="sxs-lookup"><span data-stu-id="0366d-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="0366d-136">**容器中测试** — 你可以在容器中测试，减少由于环境配置不当或上次测试遗留的其他更改而导致的故障。</span><span class="sxs-lookup"><span data-stu-id="0366d-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="0366d-137">**在容器中生成** — 你可以在容器中生成代码，消除为多个环境正确配置共享生成计算机的需要，而是转向“BYOC”（自带容器）方法。</span><span class="sxs-lookup"><span data-stu-id="0366d-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="0366d-138">**在所有环境中部署** — 可以通过你的所有环境部署映像。</span><span class="sxs-lookup"><span data-stu-id="0366d-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="0366d-139">这种方法减少了配置差异导致的故障，通常通过外部配置（例如，注入的环境变量）改变映像行为。</span><span class="sxs-lookup"><span data-stu-id="0366d-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="0366d-140">[通用指南](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md)，确定是使用 .NET Core 还是 .NET Framework 进行 Docker 容器开发。</span><span class="sxs-lookup"><span data-stu-id="0366d-140">[General guidance](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="0366d-141">常见的 Docker 开发方案</span><span class="sxs-lookup"><span data-stu-id="0366d-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="0366d-142">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="0366d-142">.NET Core</span></span>

<span data-ttu-id="0366d-143">**.NET Core 资源**</span><span class="sxs-lookup"><span data-stu-id="0366d-143">**.NET Core resources**</span></span>

 <span data-ttu-id="0366d-144">选择适合你感兴趣方案的 .NET Core 示例。</span><span class="sxs-lookup"><span data-stu-id="0366d-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="0366d-145">所有示例说明都介绍了如何从 Windows、Linux 或 macOS 主机定位 Windows 或 Linux Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="0366d-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="0366d-146">这些示例使用 .NET Core 2.0。</span><span class="sxs-lookup"><span data-stu-id="0366d-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="0366d-147">它们会在适用时使用 Docker [多阶段生成](https://github.com/dotnet/announcements/issues/18)和[多拱形标记](https://github.com/dotnet/announcements/issues/14)。</span><span class="sxs-lookup"><span data-stu-id="0366d-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="0366d-148">DockerHub 上的 .NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="0366d-149">使 .NET Core 应用程序 Docker 化</span><span class="sxs-lookup"><span data-stu-id="0366d-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="0366d-150">此 .NET Core Docker 示例演示如何[在 .NET Core 开发过程中使用 Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)。</span><span class="sxs-lookup"><span data-stu-id="0366d-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="0366d-151">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="0366d-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="0366d-152">此 .NET Core Docker 示例演示了[生成 .NET Core 应用程序的 Docker 映像以用于生产](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="0366d-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="0366d-153">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="0366d-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="0366d-154">此 [.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)演示了生成[独立式 .NET Core 应用程序](../deploying/index.md)的 Docker 映像的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="0366d-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](../deploying/index.md).</span></span> <span data-ttu-id="0366d-155">用于最小的生产容器，而不会受益于[在容器之间共享基础映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)。</span><span class="sxs-lookup"><span data-stu-id="0366d-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="0366d-156">但是，可以共享较低的 Docker 层。</span><span class="sxs-lookup"><span data-stu-id="0366d-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="0366d-157">ARM32/Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="0366d-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="0366d-158">.NET Core 运行时 ARM32 生成公告</span><span class="sxs-lookup"><span data-stu-id="0366d-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="0366d-159">DockerHub 上的 ARM32/Raspberry Pi .NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="0366d-160">GitHub 上的 ARM32/Raspberry Pi .NET Core Docker 示例</span><span class="sxs-lookup"><span data-stu-id="0366d-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="0366d-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="0366d-161">.NET Framework</span></span>

* [<span data-ttu-id="0366d-162">DockerHub 上的 .NET Framework 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-162">.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet-framework/)

<span data-ttu-id="0366d-163">此存储库包含演示各种 .NET Framework Docker 配置的示例。</span><span class="sxs-lookup"><span data-stu-id="0366d-163">This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="0366d-164">你可以将这些映像作为自己的 Docker 映像的基础。</span><span class="sxs-lookup"><span data-stu-id="0366d-164">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="0366d-165">**.NET Framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="0366d-165">**.NET Framework 4.7**</span></span>

<span data-ttu-id="0366d-166">[dotnet-framework:4.7 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)演示 [.NET Framework 4.7](../../framework/whats-new/index.md#v47) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="0366d-166">The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](../../framework/whats-new/index.md#v47).</span></span> <span data-ttu-id="0366d-167">它演示如何生成并部署依赖于 [.NET Framework 4.7 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0366d-167">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span></span>

<span data-ttu-id="0366d-168">**.NET Framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="0366d-168">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="0366d-169">[dotnet-framework:4.6.2 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)演示 [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="0366d-169">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462).</span></span> <span data-ttu-id="0366d-170">它演示如何生成并部署依赖于 [.NET Framework 4.6.2 docker 映像](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0366d-170">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span></span>

<span data-ttu-id="0366d-171">**.NET Framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="0366d-171">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="0366d-172">[dotnet-framework:3.5 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)演示 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="0366d-172">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span></span> <span data-ttu-id="0366d-173">它演示如何在 Docker 中生成并部署依赖于 .NET Framework 3.5 的项目。</span><span class="sxs-lookup"><span data-stu-id="0366d-173">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="0366d-174">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0366d-174">ASP.NET Core</span></span>

* <span data-ttu-id="0366d-175">[此 ASP.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="0366d-175">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="0366d-176">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="0366d-176">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="0366d-177">DockerHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-177">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="0366d-178">GitHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-178">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="0366d-179">ASP.NET 框架</span><span class="sxs-lookup"><span data-stu-id="0366d-179">ASP.NET Framework</span></span>

* [<span data-ttu-id="0366d-180">DockerHub 上的 ASP.NET 框架映像</span><span class="sxs-lookup"><span data-stu-id="0366d-180">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="0366d-181">.NET Framework 4.6.2 示例中的 ASP.NET Web 窗体应用</span><span class="sxs-lookup"><span data-stu-id="0366d-181">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="0366d-182">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="0366d-182">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="0366d-183">DockerHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-183">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="0366d-184">GitHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-184">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

* [<span data-ttu-id="0366d-185">使用 .NET Full Framework 4.6.2 的 Windows Communication Framework (WCF) Docker 示例</span><span class="sxs-lookup"><span data-stu-id="0366d-185">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="0366d-186">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="0366d-186">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="0366d-187">DockerHub 上的 Internet Information Server (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-187">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="0366d-188">GitHub 上的 Internet Information Server (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-188">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="0366d-189">与其他 Microsoft 堆栈容器映像进行交互</span><span class="sxs-lookup"><span data-stu-id="0366d-189">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="0366d-190">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="0366d-190">Microsoft SQL Server</span></span>

* [<span data-ttu-id="0366d-191">使用 Docker 快速入门运行 Microsoft SQL Server for Linux 2017 容器映像</span><span class="sxs-lookup"><span data-stu-id="0366d-191">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="0366d-192">DockerHub 上的 Microsoft SQL Server for Linux 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-192">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="0366d-193">DockerHub 上的 Microsoft SQL Server for Windows 容器映像</span><span class="sxs-lookup"><span data-stu-id="0366d-193">Microsoft SQL Server for Windows Containers images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="0366d-194">DockerHub 上的用于 Windows 容器的 Microsoft SQL Server Express Edition 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-194">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="0366d-195">DockerHub 上的用于 Windows 容器的 Microsoft SQL Server Developer Edition 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-195">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="0366d-196">Visual Studio Team Services (VSTS) 代理</span><span class="sxs-lookup"><span data-stu-id="0366d-196">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="0366d-197">DockerHub 上的 Visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="0366d-197">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="0366d-198">GitHub 上的 Visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="0366d-198">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="0366d-199">Operations Management Suite (OMS) Linux 代理</span><span class="sxs-lookup"><span data-stu-id="0366d-199">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="0366d-200">Operations Management Suite (OMS) Linux 代理概述</span><span class="sxs-lookup"><span data-stu-id="0366d-200">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [<span data-ttu-id="0366d-201">DockerHub 上的 Operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-201">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="0366d-202">GitHub 上的 Operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-202">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="0366d-203">Microsoft Azure 命令行接口 (CLI)</span><span class="sxs-lookup"><span data-stu-id="0366d-203">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="0366d-204">DockerHub 上的 Microsoft Azure 命令行接口 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-204">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cli/) 

* [<span data-ttu-id="0366d-205">GitHub 上的 Microsoft Azure 命令行接口 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-205">Microsoft Azure Command-Line Interface (CLI) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

> [!NOTE]
> <span data-ttu-id="0366d-206">如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="0366d-206">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="0366d-207">Microsoft Azure Cosmos DB 仿真器（仅限 Windows 容器）</span><span class="sxs-lookup"><span data-stu-id="0366d-207">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="0366d-208">DockerHub 上的 Microsoft Azure Cosmos DB 仿真器映像</span><span class="sxs-lookup"><span data-stu-id="0366d-208">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="0366d-209">将 Azure Cosmos DB 仿真器用于本地开发和测试</span><span class="sxs-lookup"><span data-stu-id="0366d-209">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](/azure/cosmos-db/local-emulator.md#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="0366d-210">探索内容丰富的 Docker 开发生态系统</span><span class="sxs-lookup"><span data-stu-id="0366d-210">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="0366d-211">了解了 Docker 平台和不同的 Docker 映像后，下一步就是探索内容丰富的 Docker 生态系统。</span><span class="sxs-lookup"><span data-stu-id="0366d-211">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="0366d-212">以下链接展示了 Microsoft 工具对容器开发所做的补充。</span><span class="sxs-lookup"><span data-stu-id="0366d-212">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="0366d-213">将 .NET 与 Docker 一起使用</span><span class="sxs-lookup"><span data-stu-id="0366d-213">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)
* [<span data-ttu-id="0366d-214">设计和开发基于微服务的多容器 .NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="0366d-214">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [<span data-ttu-id="0366d-215">Visual Studio Code Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="0366d-215">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile)
* [<span data-ttu-id="0366d-216">了解如何使用 Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="0366d-216">Learn how to use Azure Service Fabric</span></span>](/azure/service-fabric/index.md)
* [<span data-ttu-id="0366d-217">Service Fabric 入门示例</span><span class="sxs-lookup"><span data-stu-id="0366d-217">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="0366d-218">Windows 容器的优点</span><span class="sxs-lookup"><span data-stu-id="0366d-218">Benefits of Windows Containers</span></span>](/virtualization/windowscontainers/about/index.md#video-overview)
* [<span data-ttu-id="0366d-219">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="0366d-219">Working with Visual Studio Docker Tools</span></span>](/aspnet/core/publishing/visual-studio-tools-for-docker/index.md)
* [<span data-ttu-id="0366d-220">将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="0366d-220">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="0366d-221">使用 Visual Studio Code 进行调试</span><span class="sxs-lookup"><span data-stu-id="0366d-221">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* [<span data-ttu-id="0366d-222">在云中使用 Visual Studio for Mac、容器和无服务器代码</span><span class="sxs-lookup"><span data-stu-id="0366d-222">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="0366d-223">Docker 和 Visual Studio for Mac Lab 入门</span><span class="sxs-lookup"><span data-stu-id="0366d-223">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="0366d-224">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0366d-224">Next steps</span></span>

* [<span data-ttu-id="0366d-225">了解使用 .NET Core 的 Docker 的基本信息</span><span class="sxs-lookup"><span data-stu-id="0366d-225">Learn Docker Basics with .NET Core</span></span>](docker-basics-dotnet-core.md)
* [<span data-ttu-id="0366d-226">生成 .NET Core Docker 映像</span><span class="sxs-lookup"><span data-stu-id="0366d-226">Building .NET Core Docker Images</span></span>](building-net-docker-images.md)
