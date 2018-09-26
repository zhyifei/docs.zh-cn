---
title: Visual Studio Tools for Windows 上的 Docker
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170790"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="e9a9b-103">使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e9a9b-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="e9a9b-104">Visual Studio Tools for Docker 开发人员工作流是类似于使用 Visual Studio Code 和 Docker CLI （它基于出现相同的 Docker CLI）。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-104">The Visual Studio Tools for Docker developer workflow is similar to using Visual Studio Code and Docker CLI (it is based on the same Docker CLI).</span></span> <span data-ttu-id="e9a9b-105">Visual Studio Tools Docker 可以更容易，若要开始，可以简化此过程中，并且对于生成，提供更高的生产率运行和组合任务。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-105">Visual Studio Tools for Docker makes it even easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="e9a9b-106">执行和调试简单的操作，例如通过容器**F5**并**Ctrl**+**F5**。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span>

> [!NOTE]
> <span data-ttu-id="e9a9b-107">本文适用到 Windows，在 Visual Studio 并不是 Visual Studio for mac。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-107">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="e9a9b-108">配置在本地环境</span><span class="sxs-lookup"><span data-stu-id="e9a9b-108">Configure your local environment</span></span>

<span data-ttu-id="e9a9b-109">使用 Docker 的 Windows 的最新版本 ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/))，简单的安装程序可以轻松开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-109">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="e9a9b-110">Visual Studio 2017 中包括 docker 支持。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-110">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="e9a9b-111">在此处下载 Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="e9a9b-111">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="e9a9b-112">在 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="e9a9b-112">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="e9a9b-113">有两个级别的可以向项目添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-113">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="e9a9b-114">在.NET Core web 应用程序项目，只是可以添加*Dockerfile*项目，方法是启用 Docker 支持的文件。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-114">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="e9a9b-115">下一级别是容器业务流程协调程序支持，这会增加*Dockerfile*到项目 （如果它尚不存在） 和一个*的 docker-compose.yml*解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-115">The next level is container orchestrator support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span>

<span data-ttu-id="e9a9b-116">**外** > **Docker 支持**并**添加** > **容器业务流程协调程序支持**命令web 应用程序项目的项目节点的右键单击菜单 （或上下文菜单） 上位于**解决方案资源管理器**中图 4-26 所示：</span><span class="sxs-lookup"><span data-stu-id="e9a9b-116">The **Add** > **Docker Support** and **Add** > **Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![在 Visual Studio 中添加 Docker 支持菜单选项](media/add-docker-support-menu.png)

<span data-ttu-id="e9a9b-118">图 4-26： 向 Visual Studio 2017 项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="e9a9b-118">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="e9a9b-119">添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="e9a9b-119">Add Docker support</span></span>

<span data-ttu-id="e9a9b-120">可以通过选择到现有的.NET Core web 应用程序项目添加 Docker 支持**外** > **Docker 支持**中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-120">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="e9a9b-121">您还可以启用 Docker 支持在项目创建期间通过选择**启用 Docker 支持**中**新的 ASP.NET Core Web 应用程序**在单击后打开的对话框**确定**中**新建项目**对话框中，在图 4-27 所示。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-121">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![在 Visual Studio 中的新 ASP.NET Core web 应用的启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="e9a9b-123">图 4-27: Visual Studio 2017 中的项目创建过程中启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="e9a9b-123">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="e9a9b-124">在添加或启用 Docker 支持，Visual Studio 添加*Dockerfile*到项目文件。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-124">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="e9a9b-125">启用时 Docker Compose 支持在.NET Framework web 应用程序项目 （不.NET Core web 应用程序项目） 的项目创建期间在图 4-28 所示，还添加容器业务流程协调程序支持。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-125">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestrator support is also added.</span></span>
>
> ![启用 Docker compose 支持.NET Framework web 应用程序项目](media/enable-docker-compose-support.png)

> <span data-ttu-id="e9a9b-127">图 4-28： 启用 Visual Studio 2017 中的.NET Framework web 应用项目上的 Docker Compose 支持</span><span class="sxs-lookup"><span data-stu-id="e9a9b-127">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestrator-support"></a><span data-ttu-id="e9a9b-128">添加容器业务流程协调程序支持</span><span class="sxs-lookup"><span data-stu-id="e9a9b-128">Add container orchestrator support</span></span>

<span data-ttu-id="e9a9b-129">当你想要编写多容器解决方案时，请向项目添加容器业务流程协调程序支持。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-129">When you want to compose a multicontainer solution, add container orchestrator support to your projects.</span></span> <span data-ttu-id="e9a9b-130">添加容器业务流程协调程序支持，请在 Visual Studio 添加*Dockerfile*到项目 （如果它尚不存在），并全局*的 docker-compose.yml*解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-130">When you add container orchestrator support, Visual Studio adds a *Dockerfile* to the project (if it doesn't already exist) and a global *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="e9a9b-131">这样就可以运行和调试容器 （整个解决方案） 的一组在同一时间，如果在同一个定义*docker compose.yml*文件。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-131">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span> <span data-ttu-id="e9a9b-132">如果*docker compose.yml*已存在，Visual Studio 只需向其添加的配置代码所需的行。</span><span class="sxs-lookup"><span data-stu-id="e9a9b-132">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

<span data-ttu-id="e9a9b-133">将容器业务流程支持添加到你的项目后，你将看到添加到项目中的 Dockerfile 和一个**docker compose**添加到解决方案中的文件夹**解决方案资源管理器**中图 4-29 所示：</span><span class="sxs-lookup"><span data-stu-id="e9a9b-133">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![在解决方案资源管理器在 Visual Studio 中的 docker 文件](media/docker-support-solution-explorer.png)

<span data-ttu-id="e9a9b-135">图 4-29： 在 Visual Studio 2017 中的解决方案资源管理器中的 Docker 文件</span><span class="sxs-lookup"><span data-stu-id="e9a9b-135">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="e9a9b-136">**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="e9a9b-136">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="e9a9b-137">生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="e9a9b-137">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="e9a9b-138">将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="e9a9b-138">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e9a9b-139">[上一页](docker-apps-inner-loop-workflow.md)
[下一页](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e9a9b-139">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>