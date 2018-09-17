---
title: 使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743821"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="acba9-103">使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="acba9-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="acba9-104">使用 Visual Studio Code 和 Docker CLI 时，开发工作流时使用 Visual Studio Tools for Docker 是类似于工作流。</span><span class="sxs-lookup"><span data-stu-id="acba9-104">The development workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="acba9-105">实际上，它基于相同的 Docker CLI，但它是更轻松地开始，可以简化此过程中，并提供了提高工作效率生成、 运行和组合任务。</span><span class="sxs-lookup"><span data-stu-id="acba9-105">In fact, it's based on the same Docker CLI, but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="acba9-106">它还可以执行和调试你通过简单的操作，例如 F5 和 Ctrl + F5 从 Visual Studio 的容器。</span><span class="sxs-lookup"><span data-stu-id="acba9-106">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="acba9-107">通过可选容器业务流程支持，除了能够运行和调试单个容器，可运行和调试容器 （整个解决方案） 的一组在同一时间。</span><span class="sxs-lookup"><span data-stu-id="acba9-107">With the optional container orchestration support, in addition to being able to run and debug a single container, you can run and debug a group of containers (a whole solution) at the same time.</span></span> <span data-ttu-id="acba9-108">只需在同一个定义的容器*docker compose.yml*解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="acba9-108">Just define the containers in the same *docker-compose.yml* file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="acba9-109">配置在本地环境</span><span class="sxs-lookup"><span data-stu-id="acba9-109">Configuring your local environment</span></span>

<span data-ttu-id="acba9-110">与任何.NET 和.NET Core 工作负载安装 Visual Studio 2017 包含 docker 支持。</span><span class="sxs-lookup"><span data-stu-id="acba9-110">Docker support is included in Visual Studio 2017 with any of the .NET and .NET Core workloads installed.</span></span> <span data-ttu-id="acba9-111">单独安装 Docker 的 Windows。</span><span class="sxs-lookup"><span data-stu-id="acba9-111">Install Docker for Windows separately.</span></span>

<span data-ttu-id="acba9-112">使用 Docker 的 Windows 的最新版本，它是比以往要开发 Docker 应用程序的以下参考中所述，安装程序非常简单，因为更容易。</span><span class="sxs-lookup"><span data-stu-id="acba9-112">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="acba9-113">**详细信息：** 若要了解有关安装 Windows 的 Docker 的详细信息，请转到<https://docs.docker.com/docker-for-windows/>。</span><span class="sxs-lookup"><span data-stu-id="acba9-113">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="acba9-114">**详细信息：** 安装 Visual Studio 的说明，请转到[ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/)。</span><span class="sxs-lookup"><span data-stu-id="acba9-114">**More info:** For instructions on installing Visual Studio, go to [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/).</span></span>

<span data-ttu-id="acba9-115">若要查看有关安装 Visual Studio Tools for Docker 的详细信息，请转到<http://aka.ms/vstoolsfordocker>和<https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>。</span><span class="sxs-lookup"><span data-stu-id="acba9-115">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="acba9-116">在 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="acba9-116">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="acba9-117">向项目添加 Docker 支持时 （请参阅图 4-26），Visual Studio 将添加*Dockerfile*到项目根目录。</span><span class="sxs-lookup"><span data-stu-id="acba9-117">When adding Docker support to a project (see Figure 4-26), Visual Studio adds a *Dockerfile* to the project root.</span></span>

![启用 Visual Studio 2017 项目中的 Docker 解决方案支持](./media/image32.png)

<span data-ttu-id="acba9-119">图 4-26： 启用 Visual Studio 2017 项目中的 Docker 解决方案支持</span><span class="sxs-lookup"><span data-stu-id="acba9-119">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

 <span data-ttu-id="acba9-120">默认情况下，在 Visual Studio 2017 版本 15.7 或更早版本中添加容器业务流程支持，通过 Docker Compose。</span><span class="sxs-lookup"><span data-stu-id="acba9-120">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.7 or earlier.</span></span> <span data-ttu-id="acba9-121">容器业务流程支持是 Visual Studio 2017 版本 15.8 中选择的功能或更高版本，在这种情况下 Docker Compose 和 Service Fabric 支持。</span><span class="sxs-lookup"><span data-stu-id="acba9-121">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later, in which case Docker Compose and Service Fabric are supported.</span></span>

<span data-ttu-id="acba9-122">使用 Visual Studio 15.8 和更高版本，可以在每个具有相关联的容器解决方案中添加对多个项目的支持。</span><span class="sxs-lookup"><span data-stu-id="acba9-122">With Visual Studio version 15.8 and later, you can add support for multiple projects in a solution that each have an associated container.</span></span> <span data-ttu-id="acba9-123">中的解决方案或项目节点上右键单击**解决方案资源管理器**，然后选择**添加** > **容器业务流程支持**。</span><span class="sxs-lookup"><span data-stu-id="acba9-123">Right-click on the solution or project node in **Solution Explorer**, and choose **Add** > **Container Orchestration Support**.</span></span>  <span data-ttu-id="acba9-124">然后选择**Docker Compose**或**Service Fabric**管理容器。</span><span class="sxs-lookup"><span data-stu-id="acba9-124">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="acba9-125">当你选择**Docker Compose**，Visual Studio 在解决方案中添加一个服务部分*的 docker-compose.yml*文件 （或创建文件，如果它们不存在）。</span><span class="sxs-lookup"><span data-stu-id="acba9-125">When you choose **Docker Compose**, Visual Studio adds a service section in your solution's *docker-compose.yml* files (or creates the files if they didn't exist).</span></span> <span data-ttu-id="acba9-126">它是轻松地开始编写多容器解决方案;然后可以打开*docker compose.yml*文件，并使用其他功能更新这些值。</span><span class="sxs-lookup"><span data-stu-id="acba9-126">It's an easy way to begin composing your multi-container solution; you then can open the *docker-compose.yml* files and update them with additional features.</span></span>

<span data-ttu-id="acba9-127">此操作将添加所需的配置行代码来*docker compose.yml*解决方案级别的设置。</span><span class="sxs-lookup"><span data-stu-id="acba9-127">This action adds the required configuration lines of code to a *docker-compose.yml* set at the solution level.</span></span>

<span data-ttu-id="acba9-128">您还可以启用 Docker 支持在 Visual Studio 2017 中，创建 ASP.NET Core 项目时在图 4-27 所示。</span><span class="sxs-lookup"><span data-stu-id="acba9-128">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![创建项目时启用 Docker 支持](./media/image33.png)

<span data-ttu-id="acba9-130">图 4-27： 启用 Docker 支持创建项目时</span><span class="sxs-lookup"><span data-stu-id="acba9-130">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="acba9-131">向在 Visual Studio 解决方案中添加 Docker 支持后，您还将看到在新的节点树**解决方案资源管理器**使用添加*的 docker-compose.yml*文件，如下图中图 4-28 所示。</span><span class="sxs-lookup"><span data-stu-id="acba9-131">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in **Solution Explorer** with the added *docker-compose.yml* files, as depicted in Figure 4-28.</span></span>

![在解决方案资源管理器中现在显示的 docker-compose.yml 文件](./media/image34.PNG)

<span data-ttu-id="acba9-133">图 4-28： 中现在显示的 docker-compose.yml 文件**解决方案资源管理器**</span><span class="sxs-lookup"><span data-stu-id="acba9-133">Figure 4-28: docker-compose.yml files now display in **Solution Explorer**</span></span>

<span data-ttu-id="acba9-134">可以部署多容器应用程序使用单个*docker-compose.yml*文件在运行时`docker-compose up`; 但是，Visual Studio 会添加它们，一组，以便可以重写值具体取决于环境 （开发与生产） 和执行类型 （发布与调试）。</span><span class="sxs-lookup"><span data-stu-id="acba9-134">You could deploy a multi-container app by using a single *docker-compose.yml* file when you run `docker-compose up`; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="acba9-135">后面的章节中更好地解释此功能。</span><span class="sxs-lookup"><span data-stu-id="acba9-135">This capability is better explained in later chapters.</span></span>

<span data-ttu-id="acba9-136">您还可以使用 Service Fabric 而不是 Docker Compose 来管理多个容器。</span><span class="sxs-lookup"><span data-stu-id="acba9-136">You can also use Service Fabric instead of Docker Compose to manage multiple containers.</span></span> <span data-ttu-id="acba9-137">请参阅[教程： 将 Windows 容器中的.NET 应用程序部署到 Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container)。</span><span class="sxs-lookup"><span data-stu-id="acba9-137">See [Tutorial: Deploy a .NET application in a Windows container to Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).</span></span>

<span data-ttu-id="acba9-138">**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="acba9-138">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="acba9-139">生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="acba9-139">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="acba9-140">将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="acba9-140">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="acba9-141">[上一页](docker-apps-inner-loop-workflow.md)
[下一页](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="acba9-141">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
