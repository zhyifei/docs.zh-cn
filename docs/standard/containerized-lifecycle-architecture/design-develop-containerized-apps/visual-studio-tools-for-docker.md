---
title: Windows 上的 Visual Studio Tools for Docker
description: 了解 Visual Studio 2017 15.7 版及更高版本中可用的 Docker 工具。
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644653"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a><span data-ttu-id="9418a-103">在 Windows 上的 Visual Studio 2017 中使用 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="9418a-103">Use Docker Tools in Visual Studio 2017 on Windows</span></span>

<span data-ttu-id="9418a-104">使用 Visual Studio 2017 15.7 版及更高版本中附带的 Docker 工具的开发人员工作流与使用 Visual Studio Code 和 Docker CLI（事实上，它在同一 Docker CLI 基础上构建）类似，但前者更容易上手，因为它简化了流程并提高了构建、运行和创建任务的工作效率。</span><span class="sxs-lookup"><span data-stu-id="9418a-104">The developer workflow when using the Docker Tools included in Visual Studio 2017 version 15.7 and later, is similar to using Visual Studio Code and Docker CLI (in fact, it's based on the same Docker CLI), but it's easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="9418a-105">还可以通过 Visual Studio 中常用的 `F5` 和 `Ctrl+F5` 键运行和调试容器。</span><span class="sxs-lookup"><span data-stu-id="9418a-105">It can also run and debug your containers via the usual `F5` and `Ctrl+F5` keys from Visual Studio.</span></span> <span data-ttu-id="9418a-106">如果在解决方案级别的同一 `docker-compose.yml` 文件中定义其容器，甚至可以调试整个解决方案。</span><span class="sxs-lookup"><span data-stu-id="9418a-106">You can even debug a whole solution if its containers are defined in the same `docker-compose.yml` file at the solution level.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="9418a-107">配置本地环境</span><span class="sxs-lookup"><span data-stu-id="9418a-107">Configure your local environment</span></span>

<span data-ttu-id="9418a-108">使用最新版本的用于 Windows 的 Docker，开发 Docker 应用程序容易得多，因为设置非常简单，如以下参考资料中所述。</span><span class="sxs-lookup"><span data-stu-id="9418a-108">With the latest versions of Docker for Windows, it's easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

> [!TIP]
> <span data-ttu-id="9418a-109">要了解有关安装用于 Windows 的 Docker 的详细信息，请转到 (<https://docs.docker.com/docker-for-windows/>)。</span><span class="sxs-lookup"><span data-stu-id="9418a-109">To learn more about installing Docker for Windows, go to (<https://docs.docker.com/docker-for-windows/>).</span></span>

## <a name="docker-support-in-visual-studio-2017"></a><span data-ttu-id="9418a-110">Visual Studio 2017 中的 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="9418a-110">Docker support in Visual Studio 2017</span></span>

<span data-ttu-id="9418a-111">可以将两个级别的 Docker 支持添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="9418a-111">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="9418a-112">在 ASP.NET Core 项目中，启用 Docker 支持，即可将 `Dockerfile` 文件添加项目中。</span><span class="sxs-lookup"><span data-stu-id="9418a-112">In ASP.NET Core projects, you can just add a `Dockerfile` file to the project by enabling Docker support.</span></span> <span data-ttu-id="9418a-113">下一级是容器业务流程支持，它会向项目添加解决方案级别的 `Dockerfile`（如果它尚不存在）和 `docker-compose.yml` 文件。</span><span class="sxs-lookup"><span data-stu-id="9418a-113">The next level is container orchestration support, which adds a `Dockerfile` to the project (if it doesn't already exist) and a `docker-compose.yml` file at the solution level.</span></span> <span data-ttu-id="9418a-114">默认情况下，在 Visual Studio 2017 15.0 到 15.7 版中添加了通过 Docker Compose 支持的容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="9418a-114">Container orchestration support, via Docker Compose, is added by default in Visual Studio 2017 versions 15.0 to 15.7.</span></span> <span data-ttu-id="9418a-115">容器业务流程支持是 Visual Studio 2017 15.8 版或更高版本中的一个可选功能。</span><span class="sxs-lookup"><span data-stu-id="9418a-115">Container orchestration support is an opt-in feature in Visual Studio 2017 versions 15.8 or later.</span></span> <span data-ttu-id="9418a-116">15.8 版及更高版本支持 Docker Compose 和 Service Fabric。</span><span class="sxs-lookup"><span data-stu-id="9418a-116">Version 15.8 an later support Docker Compose and Service Fabric.</span></span>

<span data-ttu-id="9418a-117">“添加”>“Docker 支持”和“添加”>“容器业务流程协调程序支持”命令位于“解决方案资源管理器”中 ASP.NET Core 项目的项目节点的右键单击菜单（或上下文菜单）上，如图 4-31 所示    ：</span><span class="sxs-lookup"><span data-stu-id="9418a-117">The **Add > Docker Support** and **Add > Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for an ASP.NET Core project in **Solution Explorer**, as shown in Figure 4-31:</span></span>

![Visual Studio 中的“添加 Docker 支持”菜单选项](./media/add-docker-support-menu.png)

<span data-ttu-id="9418a-119">**图 4-31**。</span><span class="sxs-lookup"><span data-stu-id="9418a-119">**Figure 4-31**.</span></span> <span data-ttu-id="9418a-120">向 Visual Studio 2017 项目添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="9418a-120">Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="9418a-121">添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="9418a-121">Add Docker support</span></span>

<span data-ttu-id="9418a-122">在“解决方案资源管理器”中选择“添加” > “Docker 支持”，即可向现有 ASP.NET Core 项目添加 Docker 支持    。</span><span class="sxs-lookup"><span data-stu-id="9418a-122">You can add Docker support to an existing ASP.NET Core project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="9418a-123">在项目创建期间，在“新建项目”对话框中单击“确定”后打开的“新建 ASP.NET Core Web 应用程序”对话框中选择“启用 Docker 支持”，也可以启用 Docker 支持（如图 4-32 所示）     。</span><span class="sxs-lookup"><span data-stu-id="9418a-123">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-32.</span></span>

![在 Visual Studio 中为新的 ASP.NET Core Web 应用启用 Docker 支持](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="9418a-125">**图 4-32**。</span><span class="sxs-lookup"><span data-stu-id="9418a-125">**Figure 4-32**.</span></span> <span data-ttu-id="9418a-126">在 Visual Studio 2017 中创建项目期间启用 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="9418a-126">Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="9418a-127">添加或启用 Docker 支持时，Visual Studio 会向项目添加 Dockerfile 文件  。</span><span class="sxs-lookup"><span data-stu-id="9418a-127">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="9418a-128">如图 4-33 所示，在项目创建期间为 ASP.NET 项目（.NET Framework，而不是 .NET Core 项目）启用 Docker Compose 支持时，还会添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="9418a-128">When you enable Docker Compose support during project creation for a ASP.NET project (.NET Framework, not a .NET Core project) as shown in Figure 4-33, container orchestration support is also added.</span></span>

![为 ASP.NET 项目启用 Docker Compose 支持](media/enable-docker-compose-support.png)

<span data-ttu-id="9418a-130">**图 4-33**。</span><span class="sxs-lookup"><span data-stu-id="9418a-130">**Figure 4-33**.</span></span> <span data-ttu-id="9418a-131">为 Visual Studio 2017 中的 ASP.NET 项目启用 Docker Compose 支持</span><span class="sxs-lookup"><span data-stu-id="9418a-131">Enabling Docker Compose support for an ASP.NET project in Visual Studio 2017</span></span>

### <a name="add-container-orchestration-support"></a><span data-ttu-id="9418a-132">添加容器业务流程支持</span><span class="sxs-lookup"><span data-stu-id="9418a-132">Add container orchestration support</span></span>

<span data-ttu-id="9418a-133">想要构建多容器解决方案时，请为项目添加容器业务流程支持。</span><span class="sxs-lookup"><span data-stu-id="9418a-133">When you want to compose a multi-container solution, add container orchestration support to your projects.</span></span> <span data-ttu-id="9418a-134">这样就可以同时运行和调试一组容器（整个解决方案）（如果已在同一个 docker-compose.yml 文件中定义这些容器  ）。</span><span class="sxs-lookup"><span data-stu-id="9418a-134">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span>

<span data-ttu-id="9418a-135">要添加容器业务流程支持，请右键单击“解决方案资源管理器”中的解决方案或项目节点，然后选择“添加”>“容器业务流程支持”   。</span><span class="sxs-lookup"><span data-stu-id="9418a-135">To add container orchestration support, right-click on the solution or project node in **Solution Explorer**, and choose **Add > Container Orchestration Support**.</span></span> <span data-ttu-id="9418a-136">然后，选择“Docker Compose”或“Service Fabric”以管理容器   。</span><span class="sxs-lookup"><span data-stu-id="9418a-136">Then choose **Docker Compose** or **Service Fabric** to manage the containers.</span></span>

<span data-ttu-id="9418a-137">向项目添加容器业务流程支持后，会看到添加到项目的 Dockerfile 文件以及添加到“解决方案资源管理器”中的某个解决方案的 docker-compose 文件夹，如图 4-34 所示   ：</span><span class="sxs-lookup"><span data-stu-id="9418a-137">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-34:</span></span>

![Visual Studio 解决方案资源管理器中的 Docker 文件](media/docker-support-solution-explorer.png)

<span data-ttu-id="9418a-139">**图 4-34**。</span><span class="sxs-lookup"><span data-stu-id="9418a-139">**Figure 4-34**.</span></span> <span data-ttu-id="9418a-140">Visual Studio 2017 解决方案资源管理器中的 Docker 文件</span><span class="sxs-lookup"><span data-stu-id="9418a-140">Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="9418a-141">如果 docker-compose.yml  已存在，Visual Studio 只需向其添加配置代码所需的行。</span><span class="sxs-lookup"><span data-stu-id="9418a-141">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

## <a name="configure-docker-tools"></a><span data-ttu-id="9418a-142">配置 Docker 工具</span><span class="sxs-lookup"><span data-stu-id="9418a-142">Configure Docker tools</span></span>

<span data-ttu-id="9418a-143">从主菜单中，选择“工具”>“选项”，然后展开“容器工具”>“设置”   。</span><span class="sxs-lookup"><span data-stu-id="9418a-143">From the main menu, choose **Tools > Options**, and expand **Container Tools > Settings**.</span></span> <span data-ttu-id="9418a-144">随即出现容器工具设置。</span><span class="sxs-lookup"><span data-stu-id="9418a-144">The container tools settings appear.</span></span>

![Visual Studio Docker 工具选项包括：“在项目加载时自动拉取所需的 Docker 映像”、“在后台自动启动容器”、“在解决方案关闭时自动终止容器”以及“不提示需要信任 SSL 证书”。](./media/visual-studio-docker-tools-options.png)

<span data-ttu-id="9418a-146">**图 4-35**。</span><span class="sxs-lookup"><span data-stu-id="9418a-146">**Figure 4-35**.</span></span> <span data-ttu-id="9418a-147">Docker 工具选项</span><span class="sxs-lookup"><span data-stu-id="9418a-147">Docker Tools Options</span></span>

<span data-ttu-id="9418a-148">下表可帮助确定如何设置这些选项。</span><span class="sxs-lookup"><span data-stu-id="9418a-148">The following table might help you decide how to set these options.</span></span>

| <span data-ttu-id="9418a-149">name</span><span class="sxs-lookup"><span data-stu-id="9418a-149">Name</span></span> | <span data-ttu-id="9418a-150">默认设置</span><span class="sxs-lookup"><span data-stu-id="9418a-150">Default Setting</span></span> | <span data-ttu-id="9418a-151">适用于</span><span class="sxs-lookup"><span data-stu-id="9418a-151">Applies To</span></span> | <span data-ttu-id="9418a-152">说明</span><span class="sxs-lookup"><span data-stu-id="9418a-152">Description</span></span> |
| -----|:---------------:|:----------:| ----------- |
| <span data-ttu-id="9418a-153">在项目加载时自动拉取所需的 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="9418a-153">Automatically pull required Docker images on project load</span></span> | <span data-ttu-id="9418a-154">On</span><span class="sxs-lookup"><span data-stu-id="9418a-154">On</span></span> | <span data-ttu-id="9418a-155">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="9418a-155">Docker Compose</span></span> | <span data-ttu-id="9418a-156">为了在加载项目时提高性能，Visual Studio 将在后台启动 Docker 拉取操作，以便在准备好运行代码时，映像已下载或正在下载。</span><span class="sxs-lookup"><span data-stu-id="9418a-156">For increased performance when loading projects, Visual Studio will start a Docker pull operation in the background so that when you're ready to run your code, the image is already downloaded or in the process of downloading.</span></span> <span data-ttu-id="9418a-157">如果只需加载项目和浏览代码，可以将其关闭，以避免下载不需要的容器映像。</span><span class="sxs-lookup"><span data-stu-id="9418a-157">If you're just loading projects and browsing code, you can turn this off to avoid downloading container images you don't need.</span></span> |
| <span data-ttu-id="9418a-158">在后台自动启动容器</span><span class="sxs-lookup"><span data-stu-id="9418a-158">Automatically start containers in background</span></span> | <span data-ttu-id="9418a-159">On</span><span class="sxs-lookup"><span data-stu-id="9418a-159">On</span></span> | <span data-ttu-id="9418a-160">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="9418a-160">Docker Compose</span></span> | <span data-ttu-id="9418a-161">同样，为了提高性能，Visual Studio 会在构建和运行容器时创建卷装载随时可用的容器。</span><span class="sxs-lookup"><span data-stu-id="9418a-161">Again for increased performance, Visual Studio creates a container with volume mounts ready for when you build and run your container.</span></span> <span data-ttu-id="9418a-162">如果要控制创建容器的时间，请将其关闭。</span><span class="sxs-lookup"><span data-stu-id="9418a-162">If you want to control when your container is created, turn this off.</span></span> |
| <span data-ttu-id="9418a-163">在解决方案关闭时自动终止容器</span><span class="sxs-lookup"><span data-stu-id="9418a-163">Automatically kill containers on solution close</span></span> | <span data-ttu-id="9418a-164">On</span><span class="sxs-lookup"><span data-stu-id="9418a-164">On</span></span> | <span data-ttu-id="9418a-165">Docker Compose</span><span class="sxs-lookup"><span data-stu-id="9418a-165">Docker Compose</span></span> | <span data-ttu-id="9418a-166">如果希望解决方案的容器在关闭解决方案或关闭 Visual Studio 后继续运行，请将其关闭。</span><span class="sxs-lookup"><span data-stu-id="9418a-166">Turn this off if you would like containers for your solution to continue to run after closing the solution or closing Visual Studio.</span></span> |
| <span data-ttu-id="9418a-167">不提示需要信任 localhost SSL 证书</span><span class="sxs-lookup"><span data-stu-id="9418a-167">Do not prompt for trusting localhost SSL certificate</span></span> | <span data-ttu-id="9418a-168">Off</span><span class="sxs-lookup"><span data-stu-id="9418a-168">Off</span></span> | <span data-ttu-id="9418a-169">ASP.NET Core 2.2 项目</span><span class="sxs-lookup"><span data-stu-id="9418a-169">ASP.NET Core 2.2 projects</span></span> | <span data-ttu-id="9418a-170">如果 localhost SSL 证书不受信任，则每次运行项目时 Visual Studio 都会提示，除非选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9418a-170">If the localhost SSL certificate is not trusted, Visual Studio will prompt every time you run your project, unless this checkbox is checked.</span></span> |

> [!WARNING]
> <span data-ttu-id="9418a-171">如果 localhost SSL 证书不受信任且选中该框以禁止出现提示，则 HTTPS Web 请求可能会在应用或服务中在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="9418a-171">If the localhost SSL certificate is not trusted, and you check the box to suppress prompting, then HTTPS web requests might fail at runtime in your app or service.</span></span> <span data-ttu-id="9418a-172">在这种情况下，请取消选中“不提示”复选框，运行项目并在提示时指示信任  。</span><span class="sxs-lookup"><span data-stu-id="9418a-172">In that case, uncheck the **Do not prompt** checkbox, run your project, and indicate trust at the prompt.</span></span>

> [!TIP]
> <span data-ttu-id="9418a-173">有关服务实现以及 Visual Studio Tools for Docker 用法的更多详细信息，请阅读以下文章：</span><span class="sxs-lookup"><span data-stu-id="9418a-173">For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>
>
><span data-ttu-id="9418a-174">在本地 Docker 容器中调试应用：<https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span><span class="sxs-lookup"><span data-stu-id="9418a-174">Debugging apps in a local Docker container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh></span></span>
>
><span data-ttu-id="9418a-175">使用 Visual Studio 将 ASP.NET 容器部署到容器注册表：<https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span><span class="sxs-lookup"><span data-stu-id="9418a-175">Deploy an ASP.NET container to a container registry using Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9418a-176">[上一页](docker-apps-inner-loop-workflow.md)
>[下一页](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9418a-176">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>
