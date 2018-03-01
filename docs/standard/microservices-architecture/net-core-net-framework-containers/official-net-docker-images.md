---
title: "官方 .NET Docker 映像"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 官方 .NET Docker 映像"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42872caa1a9306187daeefd35feb9bec3fae60af
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="official-net-docker-images"></a><span data-ttu-id="000a0-104">官方 .NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="000a0-104">Official .NET Docker images</span></span>

<span data-ttu-id="000a0-105">官方 .NET Docker 映像是由 Microsoft 创建和优化的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="000a0-105">The Official .NET Docker images are Docker images created and optimized by Microsoft.</span></span> <span data-ttu-id="000a0-106">这些映像在 [Docker 中心](https://hub.docker.com/u/microsoft/)的 Microsoft 存储库中公开提供。</span><span class="sxs-lookup"><span data-stu-id="000a0-106">They are publicly available in the Microsoft repositories on [Docker Hub](https://hub.docker.com/u/microsoft/).</span></span> <span data-ttu-id="000a0-107">每个存储库可以包含多个映像，具体取决于 .NET 版本以及操作系统和版本（Linux Debian、Linux Alpine、Windows Nano Server、Windows Server Core 等）。</span><span class="sxs-lookup"><span data-stu-id="000a0-107">Each repository can contain multiple images, depending on .NET versions, and depending on the OS and versions (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).</span></span>

<span data-ttu-id="000a0-108">Microsoft 对 .NET 存储库的愿景是要具有细粒度和集中存储库，其中存储库表示特定方案或工作负荷。</span><span class="sxs-lookup"><span data-stu-id="000a0-108">Microsoft’s vision for .NET repositories is to have granular and focused repos, where a repo represents a specific scenario or workload.</span></span> <span data-ttu-id="000a0-109">例如，当在 Docker 上使用 ASP.NET Core 时，应使用 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 映像，因为这些 ASP.NET Core 映像提供了额外的优化，以便容器可以更快地启动。</span><span class="sxs-lookup"><span data-stu-id="000a0-109">For instance, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) images should be used when using ASP.NET Core on Docker, because those ASP.NET Core images provide additional optimizations so containers can start faster.</span></span>

<span data-ttu-id="000a0-110">另一方面，.NET Core 映像 (microsoft/dotnet) 适用于基于 .NET Core 的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="000a0-110">On the other hand, the .NET Core images (microsoft/dotnet) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="000a0-111">例如，批处理、Azure WebJobs 和其他控制台方案应使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="000a0-111">For example, batch processes, Azure WebJobs, and other console scenarios should use .NET Core.</span></span> <span data-ttu-id="000a0-112">这些映像不包括 ASP.NET Core 堆栈，因此导致容器映像更小。</span><span class="sxs-lookup"><span data-stu-id="000a0-112">Those images do not include the ASP.NET Core stack, resulting in a smaller container image.</span></span>

<span data-ttu-id="000a0-113">大多数映像存储库提供广泛的标记，以帮助选择特定的框架版本以及 OS（Linux 发行版或 Windows 版本）。</span><span class="sxs-lookup"><span data-stu-id="000a0-113">Most image repos provide extensive tagging to help you select not just a specific framework version, but also to choose an OS (Linux distro or Windows version).</span></span>

<span data-ttu-id="000a0-114">有关 Microsoft 提供的官方 .NET Docker 映像的详细信息，请参阅 [.NET Docker 映像摘要](https://aka.ms/dotnetdockerimages)。</span><span class="sxs-lookup"><span data-stu-id="000a0-114">For further information about the official .NET Docker images provided by Microsoft, see the [.NET Docker Images summary](https://aka.ms/dotnetdockerimages).</span></span>

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a><span data-ttu-id="000a0-115">适用于开发与生产的 .NET Core 和 Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="000a0-115">.NET Core and Docker image optimizations for development versus production</span></span>

<span data-ttu-id="000a0-116">为开发人员生成 Docker 映像时，Microsoft 侧重于以下主要方案：</span><span class="sxs-lookup"><span data-stu-id="000a0-116">When building Docker images for developers, Microsoft focused on the following main scenarios:</span></span>

-   <span data-ttu-id="000a0-117">用于开发和生成 .NET Core 应用的映像。</span><span class="sxs-lookup"><span data-stu-id="000a0-117">Images used to *develop* and build .NET Core apps.</span></span>

-   <span data-ttu-id="000a0-118">用于运行 .NET Core 应用的映像。</span><span class="sxs-lookup"><span data-stu-id="000a0-118">Images used to *run* .NET Core apps.</span></span>

<span data-ttu-id="000a0-119">为什么是多个映像？</span><span class="sxs-lookup"><span data-stu-id="000a0-119">Why multiple images?</span></span> <span data-ttu-id="000a0-120">因为在开发、生成和运行容器化应用程序时，通常具有不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="000a0-120">When developing, building, and running containerized applications, you usually have different priorities.</span></span> <span data-ttu-id="000a0-121">通过为这些单独的任务提供不同的映像，Microsoft 有助于优化开发、生成和部署应用程序的单独进程。</span><span class="sxs-lookup"><span data-stu-id="000a0-121">By providing different images for these separate tasks, Microsoft helps optimize the separate processes of developing, building, and deploying apps.</span></span>

### <a name="during-development-and-build"></a><span data-ttu-id="000a0-122">在开发和生成过程中</span><span class="sxs-lookup"><span data-stu-id="000a0-122">During development and build</span></span>

<span data-ttu-id="000a0-123">在开发期间，重要的是可循环访问更改的速度以及调试更改的能力。</span><span class="sxs-lookup"><span data-stu-id="000a0-123">During development, what is important is how fast you can iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="000a0-124">与更改代码的能力和快速查看更改相比，映像的大小不是那么重要。</span><span class="sxs-lookup"><span data-stu-id="000a0-124">The size of the image is not as important as the ability to make changes to your code and see the changes quickly.</span></span> <span data-ttu-id="000a0-125">某些工具和“build-agent 容器”在开发和生成过程中使用开发 ASP.NET Core 映像 (microsoft/aspnetcore-build)。</span><span class="sxs-lookup"><span data-stu-id="000a0-125">Some tools and "build-agent containers", use the development ASP.NET Core image (microsoft/aspnetcore-build) during development and build proces.</span></span> <span data-ttu-id="000a0-126">在 Docker 容器中生成时，重要方面是为了编译应用所需要的元素。</span><span class="sxs-lookup"><span data-stu-id="000a0-126">When building inside a Docker container, the important aspects are the elements that are needed in order to compile your app.</span></span> <span data-ttu-id="000a0-127">这包括编译器和任何其他 .NET 依赖项，以及 npm、Gulp和 Bower 等 Web 开发依赖项。</span><span class="sxs-lookup"><span data-stu-id="000a0-127">This includes the compiler and any other .NET dependencies, plus web development dependencies like npm, Gulp, and Bower.</span></span>

<span data-ttu-id="000a0-128">为什么此类型的生成映像很重要？</span><span class="sxs-lookup"><span data-stu-id="000a0-128">Why is this type of build image important?</span></span> <span data-ttu-id="000a0-129">不能将此映像部署到生产中。</span><span class="sxs-lookup"><span data-stu-id="000a0-129">You do not deploy this image to production.</span></span> <span data-ttu-id="000a0-130">相反，它是用于生成放置在生产映像中的内容的映像。</span><span class="sxs-lookup"><span data-stu-id="000a0-130">Instead, it is an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="000a0-131">此映像将用于持续集成 (CI) 环境或生成环境中。</span><span class="sxs-lookup"><span data-stu-id="000a0-131">This image would be used in your continuous integration (CI) environment or build environment.</span></span> <span data-ttu-id="000a0-132">例如，生成代理会将 .NET Core 实例化，其中包含构建应用程序所需的所有依赖项，而不是直接在生成代理主机（例如 VM）上手动安装所有应用程序依赖项。</span><span class="sxs-lookup"><span data-stu-id="000a0-132">For instance, rather than manually installing all your application dependencies directly on a build agent host (a VM, for example), the build agent would instantiate a .NET Core build image with all the dependencies required to build the application.</span></span> <span data-ttu-id="000a0-133">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="000a0-133">Your build agent only needs to know how to run this Docker image.</span></span> <span data-ttu-id="000a0-134">这简化了 CI 环境，并使其更可预测。</span><span class="sxs-lookup"><span data-stu-id="000a0-134">This simplifies your CI environment and makes it much more predictable.</span></span>

### <a name="in-production"></a><span data-ttu-id="000a0-135">生产中</span><span class="sxs-lookup"><span data-stu-id="000a0-135">In production</span></span>

<span data-ttu-id="000a0-136">在生产中重要的是基于生产 .NET Core 映像部署和启动容器的速度。</span><span class="sxs-lookup"><span data-stu-id="000a0-136">What is important in production is how fast you can deploy and start your containers based on a production .NET Core image.</span></span> <span data-ttu-id="000a0-137">因此，基于 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 的仅运行时映像很小，以便它可以通过网络从 Docker 注册表快速传输到 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="000a0-137">Therefore, the runtime-only image based on [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) is small so that it can travel quickly across the network from your Docker registry to your Docker hosts.</span></span> <span data-ttu-id="000a0-138">已准备运行内容，以此实现从启动容器到处理结果的最快时间。</span><span class="sxs-lookup"><span data-stu-id="000a0-138">The contents are ready to run, enabling the fastest time from starting the container to processing results.</span></span> <span data-ttu-id="000a0-139">在 Docker 模型中，不需要编译 C\# 代码，但在使用生成容器运行 dotnet 生成或 dotnet 发布时需要。</span><span class="sxs-lookup"><span data-stu-id="000a0-139">In the Docker model, there is no need for compilation from C\# code, as there is when you run dotnet build or dotnet publish when using the build container.</span></span>

<span data-ttu-id="000a0-140">在此优化的映像中，只放置运行应用程序所需的二进制文件和其他内容。</span><span class="sxs-lookup"><span data-stu-id="000a0-140">In this optimized image you put only the binaries and other content needed to run the application.</span></span> <span data-ttu-id="000a0-141">例如，由 dotnet 发布创建的内容仅包含已编译的.NET 二进制文件、映像、.js 和 .css 文件。</span><span class="sxs-lookup"><span data-stu-id="000a0-141">For example, the content created by dotnet publish contains only the compiled .NET binaries, images, .js, and .css files.</span></span> <span data-ttu-id="000a0-142">随着时间的推移，用户将看到包含预实时编译的包。</span><span class="sxs-lookup"><span data-stu-id="000a0-142">Over time, you will see images that contain pre-jitted packages.</span></span>

<span data-ttu-id="000a0-143">虽然 .NET Core 和 ASP.NET Core 映像有多个版本，但它们全都共享一个或多个层，包括基本层。</span><span class="sxs-lookup"><span data-stu-id="000a0-143">Although there are multiple versions of the .NET Core and ASP.NET Core images, they all share one or more layers, including the base layer.</span></span> <span data-ttu-id="000a0-144">因此，存储映像所需的磁盘空间量很小；它仅包含自定义映像和其基础映像之间的增量。</span><span class="sxs-lookup"><span data-stu-id="000a0-144">Therefore, the amount of disk space needed to store an image is small; it consists only of the delta between your custom image and its base image.</span></span> <span data-ttu-id="000a0-145">结果，从注册表中提取映像速度会很快。</span><span class="sxs-lookup"><span data-stu-id="000a0-145">The result is that it is quick to pull the image from your registry.</span></span>

<span data-ttu-id="000a0-146">在 Docker 中心浏览 .NET 映像存储库时，会发现已使用标记将多个映像版本进行分类或标记。</span><span class="sxs-lookup"><span data-stu-id="000a0-146">When you explore the .NET image repositories at Docker Hub, you will find multiple image versions classified or marked with tags.</span></span> <span data-ttu-id="000a0-147">这些标记有助于决定使用哪一个，具体取决于需要的版本，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="000a0-147">These tags help to decide which one to use, depending on the version you need, like those in the following table:</span></span>

-   <span data-ttu-id="000a0-148">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="000a0-148">microsoft/**aspnetcore:2.0**</span></span>

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   <span data-ttu-id="000a0-149">microsoft/aspnetcore-build:2.0</span><span class="sxs-lookup"><span data-stu-id="000a0-149">microsoft/**aspnetcore-build:2.0**</span></span>

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
<span data-ttu-id="000a0-150">[上一篇] (net-container-os-targets.md) [下一篇] (../architect-microservice-container-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="000a0-150">[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)</span></span>
