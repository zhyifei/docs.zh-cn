---
title: Docker 应用开发工作流
description: 了解用于开发基于 Docker 的应用程序的工作流的详细信息。 分步深入了解有关优化 Dockerfile 的详细信息，最后了解使用 Visual Studio 时使用的简化工作流。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 92dd63fa155ea6e49ddb1eee9c201d5d9dc0418e
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679523"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="520f1-104">Docker 应用开发工作流</span><span class="sxs-lookup"><span data-stu-id="520f1-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="520f1-105">应用程序开发生命周期从你的计算机开始，你作为开发人员在该计算机上使用首选语言对应用程序进行编码和本地测试。</span><span class="sxs-lookup"><span data-stu-id="520f1-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="520f1-106">使用此工作流，无论选择哪种语言、框架和平台，你都可以开发和测试 Docker 容器，但均在本地执行操作。</span><span class="sxs-lookup"><span data-stu-id="520f1-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="520f1-107">每个容器（Docker 映像的实例）都包含以下组成部分：</span><span class="sxs-lookup"><span data-stu-id="520f1-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="520f1-108">操作系统选择（例如，Linux 发行版、Windows Nano Server 或 Windows Server Core）。</span><span class="sxs-lookup"><span data-stu-id="520f1-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="520f1-109">开发过程中添加的文件（例如源代码和应用程序二进制文件）。</span><span class="sxs-lookup"><span data-stu-id="520f1-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="520f1-110">配置信息（例如环境设置和依赖项）。</span><span class="sxs-lookup"><span data-stu-id="520f1-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="520f1-111">开发基于 Docker 容器的应用程序的工作流</span><span class="sxs-lookup"><span data-stu-id="520f1-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="520f1-112">本节介绍基于 Docker 容器的应用程序的内部循环开发工作流。</span><span class="sxs-lookup"><span data-stu-id="520f1-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="520f1-113">内部循环工作流是指不考虑更广泛的 DevOps 工作流（最多可以包括生产部署），只关注在开发人员的计算机上进行的开发工作。</span><span class="sxs-lookup"><span data-stu-id="520f1-113">The inner-loop workflow means it's not considering the broader DevOps workflow, that can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="520f1-114">其中不包括设置环境的初始步骤，因为这些步骤只需进行一次。</span><span class="sxs-lookup"><span data-stu-id="520f1-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="520f1-115">应用程序由开发人员自己的服务和附加库（依赖项）组成。</span><span class="sxs-lookup"><span data-stu-id="520f1-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="520f1-116">以下是生成 Docker 应用程序时常用的基本步骤，如图 5-1 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![<span data-ttu-id="520f1-117">Docker 应用的开发流程：1 - 编写应用代码，2 - 编写 Dockerfile/s，3 - 创建在 Dockerfile/s 上定义的映像，4 -（可选）在 docker-compose.yml 文件中编写服务，5 - 运行容器或 docker-compose 应用，6 - 测试应用或微服务，7 - 推送到存储库并重复操作。</span><span class="sxs-lookup"><span data-stu-id="520f1-117">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span> ](./media/image1.png)

<span data-ttu-id="520f1-118">**图 5-1**。</span><span class="sxs-lookup"><span data-stu-id="520f1-118">**Figure 5-1.**</span></span> <span data-ttu-id="520f1-119">开发 Docker 容器化应用的分步工作流</span><span class="sxs-lookup"><span data-stu-id="520f1-119">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="520f1-120">本部分详细介绍了整个流程，并着重通过 Visual Studio 环境解释了每个主要步骤。</span><span class="sxs-lookup"><span data-stu-id="520f1-120">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="520f1-121">使用编辑器/CLI 开发方法（例如，Visual Studio Code 和 macOS 或 Windows 上的 Docker CLI）时，需了解每个步骤，通常需要比使用 Visual Studio 了解得更详细。</span><span class="sxs-lookup"><span data-stu-id="520f1-121">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="520f1-122">有关在 CLI 环境中进行开发的详细信息，请参阅电子书[Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/)（容器化 Docker 应用程序生命周期与 Microsoft 平台和工具）。</span><span class="sxs-lookup"><span data-stu-id="520f1-122">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="520f1-123">使用 Visual Studio 2017 时，许多步骤都无需开发人员执行，可显著提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="520f1-123">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="520f1-124">使用 Visual Studio 2017 开发多容器应用程序时更是如此。</span><span class="sxs-lookup"><span data-stu-id="520f1-124">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="520f1-125">例如，只需单击一下，Visual Studio 就会将 Dockerfile 和 docker-compose.yml 文件添加到含有应用程序配置的项目。</span><span class="sxs-lookup"><span data-stu-id="520f1-125">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="520f1-126">在 Visual Studio 中运行应用程序时，系统会生成 Docker 映像并在 Docker 中直接运行多容器应用程序；开发人员甚至还能同时调试多个容器。</span><span class="sxs-lookup"><span data-stu-id="520f1-126">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="520f1-127">这些功能可大大提高开发速度。</span><span class="sxs-lookup"><span data-stu-id="520f1-127">These features will boost your development speed.</span></span>

<span data-ttu-id="520f1-128">但即使 Visual Studio 可以自动执行这些步骤，这也并不意味着开发人员不需要了解 Docker 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="520f1-128">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="520f1-129">因此，下面的指南详细介绍了每个步骤。</span><span class="sxs-lookup"><span data-stu-id="520f1-129">Therefore, the following guidance details every step.</span></span>

![1 - 编写应用代码](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="520f1-131">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="520f1-131">Step 1.</span></span> <span data-ttu-id="520f1-132">开始编码并创建初始应用程序或服务基线</span><span class="sxs-lookup"><span data-stu-id="520f1-132">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="520f1-133">开发 Docker 应用程序的方式与开发不带 Docker 的应用程序的方式类似。</span><span class="sxs-lookup"><span data-stu-id="520f1-133">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="520f1-134">二者的区别在于，开发 Docker 应用程序时，是在本地环境中部署和测试在 Docker 容器中运行的应用程序或服务（由 Docker 设置的 Linux VM，或者如果使用 Windows 容器，则直接是 Windows）。</span><span class="sxs-lookup"><span data-stu-id="520f1-134">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="520f1-135">使用 Visual Studio 设置本地环境</span><span class="sxs-lookup"><span data-stu-id="520f1-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="520f1-136">首先，请务必按以下说明所述安装适用于 Windows 的 [Docker 社区版 (CE)](https://docs.docker.com/docker-for-windows/)：</span><span class="sxs-lookup"><span data-stu-id="520f1-136">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

<span data-ttu-id="520f1-137">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)（适用于 Windows 的 Docker CE 入门）</span><span class="sxs-lookup"><span data-stu-id="520f1-137">[Get started with Docker CE for Windows](https://docs.docker.com/docker-for-windows/)</span></span>

<span data-ttu-id="520f1-138">此外，需要安装了“.NET Core 跨平台开发”工作负载的 Visual Studio 2017 版本 15.7 或更高版本，如图 5-2 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-138">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Visual Studio 安装过程中的“.NET Core 跨平台开发工作负载”的选择。](./media/image3.png)

<span data-ttu-id="520f1-140">**图 5-2**。</span><span class="sxs-lookup"><span data-stu-id="520f1-140">**Figure 5-2**.</span></span> <span data-ttu-id="520f1-141">在 Visual Studio 2017 设置过程中，选择“.NET Core 跨平台开发”工作负载</span><span class="sxs-lookup"><span data-stu-id="520f1-141">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="520f1-142">即使尚未在应用程序中启用 Docker，开发人员也可以开始在普通 .NET 中编写应用程序（如果打算使用容器，则通常在 .NET Core 中进行），并在 Docker 中进行部署和测试。</span><span class="sxs-lookup"><span data-stu-id="520f1-142">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="520f1-143">但建议尽快开始使用 Docker，因为这才是真实环境，并且能快速发现存在的问题。</span><span class="sxs-lookup"><span data-stu-id="520f1-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="520f1-144">推荐这样做是因为通过 Visual Studio 可轻松使用 Docker，开发人员能够快速明白，在 Visual Studio 中能调试多容器应用程序就是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="520f1-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-145">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-145">Additional resources</span></span>

- <span data-ttu-id="520f1-146">适用于 Windows 的 Docker CE 入门 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-146">**Get started with Docker CE for Windows** \\</span></span>
  [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="520f1-147">Visual Studio 2017 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-147">**Visual Studio 2017** \\</span></span>
  [*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![2 - 编写 Dockerfile](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="520f1-149">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="520f1-149">Step 2.</span></span> <span data-ttu-id="520f1-150">创建与现有 .NET 基础映像相关的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="520f1-150">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="520f1-151">要生成自定义映像，需为每个自定义映像提供一个 Dockerfile；无论是从 Visual Studio 自动部署，还是使用 Docker CLI（docker run 和 docker-compose 命令）手动部署，也需为每个要部署的容器提供一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="520f1-151">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="520f1-152">如果应用程序只包含一个自定义服务，则只需要一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="520f1-152">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="520f1-153">如果应用程序包含多个服务（如在微服务体系结构中），则每个服务都需要一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="520f1-153">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="520f1-154">将 Dockerfile 放在应用程序或服务的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="520f1-154">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="520f1-155">Dockerfile 包含多个命令，可指示 Docker 如何在容器中设置和运行应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="520f1-155">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="520f1-156">开发人员可在代码中手动创建 Dockerfile，并将其与 .NET 依赖项一起添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="520f1-156">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="520f1-157">借助 Visual Studio 及其 Docker 工具，只需单击几次鼠标即可完成此任务。</span><span class="sxs-lookup"><span data-stu-id="520f1-157">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="520f1-158">在 Visual Studio 2017 中新建项目时，会有一个名为“启用容器 (Docker) 支持”的选项，如图 5-3 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-158">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![在 Visual Studio 2017 中创建新的 ASP.NET Core 项目时，启用 Docker 支持复选框](./media/image5.png)

<span data-ttu-id="520f1-160">**图 5-3**。</span><span class="sxs-lookup"><span data-stu-id="520f1-160">**Figure 5-3**.</span></span> <span data-ttu-id="520f1-161">在 Visual Studio 2017 中创建新的 ASP.NET Core 项目时，启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="520f1-161">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="520f1-162">也可以如图 5-4 所示，右键单击“解决方案资源管理器”中的项目，并选择“添加” > “Docker 支持”，从而在现有 ASP.NET Core Web 应用项目中启用 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="520f1-162">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Visual Studio 中的添加 Docker 支持菜单选项](./media/image6.png)

<span data-ttu-id="520f1-164">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="520f1-164">**Figure 5-4**.</span></span> <span data-ttu-id="520f1-165">在现有 Visual Studio 2017 项目中启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="520f1-165">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="520f1-166">此操作可将 Dockerfile 添加到具有所需配置的项目，并且仅可用于 ASP.NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="520f1-166">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="520f1-167">与其类似，Visual Studio 也可以为具有“添加 > 容器业务流程协调程序支持”选项的整个解决方案添加 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="520f1-167">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="520f1-168">在步骤 4 中，我们将更详细地探讨此选项。</span><span class="sxs-lookup"><span data-stu-id="520f1-168">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="520f1-169">使用现有的官方 .NET Docker 映像</span><span class="sxs-lookup"><span data-stu-id="520f1-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="520f1-170">开发人员通常以基础映像（从 [Docker 中心](https://hub.docker.com/)注册表等官方存储库中获取）为基础生成容器的自定义映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="520f1-171">确切地说，在 Visual Studio 中启用 Docker 支持后就可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="520f1-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="520f1-172">Dockerfile 将使用现有的 `aspnetcore` 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-172">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="520f1-173">之前我们介绍了根据开发人员选择的框架和操作系统可使用的 Docker 映像和存储库。</span><span class="sxs-lookup"><span data-stu-id="520f1-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="520f1-174">例如，如果想使用 ASP.NET Core（Linux 或 Windows），则使用的映像是 `microsoft/dotnet:2.2-aspnetcore-runtime`。</span><span class="sxs-lookup"><span data-stu-id="520f1-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="520f1-175">因此，只需指定用于容器的基础 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="520f1-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="520f1-176">为此，将 `FROM microsoft/dotnet:2.2-aspnetcore-runtime` 添加到 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="520f1-176">You do that by adding `FROM microsoft/dotnet:2.2-aspnetcore-runtime` to your Dockerfile.</span></span> <span data-ttu-id="520f1-177">Visual Studio 会自动执行此操作，但若要更新版本，则需更新此值。</span><span class="sxs-lookup"><span data-stu-id="520f1-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="520f1-178">使用从 Docker 中心获取的带版本号的官方 .NET 映像存储库可确保能在所有计算机（包括用于开发、测试和生产的计算机）上使用相同的语言功能。</span><span class="sxs-lookup"><span data-stu-id="520f1-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="520f1-179">以下示例显示了 ASP.NET Core 容器的示例 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="520f1-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/dotnet:2.2-aspnetcore-runtime
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="520f1-180">在此情况下，该映像以官方 ASP.NET Core Docker 映像的版本 2.2（适用于 Linux 和 Windows 的多体系结构）为基础。</span><span class="sxs-lookup"><span data-stu-id="520f1-180">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="520f1-181">这是 `FROM microsoft/dotnet:2.2-aspnetcore-runtime` 设置。</span><span class="sxs-lookup"><span data-stu-id="520f1-181">This is the setting `FROM microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="520f1-182">（有关此基础映像的详细信息，请参阅 [.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/dotnet/)页面。）在 Dockerfile 中，还需指示 Docker 侦听要在运行时使用的 TCP 端口（示例中由 EXPOSE 设置配置的 TPC 端口为 80）。</span><span class="sxs-lookup"><span data-stu-id="520f1-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="520f1-183">可在 Dockerfile 中指定其他配置设置，具体取决于使用的语言和框架。</span><span class="sxs-lookup"><span data-stu-id="520f1-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="520f1-184">例如，带有 `["dotnet", "MySingleContainerWebApp.dll"]` 的 ENTRYPOINT 行可指示 Docker 运行 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="520f1-185">如果使用 SDK 和 .NET Core CLI (dotnet CLI) 来生成和运行 .NET 应用程序，则此设置会有所不同。</span><span class="sxs-lookup"><span data-stu-id="520f1-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="520f1-186">底部的 ENTRYPOINT 行和其他设置会有所不同，具体取决于为应用程序选择的语言和平台。</span><span class="sxs-lookup"><span data-stu-id="520f1-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-187">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-187">Additional resources</span></span>

- <span data-ttu-id="520f1-188">为 .NET Core 应用程序生成 Docker 映像 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-188">**Building Docker Images for .NET Core Applications** \\</span></span>
  [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="520f1-189">**生成开发人员自己的映像**。</span><span class="sxs-lookup"><span data-stu-id="520f1-189">**Build your own image**.</span></span> <span data-ttu-id="520f1-190">请查看官方 Docker 文档。</span><span class="sxs-lookup"><span data-stu-id="520f1-190">In the official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

- <span data-ttu-id="520f1-191">保持 .NET 容器映像的最新状态 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-191">**Staying up-to-date with .NET Container Images** \\</span></span>
  *<https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>*

- <span data-ttu-id="520f1-192">将 .NET 与 Docker 一起使用 - DockerCon 2018 更新 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-192">**Using .NET and Docker Together - DockerCon 2018 Update** \\</span></span>
  *<https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>*

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="520f1-193">使用多体系结构映像存储库</span><span class="sxs-lookup"><span data-stu-id="520f1-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="520f1-194">单个存储库中可包含平台变量，如 Linux 映像和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="520f1-195">借助此功能，Microsoft （基础映像创建者）等供应商可创建涵盖多个平台（即 Linux 和 Windows）的单个存储库。</span><span class="sxs-lookup"><span data-stu-id="520f1-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="520f1-196">例如，Docker 中心注册表中提供的 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) 存储库可使用相同的存储库名称为 Linux 和 Windows Nano Server 提供支持。</span><span class="sxs-lookup"><span data-stu-id="520f1-196">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="520f1-197">如果指定了标签，请明确指定一个平台，如下所示：</span><span class="sxs-lookup"><span data-stu-id="520f1-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="520f1-198">目标：Linux 上的 .NET Core 2.2 仅运行时</span><span class="sxs-lookup"><span data-stu-id="520f1-198">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="520f1-199">目标：Windows Nano Server 上的 .NET Core 2.2 仅运行时</span><span class="sxs-lookup"><span data-stu-id="520f1-199">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="520f1-200">但如果指定相同的映像名称，即使使用的标记相同，多体系结构映像（如 `aspnetcore` 映像）也将使用 Linux 或 Windows 版本，具体取决于部署的 Docker 主机操作系统，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="520f1-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="520f1-201">多体系结构：Linux 或 Windows Nano Server 上的 .NET Core 2.2 仅运行时，具体取决于 Docker 主机操作系统</span><span class="sxs-lookup"><span data-stu-id="520f1-201">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="520f1-202">这样一来，从 Windows 主机拉取映像时，也会拉取 Windows 变体，并且从 Linux 主机拉取同一映像名称时，也会拉取 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="520f1-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="520f1-203">Dockerfile 中的多阶段生成</span><span class="sxs-lookup"><span data-stu-id="520f1-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="520f1-204">Dockerfile 类似于批处理脚本。</span><span class="sxs-lookup"><span data-stu-id="520f1-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="520f1-205">类似于在必须从命令行设置计算机时你会执行的操作。</span><span class="sxs-lookup"><span data-stu-id="520f1-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="520f1-206">从设置初始上下文的基本映像开始，就像位于主机操作系统上的启动文件系统。</span><span class="sxs-lookup"><span data-stu-id="520f1-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="520f1-207">它不是操作系统，但是可以将其视为近似于容器内的操作系统。</span><span class="sxs-lookup"><span data-stu-id="520f1-207">It's not an OS, but you can think of if like "the" OS inside the container.</span></span>

<span data-ttu-id="520f1-208">执行每个命令行都会在文件系统上创建新的层，其中包含对上一个层的更改，这样一来，合并时可以生成相应的文件系统。</span><span class="sxs-lookup"><span data-stu-id="520f1-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="520f1-209">由于每个新的层都位于上一层之上，并且随着每个命令的执行，生成的图像大小也会增加，因此如果必须添加生成和发布应用程序所需的 SDK，那么映像可能会变得非常大。</span><span class="sxs-lookup"><span data-stu-id="520f1-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="520f1-210">在此情况下，多阶段生成（从 Docker 17.05 及更高版本开始）可以发挥奇妙的作用。</span><span class="sxs-lookup"><span data-stu-id="520f1-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="520f1-211">核心理念如下：可以将 Dockerfile 执行过程分为几个阶段，其中一个阶段为初始映像，后续阶段是一个或多个命令，最后阶段确定最终的映像大小。</span><span class="sxs-lookup"><span data-stu-id="520f1-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="520f1-212">简言之，可以使用多阶段生成将创建拆分为不同的“阶段”，然后只采用中间阶段的相关目录来组建最终的映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="520f1-213">使用此功能的一般策略为：</span><span class="sxs-lookup"><span data-stu-id="520f1-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="520f1-214">将基础 SDK 映像（无论大小）用于生成应用程序并将其发布到文件夹所需的一切内容，然后</span><span class="sxs-lookup"><span data-stu-id="520f1-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="520f1-215">使用基础、仅运行时的小型映像，并从上一阶段复制发布文件夹，以生成小的最终映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="520f1-216">了解多阶段的最好方法可能是逐行仔细浏览 Dockerfile，因此让我们开始浏览初始 Dockerfile（由 Visual Studio 向项目中添加 Docker 支持时所创建，我们稍后将对其进行一些优化）。</span><span class="sxs-lookup"><span data-stu-id="520f1-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="520f1-217">初始 Dockerfile 可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="520f1-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks … 
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -0 /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="520f1-218">以下为每一行的详细信息：</span><span class="sxs-lookup"><span data-stu-id="520f1-218">And these are the details, line by line:</span></span>

1.  <span data-ttu-id="520f1-219">使用“小型”仅运行时基础映像开始一个阶段，将其称为“基础”，以供参考。</span><span class="sxs-lookup"><span data-stu-id="520f1-219">Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>
2.  <span data-ttu-id="520f1-220">在映像中创建 /app 目录。</span><span class="sxs-lookup"><span data-stu-id="520f1-220">Create **/app** directory in the image.</span></span>
3.  <span data-ttu-id="520f1-221">公开端口 80。</span><span class="sxs-lookup"><span data-stu-id="520f1-221">Expose port **80**.</span></span>
<!-- skip -->
5.  <span data-ttu-id="520f1-222">使用“大型”映像开始用于生成/发布的新阶段，将其称为“生成”，以供参考。</span><span class="sxs-lookup"><span data-stu-id="520f1-222">Begin a new stage with "large" image for building/publishing, call it **build** for reference.</span></span>
6.  <span data-ttu-id="520f1-223">在映像中创建目录 /src。</span><span class="sxs-lookup"><span data-stu-id="520f1-223">Create directory **/src** in the image.</span></span>
7.  <span data-ttu-id="520f1-224">在第 16 行，复制引用的项目 .csproj 文件，以便之后能够还原包。</span><span class="sxs-lookup"><span data-stu-id="520f1-224">Up to line 16, copy referenced projects **.csproj** files, to be able to restore packages later.</span></span>
<!-- skip -->
17. <span data-ttu-id="520f1-225">还原 Catalog.API 项目和引用项目的包。</span><span class="sxs-lookup"><span data-stu-id="520f1-225">Restore packages for the **Catalog.API** project and the referenced projects.</span></span>
18. <span data-ttu-id="520f1-226">将解决方案的所有目录树（.dockerignore 文件中包含的文件/目录除外）复制到映像中的 /src 目录。</span><span class="sxs-lookup"><span data-stu-id="520f1-226">Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) from to the **/src** directory in the image.</span></span>
19. <span data-ttu-id="520f1-227">将当前文件夹更改为 Catalog.API 项目。</span><span class="sxs-lookup"><span data-stu-id="520f1-227">Change current folder to **Catalog.API** project.</span></span>
20. <span data-ttu-id="520f1-228">生成项目（和其他项目依赖项）并输出到映像中的 /app 目录。</span><span class="sxs-lookup"><span data-stu-id="520f1-228">Build project (and other project dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
22. <span data-ttu-id="520f1-229">开始一个从“生成”继续的新阶段，将其称为“发布”，以供参考。</span><span class="sxs-lookup"><span data-stu-id="520f1-229">Begin a new stage continuing from build, call it **publish** for reference.</span></span>
23. <span data-ttu-id="520f1-230">发布项目（和依赖项）并输出到映像中的 /app 目录。</span><span class="sxs-lookup"><span data-stu-id="520f1-230">Publish project (and dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
25. <span data-ttu-id="520f1-231">开始一个从“基础”继续的新阶段，并将其称为“最终”</span><span class="sxs-lookup"><span data-stu-id="520f1-231">Begin a new stage continuing from **base** and call it **final**</span></span>
26. <span data-ttu-id="520f1-232">将当前目录更改为 /app</span><span class="sxs-lookup"><span data-stu-id="520f1-232">Change current directory to **/app**</span></span>
27. <span data-ttu-id="520f1-233">将 /app 目录从阶段“发布”复制到当前目录</span><span class="sxs-lookup"><span data-stu-id="520f1-233">Copy the **/app** directory from stage **publish** to the current directory</span></span>
28. <span data-ttu-id="520f1-234">定义启动容器时要运行的命令。</span><span class="sxs-lookup"><span data-stu-id="520f1-234">Define the command to run when the container is started.</span></span>

<span data-ttu-id="520f1-235">现在让我们探索一些用于提高整个流程性能（以 eShopOnContainer 为例，这意味着在 Linux 容器中构建完整的解决方案需要大约 22 分钟或更长时间）的优化。</span><span class="sxs-lookup"><span data-stu-id="520f1-235">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="520f1-236">你将利用 Docker 的层缓存功能，该功能非常简单：如果基础映像和命令与之前执行的相同，那么它可以直接使用生成的层，而不需要执行命令，从而节省一些时间。</span><span class="sxs-lookup"><span data-stu-id="520f1-236">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="520f1-237">因此，让我们重点关注“生成”阶段，第 5-6 行基本相同，但是第 7-17 行与 eShopOnContainer 中每个服务不同，因此它们必须每次都执行命令，但是如果将第 7-16 行更改为：</span><span class="sxs-lookup"><span data-stu-id="520f1-237">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```
COPY . .
```

<span data-ttu-id="520f1-238">然后，对于每项服务都相同，它会复制整个解决方案并创建一个更大的层，但是：</span><span class="sxs-lookup"><span data-stu-id="520f1-238">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1) <span data-ttu-id="520f1-239">仅在第一次时（以及如果文件发生更改，则在重新构建时）执行复制进程，而且复制进程会使用所有其他服务的缓存，并且</span><span class="sxs-lookup"><span data-stu-id="520f1-239">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2) <span data-ttu-id="520f1-240">由于较大的映像发生在中间阶段，所以不会影响最终的映像大小。</span><span class="sxs-lookup"><span data-stu-id="520f1-240">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="520f1-241">下一个重要的优化涉及在第 17 行中执行的 `restore` 命令，其对于 eShopOnContainers 的每项服务也是不同的。</span><span class="sxs-lookup"><span data-stu-id="520f1-241">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="520f1-242">如果把该行更改为：</span><span class="sxs-lookup"><span data-stu-id="520f1-242">If you change that line to just:</span></span>

```console
RUN dotnet restore
```

<span data-ttu-id="520f1-243">它将还原整个解决方案的包，但它只还原一次，而不是当前策略中的 15 次。</span><span class="sxs-lookup"><span data-stu-id="520f1-243">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="520f1-244">然而，`dotnet restore` 仅当文件夹中有单个项目或解决方案文件时才会运行，因此实现这一点有点复杂，解决此问题且无需涉及太多细节的方法是：</span><span class="sxs-lookup"><span data-stu-id="520f1-244">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1) <span data-ttu-id="520f1-245">将以下命令行添加到 .dockerignore：</span><span class="sxs-lookup"><span data-stu-id="520f1-245">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="520f1-246">`*.sln`，以忽略主文件夹树中的所有解决方案文件</span><span class="sxs-lookup"><span data-stu-id="520f1-246">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="520f1-247">`!eShopOnContainers-ServicesAndWebApps.sln`，以仅添加此解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="520f1-247">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2) <span data-ttu-id="520f1-248">将 `/ignoreprojectextensions:.dcproj` 参数添加到 `dotnet restore`，因此它也忽略 docker-compose 项目，且仅还原 eShopOnContainers-ServicesAndWebApps 解决方案的包。</span><span class="sxs-lookup"><span data-stu-id="520f1-248">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="520f1-249">在最后的优化中，第 20 行是多余的，因为第 23 行也生成应用程序，并且实质上它在第 20 行之后运行，所以这又是一个耗时的命令。</span><span class="sxs-lookup"><span data-stu-id="520f1-249">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="520f1-250">生成的文件为：</span><span class="sxs-lookup"><span data-stu-id="520f1-250">The resulting file is then:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="520f1-251">从头开始创建基础映像</span><span class="sxs-lookup"><span data-stu-id="520f1-251">Creating your base image from scratch</span></span>

<span data-ttu-id="520f1-252">开发人员可以从头开始创建自己的 Docker 基础映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-252">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="520f1-253">不推荐刚开始使用 Docker 的开发人员使用此方案，但如果想为自己的基础映像设置特定位，则可采用此方案。</span><span class="sxs-lookup"><span data-stu-id="520f1-253">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-254">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-254">Additional resources</span></span>

- <span data-ttu-id="520f1-255">多体系结构 .NET Core 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-255">**Multi-arch .NET Core images**.\\</span></span>
  [*https://github.com/dotnet/announcements/issues/14*](https://github.com/dotnet/announcements/issues/14)

- <span data-ttu-id="520f1-256">**创建基础映像**。</span><span class="sxs-lookup"><span data-stu-id="520f1-256">**Create a base image**.</span></span> <span data-ttu-id="520f1-257">请查看官方 Docker 文档。</span><span class="sxs-lookup"><span data-stu-id="520f1-257">Official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![3 - 创建在 Dockerfile 中定义的映像](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="520f1-259">步骤 3。</span><span class="sxs-lookup"><span data-stu-id="520f1-259">Step 3.</span></span> <span data-ttu-id="520f1-260">创建自定义 Docker 映像并将应用程序或服务嵌入其中</span><span class="sxs-lookup"><span data-stu-id="520f1-260">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="520f1-261">需为应用程序中的每项服务创建一个相关映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-261">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="520f1-262">如果应用程序由单个服务或 Web 应用程序组成，则只需创建一个映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-262">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="520f1-263">请注意，Visual Studio 中会自动生成 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-263">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="520f1-264">以下步骤仅适用于编辑器/CLI 工作流，下文清楚解释了各步骤的工作原理。</span><span class="sxs-lookup"><span data-stu-id="520f1-264">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="520f1-265">开发人员发布完整功能或更改源代码管理系统（例如 GitHub）之前，需在本地进行开发和测试。</span><span class="sxs-lookup"><span data-stu-id="520f1-265">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="520f1-266">这意味着开发人员需要创建 Docker 映像并向本地 Docker 主机（Windows 或 Linux VM）部署容器，并运行、测试和调试这些本地容器。</span><span class="sxs-lookup"><span data-stu-id="520f1-266">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="520f1-267">若要使用 Docker CLI 和 Dockerfile 在本地环境中创建自定义映像，可使用 docker build 命令，如图 5-5 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-267">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![生成 Docker 映像的进度屏幕](./media/image8.png)

<span data-ttu-id="520f1-269">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="520f1-269">**Figure 5-5**.</span></span> <span data-ttu-id="520f1-270">创建自定义 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="520f1-270">Creating a custom Docker image</span></span>

<span data-ttu-id="520f1-271">（可选），可先运行 `dotnet publish`，生成包含所需 .NET 库和二进制文件的可部署文件夹，然后使用 `docker build` 命令，而不是直接从项目文件夹运行 docker build。</span><span class="sxs-lookup"><span data-stu-id="520f1-271">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="520f1-272">这将创建名为 `cesardl/netcore-webapi-microservice-docker:first` 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-272">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="520f1-273">此处的 :first 是表示特定版本的标记。</span><span class="sxs-lookup"><span data-stu-id="520f1-273">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="520f1-274">为组合 Docker 应用程序创建自定义映像时，可为每个映像重复执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="520f1-274">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="520f1-275">应用程序由多个容器组成时（即多容器应用程序），还可使用 `docker-compose up --build` 命令，借助相关 docker-compose.yml 文件中公开的元数据，只需一个命令即可生成所有相关映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-275">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="520f1-276">使用 docker images 命令可查找本地存储库中的现有映像，如图 5-6 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-276">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![docker 映像命令中列出的映像的屏幕视图](./media/image9.png)

<span data-ttu-id="520f1-278">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="520f1-278">**Figure 5-6.**</span></span> <span data-ttu-id="520f1-279">使用 docker images 命令查看现有映像</span><span class="sxs-lookup"><span data-stu-id="520f1-279">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="520f1-280">使用 Visual Studio 创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="520f1-280">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="520f1-281">使用 Visual Studio 创建具有 Docker 支持的项目时，不会显示创建映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-281">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="520f1-282">而是在按下 F5（或 Ctrl-F5）运行已 docker 化的应用程序或服务时创建映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-282">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="520f1-283">Visual Studio 会自动执行此操作，开发人员不会看到该过程，但务必要了解其原理。</span><span class="sxs-lookup"><span data-stu-id="520f1-283">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![4 -（可选）在 docker-compose.yml 文件中编辑服务](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="520f1-285">步骤 4。</span><span class="sxs-lookup"><span data-stu-id="520f1-285">Step 4.</span></span> <span data-ttu-id="520f1-286">生成多容器 Docker 应用程序时，在 docker-compose.yml 中定义服务</span><span class="sxs-lookup"><span data-stu-id="520f1-286">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="520f1-287">借助 [docker-compose.yml](https://docs.docker.com/compose/compose-file/) 文件，开发人员可定义一组相关服务，通过部署命令将其部署为组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-287">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="520f1-288">它还配置其依赖项关系和运行时配置。</span><span class="sxs-lookup"><span data-stu-id="520f1-288">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="520f1-289">若要使用 docker-compose.yml 文件，则需在主解决方案文件夹或根解决方案文件夹中创建该文件，其内容与以下示例中的内容类似：</span><span class="sxs-lookup"><span data-stu-id="520f1-289">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

<span data-ttu-id="520f1-290">此 docker-compose.yml 文件是简化合并版。</span><span class="sxs-lookup"><span data-stu-id="520f1-290">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="520f1-291">其中包含始终需要的每个容器的静态配置数据（如自定义映像的名称），以及视部署环境而定的配置信息（如连接字符串）。</span><span class="sxs-lookup"><span data-stu-id="520f1-291">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="520f1-292">后面的章节将介绍如何将 docker-compose.yml 配置拆分为多个 docker-compose 文件，并根据环境和执行类型（调试或发布）覆盖值。</span><span class="sxs-lookup"><span data-stu-id="520f1-292">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="520f1-293">docker-compose.yml 示例文件中定义了四项服务：`webmvc` 服务（一个 Web 应用程序）、两个微服务（`ordering.api` 和 `basket.api`）和一个数据源容器（作为容器运行的基于 SQL Server for Linux 的 `sql.data`）。</span><span class="sxs-lookup"><span data-stu-id="520f1-293">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="520f1-294">每项服务都将部署为一个容器，因此每项服务都需要一个 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-294">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="520f1-295">docker-compose.yml 文件不仅指定正在使用的容器，还指定如何单独配置各容器。</span><span class="sxs-lookup"><span data-stu-id="520f1-295">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="520f1-296">例如，.yml 文件中的 `webmvc` 容器定义：</span><span class="sxs-lookup"><span data-stu-id="520f1-296">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="520f1-297">使用预生成的 `eshop/web:latest` 映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-297">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="520f1-298">但也可以借助基于 docker-compose 文件中 build: 部分的其他配置，在执行 docker-compose 的过程中配置要生成的映像。</span><span class="sxs-lookup"><span data-stu-id="520f1-298">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="520f1-299">初始化两个环境变量（CatalogUrl 和 OrderingUrl）。</span><span class="sxs-lookup"><span data-stu-id="520f1-299">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="520f1-300">将容器上的公开端口 80 转接到主机上的外部端口 80。</span><span class="sxs-lookup"><span data-stu-id="520f1-300">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="520f1-301">通过 depends_on 设置将 Web 应用链接到目录和排序服务。</span><span class="sxs-lookup"><span data-stu-id="520f1-301">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="520f1-302">此操作会让该服务处于等待状态，直到启用这些服务。</span><span class="sxs-lookup"><span data-stu-id="520f1-302">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="520f1-303">稍后介绍如何实现微服务和多容器应用时，我们会再次回顾 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="520f1-303">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="520f1-304">在 Visual Studio 2017 中使用 docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="520f1-304">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="520f1-305">除了向项目添加 Dockerfile，如前所述，Visual Studio 2017（从 15.8 开始）还可以向解决方案添加对 Docker Compose 的业务流程协调程序支持。</span><span class="sxs-lookup"><span data-stu-id="520f1-305">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="520f1-306">添加容器业务流程协调程序支持（如图 5-7 所示）时，Visual Studio 将首次为项目创建 Dockerfile，并在解决方案中使用几个全局 `docker-compose*.yml` 文件创建新的（服务部分）项目，然后将项目添加到这些文件。</span><span class="sxs-lookup"><span data-stu-id="520f1-306">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="520f1-307">随后可打开 docker-compose.yml 文件并对其进行更新，增加新的功能。</span><span class="sxs-lookup"><span data-stu-id="520f1-307">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="520f1-308">必须为要添加到 docker-compose.yml 文件的每个项目重复执行此操作。</span><span class="sxs-lookup"><span data-stu-id="520f1-308">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="520f1-309">在撰写此文时，Visual Studio 支持 Docker Compose 和 Service Fabric 业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-309">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![将业务流程协调程序支持添加到 ASP.NET Core 项目的上下文菜单选项](./media/image21.png)

<span data-ttu-id="520f1-311">**图 5-7**。</span><span class="sxs-lookup"><span data-stu-id="520f1-311">**Figure 5-7**.</span></span> <span data-ttu-id="520f1-312">右键单击 ASP.NET Core 项目，在 Visual Studio 2017 中添加对 Docker 的支持</span><span class="sxs-lookup"><span data-stu-id="520f1-312">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="520f1-313">在 Visual Studio 中添加业务流程协调程序支持后，解决方案资源管理器中会出现一个新节点（位于 `docker-compose.dcproj` 项目文件中），其中包含添加的 docker-compose.yml 文件，如图 5-8 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-313">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![解决方案资源管理器中的 docker-compose 节点](./media/image11.png)

<span data-ttu-id="520f1-315">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="520f1-315">**Figure 5-8**.</span></span> <span data-ttu-id="520f1-316">在 Visual Studio 2017 解决方案资源管理器中添加的 docker-compose 树节点</span><span class="sxs-lookup"><span data-stu-id="520f1-316">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="520f1-317">可使用 `docker-compose up` 命令，通过单个 docker-compose.yml 文件部署多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-317">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="520f1-318">但 Visual Studio 按组添加，因此开发人员可根据环境（开发或生产）和执行类型（发布或调试）来覆盖值。</span><span class="sxs-lookup"><span data-stu-id="520f1-318">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="520f1-319">稍后将介绍此功能。</span><span class="sxs-lookup"><span data-stu-id="520f1-319">This capability will be explained in later sections.</span></span>

![5 - 运行容器或编写的应用](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="520f1-321">步骤 5。</span><span class="sxs-lookup"><span data-stu-id="520f1-321">Step 5.</span></span> <span data-ttu-id="520f1-322">生成并运行 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="520f1-322">Build and run your Docker application</span></span>

<span data-ttu-id="520f1-323">如果应用程序只有一个容器，则可通过将其部署到 Docker 主机（虚拟机或物理服务器）来运行该程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-323">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="520f1-324">但如果应用程序包含多项服务，则可使用单个 CLI 命令 (docker-compose up) 或使用 Visual Studio（会在其中使用该命令）将其部署为组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-324">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="520f1-325">接下来介绍这两种不同的选项。</span><span class="sxs-lookup"><span data-stu-id="520f1-325">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="520f1-326">选项 A：运行单容器应用程序</span><span class="sxs-lookup"><span data-stu-id="520f1-326">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="520f1-327">使用 Docker CLI</span><span class="sxs-lookup"><span data-stu-id="520f1-327">Using Docker CLI</span></span>

<span data-ttu-id="520f1-328">可使用 `docker run` 命令运行 Docker 容器，如图 5-9 所示：</span><span class="sxs-lookup"><span data-stu-id="520f1-328">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="520f1-329">上面的命令将在每次运行时从指定的映像创建新的容器实例。</span><span class="sxs-lookup"><span data-stu-id="520f1-329">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="520f1-330">可以使用 `--name` 参数为容器指定名称，然后使用 `docker start {name}`（或者使用容器 ID 或自动名称）运行现有的容器实例。</span><span class="sxs-lookup"><span data-stu-id="520f1-330">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![使用 docker run 命令运行 Docker 容器时的屏幕视图](./media/image13.png)

<span data-ttu-id="520f1-332">**图 5-9**。</span><span class="sxs-lookup"><span data-stu-id="520f1-332">**Figure 5-9**.</span></span> <span data-ttu-id="520f1-333">使用 docker run 命令运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="520f1-333">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="520f1-334">此时，该命令将容器的内部端口 5000 绑定到主机的端口 80。</span><span class="sxs-lookup"><span data-stu-id="520f1-334">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="520f1-335">这意味着主机在侦听端口 80，并将其转接到容器上的端口 5000。</span><span class="sxs-lookup"><span data-stu-id="520f1-335">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="520f1-336">显示的哈希为容器 ID，如果不使用 `--name` 选项，还会为它分配随机可读的名称。</span><span class="sxs-lookup"><span data-stu-id="520f1-336">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="520f1-337">使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="520f1-337">Using Visual Studio</span></span>

<span data-ttu-id="520f1-338">如果尚未添加容器业务流程协调程序支持，也可按下 Ctrl-F5 在 Visual Studio 中运行单容器应用，还可使用 F5 在容器中调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-338">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="520f1-339">使用 docker run 在本地运行容器。</span><span class="sxs-lookup"><span data-stu-id="520f1-339">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="520f1-340">选项 B：运行多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="520f1-340">Option B: Running a multi-container application</span></span>

<span data-ttu-id="520f1-341">在大多数企业方案中，Docker 应用程序由多项服务组成，这意味着需要运行多容器应用程序，如图 5-10 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-341">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![具有多个 Docker 容器的 VM](./media/image14.png)

<span data-ttu-id="520f1-343">**图 5-10**。</span><span class="sxs-lookup"><span data-stu-id="520f1-343">**Figure 5-10**.</span></span> <span data-ttu-id="520f1-344">部署了 Docker 容器的 VM</span><span class="sxs-lookup"><span data-stu-id="520f1-344">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="520f1-345">使用 Docker CLI</span><span class="sxs-lookup"><span data-stu-id="520f1-345">Using Docker CLI</span></span>

<span data-ttu-id="520f1-346">若要使用 Docker CLI 运行多容器应用程序，请使用 `docker-compose up` 命令。</span><span class="sxs-lookup"><span data-stu-id="520f1-346">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="520f1-347">此命令使用解决方案级别的 docker-compose.yml 文件来部署多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-347">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="520f1-348">图 5-11 显示了从主解决方案目录（包含 docker-compose.yml 文件）运行命令的结果。</span><span class="sxs-lookup"><span data-stu-id="520f1-348">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![运行 docker-compose up 命令时的屏幕视图](./media/image15.png)

<span data-ttu-id="520f1-350">**图 5-11**。</span><span class="sxs-lookup"><span data-stu-id="520f1-350">**Figure 5-11**.</span></span> <span data-ttu-id="520f1-351">运行 docker-compose up 命令时的示例结果</span><span class="sxs-lookup"><span data-stu-id="520f1-351">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="520f1-352">运行 docker-compose up 命令后，应用程序及其相关容器将部署到 Docker 主机中，如图 5-10 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-352">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="520f1-353">使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="520f1-353">Using Visual Studio</span></span>

<span data-ttu-id="520f1-354">使用 Visual Studio 2017 运行多容器应用程序十分简单。</span><span class="sxs-lookup"><span data-stu-id="520f1-354">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="520f1-355">按 Ctrl-F5 可运行，按 F5 可调试，按照惯例，将 docker-compose 项目设置为启动项目。</span><span class="sxs-lookup"><span data-stu-id="520f1-355">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="520f1-356">Visual Studio 处理所有需要的设置，所以你可以按照惯例创建断点，并调试最终在“远程服务器”中运行的独立进程。</span><span class="sxs-lookup"><span data-stu-id="520f1-356">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="520f1-357">如前所述，每次向解决方案中的项目添加对 Docker 的支持时，都会在全局（解决方案级别）docker-compose.yml 文件中配置该项目，因此开发人员可以同时运行或调试整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="520f1-357">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="520f1-358">Visual Studio 将为每个启用了 Docker 解决方案支持的项目启动一个容器，并代为执行所有内部步骤（发布 dotnet、生成 Docker 等）。</span><span class="sxs-lookup"><span data-stu-id="520f1-358">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="520f1-359">如果想大致看看所有步骤，请查看文件：</span><span class="sxs-lookup"><span data-stu-id="520f1-359">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="520f1-360">此处的重点是，在 Visual Studio 2017 中，按下 F5 键可执行另一项 Docker 命令，如图 5-12 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-360">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="520f1-361">此选项允许开发人员在解决方案级别运行 docker-compose.yml 文件中定义的所有容器，从而运行或调试多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="520f1-361">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="520f1-362">可调试多容器解决方案就意味着，开发人员可设置多个断点，每个端点都位于不同的项目（容器）中，这样从 Visual Studio 进行调试时，会在不同项目中定义的断点处停止，并在不同容器上运行。</span><span class="sxs-lookup"><span data-stu-id="520f1-362">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![运行 docker-compose 项目的 Visual Studio 调试工具栏](./media/image16.png)

<span data-ttu-id="520f1-364">**图 5-12**。</span><span class="sxs-lookup"><span data-stu-id="520f1-364">**Figure 5-12**.</span></span> <span data-ttu-id="520f1-365">在 Visual Studio 2017 中运行多容器应用</span><span class="sxs-lookup"><span data-stu-id="520f1-365">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-366">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-366">Additional resources</span></span>

- <span data-ttu-id="520f1-367">将 ASP.NET 容器部署到远程 Docker 主机 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-367">**Deploy an ASP.NET container to a remote Docker host** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="520f1-368">有关使用业务流程协调程序进行测试和部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="520f1-368">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="520f1-369">使用 docker-compose up 和 docker run 命令（或在 Visual Studio 中运行和调试容器）足以在开发环境中测试容器。</span><span class="sxs-lookup"><span data-stu-id="520f1-369">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="520f1-370">但不应该将这种方法用于生产部署，在生产部署中应该以业务流程协调程序（例如 [Kubernetes](https://kubernetes.io/) 或 [Service Fabric](https://azure.microsoft.com/services/service-fabric/)）为目标。</span><span class="sxs-lookup"><span data-stu-id="520f1-370">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="520f1-371">如果正在使用 Kubernetes，那么必须使用 [pod](https://kubernetes.io/docs/concepts/workloads/pods/pod/) 来组织容器和[服务](https://kubernetes.io/docs/concepts/services-networking/service/)，使其互联。</span><span class="sxs-lookup"><span data-stu-id="520f1-371">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="520f1-372">还可以使用[部署](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)来组织 pod 的创建和修改。</span><span class="sxs-lookup"><span data-stu-id="520f1-372">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6 - 测试应用或微服务](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="520f1-374">步骤 6。</span><span class="sxs-lookup"><span data-stu-id="520f1-374">Step 6.</span></span> <span data-ttu-id="520f1-375">使用本地 Docker 主机测试 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="520f1-375">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="520f1-376">这一步骤会因应用程序的用途而有所不同。</span><span class="sxs-lookup"><span data-stu-id="520f1-376">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="520f1-377">对于部署为单个容器或服务的简单 .NET Core Web 应用程序而言，在 Docker 主机上打开浏览器并导航到该站点即可访问该服务，如图 5-13 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-377">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="520f1-378">（如果 Dockerfile 中的配置将容器映射到除主机上的 80 端口以外的任何端口，请在 URL 中包含该主机端口。）</span><span class="sxs-lookup"><span data-stu-id="520f1-378">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![API 终结点响应的浏览器视图](./media/image18.png)

<span data-ttu-id="520f1-380">**图 5-13**。</span><span class="sxs-lookup"><span data-stu-id="520f1-380">**Figure 5-13**.</span></span> <span data-ttu-id="520f1-381">使用 localhost 在本地测试 Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="520f1-381">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="520f1-382">如果 localhost 未指向 Docker 主机 IP（默认情况下，使用 Docker CE 时应指向主机 IP），若要导航到服务，请使用计算机网卡的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="520f1-382">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="520f1-383">请注意，在此处讨论的特定容器示例中，浏览器中的此 URL 使用的是端口 80。</span><span class="sxs-lookup"><span data-stu-id="520f1-383">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="520f1-384">但该请求会在内部被重定向到端口 5000，因为 docker run 命令之前进行了此部署，如上一步中所述。</span><span class="sxs-lookup"><span data-stu-id="520f1-384">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="520f1-385">还可从终端使用 curl 测试应用程序，如图 5-14 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-385">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="520f1-386">对于 Windows 上安装的 Docker，除计算机的实际 IP 地址以外，默认的 Docker 主机 IP 始终为 10.0.75.1。</span><span class="sxs-lookup"><span data-stu-id="520f1-386">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![使用 curl 的 API 终结点响应的屏幕视图](./media/image19.png)

<span data-ttu-id="520f1-388">**图 5-14**。</span><span class="sxs-lookup"><span data-stu-id="520f1-388">**Figure 5-14**.</span></span> <span data-ttu-id="520f1-389">使用 curl 在本地测试 Docker 应用程序的示例</span><span class="sxs-lookup"><span data-stu-id="520f1-389">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="520f1-390">使用 Visual Studio 2017 测试和调试容器</span><span class="sxs-lookup"><span data-stu-id="520f1-390">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="520f1-391">使用 Visual Studio 2017 运行和调试容器时，调试 .NET 应用程序的方式与运行不带容器的应用程序的方式类似。</span><span class="sxs-lookup"><span data-stu-id="520f1-391">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="520f1-392">不使用 Visual Studio 进行测试和调试</span><span class="sxs-lookup"><span data-stu-id="520f1-392">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="520f1-393">如果使用编辑器/CLI 方法开发应用，调试容器会更加困难，需通过生成跟踪来进行调试。</span><span class="sxs-lookup"><span data-stu-id="520f1-393">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-394">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-394">Additional resources</span></span>

- <span data-ttu-id="520f1-395">在本地 Docker 容器中调试应用 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-395">**Debugging apps in a local Docker container** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="520f1-396">**Steve Lasker。Build, Debug, Deploy ASP.NET Core Apps with Docker**（使用 Docker 生成、调试、部署 ASP.NET Core 应用）。</span><span class="sxs-lookup"><span data-stu-id="520f1-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="520f1-397">视频。</span><span class="sxs-lookup"><span data-stu-id="520f1-397">Video.</span></span> \
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="520f1-398">使用 Visual Studio 可简化开发容器的工作流</span><span class="sxs-lookup"><span data-stu-id="520f1-398">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="520f1-399">实际上，使用 Visual Studio 进行开发的工作流比使用编辑器/CLI 方法的工作流简单得多。</span><span class="sxs-lookup"><span data-stu-id="520f1-399">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="520f1-400">Visual Studio 隐藏或简化了 Docker 需要执行的与 Dockerfile 和 docker-compose.yml 文件相关的大部分步骤，如图 5-15 所示。</span><span class="sxs-lookup"><span data-stu-id="520f1-400">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![利用 Visual Studio 简化容器开发工作流：1 - 编写应用代码，2 - 向项目添加 Docker 支持（仅一次），3 - 运行容器或 docker-compose 应用，4 - 测试应用或微服务，5 - 推送到存储库并重复操作。](./media/image20.png)

<span data-ttu-id="520f1-402">**图 5-15**。</span><span class="sxs-lookup"><span data-stu-id="520f1-402">**Figure 5-15**.</span></span> <span data-ttu-id="520f1-403">使用 Visual Studio 可简化开发工作流</span><span class="sxs-lookup"><span data-stu-id="520f1-403">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="520f1-404">此外，只需执行一次第 2 步（向项目添加对 Docker 的支持）。</span><span class="sxs-lookup"><span data-stu-id="520f1-404">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="520f1-405">因此，该工作流与使用 .NET 进行任何其他开发时的普通开发任务的工作流类似。</span><span class="sxs-lookup"><span data-stu-id="520f1-405">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="520f1-406">开发人员需要了解其背后的工作原理（映像生成过程，使用的基础映像，容器的部署等），有时还需要编辑 Dockerfile 或 docker-compose.yml 文件以自定义行为。</span><span class="sxs-lookup"><span data-stu-id="520f1-406">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="520f1-407">但 Visual Studio 大大简化了大部分工作，提高了工作效率。</span><span class="sxs-lookup"><span data-stu-id="520f1-407">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="520f1-408">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-408">Additional resources</span></span>

- <span data-ttu-id="520f1-409">使用 Visual Studio 2017 进行 Steve Lasker .NET docker 开发 \\</span><span class="sxs-lookup"><span data-stu-id="520f1-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \\</span></span>
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="520f1-410">在 DockerFile 中使用 PowerShell 命令来设置 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="520f1-410">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="520f1-411">[Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/index)允许开发人员将现有 Windows 应用程序转换为 Docker 映像，并使用与 Docker 生态系统其余部分相同的工具进行部署。</span><span class="sxs-lookup"><span data-stu-id="520f1-411">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="520f1-412">若要使用 Windows 容器，请在 Dockerfile 中运行 PowerShell 命令，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="520f1-412">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="520f1-413">本示例中使用的是 Windows Server Core 基础映像（FROM 设置），并使用 PowerShell 命令（RUN 设置）来安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="520f1-413">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="520f1-414">同样，也可使用 PowerShell 命令来设置其他组件，如 ASP.NET 4.x、.NET 4.6 或任何其他 Windows 软件。</span><span class="sxs-lookup"><span data-stu-id="520f1-414">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="520f1-415">例如，Dockerfile 中的以下命令可设置 ASP.NET 4.5：</span><span class="sxs-lookup"><span data-stu-id="520f1-415">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="520f1-416">其他资源</span><span class="sxs-lookup"><span data-stu-id="520f1-416">Additional resources</span></span>

- <span data-ttu-id="520f1-417">**aspnet-docker/Dockerfile。**</span><span class="sxs-lookup"><span data-stu-id="520f1-417">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="520f1-418">在 dockerfiles 中运行以包含 Windows 功能的 Powershell 命令示例。</span><span class="sxs-lookup"><span data-stu-id="520f1-418">Example PowerShell commands to run from dockerfiles to include Windows features.\\</span></span>
  [*https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="520f1-419">[上一页](index.md)
>[下一页](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="520f1-419">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
