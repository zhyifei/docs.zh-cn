---
title: Visual Studio Tools for Windows 上的 Docker
description: 初步了解 Visual Studio 2017 版本 15.7 及更高版本中提供的 Docker 工具。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 431a0f34ba913c18c35e28ca45660495403bf688
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795539"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="f93be-103">在 Windows 上的 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="f93be-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="f93be-104">开发人员工作流时使用 Docker 工具包含在 Visual Studio 2017 版本 15.7 及更高版本，是类似于使用 Visual Studio Code 和 Docker CLI （实际上，它基于相同的 Docker CLI），但它是更轻松地开始，可以简化过程、 和提供了提高工作效率生成、 运行和组合任务。</span><span class="sxs-lookup"><span data-stu-id="f93be-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="f93be-105">它还可以运行和调试你的容器通过常用`F5`和`Ctrl+F5`Visual Studio 中的密钥。</span><span class="sxs-lookup"><span data-stu-id="f93be-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="f93be-106">如果在同一个定义了其容器，甚至可以调试整个解决方案`docker-compose.yml`解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="f93be-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="f93be-107">配置在本地环境</span><span class="sxs-lookup"><span data-stu-id="f93be-107">Configure your local environment</span></span>

<span data-ttu-id="f93be-108">使用 Docker 的 Windows 的最新版本，它是比以往要开发 Docker 应用程序的以下参考中所述，安装程序非常简单，因为更容易。</span><span class="sxs-lookup"><span data-stu-id="f93be-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="f93be-109">若要了解有关安装 Windows 的 Docker 的详细信息，请转到 (<https://docs.docker.com/docker-for-windows/>)。</span><span class="sxs-lookup"><span data-stu-id="f93be-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="f93be-110">Visual Studio 2017 中的 docker 支持</span><span class="sxs-lookup"><span data-stu-id="f93be-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="f93be-111">有两个级别的可以向项目添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="f93be-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="f93be-112">在 ASP.NET Core 项目中，您可以只需添加`Dockerfile`项目，方法是启用 Docker 支持的文件。</span><span class="sxs-lookup"><span data-stu-id="f93be-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="f93be-113">下一级别是容器业务流程支持，这会增加`Dockerfile`到项目 （如果它尚不存在） 和一个`docker-compose.yml`解决方案级文件。</span><span class="sxs-lookup"><span data-stu-id="f93be-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="f93be-114">默认情况下，在 Visual Studio 2017 版本 15.0 到 15.7 中添加容器业务流程支持，通过 Docker Compose。</span><span class="sxs-lookup"><span data-stu-id="f93be-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="f93be-115">容器业务流程支持是在 Visual Studio 2017 版本 15.8 或更高版本中选择的功能。</span><span class="sxs-lookup"><span data-stu-id="f93be-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="f93be-116">版本 15.8 的更高版本支持 Docker Compose 和 Service Fabric。</span><span class="sxs-lookup"><span data-stu-id="f93be-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="f93be-117">**添加 > Docker 支持**并**添加 > 容器业务流程协调程序支持**命令位于中的 ASP.NET Core 项目的项目节点的右键单击菜单 （或上下文菜单） 上**解决方案资源管理器**，如图 4-31 所示：</span><span class="sxs-lookup"><span data-stu-id="f93be-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio 中的“添加 Docker 支持”菜单选项](./media/add-docker-support-menu.png)

<span data-ttu-id="f93be-119">**图 4-31**。</span><span class="sxs-lookup"><span data-stu-id="f93be-119">**Figure 4-31**.</span></span> <span data-ttu-id="f93be-120">向 Visual Studio 2017 项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="f93be-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="f93be-121">添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="f93be-121">Add Docker support</span></span>

<span data-ttu-id="f93be-122">可以通过选择向现有的 ASP.NET Core 项目添加 Docker 支持**外** > **Docker 支持**中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="f93be-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="f93be-123">您还可以启用 Docker 支持在项目创建期间通过选择**启用 Docker 支持**中**新的 ASP.NET Core Web 应用程序**在单击后打开的对话框**确定**中**新建项目**对话框中，图 4-32 所示。</span><span class="sxs-lookup"><span data-stu-id="f93be-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![在 Visual Studio 中为新的 ASP.NET Core Web 应用启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="f93be-125">**图 4-32**。</span><span class="sxs-lookup"><span data-stu-id="f93be-125">**Figure 4-32**.</span></span> <span data-ttu-id="f93be-126">Visual Studio 2017 中的项目创建过程中启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="f93be-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="f93be-127">在添加或启用 Docker 支持，Visual Studio 添加*Dockerfile*到项目文件。</span><span class="sxs-lookup"><span data-stu-id="f93be-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="f93be-128">图 4-33 所示，可以在 ASP.NET 项目 (.NET Framework，.NET Core 项目) 的项目创建期间启用 Docker Compose 支持，还添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="f93be-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![为 ASP.NET 项目启用 Docker Compose 支持](media/enable-docker-compose-support.png)

<span data-ttu-id="f93be-130">**图 4-33**。</span><span class="sxs-lookup"><span data-stu-id="f93be-130">**Figure 4-33**.</span></span> <span data-ttu-id="f93be-131">在 Visual Studio 2017 中的 ASP.NET 项目的启用 Docker Compose 支持</span><span class="sxs-lookup"><span data-stu-id="f93be-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="f93be-132">添加容器业务流程的支持</span><span class="sxs-lookup"><span data-stu-id="f93be-132">Add container orchestration support</span></span>

<span data-ttu-id="f93be-133">当你想要编写多容器解决方案时，请向项目添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="f93be-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="f93be-134">这样就可以运行和调试容器 （整个解决方案） 的一组在同一时间，如果在同一个定义*docker compose.yml*文件。</span><span class="sxs-lookup"><span data-stu-id="f93be-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="f93be-135">若要添加容器业务流程支持，请右键单击中的解决方案或项目节点**解决方案资源管理器**，然后选择**添加 > 容器业务流程支持**。</span><span class="sxs-lookup"><span data-stu-id="f93be-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="f93be-136">然后选择**Docker Compose**或**Service Fabric**管理容器。</span><span class="sxs-lookup"><span data-stu-id="f93be-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="f93be-137">将容器业务流程支持添加到你的项目后，你将看到添加到项目中的 Dockerfile 和一个**docker compose**添加到解决方案中的文件夹**解决方案资源管理器**，如图 4-34 中所示：</span><span class="sxs-lookup"><span data-stu-id="f93be-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio 解决方案资源管理器中的 Docker 文件](media/docker-support-solution-explorer.png)

<span data-ttu-id="f93be-139">**图 4-34**。</span><span class="sxs-lookup"><span data-stu-id="f93be-139">**Figure 4-34**.</span></span> <span data-ttu-id="f93be-140">在 Visual Studio 2017 中的解决方案资源管理器中的 docker 文件</span><span class="sxs-lookup"><span data-stu-id="f93be-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="f93be-141">如果 docker-compose.yml 已存在，Visual Studio 只需向其添加配置代码所需的行。</span><span class="sxs-lookup"><span data-stu-id="f93be-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="f93be-142">配置 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="f93be-142">Configure Docker tools</span></span>

<span data-ttu-id="f93be-143">从主菜单中，选择**工具 > 选项**，然后展开**容器工具 > 设置**。</span><span class="sxs-lookup"><span data-stu-id="f93be-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="f93be-144">显示容器工具设置。</span><span class="sxs-lookup"><span data-stu-id="f93be-144">The container tools settings appear.</span></span>

![Visual Studio Docker 工具选项，显示：自动拉取所需的 Docker 图像在项目负载上、 在后台自动启动容器、 自动终止上关闭，解决方案的容器和不提示信任 SSL 证书。](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="f93be-146">**图 4-35**。</span><span class="sxs-lookup"><span data-stu-id="f93be-146">**Figure 4-35**.</span></span> <span data-ttu-id="f93be-147">Docker 工具选项</span><span class="sxs-lookup"><span data-stu-id="f93be-147">Docker Tools Options</span></span>

<span data-ttu-id="f93be-148">下表可能会帮助你决定如何设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="f93be-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="f93be-149">名称</span><span class="sxs-lookup"><span data-stu-id="f93be-149">Name</span></span> | <span data-ttu-id="f93be-150">默认设置</span><span class="sxs-lookup"><span data-stu-id="f93be-150">Default Setting</span></span> | <span data-ttu-id="f93be-151">适用于</span><span class="sxs-lookup"><span data-stu-id="f93be-151">Applies To</span></span> | <span data-ttu-id="f93be-152">描述</span><span class="sxs-lookup"><span data-stu-id="f93be-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="f93be-153">自动在项目负载上拉取所需的 Docker 图像</span><span class="sxs-lookup"><span data-stu-id="f93be-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="f93be-154">On</span><span class="sxs-lookup"><span data-stu-id="f93be-154">On</span></span> | <span data-ttu-id="f93be-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="f93be-155">Docker Compose</span></span> | <span data-ttu-id="f93be-156">为了加快运行速度加载项目时，Visual Studio 会启动 Docker pull 操作在后台，以便准备好运行你的代码时，该图像已下载或下载过程中。</span><span class="sxs-lookup"><span data-stu-id="f93be-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="f93be-157">如果只是加载项目，并浏览代码，您可以关闭此以避免下载不需要的容器映像。</span><span class="sxs-lookup"><span data-stu-id="f93be-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="f93be-158">在后台自动启动容器</span><span class="sxs-lookup"><span data-stu-id="f93be-158">Automatically start containers in background</span></span> | <span data-ttu-id="f93be-159">On</span><span class="sxs-lookup"><span data-stu-id="f93be-159">On</span></span> | <span data-ttu-id="f93be-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="f93be-160">Docker Compose</span></span> | <span data-ttu-id="f93be-161">再次以提高性能，Visual Studio 创建一个容器使用卷装载供当生成并运行你的容器。</span><span class="sxs-lookup"><span data-stu-id="f93be-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="f93be-162">如果你想要控制创建容器时，关闭此功能。</span><span class="sxs-lookup"><span data-stu-id="f93be-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="f93be-163">在解决方案上的终止容器自动关闭</span><span class="sxs-lookup"><span data-stu-id="f93be-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="f93be-164">On</span><span class="sxs-lookup"><span data-stu-id="f93be-164">On</span></span> | <span data-ttu-id="f93be-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="f93be-165">Docker Compose</span></span> | <span data-ttu-id="f93be-166">关闭此功能如果您想要为解决方案之后关闭解决方案或关闭 Visual Studio 继续运行的容器。</span><span class="sxs-lookup"><span data-stu-id="f93be-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="f93be-167">不提示信任 localhost SSL 证书</span><span class="sxs-lookup"><span data-stu-id="f93be-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="f93be-168">Off</span><span class="sxs-lookup"><span data-stu-id="f93be-168">Off</span></span> | <span data-ttu-id="f93be-169">ASP.NET Core 2.1 项目</span><span class="sxs-lookup"><span data-stu-id="f93be-169">ASP.NET Core 2.1 projects</span></span> | <span data-ttu-id="f93be-170">如果不信任 localhost SSL 证书，则 Visual Studio 将提示每次运行你的项目，除非选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="f93be-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="f93be-171">如果 localhost SSL 证书不受信任，并选中复选框后，若要禁止显示提示，然后 HTTPS web 请求可能会在你的应用程序或服务中的运行时失败。</span><span class="sxs-lookup"><span data-stu-id="f93be-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="f93be-172">在这种情况下，取消选中**不会提示**复选框，会运行你的项目，并指示在提示符下的信任。</span><span class="sxs-lookup"><span data-stu-id="f93be-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="f93be-173">有关服务实现和使用的 Visual Studio Tools for Docker 的详细信息，请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="f93be-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="f93be-174">在本地 Docker 容器中调试应用程序： <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="f93be-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="f93be-175">将 ASP.NET 容器部署到使用 Visual Studio 的容器注册表： <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="f93be-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f93be-176">[上一页](docker-apps-inner-loop-workflow.md)
>[下一页](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f93be-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
