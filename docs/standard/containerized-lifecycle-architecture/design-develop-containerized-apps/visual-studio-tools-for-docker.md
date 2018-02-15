---
title: "使用 Visual Studio Tools for Docker (在 Windows 上的 Visual Studio)"
description: "使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 717675170f19f18fb48c4cea3ddd15bcd9648d71
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="5ce4a-104">使用 Visual Studio Tools for Docker (在 Windows 上的 Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="5ce4a-104">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="5ce4a-105">开发人员工作流时使用 Visual Studio 工具，使用 Visual Studio Code 和 Docker CLI 时，Docker 为类似于工作流 （事实上，它基于相同的 Docker CLI），但它可以更轻松地开始，可以简化过程，并可以提供更高工作效率的生成，运行，并构建任务。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-105">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="5ce4a-106">它也是可以执行并调试 F5 和 Ctrl + F5 从 Visual Studio 之类的简单操作通过你的容器。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-106">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="5ce4a-107">更多，与 Visual Studio 2017，除了能够运行和调试为一个容器，你还可以运行和调试一组的容器 （整个解决方案） 在同一时间如果定义了解决方法级别的相同 docker-compose.yml 文件中。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-107">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="5ce4a-108">配置你的本地环境</span><span class="sxs-lookup"><span data-stu-id="5ce4a-108">Configuring your local environment</span></span>

<span data-ttu-id="5ce4a-109">用于 Windows 的 Docker 的最新版本，它是比以往来开发 Docker 应用程序中的以下引用所述，安装程序非常简单，因为更容易。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-109">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="5ce4a-110">**详细信息：** 若要了解有关安装用于 Windows 的 Docker 的详细信息，请转到<https://docs.docker.com/docker-for-windows/>。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-110">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="5ce4a-111">如果你在使用 Visual Studio 2015，你必须具有 Update 3 或更高版本以及 Visual Studio Tools for Docker。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-111">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="5ce4a-112">**详细信息：** 安装 Visual Studio 的说明，请转到[https://www.visualstudio.com/ \ 产品/vs-2015年-产品的版本](https://www.visualstudio.com/products/vs-2015-product-editions)。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-112">**More info:** For instructions on installing Visual Studio, go to [https://www.visualstudio.com/\ products/vs-2015-product-editions](https://www.visualstudio.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="5ce4a-113">若要查看更多有关安装 Visual Studio Tools for Docker，请转到<http://aka.ms/vstoolsfordocker>和<https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="5ce4a-113">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="5ce4a-114">如果你使用 Visual Studio 2017 年 1，则已包含 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-114">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="5ce4a-115">在 Visual Studio 2015 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="5ce4a-115">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="5ce4a-116">Visual Studio Tools for Docker 提供一致的方法来开发和验证本地 Docker 容器的 Linux Linux Docker 主机或 VM 或你直接在 Windows 上的 Windows 容器中。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-116">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="5ce4a-117">如果你使用单个容器，需要开始第一件事是开启 Docker 支持在.NET 核心项目。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-117">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="5ce4a-118">为此，右键单击项目文件，在图 4-25 中所示。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-118">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

<span data-ttu-id="5ce4a-120">图 4-25： 打开 Visual Studio 项目的 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="5ce4a-120">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="5ce4a-121">在 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="5ce4a-121">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="5ce4a-122">当你 Docker 将支持添加到服务项目解决方案中 （请参见图 4-26 日），Visual Studio 不只添加 DockerFile 文件到你的项目，它也添加服务部分在你的解决方案的 docker-compose.yml 文件 （或如果它们未创建文件存在）。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-122">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="5ce4a-123">它是一种简单的方式开始编写 multicontainer 解决方案;然后可以打开 docker-compose.yml 文件并更新它们具有附加功能。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-123">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="5ce4a-124">图 4-26： 打开 Visual Studio 2017 项目中的 Docker 解决方案支持</span><span class="sxs-lookup"><span data-stu-id="5ce4a-124">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="5ce4a-125">此操作不只是向你的项目添加 DockerFile，它还将所需的配置的代码行添加到在解决方案级别设置全局 docker-compose.yml。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-125">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="5ce4a-126">你还可以启用 Docker 支持在 Visual Studio 2017 中, 创建 ASP.NET Core 项目时在图 4-27 中所示。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-126">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="5ce4a-127">图 4-27： 在创建项目时开启 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="5ce4a-127">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="5ce4a-128">将 Docker 支持添加到你在 Visual Studio 中的解决方案后，你还将看到在解决方案资源管理器添加的 docker-compose.yml 文件中，具有的新节点树如下图所示图 4-28。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-128">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="5ce4a-129">图 4-28: docker-compose.yml 文件现在显示在解决方案资源管理器中</span><span class="sxs-lookup"><span data-stu-id="5ce4a-129">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="5ce4a-130">你可以部署 multicontainer 应用程序运行时使用单个 docker-compose.yml 文件 docker-撰写;但是，Visual Studio 将一组添加它们，以便您可以覆盖根据环境 （而不是生产开发） 和执行的值类型 （而不是调试版本）。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-130">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="5ce4a-131">此功能将更好地中后面的章节所述。</span><span class="sxs-lookup"><span data-stu-id="5ce4a-131">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="5ce4a-132">**详细信息：** 上的服务实现和使用 Visual Studio Tools for Docker 的进一步信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="5ce4a-132">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="5ce4a-133">生成、 调试、 更新和刷新本地 Docker 容器中的应用程序： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="5ce4a-133">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="5ce4a-134">将 ASP.NET 容器部署到远程 Docker 主机： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="5ce4a-134">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5ce4a-135">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="5ce4a-135">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>
