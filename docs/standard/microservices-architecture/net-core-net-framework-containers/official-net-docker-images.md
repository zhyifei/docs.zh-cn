---
title: "正式.NET Docker 映像"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |正式.NET Docker 映像"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a><span data-ttu-id="b204e-104">正式.NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="b204e-104">Official .NET Docker images</span></span>

<span data-ttu-id="b204e-105">官方.NET Docker 映像是创建和优化的 Microsoft 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-105">The Official .NET Docker images are Docker images created and optimized by Microsoft.</span></span> <span data-ttu-id="b204e-106">它们中公开可用的 Microsoft 存储库上[Docker Hub](https://hub.docker.com/u/microsoft/)。</span><span class="sxs-lookup"><span data-stu-id="b204e-106">They are publicly available in the Microsoft repositories on [Docker Hub](https://hub.docker.com/u/microsoft/).</span></span> <span data-ttu-id="b204e-107">每个存储库可以包含多个映像，具体取决于.NET 版本，并根据操作系统和版本 （Linux Debian、 Linux Alpine、 Windows Nano Server、 Windows Server Core 等）。</span><span class="sxs-lookup"><span data-stu-id="b204e-107">Each repository can contain multiple images, depending on .NET versions, and depending on the OS and versions (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).</span></span>

<span data-ttu-id="b204e-108">.NET 存储库的 Microsoft 的愿景是让精细的专注于存储库，其中存储库表示特定方案或工作负荷。</span><span class="sxs-lookup"><span data-stu-id="b204e-108">Microsoft’s vision for .NET repositories is to have granular and focused repos, where a repo represents a specific scenario or workload.</span></span> <span data-ttu-id="b204e-109">例如， [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)上 Docker，使用 ASP.NET Core，因为这些 ASP.NET Core 映像提供额外的优化是容器可以更快地启动时，应使用映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-109">For instance, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) images should be used when using ASP.NET Core on Docker, because those ASP.NET Core images provide additional optimizations so containers can start faster.</span></span>

<span data-ttu-id="b204e-110">另一方面，.NET 核心映像 (microsoft/dotnet) 用于基于.NET 核心的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="b204e-110">On the other hand, the .NET Core images (microsoft/dotnet) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="b204e-111">例如，批处理、 Azure WebJobs 和其他控制台方案应使用.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="b204e-111">For example, batch processes, Azure WebJobs, and other console scenarios should use .NET Core.</span></span> <span data-ttu-id="b204e-112">这些映像不包括 ASP.NET Core 堆栈，从而导致较小的容器映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-112">Those images do not include the ASP.NET Core stack, resulting in a smaller container image.</span></span>

<span data-ttu-id="b204e-113">大多数映像存储库提供大量标记，来帮助你选择不只是特定的框架版本中，而且还可以选择的操作系统 （Linux 发行版或 Windows 版本）。</span><span class="sxs-lookup"><span data-stu-id="b204e-113">Most image repos provide extensive tagging to help you select not just a specific framework version, but also to choose an OS (Linux distro or Windows version).</span></span>

<span data-ttu-id="b204e-114">由 Microsoft 提供的正式.NET Docker 映像的详细信息，请参阅[.NET Docker 映像摘要](https://aka.ms/dotnetdockerimages)。</span><span class="sxs-lookup"><span data-stu-id="b204e-114">For further information about the official .NET Docker images provided by Microsoft, see the [.NET Docker Images summary](https://aka.ms/dotnetdockerimages).</span></span>

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a><span data-ttu-id="b204e-115">用于与生产开发的.NET 核心和 Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="b204e-115">.NET Core and Docker image optimizations for development versus production</span></span>

<span data-ttu-id="b204e-116">当为开发人员构建 Docker 映像，Microsoft 将侧重于以下主要方案：</span><span class="sxs-lookup"><span data-stu-id="b204e-116">When building Docker images for developers, Microsoft focused on the following main scenarios:</span></span>

-   <span data-ttu-id="b204e-117">使用到的图像*开发*和生成.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="b204e-117">Images used to *develop* and build .NET Core apps.</span></span>

-   <span data-ttu-id="b204e-118">使用到的图像*运行*.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="b204e-118">Images used to *run* .NET Core apps.</span></span>

<span data-ttu-id="b204e-119">为什么多个映像？</span><span class="sxs-lookup"><span data-stu-id="b204e-119">Why multiple images?</span></span> <span data-ttu-id="b204e-120">当开发、 构建和运行容器化应用程序时，你通常具有不同的优先级别。</span><span class="sxs-lookup"><span data-stu-id="b204e-120">When developing, building, and running containerized applications, you usually have different priorities.</span></span> <span data-ttu-id="b204e-121">通过适用于这些单独的任务提供不同的映像，Microsoft 有助于优化的开发、 构建和部署应用程序的单独进程。</span><span class="sxs-lookup"><span data-stu-id="b204e-121">By providing different images for these separate tasks, Microsoft helps optimize the separate processes of developing, building, and deploying apps.</span></span>

### <a name="during-development-and-build"></a><span data-ttu-id="b204e-122">在开发和生成过程</span><span class="sxs-lookup"><span data-stu-id="b204e-122">During development and build</span></span>

<span data-ttu-id="b204e-123">在开发期间，重要的一点是速度可循环更改和调试所做的更改的能力。</span><span class="sxs-lookup"><span data-stu-id="b204e-123">During development, what is important is how fast you can iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="b204e-124">图像的大小不是对代码进行更改并快速查看的更改的功能与同等重要的。</span><span class="sxs-lookup"><span data-stu-id="b204e-124">The size of the image is not as important as the ability to make changes to your code and see the changes quickly.</span></span> <span data-ttu-id="b204e-125">某些工具和"生成代理容器"，使用开发 ASP.NET Core 映像 （microsoft/aspnetcore-生成） 在开发过程和生成流程。</span><span class="sxs-lookup"><span data-stu-id="b204e-125">Some tools and "build-agent containers", use the development ASP.NET Core image (microsoft/aspnetcore-build) during development and build proces.</span></span> <span data-ttu-id="b204e-126">构建在 Docker 容器内时, 的重要方面是为了编译你的应用程序所需要的元素。</span><span class="sxs-lookup"><span data-stu-id="b204e-126">When building inside a Docker container, the important aspects are the elements that are needed in order to compile your app.</span></span> <span data-ttu-id="b204e-127">这包括编译器和任何其他.NET 依赖关系，以及 npm，如 web 开发依赖项的 Gulp，和 Bower。</span><span class="sxs-lookup"><span data-stu-id="b204e-127">This includes the compiler and any other .NET dependencies, plus web development dependencies like npm, Gulp, and Bower.</span></span>

<span data-ttu-id="b204e-128">此类型的生成映像为什么很重要？</span><span class="sxs-lookup"><span data-stu-id="b204e-128">Why is this type of build image important?</span></span> <span data-ttu-id="b204e-129">你无需向生产部署此映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-129">You do not deploy this image to production.</span></span> <span data-ttu-id="b204e-130">相反，它是用于放置的内容生成到生产映像的映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-130">Instead, it is an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="b204e-131">在持续集成 (CI) 环境或生成环境中，将使用此映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-131">This image would be used in your continuous integration (CI) environment or build environment.</span></span> <span data-ttu-id="b204e-132">例如，而不是直接在生成代理上手动安装所有应用程序依赖关系托管 (例如，一个 VM)，生成代理会在生成应用程序所需的所有依赖项的情况下实例化.NET Core 生成映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-132">For instance, rather than manually installing all your application dependencies directly on a build agent host (a VM, for example), the build agent would instantiate a .NET Core build image with all the dependencies required to build the application.</span></span> <span data-ttu-id="b204e-133">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="b204e-133">Your build agent only needs to know how to run this Docker image.</span></span> <span data-ttu-id="b204e-134">这简化了 CI 环境，并使其更可预测。</span><span class="sxs-lookup"><span data-stu-id="b204e-134">This simplifies your CI environment and makes it much more predictable.</span></span>

### <a name="in-production"></a><span data-ttu-id="b204e-135">在生产环境中</span><span class="sxs-lookup"><span data-stu-id="b204e-135">In production</span></span>

<span data-ttu-id="b204e-136">在生产中重要的是如何快速你可以部署和启动你的生产.NET Core 映像所基于的容器。</span><span class="sxs-lookup"><span data-stu-id="b204e-136">What is important in production is how fast you can deploy and start your containers based on a production .NET Core image.</span></span> <span data-ttu-id="b204e-137">因此，仅运行时映像基于[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)很小，以便它可以快速通过网络传输从 Docker 注册表到 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="b204e-137">Therefore, the runtime-only image based on [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) is small so that it can travel quickly across the network from your Docker registry to your Docker hosts.</span></span> <span data-ttu-id="b204e-138">内容已准备好运行，启用从启动到处理结果容器时间最短。</span><span class="sxs-lookup"><span data-stu-id="b204e-138">The contents are ready to run, enabling the fastest time from starting the container to processing results.</span></span> <span data-ttu-id="b204e-139">在 Docker 模型中，没有编译 C 中无需\#代码，因为存在正在运行 dotnet 生成或 dotnet 发布时时使用生成容器。</span><span class="sxs-lookup"><span data-stu-id="b204e-139">In the Docker model, there is no need for compilation from C\# code, as there is when you run dotnet build or dotnet publish when using the build container.</span></span>

<span data-ttu-id="b204e-140">在此优化的映像您放入仅的二进制文件和运行应用程序所需的其他内容。</span><span class="sxs-lookup"><span data-stu-id="b204e-140">In this optimized image you put only the binaries and other content needed to run the application.</span></span> <span data-ttu-id="b204e-141">例如，由 dotnet 创建的内容发布包含已编译的.NET 二进制文件、 映像、.js 和.css 文件。</span><span class="sxs-lookup"><span data-stu-id="b204e-141">For example, the content created by dotnet publish contains only the compiled .NET binaries, images, .js, and .css files.</span></span> <span data-ttu-id="b204e-142">随着时间推移，你将看到包含 pre jitted 包的映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-142">Over time, you will see images that contain pre-jitted packages.</span></span>

<span data-ttu-id="b204e-143">虽然有多个版本的.NET Core 和 ASP.NET Core 映像，但它们都共享一个或多个层，包括基本层。</span><span class="sxs-lookup"><span data-stu-id="b204e-143">Although there are multiple versions of the .NET Core and ASP.NET Core images, they all share one or more layers, including the base layer.</span></span> <span data-ttu-id="b204e-144">因此，存储映像所需的磁盘空间量是小;它仅包含自定义映像和其基础的映像之间的增量。</span><span class="sxs-lookup"><span data-stu-id="b204e-144">Therefore, the amount of disk space needed to store an image is small; it consists only of the delta between your custom image and its base image.</span></span> <span data-ttu-id="b204e-145">结果是，它是快速从您的注册表中提取映像。</span><span class="sxs-lookup"><span data-stu-id="b204e-145">The result is that it is quick to pull the image from your registry.</span></span>

<span data-ttu-id="b204e-146">当你浏览在 Docker Hub.NET 映像存储库时，您会发现多个映像版本分类或标记与标记。</span><span class="sxs-lookup"><span data-stu-id="b204e-146">When you explore the .NET image repositories at Docker Hub, you will find multiple image versions classified or marked with tags.</span></span> <span data-ttu-id="b204e-147">这些标记可帮助决定要使用，根据需要类似于下表中的版本哪一种：</span><span class="sxs-lookup"><span data-stu-id="b204e-147">These tags help to decide which one to use, depending on the version you need, like those in the following table:</span></span>

-   <span data-ttu-id="b204e-148">microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="b204e-148">microsoft/**aspnetcore:2.0**</span></span>

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   <span data-ttu-id="b204e-149">microsoft /**aspnetcore-生成： 2.0**</span><span class="sxs-lookup"><span data-stu-id="b204e-149">microsoft/**aspnetcore-build:2.0**</span></span>

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
<span data-ttu-id="b204e-150">[以前](net-容器-os-targets.md) [下一步] (.../architect-microservice-container-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b204e-150">[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)</span></span>
