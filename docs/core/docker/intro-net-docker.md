---
title: .NET 和 Docker 简介
description: 了解 Docker 和 .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.custom: mvc
ms.openlocfilehash: bc652a375abd03bbc70f055b34d6ecea4d9fc374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219162"
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="4d046-103">.NET 和 Docker 简介</span><span class="sxs-lookup"><span data-stu-id="4d046-103">Introduction to .NET and Docker</span></span>

<span data-ttu-id="4d046-104">本文提供了如何在 Docker 上使用 .NET 的简介和概念背景。</span><span class="sxs-lookup"><span data-stu-id="4d046-104">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span>

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="4d046-105">Docker：打包应用程序以在任何位置部署和运行</span><span class="sxs-lookup"><span data-stu-id="4d046-105">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="4d046-106">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) 是一个开放平台，使开发人员和管理员可以在称为[容器](https://www.docker.com/what-container)的松散隔离的环境中构建[映像](https://docs.docker.com/glossary/?term=image)、交付和运行分布式应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d046-106">[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="4d046-107">此方法可以在开发、QA 和生产环境之间进行高效的应用程序生命周期管理。</span><span class="sxs-lookup"><span data-stu-id="4d046-107">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="4d046-108">[Docker 平台](https://docs.docker.com/engine/docker-overview/#the-docker-platform)使用 [Docker 引擎](https://docs.docker.com/engine/docker-overview/#docker-engine)快速构建应用程序，并将其打包为使用以 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 格式编写的文件创建的 [Docker 映像](https://docs.docker.com/glossary/?term=image)，然后在[分层容器](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)中部署和运行。</span><span class="sxs-lookup"><span data-stu-id="4d046-108">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="4d046-109">你可以创建自己的[分层映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)作为 dockerfiles，或使用[注册表](https://docs.docker.com/glossary/?term=registry)中的现有映像，例如 [Docker 中心](https://docs.docker.com/glossary/?term=Docker%20Hub)。</span><span class="sxs-lookup"><span data-stu-id="4d046-109">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="4d046-110">[Docker 容器、映像和注册表之间的关系](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md)是[构建和生成容器化应用程序或微服务](../../standard/microservices-architecture/architect-microservice-container-applications/index.md)时的一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="4d046-110">The [relationship between Docker containers, images, and registries](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) is an important concept when [architecting and building containerized applications or microservices](../../standard/microservices-architecture/architect-microservice-container-applications/index.md).</span></span> <span data-ttu-id="4d046-111">此方法大大缩短了开发和部署之间的时间。</span><span class="sxs-lookup"><span data-stu-id="4d046-111">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="4d046-112">其他阅读材料（和视频）</span><span class="sxs-lookup"><span data-stu-id="4d046-112">Further reading (and watching)</span></span>

* [<span data-ttu-id="4d046-113">基于 Windows 的容器：使用企业级控件的新式应用开发。</span><span class="sxs-lookup"><span data-stu-id="4d046-113">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="4d046-114">Docker 概述</span><span class="sxs-lookup"><span data-stu-id="4d046-114">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="4d046-115">Windows 容器上的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="4d046-115">Dockerfile on Windows Containers</span></span>](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="4d046-116">编写 Dockerfile 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="4d046-116">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="4d046-117">为 .NET Core 应用程序生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-117">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="4d046-118">获取 .NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-118">Getting .NET Docker images</span></span>

<span data-ttu-id="4d046-119">由 Microsoft 创建和优化官方 .NET Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="4d046-119">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="4d046-120">这些映像在 Docker 中心的 Microsoft 存储库中公开提供。</span><span class="sxs-lookup"><span data-stu-id="4d046-120">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="4d046-121">每个存储库可以包含多个映像，具体取决于 .NET 和 OS 版本。</span><span class="sxs-lookup"><span data-stu-id="4d046-121">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="4d046-122">大多数映像存储库提供广泛的标记，以帮助选择特定的框架版本和 OS（Linux 发行版或 Windows 版本）。</span><span class="sxs-lookup"><span data-stu-id="4d046-122">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="4d046-123">基于方案的指南</span><span class="sxs-lookup"><span data-stu-id="4d046-123">Scenario based guidance</span></span>

<span data-ttu-id="4d046-124">Microsoft 对 .NET 存储库的打算是要有细化和集中存储库，表示特定方案或工作负载。</span><span class="sxs-lookup"><span data-stu-id="4d046-124">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="4d046-125">`microsoft/aspnetcore` 映像针对 Docker 上的 ASP.NET Core 应用进行了优化，因此容器可以更快启动。</span><span class="sxs-lookup"><span data-stu-id="4d046-125">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="4d046-126">.NET Core 映像 (`microsoft/dotnet`) 适用于基于 .NET Core 的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="4d046-126">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="4d046-127">例如，批处理、Azure WebJobs 和其他控制台方案应该使用优化的 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="4d046-127">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="4d046-128">使用 Docker 和 .NET 应用程序最显而易见的水平方案是用于生产部署和托管。</span><span class="sxs-lookup"><span data-stu-id="4d046-128">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="4d046-129">事实证明，生产只是一种方案，其他方案同样有用。</span><span class="sxs-lookup"><span data-stu-id="4d046-129">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="4d046-130">这些方案不是特定于 .NET，但应该适用于大多数开发人员平台。</span><span class="sxs-lookup"><span data-stu-id="4d046-130">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="4d046-131">**低摩擦安装** — 你可以尝试使用 .NET，无需本地安装。</span><span class="sxs-lookup"><span data-stu-id="4d046-131">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="4d046-132">只下载 Docker 映像，其中包含 .NET。</span><span class="sxs-lookup"><span data-stu-id="4d046-132">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="4d046-133">**在容器中开发**你可以在一致的环境中开发，使开发和生产环境类似（可避免一些问题，例如开发人员计算机上的全局状态）。</span><span class="sxs-lookup"><span data-stu-id="4d046-133">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="4d046-134">通过 Visual Studio Tools for Docker，你甚至可以直接从 Visual Studio 启动容器。</span><span class="sxs-lookup"><span data-stu-id="4d046-134">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="4d046-135">**容器中测试** — 你可以在容器中测试，减少由于环境配置不当或上次测试遗留的其他更改而导致的故障。</span><span class="sxs-lookup"><span data-stu-id="4d046-135">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="4d046-136">**在容器中生成** — 你可以在容器中生成代码，消除为多个环境正确配置共享生成计算机的需要，而是转向“BYOC”（自带容器）方法。</span><span class="sxs-lookup"><span data-stu-id="4d046-136">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="4d046-137">**在所有环境中部署** — 可以通过你的所有环境部署映像。</span><span class="sxs-lookup"><span data-stu-id="4d046-137">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="4d046-138">这种方法减少了配置差异导致的故障，通常通过外部配置（例如，注入的环境变量）改变映像行为。</span><span class="sxs-lookup"><span data-stu-id="4d046-138">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="4d046-139">[通用指南](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md)，确定是使用 .NET Core 还是 .NET Framework 进行 Docker 容器开发。</span><span class="sxs-lookup"><span data-stu-id="4d046-139">[General guidance](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="4d046-140">常见的 Docker 开发方案</span><span class="sxs-lookup"><span data-stu-id="4d046-140">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="4d046-141">.NET Core</span><span class="sxs-lookup"><span data-stu-id="4d046-141">.NET Core</span></span>

<span data-ttu-id="4d046-142">**.NET Core 资源**</span><span class="sxs-lookup"><span data-stu-id="4d046-142">**.NET Core resources**</span></span>

 <span data-ttu-id="4d046-143">选择适合你感兴趣方案的 .NET Core 示例。</span><span class="sxs-lookup"><span data-stu-id="4d046-143">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="4d046-144">所有示例说明都介绍了如何从 Windows、Linux 或 macOS 主机定位 Windows 或 Linux Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="4d046-144">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="4d046-145">这些示例使用 .NET Core 2.0。</span><span class="sxs-lookup"><span data-stu-id="4d046-145">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="4d046-146">它们会在适用时使用 Docker [多阶段生成](https://github.com/dotnet/announcements/issues/18)和[多拱形标记](https://github.com/dotnet/announcements/issues/14)。</span><span class="sxs-lookup"><span data-stu-id="4d046-146">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="4d046-147">DockerHub 上的 .NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-147">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="4d046-148">使 .NET Core 应用程序 Docker 化</span><span class="sxs-lookup"><span data-stu-id="4d046-148">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="4d046-149">此 .NET Core Docker 示例演示如何[在 .NET Core 开发过程中使用 Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)。</span><span class="sxs-lookup"><span data-stu-id="4d046-149">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="4d046-150">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="4d046-150">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="4d046-151">此 .NET Core Docker 示例演示了[生成 .NET Core 应用程序的 Docker 映像以用于生产](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="4d046-151">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="4d046-152">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="4d046-152">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="4d046-153">此 [.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)演示了生成[独立式 .NET Core 应用程序](../deploying/index.md)的 Docker 映像的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="4d046-153">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](../deploying/index.md).</span></span> <span data-ttu-id="4d046-154">用于最小的生产容器，而不会受益于[在容器之间共享基础映像](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)。</span><span class="sxs-lookup"><span data-stu-id="4d046-154">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="4d046-155">但是，可以共享较低的 Docker 层。</span><span class="sxs-lookup"><span data-stu-id="4d046-155">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="4d046-156">ARM32/Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="4d046-156">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="4d046-157">.NET Core 运行时 ARM32 生成公告</span><span class="sxs-lookup"><span data-stu-id="4d046-157">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="4d046-158">DockerHub 上的 ARM32/Raspberry Pi .NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-158">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="4d046-159">GitHub 上的 ARM32/Raspberry Pi .NET Core Docker 示例</span><span class="sxs-lookup"><span data-stu-id="4d046-159">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="4d046-160">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="4d046-160">.NET Framework</span></span>

* [<span data-ttu-id="4d046-161">DockerHub 上的 .NET Framework 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-161">.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet-framework/)

<span data-ttu-id="4d046-162">此存储库包含演示各种 .NET Framework Docker 配置的示例。</span><span class="sxs-lookup"><span data-stu-id="4d046-162">This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="4d046-163">你可以将这些映像作为自己的 Docker 映像的基础。</span><span class="sxs-lookup"><span data-stu-id="4d046-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="4d046-164">**.NET Framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="4d046-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="4d046-165">[dotnet-framework:4.7 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)演示 [.NET Framework 4.7](../../framework/whats-new/index.md#v47) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="4d046-165">The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](../../framework/whats-new/index.md#v47).</span></span> <span data-ttu-id="4d046-166">它演示如何生成并部署依赖于 [.NET Framework 4.7 docker 映像](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile)的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d046-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).</span></span>

<span data-ttu-id="4d046-167">**.NET Framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="4d046-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="4d046-168">[dotnet-framework:4.6.2 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)演示 [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="4d046-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462).</span></span> <span data-ttu-id="4d046-169">它演示如何生成并部署依赖于 [.NET Framework 4.6.2 docker 映像](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile)的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d046-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile).</span></span>

<span data-ttu-id="4d046-170">**.NET Framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="4d046-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="4d046-171">[dotnet-framework:3.5 示例](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)演示 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile) 的基本“hello world”用法。</span><span class="sxs-lookup"><span data-stu-id="4d046-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile).</span></span> <span data-ttu-id="4d046-172">它演示如何在 Docker 中生成并部署依赖于 .NET Framework 3.5 的项目。</span><span class="sxs-lookup"><span data-stu-id="4d046-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="4d046-173">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4d046-173">ASP.NET Core</span></span>

* <span data-ttu-id="4d046-174">[此 ASP.NET Core Docker 示例](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)演示了生成 ASP.NET Core 应用程序的 Docker 映像以用于生产的最佳实践模式。</span><span class="sxs-lookup"><span data-stu-id="4d046-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="4d046-175">此示例适用于 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="4d046-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="4d046-176">DockerHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="4d046-177">GitHub 上的 ASP.NET Core 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="4d046-178">ASP.NET 框架</span><span class="sxs-lookup"><span data-stu-id="4d046-178">ASP.NET Framework</span></span>

* [<span data-ttu-id="4d046-179">DockerHub 上的 ASP.NET 框架映像</span><span class="sxs-lookup"><span data-stu-id="4d046-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="4d046-180">.NET Framework 4.6.2 示例中的 ASP.NET Web 窗体应用</span><span class="sxs-lookup"><span data-stu-id="4d046-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="4d046-181">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="4d046-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="4d046-182">DockerHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="4d046-183">GitHub 上的 Windows Communication Framework (WCF) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

* [<span data-ttu-id="4d046-184">使用 .NET Full Framework 4.6.2 的 Windows Communication Framework (WCF) Docker 示例</span><span class="sxs-lookup"><span data-stu-id="4d046-184">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="4d046-185">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="4d046-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="4d046-186">DockerHub 上的 Internet Information Server (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="4d046-187">GitHub 上的 Internet Information Server (IIS) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="4d046-188">与其他 Microsoft 堆栈容器映像进行交互</span><span class="sxs-lookup"><span data-stu-id="4d046-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="4d046-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d046-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="4d046-190">使用 Docker 快速入门运行 Microsoft SQL Server for Linux 2017 容器映像</span><span class="sxs-lookup"><span data-stu-id="4d046-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="4d046-191">DockerHub 上的 Microsoft SQL Server for Linux 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [<span data-ttu-id="4d046-192">DockerHub 上的用于 Windows 容器的 Microsoft SQL Server Express Edition 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-192">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="4d046-193">DockerHub 上的用于 Windows 容器的 Microsoft SQL Server Developer Edition 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-193">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="4d046-194">Visual Studio Team Services (VSTS) 代理</span><span class="sxs-lookup"><span data-stu-id="4d046-194">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="4d046-195">DockerHub 上的 Visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="4d046-195">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="4d046-196">GitHub 上的 Visual Studio Team Services (VSTS) 代理映像</span><span class="sxs-lookup"><span data-stu-id="4d046-196">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="4d046-197">Operations Management Suite (OMS) Linux 代理</span><span class="sxs-lookup"><span data-stu-id="4d046-197">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="4d046-198">Operations Management Suite (OMS) Linux 代理概述</span><span class="sxs-lookup"><span data-stu-id="4d046-198">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [<span data-ttu-id="4d046-199">DockerHub 上的 Operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-199">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/oms/)

* [<span data-ttu-id="4d046-200">GitHub 上的 Operations Management Suite (OMS) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-200">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="4d046-201">Microsoft Azure 命令行接口 (CLI)</span><span class="sxs-lookup"><span data-stu-id="4d046-201">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="4d046-202">DockerHub 上的 Microsoft Azure 命令行接口 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-202">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cli/) 

* [<span data-ttu-id="4d046-203">GitHub 上的 Microsoft Azure 命令行接口 (CLI) 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-203">Microsoft Azure Command-Line Interface (CLI) images on GitHub</span></span>](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> <span data-ttu-id="4d046-204">如果你没有 Azure 订阅，请[立即注册](https://azure.microsoft.com/free/?b=16.48)获取一个免费的 30 天试用帐户和 200 美元的 Azure 信用额度，以便试用 Azure 服务的任意组合。</span><span class="sxs-lookup"><span data-stu-id="4d046-204">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="4d046-205">Microsoft Azure Cosmos DB 仿真器（仅限 Windows 容器）</span><span class="sxs-lookup"><span data-stu-id="4d046-205">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="4d046-206">DockerHub 上的 Microsoft Azure Cosmos DB 仿真器映像</span><span class="sxs-lookup"><span data-stu-id="4d046-206">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="4d046-207">将 Azure Cosmos DB 仿真器用于本地开发和测试</span><span class="sxs-lookup"><span data-stu-id="4d046-207">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="4d046-208">探索内容丰富的 Docker 开发生态系统</span><span class="sxs-lookup"><span data-stu-id="4d046-208">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="4d046-209">了解了 Docker 平台和不同的 Docker 映像后，下一步就是探索内容丰富的 Docker 生态系统。</span><span class="sxs-lookup"><span data-stu-id="4d046-209">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="4d046-210">以下链接展示了 Microsoft 工具对容器开发所做的补充。</span><span class="sxs-lookup"><span data-stu-id="4d046-210">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="4d046-211">将 .NET 与 Docker 一起使用</span><span class="sxs-lookup"><span data-stu-id="4d046-211">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)
* [<span data-ttu-id="4d046-212">设计和开发基于微服务的多容器 .NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="4d046-212">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [<span data-ttu-id="4d046-213">Visual Studio Code Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="4d046-213">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile)
* [<span data-ttu-id="4d046-214">了解如何使用 Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="4d046-214">Learn how to use Azure Service Fabric</span></span>](/azure/service-fabric/index)
* [<span data-ttu-id="4d046-215">Service Fabric 入门示例</span><span class="sxs-lookup"><span data-stu-id="4d046-215">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="4d046-216">Windows 容器的优点</span><span class="sxs-lookup"><span data-stu-id="4d046-216">Benefits of Windows Containers</span></span>](/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="4d046-217">使用 Visual Studio Docker 工具</span><span class="sxs-lookup"><span data-stu-id="4d046-217">Working with Visual Studio Docker Tools</span></span>](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* [<span data-ttu-id="4d046-218">将 Azure 容器注册表中的 Docker 映像部署到 Azure 容器实例</span><span class="sxs-lookup"><span data-stu-id="4d046-218">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="4d046-219">使用 Visual Studio Code 进行调试</span><span class="sxs-lookup"><span data-stu-id="4d046-219">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* [<span data-ttu-id="4d046-220">在云中使用 Visual Studio for Mac、容器和无服务器代码</span><span class="sxs-lookup"><span data-stu-id="4d046-220">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="4d046-221">Docker 和 Visual Studio for Mac Lab 入门</span><span class="sxs-lookup"><span data-stu-id="4d046-221">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="4d046-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4d046-222">Next steps</span></span>

* [<span data-ttu-id="4d046-223">了解使用 .NET Core 的 Docker 的基本信息</span><span class="sxs-lookup"><span data-stu-id="4d046-223">Learn Docker Basics with .NET Core</span></span>](docker-basics-dotnet-core.md)
* [<span data-ttu-id="4d046-224">生成 .NET Core Docker 映像</span><span class="sxs-lookup"><span data-stu-id="4d046-224">Building .NET Core Docker Images</span></span>](building-net-docker-images.md)
