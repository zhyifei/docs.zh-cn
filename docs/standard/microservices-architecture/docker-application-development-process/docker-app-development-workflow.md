---
title: "Docker 应用的开发工作流"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Docker 应用的开发工作流"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="1a9c6-104">Docker 应用的开发工作流</span><span class="sxs-lookup"><span data-stu-id="1a9c6-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="1a9c6-105">应用程序开发生命周期开始每个开发人员的计算机，其中开发人员代码使用其首选的语言的应用程序和本地测试它。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="1a9c6-106">无论哪个语言、 框架和平台选择开发人员，借助此工作流，开发人员始终开发和测试 Docker 容器，但是本地执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="1a9c6-107">每个容器 （Docker 映像的实例） 包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="1a9c6-108">操作系统选择 （例如，一种 Linux 分发，Windows Nano Server 或 Windows Server Core）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="1a9c6-109">由开发人员 （应用程序二进制文件等） 添加的文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="1a9c6-110">（环境设置及依赖关系） 的配置信息。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="1a9c6-111">有关在开发 Docker 容器基于应用程序的工作流</span><span class="sxs-lookup"><span data-stu-id="1a9c6-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="1a9c6-112">本部分介绍*内部循环*Docker 容器基于应用程序的开发工作流。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="1a9c6-113">内部循环工作流意味着它不会占用考虑更广泛的 DevOps 工作流，并只重点介绍在开发人员计算机上完成开发工作。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="1a9c6-114">设置环境的初始步骤不包括，，因为这些中进行一次。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="1a9c6-115">应用程序组成你自己的服务和其他库 （依赖项）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="1a9c6-116">以下是你通常执行时生成 Docker 应用程序，如图 5-1 中所示的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="1a9c6-117">**图 5-1。**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-117">**Figure 5-1.**</span></span> <span data-ttu-id="1a9c6-118">开发 Docker 容器化应用程序的分步工作流</span><span class="sxs-lookup"><span data-stu-id="1a9c6-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="1a9c6-119">本指南中详细介绍了此整个过程和每个主要步骤通过将重点放在 Visual Studio 环境上所述。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="1a9c6-120">当你使用的编辑器/CLI 开发方法 （例如，Visual Studio 代码以及在 macOS 上的 Docker CLI 或 Windows） 时，你需要知道每个步骤中，通常比使用 Visual Studio 的更详细地。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="1a9c6-121">有关使用 CLI 环境中的更多详细信息，请参阅电子书[与 Microsoft 平台和工具的容器的 Docker 应用程序生命周期](http://aka.ms/dockerlifecycleebook/)。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="1a9c6-122">当你使用 Visual Studio 2015 或 Visual Studio 2017 时，许多这些步骤会替你处理，这将显著提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="1a9c6-123">当你使用 Visual Studio 2017 并且面向多容器应用程序，也是如此。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="1a9c6-124">例如，只在一个鼠标单击 Visual Studio Dockerfile 并将其 docker-compose.yml 将文件添加到您的项目与你的应用程序的配置。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="1a9c6-125">Visual Studio 中运行应用程序时，它能够构建 Docker 映像和直接在 Docker; 运行多容器应用程序它甚至可以同时调试多个容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="1a9c6-126">这些功能将大大提高开发速度。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-126">These features will boost your development speed.</span></span>

<span data-ttu-id="1a9c6-127">但是，只是因为 Visual Studio 使这些步骤自动并不意味着不需要知道哪些是使用 Docker 后台。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="1a9c6-128">因此，在下面的指引，我们详细介绍每个步骤。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="1a9c6-129">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-129">Step 1.</span></span> <span data-ttu-id="1a9c6-130">开始编码并创建初始应用程序或服务基线</span><span class="sxs-lookup"><span data-stu-id="1a9c6-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="1a9c6-131">开发 Docker 应用程序是开发应用程序，而 Docker 不工作方式相似。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="1a9c6-132">区别是，开发时对 Docker，你部署和测试您的应用程序或服务在本地环境中的 Docker 容器内运行。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="1a9c6-133">容器可以是 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="1a9c6-134">设置本地环境使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1a9c6-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="1a9c6-135">若要开始，请确保你具有[Docker 社区版 (CE)](https://www.docker.com/community-edition)适用于 Windows 安装，如下面的说明中所述：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="1a9c6-136">要开始使用 CE 用于 Windows 的 Docker</span><span class="sxs-lookup"><span data-stu-id="1a9c6-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="1a9c6-137">此外，你将需要安装的 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="1a9c6-138">这是首选通过 Visual Studio 2015 使用 Visual Studio Tools for Docker 外接程序，因为 Visual Studio 2017 具有更高级的支持 Docker，如对调试容器的支持。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="1a9c6-139">Visual Studio 2017 包括 Docker 的工具，如果你选择**.NET 核心和 Docker**在安装期间，在图 5-2 中所示的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="1a9c6-140">**图 5-2**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-140">**Figure 5-2**.</span></span> <span data-ttu-id="1a9c6-141">选择**.NET 核心和 Docker**在 Visual Studio 2017 安装过程的工作负荷</span><span class="sxs-lookup"><span data-stu-id="1a9c6-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="1a9c6-142">即使之前，应用程序中启用 Docker 和部署和测试在 Docker 中启动编码 （通常在.NET 核心如果你打算使用容器） 中的纯.NET 中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="1a9c6-143">但是，建议你开始使用 Docker 上尽可能快，因为这将是对实际环境，并且可以尽可能快地发现任何问题。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="1a9c6-144">这因为 Visual Studio 使因此用户可轻松地使用 Docker，它几乎外观透明鼓励-调试从 Visual Studio 的多容器应用程序时的最佳示例。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-145">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-145">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-146">**要开始使用 CE 用于 Windows 的 Docker**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="1a9c6-147">**Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-147">**Visual Studio 2017**
[*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="1a9c6-148">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-148">Step 2.</span></span> <span data-ttu-id="1a9c6-149">创建与现有的.NET 基映像相关 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="1a9c6-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="1a9c6-150">你需要为你想要生成; 每个自定义图像的 Dockerfile你还需要每个容器的 Dockerfile，若要部署，是否自动从 Visual Studio 或使用 Docker CLI 手动部署 (运行的 docker 和 docker-撰写命令)。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="1a9c6-151">如果你的应用程序包含单个自定义服务，则需要单个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="1a9c6-152">如果你的应用程序包含多个服务 （如所示的微服务体系结构），你将需要一个 Dockerfile，为每个服务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="1a9c6-153">Dockerfile 放置在应用程序或服务的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="1a9c6-154">它包含告诉 Docker 如何设置和容器中运行应用程序或服务的命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="1a9c6-155">你可以手动在代码中创建 Dockerfile 和将其添加到你的项目，.NET 依赖项。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="1a9c6-156">使用 Visual Studio 和 Docker 其工具，此任务需要仅单击几下鼠标。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="1a9c6-157">当你在 Visual Studio 2017 年 1 中创建新项目时，可选择名为**启用容器 (Docker) 支持**，如图 5-3 中所示。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="1a9c6-158">**图 5-3**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-158">**Figure 5-3**.</span></span> <span data-ttu-id="1a9c6-159">在 Visual Studio 2017 年 1 中创建新项目时启用 Docker 的支持</span><span class="sxs-lookup"><span data-stu-id="1a9c6-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="1a9c6-160">此外可以通过右键单击你在 Visual Studio 中的项目文件并选择选项来启用对新的或现有项目的 Docker 支持**添加 Docker 项目支持**，如图 5-4 中所示。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="1a9c6-161">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-161">**Figure 5-4**.</span></span> <span data-ttu-id="1a9c6-162">在现有 Visual Studio 2017 项目中的启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="1a9c6-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="1a9c6-163">此操作 （如 ASP.NET Web 应用程序或 Web API 服务） 项目将添加到具有所需的配置项目的 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="1a9c6-164">它还添加了整个解决方案的 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="1a9c6-165">在以下部分中，我们将介绍将进入每个文件的信息。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="1a9c6-166">Visual Studio 可为你完成此工作，但它可用于了解哪些内容放到 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="1a9c6-167">选项 a： 创建项目使用现有官方.NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="1a9c6-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="1a9c6-168">通常在你可以从在正式存储库的基本映像之上容器生成自定义映像[Docker Hub](https://hub.docker.com/)注册表。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="1a9c6-169">这确切地说是时会发生什么情况下启用 Visual Studio 中的 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="1a9c6-170">Dockerfile 将使用现有 aspnetcore 映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="1a9c6-171">前面我们介绍了哪些 Docker 映像和存储库可以使用，具体取决于框架和你已选择的操作系统。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="1a9c6-172">例如，如果你想要使用 ASP.NET Core （Linux 或 Windows），要使用的图像是 microsoft / aspnetcore:2.0。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="1a9c6-173">因此，你只需指定将用于你的容器哪些基本 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="1a9c6-174">执行此操作通过从 microsoft 添加 / aspnetcore:2.0 到 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="1a9c6-175">这将由 Visual Studio 中，自动执行，但如果你是更新的版本，则更新此值。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="1a9c6-176">从 Docker Hub 官方.NET 映像存储库使用的版本号，可确保相同的语言功能是可用 （包括开发、 测试和生产） 的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="1a9c6-177">下面的示例显示了一个示例 Dockerfile ASP.NET Core 容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="1a9c6-178">在这种情况下，容器基于版本 2.0 的官方 ASP.NET 核心 Docker 映像 （适用于 Linux 和 Windows 多体系结构）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="1a9c6-179">这是设置`FROM microsoft/aspnetcore:2.0`。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="1a9c6-180">(有关此基本映像的详细信息，请参阅[ASP.NET Core Docker 映像](https://hub.docker.com/r/microsoft/aspnetcore/)页和[.NET Core Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)页。)Dockerfile，还需要指示 Docker 在你将在运行时 （在此情况下，端口 80，如使用公开设置配置） 使用的 TCP 端口上侦听。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="1a9c6-181">Dockerfile，具体取决于的语言和框架正在使用中，可以指定其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="1a9c6-182">例如，使用的入口点行\["dotnet"，"MySingleContainerWebApp.dll"\]告知 Docker 运行.NET 核心应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="1a9c6-183">如果你使用 SDK 和.NET 核心 CLI (dotnet CLI) 生成并运行.NET 应用程序，此设置会有所不同。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="1a9c6-184">底部行是入口点行和其他设置将无法为应用程序选择的语言和平台而异。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-185">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-185">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-186">**.NET 核心应用程序的构建 Docker 映像**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span></span>

-   <span data-ttu-id="1a9c6-187">**生成你自己的映像**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-187">**Build your own image**.</span></span> <span data-ttu-id="1a9c6-188">在正式的 Docker 文档。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="1a9c6-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="1a9c6-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="1a9c6-190">使用多 arch 映像存储库</span><span class="sxs-lookup"><span data-stu-id="1a9c6-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="1a9c6-191">单个存储库可以包含平台的不同版本，如 Linux 映像和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="1a9c6-192">此功能，如 Microsoft （基本映像创建者） 供应商创建的单个存储库以涵盖多个平台 （这是 Linux 和 Windows）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="1a9c6-193">例如， [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Docker Hub 注册表中的可用存储库通过使用相同的存储库名称提供了适用于 Linux 和 Windows Nano Server 的支持。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="1a9c6-194">如果指定的标记，面向的平台的显式诸如在以下情况：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="1a9c6-195">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="1a9c6-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="1a9c6-197">但是，并且这是新自后中旬 2017，如果你指定的相同的映像名称，即使使用相同的标记，新的多 arch 映像 （如支持多体系结构 aspnetcore 映像） 将使用的 Linux 或 Windows 的版本，具体取决于要部署的 Docker 主机操作系统如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="1a9c6-198">**microsoft / aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="1a9c6-199">这样，当你从 Windows 主机请求映像时，它将请求 Windows 变体，并且从 Linux 主机提取相同的映像名称将请求 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="1a9c6-200">选项 b： 创建您从零开始的基础映像</span><span class="sxs-lookup"><span data-stu-id="1a9c6-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="1a9c6-201">你可以从头开始创建你自己 Docker 的基本映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="1a9c6-202">这种情况下不建议的人员开始使用 Docker，但如果你想要设置自己的基本映像的特定位，则可以这样。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-203">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-203">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-204">**多 arch.NET Core 映像**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="1a9c6-205">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="1a9c6-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="1a9c6-206">**创建基本映像**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-206">**Create a base image**.</span></span> <span data-ttu-id="1a9c6-207">Docker 的正式文档。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="1a9c6-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="1a9c6-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="1a9c6-209">步骤 3。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-209">Step 3.</span></span> <span data-ttu-id="1a9c6-210">创建自定义的 Docker 映像和在它们中嵌入应用程序或服务</span><span class="sxs-lookup"><span data-stu-id="1a9c6-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="1a9c6-211">对于应用程序中每个服务，你需要创建相关的映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="1a9c6-212">如果你的应用程序有一个服务或 web 应用程序组成，只需单个映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="1a9c6-213">请注意，Docker 映像生成自动为你在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="1a9c6-214">以下步骤只需要编辑器/CLI 工作流和为清楚起见相关下会发生什么情况的说明。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="1a9c6-215">作为开发人员，需要开发和测试本地直到你推送已完成功能，或将更改为源代码管理系统 （例如，若要 GitHub)。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="1a9c6-216">这意味着你需要创建的 Docker 映像和部署到本地的 Docker 主机 （Windows 或 Linux VM） 的容器和运行、 测试和调试针对这些本地的容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="1a9c6-217">若要在本地环境中创建自定义映像，通过 Docker CLI 和 Dockerfile，可以使用 docker 生成命令，如图 5-5 中。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="1a9c6-218">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-218">**Figure 5-5**.</span></span> <span data-ttu-id="1a9c6-219">创建自定义的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="1a9c6-219">Creating a custom Docker image</span></span>

<span data-ttu-id="1a9c6-220">（可选） 而不是直接从项目文件夹运行 docker 生成，你可以首先生成具有所需的.NET 库的可部署文件夹并通过运行 dotnet 的二进制文件发布，然后使用 docker 生成命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="1a9c6-221">这将创建名称 cesardl/netcore webapi-微服务构成的 Docker 映像-docker： 第一个。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="1a9c6-222">在这种情况下，： 首先是表示特定版本的标记。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="1a9c6-223">你需要创建 Docker 应用程序由每个自定义映像，可以重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="1a9c6-224">当应用程序由多个容器 （即，它是一个多容器应用程序），你还可以使用 docker compose 向上-生成命令，以使用在相关的中公开的元数据生成使用单个命令的所有相关的映像docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="1a9c6-225">你可以找到现有的映像在本地存储库中使用 docker 映像命令，在图 5-6 中所示。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="1a9c6-226">**图 5-6。**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-226">**Figure 5-6.**</span></span> <span data-ttu-id="1a9c6-227">查看现有的映像使用 docker 映像命令</span><span class="sxs-lookup"><span data-stu-id="1a9c6-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="1a9c6-228">使用 Visual Studio 中创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="1a9c6-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="1a9c6-229">当你使用 Visual Studio 与 Docker 支持创建项目时，你未显式创建映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="1a9c6-230">相反，创建映像为你在按 F5 并运行 dockerized 应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="1a9c6-231">此步骤是自动在 Visual Studio 中，和你看不到这种情况，但很重要，你知道这一点后台。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="1a9c6-232">步骤 4。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-232">Step 4.</span></span> <span data-ttu-id="1a9c6-233">构建多容器 Docker 应用程序时在 docker-compose.yml 中定义你的服务</span><span class="sxs-lookup"><span data-stu-id="1a9c6-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="1a9c6-234">[Docker-compose.yml](https://docs.docker.com/compose/compose-file/)文件，您可以定义一组相关的服务，若要部署为一个由应用程序使用部署命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="1a9c6-235">若要使用 docker-compose.yml 文件，需要创建你 main 中的文件或根解决方案文件夹中，使用类似于下面的示例中的内容：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

<span data-ttu-id="1a9c6-236">请注意，此 docker-compose.yml 文件简化并已合并的版本。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="1a9c6-237">它包含每个容器 （如自定义映像的名称中），它始终适用，加上可能取决于部署环境，如连接字符串的配置信息的静态配置数据。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="1a9c6-238">在后面的部分，你将了解如何可以拆分成多个 docker-compose.yml 配置 docker 编写的文件和重写值根据环境和执行类型 （调试或发布）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="1a9c6-239">Docker-compose.yml 文件示例定义了五个服务： webmvc 服务 （web 应用程序）、 两个微服务 （catalog.api 和 ordering.api） 和一个数据源容器，sql.data，基于适用于 Linux 容器作为运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="1a9c6-240">每个服务部署为一个容器，因此 Docker 映像需要为每个。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="1a9c6-241">Docker-compose.yml 文件指定不仅正在使用哪些容器，但它们单独配置的方式。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="1a9c6-242">例如，webmvc 容器中的定义.yml 文件：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="1a9c6-243">使用预建电子商店 / web： 最新映像。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="1a9c6-244">但是，你也可以配置要作为的一部分生成的映像 docker 撰写基于生成的执行额外的配置： docker-compose 文件中的部分。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="1a9c6-245">初始化两个环境变量 （CatalogUrl 和 OrderingUrl）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="1a9c6-246">将转发公开的端口 80 上容器主机上的外部端口 80。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="1a9c6-247">链接到该目录并进行排序来与服务的 web 应用取决于\_上设置。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="1a9c6-248">这会导致服务等待，直到启动这些服务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="1a9c6-249">当我们涵盖如何实现微服务和多容器应用程序时，我们将重温后面的部分中的 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="1a9c6-250">使用在 Visual Studio 2017 docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="1a9c6-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="1a9c6-251">图 5-7 中所示 Docker 解决方案支持添加到在 Visual Studio 解决方案中，服务项目，Visual Studio 将 Dockerfile 添加到你的项目，并 docker-compose.yml 文件解决方案中添加服务部分 （项目）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="1a9c6-252">它是开始编写你的多个容器解决方案的简单办法。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="1a9c6-253">然后，你可以打开 docker-compose.yml 文件，并更新它们具有附加功能。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="1a9c6-254">**图 5-7**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-254">**Figure 5-7**.</span></span> <span data-ttu-id="1a9c6-255">通过右击 ASP.NET Core 项目在 Visual Studio 2017 中添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="1a9c6-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="1a9c6-256">在 Visual Studio 中添加 Docker 支持不仅能将 Dockerfile 添加到你的项目，还将配置信息添加到在解决方案级别设置的多个全局 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="1a9c6-257">将 Docker 支持添加到你在 Visual Studio 中的解决方案后，你还将看到包含添加的 docker-compose.yml 文件中，在图 5-8 中所示的解决方案资源管理器中的新节点 （在 docker compose.dcproj 项目文件中）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="1a9c6-258">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-258">**Figure 5-8**.</span></span> <span data-ttu-id="1a9c6-259">**Docker compose**添加在 Visual Studio 2017 解决方案资源管理器的树节点</span><span class="sxs-lookup"><span data-stu-id="1a9c6-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="1a9c6-260">可以使用单个 docker-compose.yml 文件中部署多容器应用程序通过 docker compose 命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="1a9c6-261">但是，Visual Studio 将一组添加它们以便您可以覆盖根据环境 （而不是生产开发） 和执行的值类型 （而不是调试版本）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="1a9c6-262">此功能将在后面的部分中所述。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="1a9c6-263">步骤 5。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-263">Step 5.</span></span> <span data-ttu-id="1a9c6-264">生成并运行你的 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="1a9c6-264">Build and run your Docker application</span></span>

<span data-ttu-id="1a9c6-265">如果你的应用程序中只有单个容器，你可以通过将其部署到你的 Docker 主机 （VM 或物理服务器） 来运行它。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="1a9c6-266">但是，如果你的应用程序包含多个服务，你可以将其部署为一个由应用程序，使用单个 CLI 命令 （docker-撰写向上），或使用 Visual Studio，它将使用事实上该命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="1a9c6-267">我们来看的不同选项。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="1a9c6-268">选项 a： 使用 Docker CLI 运行单容器</span><span class="sxs-lookup"><span data-stu-id="1a9c6-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="1a9c6-269">你可以运行使用 docker 运行命令，如图 5-9 中的 Docker 容器：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="1a9c6-270">**图 5-9**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-270">**Figure 5-9**.</span></span> <span data-ttu-id="1a9c6-271">运行使用 docker run 命令的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="1a9c6-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="1a9c6-272">在这种情况下，该命令将容器的内部端口 5000 绑定到主机的端口 80。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="1a9c6-273">这意味着在端口 80 上侦听并转发到端口 5000 上容器主机。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="1a9c6-274">选项 b： 运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="1a9c6-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="1a9c6-275">在大多数的企业方案中，Docker 应用程序将由构成的多个服务，这意味着你需要运行多容器应用程序，如图 5-10 中所示。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="1a9c6-276">**图 5-10**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-276">**Figure 5-10**.</span></span> <span data-ttu-id="1a9c6-277">与部署的 Docker 容器的 VM</span><span class="sxs-lookup"><span data-stu-id="1a9c6-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="1a9c6-278">使用 Docker CLI 运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="1a9c6-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="1a9c6-279">若要使用 Docker CLI 运行多容器应用程序，你可以运行 docker-撰写命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="1a9c6-280">在解决方案级别部署多容器应用程序具有此命令使用 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="1a9c6-281">图 5-11 从主项目目录，其中包含 docker-compose.yml 文件运行命令时显示的结果。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="1a9c6-282">**图 5-11**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-282">**Figure 5-11**.</span></span> <span data-ttu-id="1a9c6-283">运行时结果示例 docker compose 命令</span><span class="sxs-lookup"><span data-stu-id="1a9c6-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="1a9c6-284">后 docker-撰写向上命令运行，应用程序和其相关的容器部署到你的 Docker 主机，如图 5-10 中的 VM 表示中所示。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="1a9c6-285">运行和调试使用 Visual Studio 的多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="1a9c6-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="1a9c6-286">运行使用 Visual Studio 2017 的多容器应用程序无法获取更简单。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="1a9c6-287">您可以不仅运行多容器应用程序，但你能够通过设置正则断点调试其直接从 Visual Studio 的所有容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="1a9c6-288">如前所述，每次你 Docker 解决方案将支持添加到解决方案中的项目，该项目配置在全局 （解决方案级） docker-compose.yml 文件中，这样就可以运行或在一次调试整个解决方案中。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="1a9c6-289">Visual Studio 将启动一个容器的 Docker 解决方案启用了支持，每个项目，并为你执行内部的所有步骤 （dotnet 发布，docker 生成，等等。）。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="1a9c6-290">重要的一点是，如所示图 5-12 中，在 Visual Studio 2017 还有一个额外**Docker** F5 键操作的命令。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="1a9c6-291">此选项允许你运行或调试多容器应用程序正在运行的解决方法级别的 docker-compose.yml 文件中定义的所有容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="1a9c6-292">调试多个容器解决方案的能力意味着你可以在不同的项目 （容器），设置多个断点，每个断点，并从 Visual Studio 进行调试时你可以停止在断点在不同项目中定义和上运行不同的容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="1a9c6-293">**图 5-12**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-293">**Figure 5-12**.</span></span> <span data-ttu-id="1a9c6-294">在 Visual Studio 2017 中运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="1a9c6-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-295">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-295">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-296">**将 ASP.NET 容器部署到远程 Docker 主机**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="1a9c6-297">有关测试和使用 orchestrators 部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="1a9c6-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="1a9c6-298">向上 docker compose 和 docker 运行命令 （或运行调试 Visual Studio 中的容器），而对于在你的开发环境中测试容器。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="1a9c6-299">但如果你面向的 Docker 群集且 orchestrators 喜欢 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes，则不应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="1a9c6-300">如果你使用群集例如[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（适用于 Docker CE for Windows 和 Mac 自版本 1.12），你需要部署和测试与其他命令，如[docker 服务创建](https://docs.docker.com/engine/reference/commandline/service_create/)为单个服务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="1a9c6-301">如果你要部署的多个容器构成应用程序，则使用[docker compose 捆绑](https://docs.docker.com/compose/reference/bundle/)和[docker 部署 myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/)部署由应用程序作为*堆栈*.</span><span class="sxs-lookup"><span data-stu-id="1a9c6-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="1a9c6-302">有关详细信息，请参阅博客文章[简介实验的分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)Docker 文档中。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="1a9c6-303">上的 Docker 站点。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-303">on the Docker site.</span></span>

<span data-ttu-id="1a9c6-304">有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)和[Kubernetes](http://kubernetes.io/docs/user-guide/deployments/)你会使用不同的部署命令和脚本以及。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="1a9c6-305">步骤 6。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-305">Step 6.</span></span> <span data-ttu-id="1a9c6-306">测试 Docker 应用程序使用本地 Docker 主机</span><span class="sxs-lookup"><span data-stu-id="1a9c6-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="1a9c6-307">此步骤根据你的应用程序正在执行什么操作会有所不同。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="1a9c6-308">在部署为单个容器或服务的简单.NET 核心 Web 应用，你可以通过打开 Docker 主机上的浏览器并导航到该站点，在图 5-13 中所示来访问服务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="1a9c6-309">（如果 Dockerfile 中的配置将容器映射到是 80 之外的任何主机上的端口，包括主机后在 URL 中。）</span><span class="sxs-lookup"><span data-stu-id="1a9c6-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="1a9c6-310">**图 5-13**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-310">**Figure 5-13**.</span></span> <span data-ttu-id="1a9c6-311">测试本地使用 localhost Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="1a9c6-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="1a9c6-312">如果 localhost 不指向 Docker 主机 IP （默认情况下，当使用 Docker CE 时，它应），若要导航到你的服务时，使用计算机的网络卡的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="1a9c6-313">请注意此 URL 在浏览器中的，对于所讨论的特定容器示例使用端口 80。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="1a9c6-314">但是，内部请求会重定向到端口 5000，因为这是它的部署方式与 docker 运行命令上, 一步中所述。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="1a9c6-315">图 5-14 中所示，你还可以测试使用从终端，curl 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="1a9c6-316">在 Windows 上的 Docker 安装，默认 Docker 主机 IP 始终是 10.0.75.1 除了您的计算机的实际 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="1a9c6-317">**图 5-14**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-317">**Figure 5-14**.</span></span> <span data-ttu-id="1a9c6-318">测试本地使用 curl Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="1a9c6-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="1a9c6-319">测试和调试使用 Visual Studio 2017 容器</span><span class="sxs-lookup"><span data-stu-id="1a9c6-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="1a9c6-320">当运行和调试使用 Visual Studio 2017 容器，你可以在基本相同的方法中调试.NET 应用程序，就像没有容器的情况下运行时。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="1a9c6-321">测试和调试而无需 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1a9c6-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="1a9c6-322">如果你正在开发使用编辑器/CLI 方法，调试容器的难度，并且你将想要调试生成跟踪。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-323">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-323">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-324">**本地 Docker 容器中调试应用程序**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="1a9c6-325">**Steve Lasker。生成、 调试、 部署使用 Docker 的 ASP.NET Core 应用。**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="1a9c6-326">视频。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-326">Video.</span></span>
    [<span data-ttu-id="1a9c6-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="1a9c6-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="1a9c6-328">在开发使用 Visual Studio 的容器时的简化工作流</span><span class="sxs-lookup"><span data-stu-id="1a9c6-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="1a9c6-329">实际上，工作流时使用 Visual Studio 会比在使用的编辑器/CLI 方法大量更简单。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="1a9c6-330">与 Dockerfile 相关的大多数步骤所需的 Docker，隐藏或图 5-15 中所示，由 Visual Studio 中，简化 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="1a9c6-331">**图 5-15**。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-331">**Figure 5-15**.</span></span> <span data-ttu-id="1a9c6-332">简化工作流时使用 Visual Studio 进行开发</span><span class="sxs-lookup"><span data-stu-id="1a9c6-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="1a9c6-333">此外，你需要执行步骤 2 （向你的项目添加 Docker 支持） 只需一次。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="1a9c6-334">因此，工作流时使用的任何其他开发.NET 是类似于常用的开发任务。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="1a9c6-335">你需要知道发生了什么情况 （映像生成过程、 哪些正在使用的基础映像、 部署的容器，等等） 在后台，有时你还需要编辑 Dockerfile 或 docker-compose.yml 文件，可以自定义行为。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="1a9c6-336">但是，通过使用 Visual Studio 中，使大量提高工作效率极大地简化的大部分工作。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-337">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-337">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-338">**Steve Lasker。使用 Visual Studio 2017 的.NET docker 开发**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="1a9c6-339">**Jeffrey t。 Fritz。For Visual Studio.NET 核心应用程序放入新的 Docker 工具与容器**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="1a9c6-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="1a9c6-340">使用在 Dockerfile 中的 PowerShell 命令来设置 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="1a9c6-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="1a9c6-341">[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)允许你将现有的 Windows 应用程序转换为 Docker 映像并将其部署与 Docker 生态系统的其余部分所在的相同工具。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="1a9c6-342">若要使用 Windows 容器，你运行 PowerShell 命令在 Dockerfile，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="1a9c6-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="1a9c6-343">在这种情况下，我们已使用 Windows Server Core 基本映像 （FROM 设置），并使用 PowerShell 命令 （运行设置） 安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="1a9c6-344">以类似的方式，还可以使用 PowerShell 命令来设置其他组件，如 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="1a9c6-345">例如，Dockerfile 中的以下命令将设置 ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="1a9c6-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="1a9c6-346">其他资源</span><span class="sxs-lookup"><span data-stu-id="1a9c6-346">Additional resources</span></span>

-   <span data-ttu-id="1a9c6-347">**aspnet-docker/Dockerfile。**</span><span class="sxs-lookup"><span data-stu-id="1a9c6-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="1a9c6-348">示例 Powershell 命令，以从 dockerfile 以包括 Windows 功能运行。</span><span class="sxs-lookup"><span data-stu-id="1a9c6-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="1a9c6-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="1a9c6-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="1a9c6-350">[以前](index.md) [下一步] (.../ net-core-single-containers-linux-windows-server-hosts/index.md）</span><span class="sxs-lookup"><span data-stu-id="1a9c6-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
