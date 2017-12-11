---
title: "在 Docker 中运行控制台应用程序"
description: "了解如何利用现有 .NET Framework 控制台应用程序并在 Windows Docker 容器中运行该程序。"
author: spboyer
keywords: ".NET, 容器, 控制台, 应用程序"
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: 037d94452dd62c06fe6d8ac7aea1143f52b96d32
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="running-console-applications-in-windows-containers"></a><span data-ttu-id="9bc7c-104">在 Windows 容器中运行控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="9bc7c-104">Running console applications in Windows containers</span></span>

<span data-ttu-id="9bc7c-105">控制台应用程序具有多种用途；从简单的状态查询到长时间运行的文档图像处理任务。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-105">Console applications are used for many purposes; from simple querying of a status to long running document image processing tasks.</span></span> <span data-ttu-id="9bc7c-106">在任何情况下，启动和缩放这些应用程序的能力始终在硬件购置、启动时间或运行多个实例方面受限。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-106">In any case, the ability to start up and scale these applications are met with limitations of hardware acquisitions, startup times or running multiple instances.</span></span>

<span data-ttu-id="9bc7c-107">通过移动控制台应用程序以使用 Docker 和 Windows Server 容器，可以从干净状态启动这些应用程序，使其执行操作，然后完全关闭该程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-107">Moving your console applications to use Docker and Windows Server containers allows for starting these applications from a clean state, enabling them to perform the operation and then shutdown cleanly.</span></span> <span data-ttu-id="9bc7c-108">本主题将演示将控制台应用程序移动到基于 Windows 的容器并使用 PowerShell 脚本启动该程序所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-108">This topic will show the steps needed to move a console application to a Windows based container and start it using a PowerShell script.</span></span>

<span data-ttu-id="9bc7c-109">本示例控制台应用程序是一个简单示例，其中具有一个参数、一个此情况下的问题，并返回随机答案。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-109">The sample console application is a simple example which takes an argument, a question in this case, and returns a random answer.</span></span> <span data-ttu-id="9bc7c-110">这可能需要 `customer_id` 并处理他们的税款，或创建 `image_url` 参数的缩略图。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-110">This could take a `customer_id` and process their taxes, or create a thumbnail for an `image_url` argument.</span></span>

<span data-ttu-id="9bc7c-111">除答案外，已将 `Environment.MachineName` 添加到响应中，以显示在本地与在 Windows 容器中运行该应用程序的区别。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-111">In addition to the answer, the `Environment.MachineName` has been added to the response to show the difference between running the application locally and in a Windows container.</span></span> <span data-ttu-id="9bc7c-112">本地运行应用程序时，会返回本地计算机名称；在 Windows 容器中运行该应用程序时，则会返回容器会话 ID。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-112">When running the application locally, your local machine name should be returned and when running in a Windows Container; the container session id is returned.</span></span>

<span data-ttu-id="9bc7c-113">[完整示例](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator)位于 GitHub 上的 dotnet/docs 存储库中。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-113">The [complete example](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator) is available in the dotnet/docs repository on GitHub.</span></span> <span data-ttu-id="9bc7c-114">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-114">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="9bc7c-115">开始着手将应用程序移动到容器之前，需要熟悉某些 Docker 术语。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-115">You need to be familiar with some Docker terms before you begin working on moving your application to a container.</span></span>

> <span data-ttu-id="9bc7c-116">Docker 映像是用于定义运行中容器的环境（包括操作系统 (OS)、系统组件和应用程序）的只读模板。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-116">A *Docker image* is a read-only template that defines the environment for a running container, including the operating system (OS), system components, and application(s).</span></span>

<span data-ttu-id="9bc7c-117">Docker 映像的一个重要特性是映像由基本映像组合而成。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-117">One important feature of Docker images is that images are composed from a base image.</span></span> <span data-ttu-id="9bc7c-118">每个新映像均会向现有映像添加小部分功能。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-118">Each new image adds a small set of features to an existing image.</span></span> 

> <span data-ttu-id="9bc7c-119">Docker 容器是映像的运行实例。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-119">A *Docker container* is a running instance of an image.</span></span> 

<span data-ttu-id="9bc7c-120">通过在多个容器中运行同一映像来缩放应用程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-120">You scale an application by running the same image in many containers.</span></span>
<span data-ttu-id="9bc7c-121">从概念上讲，这类似于在多个主机中运行同一应用程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-121">Conceptually, this is similar to running the same application in multiple hosts.</span></span>

<span data-ttu-id="9bc7c-122">有关 Docker 体系结构的详细信息，请参阅 Docker 站点上的 [Docker 概述](https://docs.docker.com/engine/understanding-docker/)。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-122">You can learn more about the Docker architecture by reading the [Docker Overview](https://docs.docker.com/engine/understanding-docker/) on the Docker site.</span></span> 

<span data-ttu-id="9bc7c-123">移动控制台应用程序只需几个步骤。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-123">Moving your console application is a matter of a few steps.</span></span>

1. [<span data-ttu-id="9bc7c-124">生成应用程序</span><span class="sxs-lookup"><span data-stu-id="9bc7c-124">Build the application</span></span>](#building-the-application)
1. [<span data-ttu-id="9bc7c-125">创建映像的 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="9bc7c-125">Creating a Dockerfile for the image</span></span>](#creating-the-dockerfile)
1. [<span data-ttu-id="9bc7c-126">生成并运行 Docker 容器的过程</span><span class="sxs-lookup"><span data-stu-id="9bc7c-126">Process to build and run the Docker container</span></span>](#creating-the-image)

## <a name="prerequisites"></a><span data-ttu-id="9bc7c-127">先决条件</span><span class="sxs-lookup"><span data-stu-id="9bc7c-127">Prerequisites</span></span>
<span data-ttu-id="9bc7c-128">[Windows 10 周年更新](https://www.microsoft.com/en-us/software-download/windows10/) 或 [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server) 支持 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-128">Windows containers are supported on [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) or [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span></span>

> [!NOTE]
><span data-ttu-id="9bc7c-129">如果使用 Windows Server 2016，则需手动启用容器，因为 Docker for Windows 安装程序不会启用该功能。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-129">If you are using Windows Server 2016, you must enable containers manually since the Docker for Windows installer will not enable the feature.</span></span> <span data-ttu-id="9bc7c-130">请确保已为操作系统运行所有更新，然后按照[容器主机部署](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment)文章中的说明来安装容器和 Docker 功能。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-130">Make sure all updates have run for the OS and then follow the instructions from the [Container Host Deployment](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) article to install the containers and Docker features.</span></span>

<span data-ttu-id="9bc7c-131">需要安装 Docker for Windows 1.12 Beta 26 版或更高版本才能支持 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-131">You need to have Docker for Windows, version 1.12 Beta 26 or higher to support Windows containers.</span></span> <span data-ttu-id="9bc7c-132">默认情况下，Docker 支持将基于 Linux 的容器切换到 Windows 容器，通过右键单击系统托盘中的 Docker 图标，然后选择“切换到 Windows 容器”。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-132">By default, Docker enables Linux based containers; switch to Windows containers by right clicking the Docker icon in the system tray and select **Switch to Windows containers**.</span></span> <span data-ttu-id="9bc7c-133">Docker 将运行该过程进行更改，且可能需要重启。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-133">Docker will run the process to change and a restart may be required.</span></span>

![Windows 容器](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a><span data-ttu-id="9bc7c-135">生成应用程序</span><span class="sxs-lookup"><span data-stu-id="9bc7c-135">Building the application</span></span>
<span data-ttu-id="9bc7c-136">通常，通过安装程序、FTP 或文件共享部署分配控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-136">Typically console applications are distributed through an installer, FTP, or File Share deployment.</span></span> <span data-ttu-id="9bc7c-137">部署到容器时，需要编译资产并将其暂存到创建 Docker 映像时可以使用的位置。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-137">When deploying to a container, the assets need to be compiled and staged to a location that can be used when the Docker image is created.</span></span>

<span data-ttu-id="9bc7c-138">在 *build.ps1* 中，脚本使用 [MSBuild](/visualstudio/msbuild/msbuild) 编译应用程序以完成生成资产的任务。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-138">In *build.ps1*, the script uses [MSBuild](/visualstudio/msbuild/msbuild) to compile the application to complete the task of building the assets.</span></span> <span data-ttu-id="9bc7c-139">有几个传递到 MSBuild 来完成所需资产的参数。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-139">There are a few parameters passed to MSBuild to finalize the needed assets.</span></span> <span data-ttu-id="9bc7c-140">要编译的项目文件或解决方案的名称、输出位置，最后是配置（版本或调试）。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-140">The name of the project file or solution to be compiled, the location for the output and finally the configuration (Release or Debug).</span></span>

<span data-ttu-id="9bc7c-141">在对 `Invoke-MSBuild` 的调用中，将 `OutputPath` 设置为 **Publish**，`Configuration` 设置为 **Release**。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-141">In the call to `Invoke-MSBuild` the `OutputPath` is set to **publish** and  `Configuration` set to **Release**.</span></span> 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj /p:OutputPath=.\publish /p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a><span data-ttu-id="9bc7c-142">创建 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="9bc7c-142">Creating the Dockerfile</span></span>
<span data-ttu-id="9bc7c-143">用于控制台 .NET Framework 应用程序的基本映像是 [Docker 中心](https://hub.docker.com/r/microsoft/windowsservercore/)上正式推出的 `microsoft/windowsservercore`。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-143">The base image used for a console .NET Framework application is `microsoft/windowsservercore`, publicly available on [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span></span> <span data-ttu-id="9bc7c-144">该基本映像包含 Windows Server 2016、.NET Framework 4.6.2 的最小安装，并充当 Windows 容器的基本 OS 映像。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-144">The base image contains a minimal installation of Windows Server 2016, .NET Framework 4.6.2 and serves as the base OS image for Windows Containers.</span></span>

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
<span data-ttu-id="9bc7c-145">Dockerfile 中的首行使用 [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) 指令指定基本映像。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-145">The first line in the Dockerfile designates the base image using the [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) instruction.</span></span> <span data-ttu-id="9bc7c-146">接下来，文件中的 [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) 将应用程序资产从 **publish** 文件夹复制到容器的根文件夹；最后，设置映像的 [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint)，表明这是将在容器启动时运行的命令或应用程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-146">Next, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in the file copies the application assets from the **publish** folder to root folder of the container and last; setting the [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) of the image states that this is the command or application that will run when the container starts.</span></span> 

## <a name="creating-the-image"></a><span data-ttu-id="9bc7c-147">创建映像</span><span class="sxs-lookup"><span data-stu-id="9bc7c-147">Creating the image</span></span>
<span data-ttu-id="9bc7c-148">为创建 Docker 映像，将以下代码添加到 *build.ps1* 脚本。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-148">In order to create the Docker image, the following code is added to the *build.ps1* script.</span></span> <span data-ttu-id="9bc7c-149">运行脚本时，使用从 MSBuild（在[生成应用程序](#building-the-application)部分定义）编译的资产创建 `console-random-answer-generator` 映像。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-149">When the script is run, the `console-random-answer-generator` image is created using the assets compiled from MSBuild defined in the [Building the application](#building-the-application) section.</span></span>

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

<span data-ttu-id="9bc7c-150">使用 PowerShell 命令提示符中的 `.\build.ps1` 运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-150">Run the script using `.\build.ps1` from the PowerShell command prompt.</span></span>

<span data-ttu-id="9bc7c-151">生成完成后，使用命令行或 PowerShell 提示符中的 `docker images` 命令，可以看到已创建该映像并可随时运行。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-151">When the build is complete, using the `docker images` command from a command line or PowerShell prompt; you'll see that the image is created and ready to be run.</span></span>

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a><span data-ttu-id="9bc7c-152">运行容器</span><span class="sxs-lookup"><span data-stu-id="9bc7c-152">Running the container</span></span>
<span data-ttu-id="9bc7c-153">可以使用 Docker 命令从命令行启动该容器。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-153">You can start the container from the command line using the Docker commands.</span></span>

```
docker run console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="9bc7c-154">输出为</span><span class="sxs-lookup"><span data-stu-id="9bc7c-154">The output is</span></span>

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

<span data-ttu-id="9bc7c-155">如果从 PowerShell 运行 `docker ps -a` 命令，则可以看到该容器仍然存在。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-155">If you run the `docker ps -a` command from PowerShell, you can see that the container still exists.</span></span>

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

<span data-ttu-id="9bc7c-156">STATUS 列显示“大约 1 分钟前”，已完成并可关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-156">The STATUS column shows at "About a minute ago", the application was complete and could be shut down.</span></span> <span data-ttu-id="9bc7c-157">如果该命令运行了一百次，则会存在一百个无工作的静态容器。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-157">If the command was run a hundred times, there would be a hundred containers left static with no work to do.</span></span> <span data-ttu-id="9bc7c-158">开始时，理想操作是完成工作并关闭或清理程序。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-158">In the beginning scenario the ideal operation was to do the work and shutdown or cleanup.</span></span> <span data-ttu-id="9bc7c-159">若要完成该工作流，将 `--rm` 选项添加到 `docker run` 命令会在收到 `Exited` 信号后立即删除该容器。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-159">To accomplish that workflow, adding the `--rm` option to the `docker run` command will remove the container as soon as the `Exited` signal is received.</span></span>

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="9bc7c-160">运行带有此选项的命令，然后查看 `docker ps -a` 命令的输出；请注意，容器 ID (`Environment.MachineName`) 不在列表中。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-160">Running the command with this option and then looking at the output of `docker ps -a` command; notice that the container id (the `Environment.MachineName`) is not in the list.</span></span>

### <a name="running-the-container-using-powershell"></a><span data-ttu-id="9bc7c-161">使用 PowerShell 运行容器</span><span class="sxs-lookup"><span data-stu-id="9bc7c-161">Running the container using PowerShell</span></span>
<span data-ttu-id="9bc7c-162">示例项目文件中还包含 *run.ps1*，这是如何使用 PowerShell 来运行接受参数的应用程序的示例。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-162">In the sample project files there is also a *run.ps1* which is an example of how to use PowerShell to run the application accepting the arguments.</span></span>

<span data-ttu-id="9bc7c-163">若要运行，请打开 PowerShell，然后使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="9bc7c-163">To run, open PowerShell and use the following command:</span></span>

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a><span data-ttu-id="9bc7c-164">摘要</span><span class="sxs-lookup"><span data-stu-id="9bc7c-164">Summary</span></span>
<span data-ttu-id="9bc7c-165">无需对应用程序代码进行任何更改，只需通过添加 Dockerfile 并发布应用程序，即可容器化 .NET Framework 控制台应用程序、立即利用运行多个实例的优势、洁净启动和停止，以及使用更多 Windows Server 2016 功能。</span><span class="sxs-lookup"><span data-stu-id="9bc7c-165">Just by adding a Dockerfile and publishing the application, you can containerize your .NET Framework console applications and now take the advantage of running multiple instances, clean start and stop and more Windows Server 2016 capabilities without making any changes to the application code at all.</span></span>
