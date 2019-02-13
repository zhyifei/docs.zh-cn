---
title: Visual Studio Tools for Windows 上的 Docker
description: 初步了解 Visual Studio 2017 版本 15.7 及更高版本中提供的 Docker 工具。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.custom: vs-dotnet
ms.openlocfilehash: a373a8ebfef605b9845a684d3987355f8841aa1b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219537"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="63a5a-103">使用 Visual Studio Tools for Docker (Windows 上的 Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="63a5a-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="63a5a-104">使用 Visual Studio Code 和 Docker CLI 时，Visual Studio Tools for Docker 开发工作流是类似于工作流。</span><span class="sxs-lookup"><span data-stu-id="63a5a-104">The Visual Studio Tools for Docker development workflow is similar to the workflow when using Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="63a5a-105">实际上，它基于相同的 Docker CLI，但它是更轻松地开始，可以简化此过程中，并提供了提高工作效率生成、 运行和组合任务。</span><span class="sxs-lookup"><span data-stu-id="63a5a-105">In fact, it's based on the same Docker CLI, but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="63a5a-106">执行和调试简单的操作，例如通过容器**F5**并**Ctrl**+**F5**。</span><span class="sxs-lookup"><span data-stu-id="63a5a-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span> <span data-ttu-id="63a5a-107">通过可选容器业务流程支持，除了能够运行和调试单个容器，可运行和调试容器 （整个解决方案） 的一组在同一时间。</span><span class="sxs-lookup"><span data-stu-id="63a5a-107">With the optional container orchestration support, in addition to being able to run and debug a single container, you can run and debug a group of containers (a whole solution) at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="63a5a-108">本文适用到 Windows，在 Visual Studio 并不是 Visual Studio for mac。</span><span class="sxs-lookup"><span data-stu-id="63a5a-108">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="63a5a-109">配置在本地环境</span><span class="sxs-lookup"><span data-stu-id="63a5a-109">Configure your local environment</span></span>

<span data-ttu-id="63a5a-110">使用 Docker 的 Windows 的最新版本 ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/))，简单的安装程序可以轻松开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="63a5a-110">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="63a5a-111">Visual Studio 2017 中包括 docker 支持。</span><span class="sxs-lookup"><span data-stu-id="63a5a-111">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="63a5a-112">在此处下载 Visual Studio 2017: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="63a5a-112">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="63a5a-113">在 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="63a5a-113">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="63a5a-114">有两个级别的可以向项目添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="63a5a-114">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="63a5a-115">在.NET Core web 应用程序项目，只是可以添加*Dockerfile*项目，方法是启用 Docker 支持的文件。</span><span class="sxs-lookup"><span data-stu-id="63a5a-115">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="63a5a-116">下一级别是容器业务流程支持，这会增加*Dockerfile*到项目 （如果它尚不存在） 和一个*的 docker-compose.yml*解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="63a5a-116">The next level is container orchestration support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="63a5a-117">默认情况下，在 Visual Studio 2017 版本 15.7 或更早版本中添加容器业务流程支持，通过 Docker Compose。</span><span class="sxs-lookup"><span data-stu-id="63a5a-117">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.7 or earlier.</span></span> <span data-ttu-id="63a5a-118">容器业务流程支持是 Visual Studio 2017 版本 15.8 中选择的功能或更高版本，在这种情况下 Docker Compose 和 Service Fabric 支持。</span><span class="sxs-lookup"><span data-stu-id="63a5a-118">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later, in which case Docker Compose and Service Fabric are supported.</span></span>

<span data-ttu-id="63a5a-119">**外** > **Docker 支持**并**添加** > **容器业务流程支持**命令web 应用程序项目的项目节点的右键单击菜单 （或上下文菜单） 上位于**解决方案资源管理器**中图 4-26 所示：</span><span class="sxs-lookup"><span data-stu-id="63a5a-119">The **Add** > **Docker Support** and **Add** > **Container orchestration Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![在 Visual Studio 中添加 Docker 支持菜单选项](media/add-docker-support-menu.png)

<span data-ttu-id="63a5a-121">图 4-26:向 Visual Studio 2017 项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="63a5a-121">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="63a5a-122">添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="63a5a-122">Add Docker support</span></span>

<span data-ttu-id="63a5a-123">可以通过选择到现有的.NET Core web 应用程序项目添加 Docker 支持**外** > **Docker 支持**中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="63a5a-123">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="63a5a-124">您还可以启用 Docker 支持在项目创建期间通过选择**启用 Docker 支持**中**新的 ASP.NET Core Web 应用程序**在单击后打开的对话框**确定**中**新建项目**对话框中，在图 4-27 所示。</span><span class="sxs-lookup"><span data-stu-id="63a5a-124">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![在 Visual Studio 中的新 ASP.NET Core web 应用的启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="63a5a-126">图 4-27:Visual Studio 2017 中的项目创建过程中启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="63a5a-126">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="63a5a-127">在添加或启用 Docker 支持，Visual Studio 添加*Dockerfile*到项目文件。</span><span class="sxs-lookup"><span data-stu-id="63a5a-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="63a5a-128">启用时 Docker Compose 支持在.NET Framework web 应用程序项目 （不.NET Core web 应用程序项目） 的项目创建期间在图 4-28 所示，还添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="63a5a-128">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestration support is also added.</span></span>
>
> ![启用 Docker compose 支持.NET Framework web 应用程序项目](media/enable-docker-compose-support.png)

> <span data-ttu-id="63a5a-130">图 4 日至 28 日：启用 Visual Studio 2017 中的.NET Framework web 应用项目上的 Docker Compose 支持</span><span class="sxs-lookup"><span data-stu-id="63a5a-130">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="63a5a-131">添加容器业务流程的支持</span><span class="sxs-lookup"><span data-stu-id="63a5a-131">Add container orchestration support</span></span>

<span data-ttu-id="63a5a-132">当你想要编写多容器解决方案时，请向项目添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="63a5a-132">When you want to compose a multicontainer solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="63a5a-133">这样就可以运行和调试容器 （整个解决方案） 的一组在同一时间，如果在同一个定义*docker compose.yml*文件。</span><span class="sxs-lookup"><span data-stu-id="63a5a-133">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="63a5a-134">若要添加容器业务流程支持，请右键单击中的解决方案或项目节点**解决方案资源管理器**，然后选择**添加** > **容器业务流程支持**.</span><span class="sxs-lookup"><span data-stu-id="63a5a-134">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add** > **Container Orchestration Support**.</span></span> <span data-ttu-id="63a5a-135">然后选择**Docker Compose**或**Service Fabric**管理容器。</span><span class="sxs-lookup"><span data-stu-id="63a5a-135">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="63a5a-136">将容器业务流程支持添加到你的项目后，你将看到添加到项目中的 Dockerfile 和一个**docker compose**添加到解决方案中的文件夹**解决方案资源管理器**中图 4-29 所示：</span><span class="sxs-lookup"><span data-stu-id="63a5a-136">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![在解决方案资源管理器在 Visual Studio 中的 docker 文件](media/docker-support-solution-explorer.png)

<span data-ttu-id="63a5a-138">图 4-29:在 Visual Studio 2017 中的解决方案资源管理器中的 docker 文件</span><span class="sxs-lookup"><span data-stu-id="63a5a-138">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="63a5a-139">如果*docker compose.yml*已存在，Visual Studio 只需向其添加的配置代码所需的行。</span><span class="sxs-lookup"><span data-stu-id="63a5a-139">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="63a5a-140">配置 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="63a5a-140">Configure Docker tools</span></span>

<span data-ttu-id="63a5a-141">从主菜单中，选择**工具** > **选项**，然后展开**容器工具** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="63a5a-141">From the main menu, choose **Tools** > **Options**, and expand **Container Tools** > **Settings**.</span></span> <span data-ttu-id="63a5a-142">显示容器工具设置。</span><span class="sxs-lookup"><span data-stu-id="63a5a-142">The container tools settings appear.</span></span>

![](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="63a5a-143">图 4-30:Docker 工具选项</span><span class="sxs-lookup"><span data-stu-id="63a5a-143">Figure 4-30: Docker Tools Options</span></span>

<span data-ttu-id="63a5a-144">下表可能会帮助你决定如何设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="63a5a-144">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="63a5a-145">name</span><span class="sxs-lookup"><span data-stu-id="63a5a-145">Name</span></span> | <span data-ttu-id="63a5a-146">默认设置</span><span class="sxs-lookup"><span data-stu-id="63a5a-146">Default Setting</span></span> | <span data-ttu-id="63a5a-147">适用于</span><span class="sxs-lookup"><span data-stu-id="63a5a-147">Applies To</span></span> | <span data-ttu-id="63a5a-148">描述</span><span class="sxs-lookup"><span data-stu-id="63a5a-148">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="63a5a-149">自动在项目负载上拉取所需的 Docker 图像</span><span class="sxs-lookup"><span data-stu-id="63a5a-149">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="63a5a-150">On</span><span class="sxs-lookup"><span data-stu-id="63a5a-150">On</span></span> | <span data-ttu-id="63a5a-151">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="63a5a-151">Docker Compose</span></span> | <span data-ttu-id="63a5a-152">为了提高性能，加载项目时，Visual Studio 会启动 Docker pull 操作在后台，以便当准备好运行你的代码，该图像已下载或下载过程中。</span><span class="sxs-lookup"><span data-stu-id="63a5a-152">For increased performance, when loading projects, Visual Studio will start a Docker pull operation in the background so that when you are ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="63a5a-153">如果只是加载项目，并浏览代码，您可以关闭此以避免下载不需要的容器映像。</span><span class="sxs-lookup"><span data-stu-id="63a5a-153">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="63a5a-154">在后台自动启动容器</span><span class="sxs-lookup"><span data-stu-id="63a5a-154">Automatically start containers in background</span></span> | <span data-ttu-id="63a5a-155">On</span><span class="sxs-lookup"><span data-stu-id="63a5a-155">On</span></span> | <span data-ttu-id="63a5a-156">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="63a5a-156">Docker Compose</span></span> | <span data-ttu-id="63a5a-157">再次以提高性能，Visual Studio 创建一个容器使用卷装载供当生成并运行你的容器。</span><span class="sxs-lookup"><span data-stu-id="63a5a-157">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="63a5a-158">如果你想要控制创建容器时，关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="63a5a-158">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="63a5a-159">在解决方案上的终止容器自动关闭</span><span class="sxs-lookup"><span data-stu-id="63a5a-159">Automatically kill containers on solution close</span></span> | <span data-ttu-id="63a5a-160">On</span><span class="sxs-lookup"><span data-stu-id="63a5a-160">On</span></span> | <span data-ttu-id="63a5a-161">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="63a5a-161">Docker Compose</span></span> | <span data-ttu-id="63a5a-162">关闭此功能如果您想要为解决方案之后关闭解决方案或关闭 Visual Studio 继续运行的容器。</span><span class="sxs-lookup"><span data-stu-id="63a5a-162">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="63a5a-163">不提示信任 localhost SSL 证书</span><span class="sxs-lookup"><span data-stu-id="63a5a-163">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="63a5a-164">Off</span><span class="sxs-lookup"><span data-stu-id="63a5a-164">Off</span></span> | <span data-ttu-id="63a5a-165">ASP.NET Core 2.1 项目</span><span class="sxs-lookup"><span data-stu-id="63a5a-165">ASP.NET Core 2.1 projects</span></span> | <span data-ttu-id="63a5a-166">如果不信任 localhost SSL 证书，则 Visual Studio 将提示每次运行你的项目，除非选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="63a5a-166">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="63a5a-167">如果 localhost SSL 证书不受信任，并选中复选框后，若要禁止显示提示，然后 HTTPS web 请求可能会在你的应用程序或服务中的运行时失败。</span><span class="sxs-lookup"><span data-stu-id="63a5a-167">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="63a5a-168">在这种情况下，取消选中**不会提示**复选框，会运行你的项目，并指示在提示符下的信任。</span><span class="sxs-lookup"><span data-stu-id="63a5a-168">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

<span data-ttu-id="63a5a-169">**详细信息：** 有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="63a5a-169">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="63a5a-170">生成、 调试、 更新和刷新本地 Docker 容器中的应用： [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="63a5a-170">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="63a5a-171">将 ASP.NET Core Docker 容器部署到容器注册表： [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="63a5a-171">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="63a5a-172">[上一页](docker-apps-inner-loop-workflow.md)
>[下一页](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="63a5a-172">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>