---
title: Docker 应用开发工作流
description: 用于容器化 .NET 应用程序的 .NET 微服务体系结构 | Docker 应用开发工作流
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 2eb205e85300f22108b866e8446d6730d89ae6cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579673"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="17adf-103">Docker 应用开发工作流</span><span class="sxs-lookup"><span data-stu-id="17adf-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="17adf-104">应用程序开发生命周期从每位开发人员的计算机上开始，开发人员在计算机上使用其首选语言对应用程序进行编码和本地测试。</span><span class="sxs-lookup"><span data-stu-id="17adf-104">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="17adf-105">无论选择哪种语言、框架和平台，采用本工作流后，开发人员始终要开发和测试 Docker 容器，但在本地进行操作即可。</span><span class="sxs-lookup"><span data-stu-id="17adf-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="17adf-106">每个容器（Docker 映像的实例）都包含以下组成部分：</span><span class="sxs-lookup"><span data-stu-id="17adf-106">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="17adf-107">选择的操作系统（例如，Linux 发行版、Windows Nano Server 或 Windows Server Core）。</span><span class="sxs-lookup"><span data-stu-id="17adf-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="17adf-108">开发人员添加的文件（应用程序二进制文件等）。</span><span class="sxs-lookup"><span data-stu-id="17adf-108">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="17adf-109">配置信息（环境设置和依赖项）。</span><span class="sxs-lookup"><span data-stu-id="17adf-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="17adf-110">开发基于 Docker 容器的应用程序的工作流</span><span class="sxs-lookup"><span data-stu-id="17adf-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="17adf-111">本节介绍基于 Docker 容器的应用程序的内部循环开发工作流。</span><span class="sxs-lookup"><span data-stu-id="17adf-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="17adf-112">内部循环工作流是指不考虑更广泛的 DevOps 工作流，只关注在开发人员的计算机上进行的开发工作。</span><span class="sxs-lookup"><span data-stu-id="17adf-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="17adf-113">其中不包括设置环境的初始步骤，因为这些步骤只需进行一次。</span><span class="sxs-lookup"><span data-stu-id="17adf-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="17adf-114">应用程序由开发人员自己的服务和附加库（依赖项）组成。</span><span class="sxs-lookup"><span data-stu-id="17adf-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="17adf-115">以下是生成 Docker 应用程序时常用的基本步骤，如图 5-1 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="17adf-116">**图 5-1**。</span><span class="sxs-lookup"><span data-stu-id="17adf-116">**Figure 5-1.**</span></span> <span data-ttu-id="17adf-117">开发 Docker 容器化应用的分步工作流</span><span class="sxs-lookup"><span data-stu-id="17adf-117">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="17adf-118">本指南详细介绍了整个流程，并着重通过 Visual Studio 环境解释了每个主要步骤。</span><span class="sxs-lookup"><span data-stu-id="17adf-118">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="17adf-119">使用编辑器/CLI 开发方法（例如，Visual Studio Code 和 macOS 或 Windows 上的 Docker CLI）时，需了解每个步骤，通常需要比使用 Visual Studio 了解得更详细。</span><span class="sxs-lookup"><span data-stu-id="17adf-119">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="17adf-120">有关在 CLI 环境中进行开发的详细信息，请参阅电子书 [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/)（容器化 Docker 应用程序生命周期与 Microsoft 平台和工具）。</span><span class="sxs-lookup"><span data-stu-id="17adf-120">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="17adf-121">使用 Visual Studio 2015 或 Visual Studio 2017 时，许多步骤都无需开发者执行，可显著提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="17adf-121">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="17adf-122">使用 Visual Studio 2017 开发多容器应用程序时更是如此。</span><span class="sxs-lookup"><span data-stu-id="17adf-122">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="17adf-123">例如，只需单击一下，Visual Studio 就会将 Dockerfile 和 docker-compose.yml 文件添加到含有应用程序配置的项目。</span><span class="sxs-lookup"><span data-stu-id="17adf-123">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="17adf-124">在 Visual Studio 中运行应用程序时，系统会生成 Docker 映像并在 Docker 中直接运行多容器应用程序；开发人员甚至还能同时调试多个容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-124">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="17adf-125">这些功能可大大提高开发速度。</span><span class="sxs-lookup"><span data-stu-id="17adf-125">These features will boost your development speed.</span></span>

<span data-ttu-id="17adf-126">但即使 Visual Studio 可以自动执行这些步骤，这也并不意味着开发人员不需要了解 Docker 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="17adf-126">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="17adf-127">因此，接下来的内容会详细介绍每个步骤。</span><span class="sxs-lookup"><span data-stu-id="17adf-127">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="17adf-128">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="17adf-128">Step 1.</span></span> <span data-ttu-id="17adf-129">开始编码并创建初始应用程序或服务基线</span><span class="sxs-lookup"><span data-stu-id="17adf-129">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="17adf-130">开发 Docker 应用程序的方式与开发不带 Docker 的应用程序的方式类似。</span><span class="sxs-lookup"><span data-stu-id="17adf-130">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="17adf-131">二者的区别在于，开发 Docker 应用程序时，是在本地环境中部署和测试在 Docker 容器中运行的应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="17adf-131">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="17adf-132">该容器可以是 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-132">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="17adf-133">使用 Visual Studio 设置本地环境</span><span class="sxs-lookup"><span data-stu-id="17adf-133">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="17adf-134">首先，请务必按以下说明所述安装适用于 Windows 的 [Docker 社区版 (CE)](https://www.docker.com/community-edition)：</span><span class="sxs-lookup"><span data-stu-id="17adf-134">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

<span data-ttu-id="17adf-135">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)（适用于 Windows 的 Docker CE 入门）</span><span class="sxs-lookup"><span data-stu-id="17adf-135">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)</span></span>

<span data-ttu-id="17adf-136">此外还需安装 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="17adf-136">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="17adf-137">Visual Studio 2015 含有 Visual Studio Tools for Docker 加载项，但推荐安装 Visual Studio 2017，因为它为 Docker 提供了更高级的支持，例如容器调试支持。</span><span class="sxs-lookup"><span data-stu-id="17adf-137">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="17adf-138">如果在安装时选择了“ .NET Core 和 Docker”工作负载，Visual Studio 2017 会包含 Docker 工具，如图 5-2 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-138">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="17adf-139">**图 5-2**。</span><span class="sxs-lookup"><span data-stu-id="17adf-139">**Figure 5-2**.</span></span> <span data-ttu-id="17adf-140">安装 Visual Studio 2017 时选择“.NET Core 和 Docker”工作负载</span><span class="sxs-lookup"><span data-stu-id="17adf-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="17adf-141">即使尚未在应用程序中启用 Docker，开发人员也可以开始在普通 .NET 中编写应用程序（如果打算使用容器，则通常在 .NET Core 中进行），并在 Docker 中进行部署和测试。</span><span class="sxs-lookup"><span data-stu-id="17adf-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="17adf-142">但建议尽快开始使用 Docker，因为这才是真实环境，并且能快速发现存在的问题。</span><span class="sxs-lookup"><span data-stu-id="17adf-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="17adf-143">推荐这样做是因为通过 Visual Studio 可轻松使用 Docker，开发人员能够快速明白，在 Visual Studio 中能调试多容器应用程序就是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="17adf-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-144">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-144">Additional resources</span></span>

-   <span data-ttu-id="17adf-145">**Get started with Docker CE for Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)（适用于 Windows 的 Docker CE 入门）</span><span class="sxs-lookup"><span data-stu-id="17adf-145">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="17adf-146">**Visual Studio 2017**
    [*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="17adf-146">**Visual Studio 2017**
[*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="17adf-147">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="17adf-147">Step 2.</span></span> <span data-ttu-id="17adf-148">创建与现有 .NET 基础映像相关的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="17adf-148">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="17adf-149">要生成自定义映像，需为每个自定义映像提供一个 Dockerfile；无论是从 Visual Studio 自动部署，还是使用 Docker CLI（docker run 和 docker-compose 命令）手动部署，也需为每个要部署的容器提供一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-149">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="17adf-150">如果应用程序只包含一个自定义服务，则只需要一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-150">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="17adf-151">如果应用程序包含多个服务（如在微服务体系结构中），则每个服务都需要一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-151">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="17adf-152">将 Dockerfile 放在应用程序或服务的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="17adf-152">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="17adf-153">Dockerfile 包含多个命令，可指示 Docker 如何在容器中设置和运行应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="17adf-153">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="17adf-154">开发人员可在代码中手动创建 Dockerfile，并将其与 .NET 依赖项一起添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="17adf-154">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="17adf-155">借助 Visual Studio 及其 Docker 工具，只需单击几次鼠标即可完成此任务。</span><span class="sxs-lookup"><span data-stu-id="17adf-155">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="17adf-156">在 Visual Studio 2017 中新建项目时，会有一个名为“启用容器 (Docker) 支持”的选项，如图 5-3 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-156">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="17adf-157">**图 5-3**。</span><span class="sxs-lookup"><span data-stu-id="17adf-157">**Figure 5-3**.</span></span> <span data-ttu-id="17adf-158">在 Visual Studio 2017 中新建项目时的“启用 Docker 支持”</span><span class="sxs-lookup"><span data-stu-id="17adf-158">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="17adf-159">还可通过在 Visual Studio 中右键单击项目文件，选择“添加 Docker 项目支持”选项，为新项目或现有项目启用 Docker 支持，如图 5-4 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-159">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="17adf-160">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="17adf-160">**Figure 5-4**.</span></span> <span data-ttu-id="17adf-161">在现有 Visual Studio 2017 项目中启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="17adf-161">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="17adf-162">对项目（如 ASP.NET Web 应用程序或 Web API 服务）应用此操作后，系统会向含有所需配置的项目添加 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-162">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="17adf-163">同时还会向整个解决方案添加 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="17adf-163">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="17adf-164">接下来将介绍每个文件中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="17adf-164">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="17adf-165">Visual Studio 可代为执行此操作，但了解 Dockerfile 中的内容也十分有用。</span><span class="sxs-lookup"><span data-stu-id="17adf-165">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="17adf-166">选项 A：使用现有的官方 .NET Docker 映像创建项目</span><span class="sxs-lookup"><span data-stu-id="17adf-166">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="17adf-167">开发人员通常以基础映像（可从 [Docker 中心](https://hub.docker.com/)注册表的官方存储库中获取）为基础生成自定义映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-167">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="17adf-168">确切地说，在 Visual Studio 中启用 Docker 支持后就可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="17adf-168">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="17adf-169">Dockerfile 将使用现有的 aspnetcore 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-169">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="17adf-170">之前我们介绍了根据开发人员选择的框架和操作系统可使用的 Docker 映像和存储库。</span><span class="sxs-lookup"><span data-stu-id="17adf-170">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="17adf-171">例如，如果想使用 ASP.NET Core（Linux 或 Windows），则使用的映像是 microsoft/aspnetcore:2.0。</span><span class="sxs-lookup"><span data-stu-id="17adf-171">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="17adf-172">因此，只需指定用于容器的基础 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="17adf-172">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="17adf-173">方法是将 FROM microsoft/aspnetcore:2.0 添加到 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-173">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="17adf-174">Visual Studio 会自动执行此操作，但若要更新版本，则需更新此值。</span><span class="sxs-lookup"><span data-stu-id="17adf-174">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="17adf-175">使用从 Docker 中心获取的带版本号的官方 .NET 映像存储库可确保能在所有计算机（包括用于开发、测试和生产的计算机）上使用相同的语言功能。</span><span class="sxs-lookup"><span data-stu-id="17adf-175">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="17adf-176">以下示例显示了 ASP.NET Core 容器的示例 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="17adf-176">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="17adf-177">此时该容器以 2.0 版官方 ASP.NET Core Docker 映像为基础（适用于 Linux 和 Windows 的多体系结构）。</span><span class="sxs-lookup"><span data-stu-id="17adf-177">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="17adf-178">这是 `FROM microsoft/aspnetcore:2.0` 设置。</span><span class="sxs-lookup"><span data-stu-id="17adf-178">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="17adf-179">（有关此基础映像的详细信息，请参阅 [ASP.NET Core Docker 映像](https://hub.docker.com/r/microsoft/aspnetcore/)页和 [.NET Core Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)页。）在 Dockerfile 中，还需指示 Docker 侦听要在运行时使用的 TCP 端口（示例中由 EXPOSE 设置配置的 TPC 端口为 80）。</span><span class="sxs-lookup"><span data-stu-id="17adf-179">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="17adf-180">可在 Dockerfile 中指定其他配置设置，具体取决于使用的语言和框架。</span><span class="sxs-lookup"><span data-stu-id="17adf-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="17adf-181">例如，带有 \["dotnet", "MySingleContainerWebApp.dll"\] 的 ENTRYPOINT 行可指示 Docker 运行 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-181">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="17adf-182">如果使用 SDK 和 .NET Core CLI (dotnet CLI) 来生成和运行 .NET 应用程序，则此设置会有所不同。</span><span class="sxs-lookup"><span data-stu-id="17adf-182">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="17adf-183">底部的 ENTRYPOINT 行和其他设置会有所不同，具体取决于为应用程序选择的语言和平台。</span><span class="sxs-lookup"><span data-stu-id="17adf-183">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-184">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-184">Additional resources</span></span>

-   <span data-ttu-id="17adf-185">**为 .NET Core 应用程序生成 Docker 映像**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="17adf-185">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span></span>

-   <span data-ttu-id="17adf-186">**生成开发人员自己的映像**。</span><span class="sxs-lookup"><span data-stu-id="17adf-186">**Build your own image**.</span></span> <span data-ttu-id="17adf-187">请查看官方 Docker 文档。</span><span class="sxs-lookup"><span data-stu-id="17adf-187">In the official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="17adf-188">使用多体系结构映像存储库</span><span class="sxs-lookup"><span data-stu-id="17adf-188">Using multi-arch image repositories</span></span>

<span data-ttu-id="17adf-189">单个存储库中可包含平台变量，如 Linux 映像和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-189">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="17adf-190">借助此功能，Microsoft （基础映像创建者）等供应商可创建涵盖多个平台（即 Linux 和 Windows）的单个存储库。</span><span class="sxs-lookup"><span data-stu-id="17adf-190">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="17adf-191">例如，Docker 中心注册表中提供的 [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) 存储库可使用相同的存储库名称为 Linux 和 Windows Nano Server 提供支持。</span><span class="sxs-lookup"><span data-stu-id="17adf-191">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="17adf-192">如果指定了标签，请明确指定一个平台，如下所示：</span><span class="sxs-lookup"><span data-stu-id="17adf-192">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="17adf-193">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="17adf-193">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="17adf-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="17adf-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="17adf-195">但自 2017 年中旬以来，此情况出现了变化，如果指定相同的映像名称，即使使用的标记相同，新的多体系结构映像（如支持多体系结构的 aspnetcore 映像）也将使用 Linux 或 Windows 版本，具体取决于正在部署的 Docker 主机操作系统，如下所示：</span><span class="sxs-lookup"><span data-stu-id="17adf-195">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="17adf-196">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="17adf-196">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="17adf-197">这样一来，从 Windows 主机拉取映像时，也会拉取 Windows 变体，并且从 Linux 主机拉取同一映像名称时，也会拉取 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="17adf-197">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="17adf-198">选项 B：从头开始创建基础映像</span><span class="sxs-lookup"><span data-stu-id="17adf-198">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="17adf-199">开发人员可以从头开始创建自己的 Docker 基础映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-199">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="17adf-200">不推荐刚开始使用 Docker 的开发人员使用此方案，但如果想为自己的基础映像设置特定位，则可采用此方案。</span><span class="sxs-lookup"><span data-stu-id="17adf-200">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-201">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-201">Additional resources</span></span>

-   <span data-ttu-id="17adf-202">**Multi-arch .NET Core images**（多体系结构 .NET Core 映像）。</span><span class="sxs-lookup"><span data-stu-id="17adf-202">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="17adf-203">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="17adf-203">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="17adf-204">**创建基础映像**。</span><span class="sxs-lookup"><span data-stu-id="17adf-204">**Create a base image**.</span></span> <span data-ttu-id="17adf-205">请查看官方 Docker 文档。</span><span class="sxs-lookup"><span data-stu-id="17adf-205">Official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="17adf-206">步骤 3。</span><span class="sxs-lookup"><span data-stu-id="17adf-206">Step 3.</span></span> <span data-ttu-id="17adf-207">创建自定义 Docker 映像并将应用程序或服务嵌入其中</span><span class="sxs-lookup"><span data-stu-id="17adf-207">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="17adf-208">需为应用程序中的每项服务创建一个相关映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-208">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="17adf-209">如果应用程序由单个服务或 Web 应用程序组成，则只需创建一个映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-209">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="17adf-210">请注意，Visual Studio 中会自动生成 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-210">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="17adf-211">以下步骤仅适用于编辑器/CLI 工作流，下文清楚解释了各步骤的工作原理。</span><span class="sxs-lookup"><span data-stu-id="17adf-211">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="17adf-212">开发人员发布完整功能或更改源代码管理系统（例如 GitHub）之前，需在本地进行开发和测试。</span><span class="sxs-lookup"><span data-stu-id="17adf-212">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="17adf-213">这意味着开发人员需要创建 Docker 映像并向本地 Docker 主机（Windows 或 Linux VM）部署容器，并运行、测试和调试这些本地容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-213">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="17adf-214">若要使用 Docker CLI 和 Dockerfile 在本地环境中创建自定义映像，可使用 docker build 命令，如图 5-5 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-214">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="17adf-215">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="17adf-215">**Figure 5-5**.</span></span> <span data-ttu-id="17adf-216">创建自定义 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="17adf-216">Creating a custom Docker image</span></span>

<span data-ttu-id="17adf-217">（可选），可先运行 dotnet 发布生成包含所需 .NET 库和二进制文件的可部署文件夹，然后使用 docker build 命令，而不直接从项目文件夹运行 docker 生成。</span><span class="sxs-lookup"><span data-stu-id="17adf-217">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="17adf-218">此操作会创建一个名为 cesardl/netcore-webapi-microservice-docker:first 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-218">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="17adf-219">此处的 :first 是表示特定版本的标记。</span><span class="sxs-lookup"><span data-stu-id="17adf-219">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="17adf-220">为组合 Docker 应用程序创建自定义映像时，可为每个映像重复执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="17adf-220">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="17adf-221">应用程序由多个容器组成时（即多容器应用程序），还可使用 docker-compose up --build 命令，借助相关 docker-compose.yml 文件中公开的元数据，只需一个命令即可生成所有相关映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-221">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="17adf-222">使用 docker images 命令可查找本地存储库中的现有映像，如图 5-6 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-222">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="17adf-223">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="17adf-223">**Figure 5-6.**</span></span> <span data-ttu-id="17adf-224">使用 docker images 命令查看现有映像</span><span class="sxs-lookup"><span data-stu-id="17adf-224">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="17adf-225">使用 Visual Studio 创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="17adf-225">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="17adf-226">使用 Visual Studio 创建带 Docker 支持的项目时，不会显式创建映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-226">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="17adf-227">开发人员按下 F5 并运行已 Docker 化的应用程序或服务时，Visual Studio 就会创建映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-227">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="17adf-228">Visual Studio 会自动执行此操作，不会出现明显的过程，但开发人员需要了解其原理。</span><span class="sxs-lookup"><span data-stu-id="17adf-228">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="17adf-229">步骤 4。</span><span class="sxs-lookup"><span data-stu-id="17adf-229">Step 4.</span></span> <span data-ttu-id="17adf-230">生成多容器 Docker 应用程序时，在 docker-compose.yml 中定义服务</span><span class="sxs-lookup"><span data-stu-id="17adf-230">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="17adf-231">借助 [docker-compose.yml](https://docs.docker.com/compose/compose-file/) 文件，开发人员可定义一组相关服务，通过部署命令将其部署为组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-231">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="17adf-232">若要使用 docker-compose.yml 文件，则需在主解决方案文件夹或根解决方案文件夹中创建该文件，其内容与以下示例中的内容类似：</span><span class="sxs-lookup"><span data-stu-id="17adf-232">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="17adf-233">请注意，这是一个简化合并版的 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="17adf-233">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="17adf-234">其中包含始终适用的每个容器的静态配置数据（如自定义映像的名称），以及视部署环境而定的配置信息（如连接字符串）。</span><span class="sxs-lookup"><span data-stu-id="17adf-234">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="17adf-235">后面的章节将介绍如何将 docker-compose.yml 配置拆分为多个 docker-compose 文件，并根据环境和执行类型（调试或发布）覆盖值。</span><span class="sxs-lookup"><span data-stu-id="17adf-235">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="17adf-236">docker-compose.yml 示例文件中定义了五项服务：webmvc 服务（一个 Web 应用程序）、两个微服务（catalog.api 和 ordering.api）、一个数据源容器以及一个作为容器运行的基于 SQL Server for Linux 的 sql.data。</span><span class="sxs-lookup"><span data-stu-id="17adf-236">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="17adf-237">每项服务都部署为一个容器，因此每项服务都需要一个 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-237">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="17adf-238">docker-compose.yml 文件不仅指定正在使用的容器，还指定如何单独配置各容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-238">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="17adf-239">例如，.yml 文件中的 webmvc 容器定义：</span><span class="sxs-lookup"><span data-stu-id="17adf-239">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="17adf-240">使用预生成的 eshop/web:latest 映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-240">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="17adf-241">但也可以借助基于 docker-compose 文件中 build: 部分的其他配置，在执行 docker-compose 的过程中配置要生成的映像。</span><span class="sxs-lookup"><span data-stu-id="17adf-241">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="17adf-242">初始化两个环境变量（CatalogUrl 和 OrderingUrl）。</span><span class="sxs-lookup"><span data-stu-id="17adf-242">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="17adf-243">将容器上的公开端口 80 转接到主机上的外部端口 80。</span><span class="sxs-lookup"><span data-stu-id="17adf-243">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="17adf-244">通过 depends\_on 设置将 Web 应用链接到目录和排序服务。</span><span class="sxs-lookup"><span data-stu-id="17adf-244">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="17adf-245">此操作会让该服务处于等待状态，直到启用这些服务。</span><span class="sxs-lookup"><span data-stu-id="17adf-245">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="17adf-246">稍后介绍如何实现微服务和多容器应用时，我们会再次回顾 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="17adf-246">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="17adf-247">在 Visual Studio 2017 中使用 docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="17adf-247">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="17adf-248">如图 5-7 所示，向 Visual Studio 解决方案中的服务项目添加对 Docker 解决方案的支持时，Visual Studio 会向项目添加 Dockerfile，且会通过 docker-compose.yml 文件在解决方案中添加一个服务部分（项目）。</span><span class="sxs-lookup"><span data-stu-id="17adf-248">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="17adf-249">通过这种方式可以轻松开始编写多容器解决方案。</span><span class="sxs-lookup"><span data-stu-id="17adf-249">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="17adf-250">随后可打开 docker-compose.yml 文件并对其进行更新，增加新的功能。</span><span class="sxs-lookup"><span data-stu-id="17adf-250">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="17adf-251">**图 5-7**。</span><span class="sxs-lookup"><span data-stu-id="17adf-251">**Figure 5-7**.</span></span> <span data-ttu-id="17adf-252">右键单击 ASP.NET Core 项目，在 Visual Studio 2017 中添加对 Docker 的支持</span><span class="sxs-lookup"><span data-stu-id="17adf-252">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="17adf-253">在 Visual Studio 中添加对 Docker 的支持时，不仅会向项目添加 Dockerfile，还会向在解决方案级设置的多个全局 docker-compose.yml 文件添加配置信息。</span><span class="sxs-lookup"><span data-stu-id="17adf-253">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="17adf-254">在 Visual Studio 中添加对 Docker 的支持后，解决方案资源管理器中会出现一个新节点（位于 docker-compose.dcproj 项目文件中），其中包含添加的 docker-compose.yml 文件，如图 5-8 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-254">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="17adf-255">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="17adf-255">**Figure 5-8**.</span></span> <span data-ttu-id="17adf-256">在 Visual Studio 2017 解决方案资源管理器中添加的 docker-compose 树节点</span><span class="sxs-lookup"><span data-stu-id="17adf-256">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="17adf-257">可使用 docker-compose up 命令，通过单个 docker-compose.yml 文件部署多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-257">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="17adf-258">但 Visual Studio 按组添加，因此开发人员可根据环境（开发与生产）和执行类型（发布与调试）来覆盖值。</span><span class="sxs-lookup"><span data-stu-id="17adf-258">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="17adf-259">稍后将介绍此功能。</span><span class="sxs-lookup"><span data-stu-id="17adf-259">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="17adf-260">步骤 5。</span><span class="sxs-lookup"><span data-stu-id="17adf-260">Step 5.</span></span> <span data-ttu-id="17adf-261">生成并运行 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="17adf-261">Build and run your Docker application</span></span>

<span data-ttu-id="17adf-262">如果应用程序只有一个容器，则可通过将其部署到 Docker 主机（虚拟机或物理服务器）来运行该程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-262">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="17adf-263">但如果应用程序包含多项服务，则可使用单个 CLI 命令 (docker-compose up) 或使用 Visual Studio（会在其中使用该命令）将其部署为组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-263">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="17adf-264">接下来介绍这两种不同的选项。</span><span class="sxs-lookup"><span data-stu-id="17adf-264">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="17adf-265">选项 A：使用 Docker CLI 运行单容器</span><span class="sxs-lookup"><span data-stu-id="17adf-265">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="17adf-266">可使用 docker run 命令运行 Docker 容器，如图 5-9 所示：</span><span class="sxs-lookup"><span data-stu-id="17adf-266">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="17adf-267">**图 5-9**。</span><span class="sxs-lookup"><span data-stu-id="17adf-267">**Figure 5-9**.</span></span> <span data-ttu-id="17adf-268">使用 docker run 命令运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="17adf-268">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="17adf-269">此时，该命令将容器的内部端口 5000 绑定到主机的端口 80。</span><span class="sxs-lookup"><span data-stu-id="17adf-269">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="17adf-270">这意味着主机在侦听端口 80，并将其转接到容器上的端口 5000。</span><span class="sxs-lookup"><span data-stu-id="17adf-270">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="17adf-271">选项 B：运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="17adf-271">Option B: Running a multi-container application</span></span>

<span data-ttu-id="17adf-272">在大多数企业方案中，Docker 应用程序由多项服务组成，这意味着需要运行多容器应用程序，如图 5-10 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-272">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="17adf-273">**图 5-10**。</span><span class="sxs-lookup"><span data-stu-id="17adf-273">**Figure 5-10**.</span></span> <span data-ttu-id="17adf-274">部署了 Docker 容器的 VM</span><span class="sxs-lookup"><span data-stu-id="17adf-274">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="17adf-275">使用 Docker CLI 运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="17adf-275">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="17adf-276">若要使用 Docker CLI 运行多容器应用程序，可运行 docker-compose up 命令。</span><span class="sxs-lookup"><span data-stu-id="17adf-276">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="17adf-277">此命令使用解决方案级别的 docker-compose.yml 文件来部署多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-277">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="17adf-278">图 5-11 显示了从主项目目录（包含 docker-compose.yml 文件）运行命令的结果。</span><span class="sxs-lookup"><span data-stu-id="17adf-278">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="17adf-279">**图 5-11**。</span><span class="sxs-lookup"><span data-stu-id="17adf-279">**Figure 5-11**.</span></span> <span data-ttu-id="17adf-280">运行 docker-compose up 命令时的示例结果</span><span class="sxs-lookup"><span data-stu-id="17adf-280">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="17adf-281">运行 docker-compose up 命令后，应用程序及其相关容器将部署到 Docker 主机中，如图 5-10 中的 VM 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-281">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="17adf-282">使用 Visual Studio 运行和调试多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="17adf-282">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="17adf-283">使用 Visual Studio 2017 运行多容器应用程序十分简单。</span><span class="sxs-lookup"><span data-stu-id="17adf-283">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="17adf-284">使用 Visual Studio 不仅可以运行多容器应用程序，还可通过设置常规断点直接在 Visual Studio 中调试程序的所有容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-284">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="17adf-285">如前所述，每次向解决方案中的项目添加对 Docker 的支持时，都会在全局（解决方案级别）docker-compose.yml 文件中配置该项目，因此开发人员可以同时运行或调试整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="17adf-285">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="17adf-286">Visual Studio 将为每个启用了 Docker 解决方案支持的项目启动一个容器，并代为执行所有内部步骤（发布 dotnet、生成 Docker 等）。</span><span class="sxs-lookup"><span data-stu-id="17adf-286">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="17adf-287">此处的重点是，在 Visual Studio 2017 中，按下 F5 键可执行另一项 Docker 命令，如图 5-12 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-287">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="17adf-288">此选项允许开发人员在解决方案级别运行 docker-compose.yml 文件中定义的所有容器，从而运行或调试多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="17adf-288">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="17adf-289">可调试多容器解决方案就意味着，开发人员可设置多个断点，每个端点都位于不同的项目（容器）中，这样从 Visual Studio 进行调试时，会在不同项目中定义的断点处停止，并在不同容器上运行。</span><span class="sxs-lookup"><span data-stu-id="17adf-289">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="17adf-290">**图 5-12**。</span><span class="sxs-lookup"><span data-stu-id="17adf-290">**Figure 5-12**.</span></span> <span data-ttu-id="17adf-291">在 Visual Studio 2017 中运行多容器应用</span><span class="sxs-lookup"><span data-stu-id="17adf-291">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-292">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-292">Additional resources</span></span>

-   <span data-ttu-id="17adf-293">**将 ASP.NET 容器部署到远程 Docker 主机**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="17adf-293">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="17adf-294">有关使用业务流程协调程序进行测试和部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="17adf-294">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="17adf-295">使用 docker-compose up 和 docker run 命令（或在 Visual Studio 中运行和调试容器）足以在开发环境中测试容器。</span><span class="sxs-lookup"><span data-stu-id="17adf-295">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="17adf-296">但如果对象是 Docker 群集和业务流程协调程序（如 Docker Swarm、Mesosphere DC/OS 或 Kubernetes），则不应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="17adf-296">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="17adf-297">如果使用 [Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（自 1.12 版起可用于 Windows 和 Mac 适用的 Docker CE）等集群，则需使用 [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) 等附加命令部署和测试单个服务。</span><span class="sxs-lookup"><span data-stu-id="17adf-297">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="17adf-298">如果要部署由多个容器组成的应用程序，请使用 [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) 和 [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) 将组合应用程序部署为堆栈。</span><span class="sxs-lookup"><span data-stu-id="17adf-298">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="17adf-299">有关详细信息，请参阅 Docker 文档中的博客文章 [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/)（实验得出的分布式应用程序捆绑报简介）。</span><span class="sxs-lookup"><span data-stu-id="17adf-299">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="17adf-300">请访问 Docker 站点。</span><span class="sxs-lookup"><span data-stu-id="17adf-300">on the Docker site.</span></span>

<span data-ttu-id="17adf-301">对于 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 和 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/)，也可使用不同的部署命令和脚本。</span><span class="sxs-lookup"><span data-stu-id="17adf-301">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="17adf-302">步骤 6。</span><span class="sxs-lookup"><span data-stu-id="17adf-302">Step 6.</span></span> <span data-ttu-id="17adf-303">使用本地 Docker 主机测试 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="17adf-303">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="17adf-304">这一步骤会因应用程序的用途而有所不同。</span><span class="sxs-lookup"><span data-stu-id="17adf-304">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="17adf-305">对于部署为单个容器或服务的简单 .NET Core Web 应用程序而言，在 Docker 主机上打开浏览器并导航到该站点即可访问该服务，如图 5-13 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-305">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="17adf-306">（如果 Dockerfile 中的配置将容器映射到除主机上的 80 端口以外的任何端口，请在 URL 中包含该主机端口。）</span><span class="sxs-lookup"><span data-stu-id="17adf-306">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="17adf-307">**图 5-13**。</span><span class="sxs-lookup"><span data-stu-id="17adf-307">**Figure 5-13**.</span></span> <span data-ttu-id="17adf-308">使用 localhost 在本地测试 Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="17adf-308">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="17adf-309">如果 localhost 未指向 Docker 主机 IP（默认情况下，使用 Docker CE 时应指向主机 IP），若要导航到服务，请使用计算机网卡的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="17adf-309">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="17adf-310">请注意，在此处讨论的特定容器示例中，浏览器中的此 URL 使用的是端口 80。</span><span class="sxs-lookup"><span data-stu-id="17adf-310">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="17adf-311">但该请求会在内部被重定向到端口 5000，因为 docker run 命令之前进行了此部署，如上一步中所述。</span><span class="sxs-lookup"><span data-stu-id="17adf-311">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="17adf-312">还可从终端使用 curl 测试应用程序，如图 5-14 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-312">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="17adf-313">对于 Windows 上安装的 Docker，除计算机的实际 IP 地址以外，默认的 Docker 主机 IP 始终为 10.0.75.1。</span><span class="sxs-lookup"><span data-stu-id="17adf-313">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="17adf-314">**图 5-14**。</span><span class="sxs-lookup"><span data-stu-id="17adf-314">**Figure 5-14**.</span></span> <span data-ttu-id="17adf-315">使用 curl 在本地测试 Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="17adf-315">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="17adf-316">使用 Visual Studio 2017 测试和调试容器</span><span class="sxs-lookup"><span data-stu-id="17adf-316">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="17adf-317">使用 Visual Studio 2017 运行和调试容器时，调试 .NET 应用程序的方式与运行不带容器的应用程序的方式类似。</span><span class="sxs-lookup"><span data-stu-id="17adf-317">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="17adf-318">不使用 Visual Studio 进行测试和调试</span><span class="sxs-lookup"><span data-stu-id="17adf-318">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="17adf-319">如果使用编辑器/CLI 方法开发应用，调试容器会更加困难，需通过生成跟踪来进行调试。</span><span class="sxs-lookup"><span data-stu-id="17adf-319">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-320">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-320">Additional resources</span></span>

-   <span data-ttu-id="17adf-321">**在本地 Docker 容器中调试应用**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="17adf-321">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="17adf-322">**Steve Lasker。Build, Debug, Deploy ASP.NET Core Apps with Docker**（使用 Docker 生成、调试、部署 ASP.NET Core 应用）。</span><span class="sxs-lookup"><span data-stu-id="17adf-322">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="17adf-323">视频。</span><span class="sxs-lookup"><span data-stu-id="17adf-323">Video.</span></span>
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="17adf-324">使用 Visual Studio 可简化开发容器的工作流</span><span class="sxs-lookup"><span data-stu-id="17adf-324">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="17adf-325">实际上，使用 Visual Studio 进行开发的工作流比使用编辑器/CLI 方法的工作流简单得多。</span><span class="sxs-lookup"><span data-stu-id="17adf-325">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="17adf-326">Visual Studio 隐藏或简化了 Docker 需要执行的与 Dockerfile 和 docker-compose.yml 文件相关的大部分步骤，如图 5-15 所示。</span><span class="sxs-lookup"><span data-stu-id="17adf-326">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="17adf-327">**图 5-15**。</span><span class="sxs-lookup"><span data-stu-id="17adf-327">**Figure 5-15**.</span></span> <span data-ttu-id="17adf-328">使用 Visual Studio 可简化开发工作流</span><span class="sxs-lookup"><span data-stu-id="17adf-328">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="17adf-329">此外，只需执行一次第 2 步（向项目添加对 Docker 的支持）。</span><span class="sxs-lookup"><span data-stu-id="17adf-329">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="17adf-330">因此，该工作流与使用 .NET 进行任何其他开发时的普通开发任务的工作流类似。</span><span class="sxs-lookup"><span data-stu-id="17adf-330">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="17adf-331">开发人员需要了解其背后的工作原理（映像生成过程，使用的基础映像，容器的部署等），有时还需要编辑 Dockerfile 或 docker-compose.yml 文件以自定义行为。</span><span class="sxs-lookup"><span data-stu-id="17adf-331">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="17adf-332">但 Visual Studio 大大简化了大部分工作，提高了工作效率。</span><span class="sxs-lookup"><span data-stu-id="17adf-332">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="17adf-333">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-333">Additional resources</span></span>

-   <span data-ttu-id="17adf-334">**Steve Lasker。使用 Visual Studio 2017 进行 .NET Docker 开发**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="17adf-334">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="17adf-335">**Jeffrey T. Fritz。使用新的针对 Visual Studio 的 Docker 工具将 .NET Core 应用放入容器**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="17adf-335">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="17adf-336">在 DockerFile 中使用 PowerShell 命令来设置 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="17adf-336">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="17adf-337">[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)允许开发人员将现有 Windows 应用程序转换为 Docker 映像，并使用与 Docker 生态系统其余部分相同的工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="17adf-337">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="17adf-338">若要使用 Windows 容器，请在 Dockerfile 中运行 PowerShell 命令，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="17adf-338">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="17adf-339">本示例中使用的是 Windows Server Core 基础映像（FROM 设置），并使用 PowerShell 命令（RUN 设置）来安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="17adf-339">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="17adf-340">同样，也可使用 PowerShell 命令来设置其他组件，如 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件。</span><span class="sxs-lookup"><span data-stu-id="17adf-340">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="17adf-341">例如，Dockerfile 中的以下命令可设置 ASP.NET 4.5：</span><span class="sxs-lookup"><span data-stu-id="17adf-341">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="17adf-342">其他资源</span><span class="sxs-lookup"><span data-stu-id="17adf-342">Additional resources</span></span>

-   <span data-ttu-id="17adf-343">**aspnet-docker/Dockerfile。**</span><span class="sxs-lookup"><span data-stu-id="17adf-343">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="17adf-344">Example Powershell commands to run from dockerfiles to include Windows features（在 dockerfiles 中运行以包含 Windows 功能的 Powershell 命令示例）。</span><span class="sxs-lookup"><span data-stu-id="17adf-344">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="17adf-345">[上一篇] (index.md) [下一篇] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="17adf-345">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
