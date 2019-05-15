---
title: Docker 应用的内部循环开发工作流
description: 了解开发 Docker 应用程序的"内部循环"工作流。
ms.date: 02/15/2019
ms.openlocfilehash: ce573546f61b98c2f93e998203497fa949e9efe8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644858"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="1c601-103">Docker 应用的内部循环开发工作流</span><span class="sxs-lookup"><span data-stu-id="1c601-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="1c601-104">触发跨越整个 DevOps 的外部循环工作流之前循环，开始整个过程的每个开发人员的计算机上，应用本身进行编码、 使用其首选的语言或平台，以及本地测试 (图 4-21)。</span><span class="sxs-lookup"><span data-stu-id="1c601-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="1c601-105">但在所有情况下，您必须很重要的一点共同点，无论选择何种语言、 框架或平台。</span><span class="sxs-lookup"><span data-stu-id="1c601-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="1c601-106">在此特定的工作流，你始终在开发和测试 Docker 容器，但却在本地。</span><span class="sxs-lookup"><span data-stu-id="1c601-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![步骤 1-代码/运行/调试](./media/image18.png)

<span data-ttu-id="1c601-108">图 4-21。</span><span class="sxs-lookup"><span data-stu-id="1c601-108">**Figure 4-21**.</span></span> <span data-ttu-id="1c601-109">内部循环开发上下文</span><span class="sxs-lookup"><span data-stu-id="1c601-109">Inner-loop development context</span></span>

<span data-ttu-id="1c601-110">容器或 Docker 映像的实例将包含这些组件：</span><span class="sxs-lookup"><span data-stu-id="1c601-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="1c601-111">选择 （例如，Linux 分发版或 Windows） 的操作系统</span><span class="sxs-lookup"><span data-stu-id="1c601-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="1c601-112">由开发人员 （例如，应用程序二进制文件） 添加的文件</span><span class="sxs-lookup"><span data-stu-id="1c601-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="1c601-113">配置 （例如，环境设置和依赖项）</span><span class="sxs-lookup"><span data-stu-id="1c601-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="1c601-114">哪些过程操作即可运行 Docker 的说明</span><span class="sxs-lookup"><span data-stu-id="1c601-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="1c601-115">您可以将设置为 （下一节中所述） 的过程中使用 Docker 的内部循环开发工作流。</span><span class="sxs-lookup"><span data-stu-id="1c601-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="1c601-116">考虑设置环境的初始步骤不包括在内，因为只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="1c601-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="1c601-117">构建单个应用程序中使用 Visual Studio Code 和 Docker CLI 的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="1c601-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="1c601-118">应用是从你自己的服务和附加库 （依赖项） 组成。</span><span class="sxs-lookup"><span data-stu-id="1c601-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="1c601-119">图 4-22 显示了通常需要构建 Docker 应用程序后, 跟每个步骤的详细说明时要执行的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="1c601-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![工作流概述：步骤 1-代码中，第 2 步-编写 Dockerfile，第 3 步-创建映像的 Dockerfile，步骤 4 中使用定义-使用 docker-compose 文件，步骤 5-运行容器定义的服务或组合式的应用，第 6 步-测试应用程序，第 7 步-推送开始外部循环 （CI/CD 管道），或继续 developing。](./media/image19.png)

<span data-ttu-id="1c601-121">**图 4-22**。</span><span class="sxs-lookup"><span data-stu-id="1c601-121">**Figure 4-22**.</span></span> <span data-ttu-id="1c601-122">使用 Docker CLI 适用于容器化 Docker 应用程序生命周期的高级工作流</span><span class="sxs-lookup"><span data-stu-id="1c601-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="1c601-123">步骤 1：开始在 Visual Studio Code 中编写代码并创建初始应用/服务基线</span><span class="sxs-lookup"><span data-stu-id="1c601-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="1c601-124">开发应用程序的方法是执行不带 Docker 的方式类似。</span><span class="sxs-lookup"><span data-stu-id="1c601-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="1c601-125">不同之处是，在开发时，你在部署和测试应用程序或服务 （如 Windows 或 Linux VM） 在本地环境中放置的 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="1c601-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="1c601-126">**设置本地环境**</span><span class="sxs-lookup"><span data-stu-id="1c601-126">**Setting up your local environment**</span></span>

<span data-ttu-id="1c601-127">使用适用于 Mac 和 Windows 的 Docker 的最新版本，比以往要开发 Docker 应用程序更容易和安装程序非常简单。</span><span class="sxs-lookup"><span data-stu-id="1c601-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="1c601-129">有关 Docker 的 Windows 设置的说明，请转到<https://docs.docker.com/docker-for-windows/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="1c601-130">有关设置 Docker for Mac 的说明，请转到<https://docs.docker.com/docker-for-mac/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="1c601-131">此外，还需要代码编辑器，以便您可以实际开发正在使用 Docker CLI 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c601-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="1c601-132">Microsoft 提供了 Visual Studio Code 中，这是一个轻量级代码编辑器，支持在 Mac、 Windows、 和 Linux，并提供与 IntelliSense[支持多种语言](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、 Go、 Java、 Ruby、 Python 和大部分现代语言）、[调试](https://code.visualstudio.com/Docs/editor/debugging)，[与 Git 集成](https://code.visualstudio.com/Docs/editor/versioncontrol)并[扩展插件支持](https://code.visualstudio.com/docs/extensions/overview)。</span><span class="sxs-lookup"><span data-stu-id="1c601-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="1c601-133">此编辑器是非常适合用于 Mac 和 Linux 的开发人员。</span><span class="sxs-lookup"><span data-stu-id="1c601-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="1c601-134">在 Windows 中，您还可以使用完整的 Visual Studio 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c601-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="1c601-136">有关安装 Visual Studio 代码的 Windows、 Mac 或 Linux 的说明，请转到<https://code.visualstudio.com/docs/setup/setup-overview/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="1c601-137">有关设置 Docker for Mac 的说明，请转到<https://docs.docker.com/docker-for-mac/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="1c601-138">可以使用 Docker CLI 和写入你的代码使用任何代码编辑器中，但 Docker 扩展中使用 Visual Studio Code，可轻松作者`Dockerfile`和`docker-compose.yml`工作区中的文件。</span><span class="sxs-lookup"><span data-stu-id="1c601-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="1c601-139">您还可以从 Visual Studio 代码 IDE 执行 Docker 命令使用 Docker CLI 下运行的任务和脚本。</span><span class="sxs-lookup"><span data-stu-id="1c601-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="1c601-140">适用于 VS Code 的 Docker 扩展提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="1c601-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="1c601-141">自动`Dockerfile`和`docker-compose.yml`文件生成</span><span class="sxs-lookup"><span data-stu-id="1c601-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="1c601-142">语法突出显示并将鼠标悬停提示`docker-compose.yml`和`Dockerfile`文件</span><span class="sxs-lookup"><span data-stu-id="1c601-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="1c601-143">（完成） 适用于 IntelliSense`Dockerfile`和`docker-compose.yml`文件</span><span class="sxs-lookup"><span data-stu-id="1c601-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="1c601-144">Linting （错误和警告） 的`Dockerfile`文件</span><span class="sxs-lookup"><span data-stu-id="1c601-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="1c601-145">最常见的 Docker 命令的命令面板 (F1) 集成</span><span class="sxs-lookup"><span data-stu-id="1c601-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="1c601-146">用于管理映像和容器的资源管理器集成</span><span class="sxs-lookup"><span data-stu-id="1c601-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="1c601-147">部署到 Azure 应用服务从 DockerHub 和 Azure 容器注册表的映像</span><span class="sxs-lookup"><span data-stu-id="1c601-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="1c601-148">若要安装 Docker 扩展，按 Ctrl + Shift + P，键入`ext install`，然后运行安装扩展命令以打开 Marketplace 扩展列表。</span><span class="sxs-lookup"><span data-stu-id="1c601-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="1c601-149">接下来，键入**docker**对结果进行筛选，然后选择 Docker 支持扩展中，如下图所示图 4-23。</span><span class="sxs-lookup"><span data-stu-id="1c601-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![VS Code 的 Docker 扩展视图。](./media/image20.png)

<span data-ttu-id="1c601-151">图 4-23。</span><span class="sxs-lookup"><span data-stu-id="1c601-151">**Figure 4-23**.</span></span> <span data-ttu-id="1c601-152">在 Visual Studio Code 中安装 Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="1c601-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="1c601-153">步骤 2：创建到现有映像 （普通 OS 或开发环境，如.NET Core、 Node.js 和 Ruby） 相关的 DockerFile</span><span class="sxs-lookup"><span data-stu-id="1c601-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="1c601-154">你将需要`DockerFile`每个要生成的自定义映像和每个要部署的容器。</span><span class="sxs-lookup"><span data-stu-id="1c601-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="1c601-155">如果您的应用程序由一个自定义服务组成，则需要将单个`DockerFile`。</span><span class="sxs-lookup"><span data-stu-id="1c601-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="1c601-156">但是如果您的应用程序组成 （如中所示的微服务体系结构） 的多个服务，您将需要一个`Dockerfile`每个服务。</span><span class="sxs-lookup"><span data-stu-id="1c601-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="1c601-157">`DockerFile`通常位于应用或服务的根文件夹中并包含所需的命令，以便 Docker 知道如何设置和运行该应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="1c601-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="1c601-158">可以创建你`DockerFile`并将其添加到你的项目以及你的代码 (.NET Core、 node.js 等)，或者，如果您是初次接触环境，请看看以下提示。</span><span class="sxs-lookup"><span data-stu-id="1c601-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="1c601-159">可以使用 Docker 扩展时使用指导您`Dockerfile`和`docker-compose.yml`与 Docker 容器相关的文件。</span><span class="sxs-lookup"><span data-stu-id="1c601-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="1c601-160">最终，可能将编写这些种类的文件而无需此工具，但使用 Docker 扩展是很好的起点，可加快学习曲线。</span><span class="sxs-lookup"><span data-stu-id="1c601-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="1c601-161">在图 4 至 24 日，您可以看到如何 docker-compose 文件添加通过使用适用于 VS Code Docker 扩展。</span><span class="sxs-lookup"><span data-stu-id="1c601-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![用于 VS Code Docker 扩展控制台视图。](./media/image24.png)

<span data-ttu-id="1c601-163">图 4-24。</span><span class="sxs-lookup"><span data-stu-id="1c601-163">**Figure 4-24**.</span></span> <span data-ttu-id="1c601-164">添加使用 docker 文件**添加 Docker 文件复制到工作区命令**</span><span class="sxs-lookup"><span data-stu-id="1c601-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="1c601-165">当添加 DockerFile 时，指定要使用的基础 Docker 映像 (如使用`FROM mcr.microsoft.com/dotnet/core/aspnet`)。</span><span class="sxs-lookup"><span data-stu-id="1c601-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="1c601-166">你通常将生成自定义映像从在任何官方存储库获取的基本映像之上[Docker Hub 注册表](https://hub.docker.com/)(如[适用于.NET Core 映像](https://hub.docker.com/_/microsoft-dotnet-core/)或一个[适用于 Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="1c601-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="1c601-167">***使用现有的官方 Docker 映像***</span><span class="sxs-lookup"><span data-stu-id="1c601-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="1c601-168">语言堆栈的官方存储库中使用版本号可确保相同的语言功能 （包括开发、 测试和生产） 的所有计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="1c601-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="1c601-169">下面是.NET Core 容器的示例 DockerFile:</span><span class="sxs-lookup"><span data-stu-id="1c601-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="1c601-170">在这种情况下，该映像基于版本 2.2 的官方 ASP.NET Core Docker 映像 （多体系结构适用于 Linux 和 Windows），根据行的`FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`。</span><span class="sxs-lookup"><span data-stu-id="1c601-170">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="1c601-171">(有关此主题的详细信息，请参阅[ASP.NET Core Docker 映像](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)页并[.NET Core Docker 映像](https://hub.docker.com/_/microsoft-dotnet-core/)页)。</span><span class="sxs-lookup"><span data-stu-id="1c601-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="1c601-172">在 DockerFile，还可以指示 Docker 侦听在运行时 （如端口 80） 将使用的 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="1c601-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="1c601-173">可在 Dockerfile 中指定其他配置设置，具体取决于使用的语言和框架。</span><span class="sxs-lookup"><span data-stu-id="1c601-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="1c601-174">例如，`ENTRYPOINT`行与`["dotnet", "MySingleContainerWebApp.dll"]`指示 Docker 运行.NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c601-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="1c601-175">如果在使用 SDK 和.NET Core CLI (`dotnet CLI`) 生成并运行.NET 应用程序，此设置会有所不同。</span><span class="sxs-lookup"><span data-stu-id="1c601-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="1c601-176">此处的关键点是 ENTRYPOINT 行和其他设置的依赖于为应用程序选择的语言和平台。</span><span class="sxs-lookup"><span data-stu-id="1c601-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="1c601-178">有关生成.NET Core 应用程序的 Docker 映像的详细信息，请转到<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>。</span><span class="sxs-lookup"><span data-stu-id="1c601-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="1c601-179">若要了解有关构建你自己的映像的详细信息，请转到<https://docs.docker.com/engine/tutorials/dockerimages/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="1c601-180">**使用多体系结构映像存储库**</span><span class="sxs-lookup"><span data-stu-id="1c601-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="1c601-181">存储库中的单一映像名称可以包含平台变量，如 Linux 映像和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="1c601-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="1c601-182">此功能允许 Microsoft （基础映像创建者） 等供应商创建涵盖多个平台 （Linux 和 Windows） 的单个存储库。</span><span class="sxs-lookup"><span data-stu-id="1c601-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="1c601-183">例如， [dotnet/核心/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Docker 中心注册表中的可用存储库使用的同一映像名称提供适用于 Linux 和 Windows Nano Server 的支持。</span><span class="sxs-lookup"><span data-stu-id="1c601-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="1c601-184">拉取[dotnet/核心/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)映像从 Windows 主机拉取 Windows 变体，而从 Linux 主机拉取同一映像名称拉取 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="1c601-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="1c601-185">***从头开始创建您的基础映像***</span><span class="sxs-lookup"><span data-stu-id="1c601-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="1c601-186">您可以从头开始创建您自己的 Docker 基础映像在此所述[一文](https://docs.docker.com/engine/userguide/eng-image/baseimages/)从 Docker。</span><span class="sxs-lookup"><span data-stu-id="1c601-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="1c601-187">如果你刚开始使用 Docker，但如果你想要设置的基础映像的特定位，您可以执行此操作，这种情况下可能不是最适合您。</span><span class="sxs-lookup"><span data-stu-id="1c601-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="1c601-188">步骤 3：创建自定义 Docker 映像中嵌入你的服务</span><span class="sxs-lookup"><span data-stu-id="1c601-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="1c601-189">对于每个包含您的应用程序的自定义服务，你将需要创建一个相关的映像。</span><span class="sxs-lookup"><span data-stu-id="1c601-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="1c601-190">如果您的应用程序由单个服务或 web 应用的组成，将需要一个映像。</span><span class="sxs-lookup"><span data-stu-id="1c601-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="1c601-191">每当你将源代码推送到 Git 存储库 （持续集成），以便将该全局环境中创建映像从时考虑到"外部循环 DevOps 工作流"，将通过自动的生成过程中创建映像应用源代码。</span><span class="sxs-lookup"><span data-stu-id="1c601-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="1c601-192">但我们考虑转到该外部循环路由之前，我们需要确保，Docker 应用程序工作正常，以便它们不推送到源代码管理系统 （Git 等） 可能无法正常工作的代码。</span><span class="sxs-lookup"><span data-stu-id="1c601-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="1c601-193">因此，每个开发人员首先需要执行整个的内部循环过程，以在本地测试，继续开发直到他们想要推送完整的功能或将更改为源代码管理系统。</span><span class="sxs-lookup"><span data-stu-id="1c601-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="1c601-194">若要在本地环境和使用 DockerFile 创建映像，您可以使用 docker 生成命令，在图 4-25 所示 (还可以运行`docker-compose up --build`的应用程序由多个容器/服务)。</span><span class="sxs-lookup"><span data-stu-id="1c601-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Docker-compose build，显示下载进度的映像的控制台输出。](./media/image25.png)

<span data-ttu-id="1c601-196">图 4-25。</span><span class="sxs-lookup"><span data-stu-id="1c601-196">**Figure 4-25**.</span></span> <span data-ttu-id="1c601-197">正在运行的 docker 生成</span><span class="sxs-lookup"><span data-stu-id="1c601-197">Running docker build</span></span>

<span data-ttu-id="1c601-198">（可选） 而不是直接运行`docker build`项目文件夹中，首先可以从生成的可部署文件夹使用运行所需的.NET 库`dotnet publish`命令，然后再运行`docker build`。</span><span class="sxs-lookup"><span data-stu-id="1c601-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="1c601-199">此示例中使用的名称创建 Docker 映像`cesardl/netcore-webapi-microservice-docker:first`(`:first`一个标记，如特定版本)。</span><span class="sxs-lookup"><span data-stu-id="1c601-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="1c601-200">可能需要此步骤中的每个自定义映像需要创建组合 Docker 应用程序与多个容器。</span><span class="sxs-lookup"><span data-stu-id="1c601-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="1c601-201">你可以找到现有的映像在本地存储库中 （在开发计算机） 使用 docker 映像命令，在图 4-26 所示。</span><span class="sxs-lookup"><span data-stu-id="1c601-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![控制台输出中显示现有的映像的命令 docker 图像。](./media/image26.png)

<span data-ttu-id="1c601-203">**图 4-26**。</span><span class="sxs-lookup"><span data-stu-id="1c601-203">**Figure 4-26**.</span></span> <span data-ttu-id="1c601-204">查看现有的映像使用的 docker 映像</span><span class="sxs-lookup"><span data-stu-id="1c601-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="1c601-205">步骤 4：生成包含多个服务的组合的 Docker 应用程序时在 docker-compose.yml 中定义服务</span><span class="sxs-lookup"><span data-stu-id="1c601-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="1c601-206">使用`docker-compose.yml`文件中，可以定义一组相关服务部署为组合应用程序与下一步的步骤部分所述的部署命令。</span><span class="sxs-lookup"><span data-stu-id="1c601-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="1c601-207">创建该文件在主或根解决方案文件夹;它应该类似于在此显示内容`docker-compose.yml`文件：</span><span class="sxs-lookup"><span data-stu-id="1c601-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="1c601-208">在此特定情况下，此文件定义两个服务： web 服务 （自定义的服务） 和 redis 服务 （受欢迎的缓存服务）。</span><span class="sxs-lookup"><span data-stu-id="1c601-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="1c601-209">每个服务将部署为一个容器，因此我们需要为每个使用具体的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="1c601-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="1c601-210">对于此特定的 web 服务，该映像将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c601-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="1c601-211">中的当前目录中的 DockerFile 生成</span><span class="sxs-lookup"><span data-stu-id="1c601-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="1c601-212">转发的公开的端口 80 上向主机计算机上的端口 81 容器</span><span class="sxs-lookup"><span data-stu-id="1c601-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="1c601-213">到 /code 在容器中，使你能够修改代码，而无需重新生成映像可能在主机上装载项目目录</span><span class="sxs-lookup"><span data-stu-id="1c601-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="1c601-214">Web 服务链接到 redis 服务</span><span class="sxs-lookup"><span data-stu-id="1c601-214">Link the web service to the redis service</span></span>

<span data-ttu-id="1c601-215">Redis 服务使用[最新的公共 redis 映像](https://hub.docker.com/_/redis/)从 Docker 中心注册表中拉取。</span><span class="sxs-lookup"><span data-stu-id="1c601-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="1c601-216">[redis](https://redis.io/)是用于服务器端应用程序的受欢迎的缓存。</span><span class="sxs-lookup"><span data-stu-id="1c601-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="1c601-217">步骤 5：生成并运行 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="1c601-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="1c601-218">如果您的应用程序具有单个容器，只需通过将其部署到 Docker 主机 （VM 或物理服务器） 运行。</span><span class="sxs-lookup"><span data-stu-id="1c601-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="1c601-219">但是，如果您的应用程序由多个服务组成，则需要*compose 它*、 过。</span><span class="sxs-lookup"><span data-stu-id="1c601-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="1c601-220">让我们查看不同的选项。</span><span class="sxs-lookup"><span data-stu-id="1c601-220">Let's see the different options.</span></span>

<span data-ttu-id="1c601-221">***选项 a:运行单个容器或服务***</span><span class="sxs-lookup"><span data-stu-id="1c601-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="1c601-222">可以通过使用 docker 运行命令，如下所示运行 Docker 映像：</span><span class="sxs-lookup"><span data-stu-id="1c601-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="1c601-223">为此特定部署中，我们将重定向请求发送到端口 80 到内部端口 5000。</span><span class="sxs-lookup"><span data-stu-id="1c601-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="1c601-224">现在该应用程序侦听的外部端口 80 主机级别。</span><span class="sxs-lookup"><span data-stu-id="1c601-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="1c601-225">***选项 b:编写和运行多容器应用程序***</span><span class="sxs-lookup"><span data-stu-id="1c601-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="1c601-226">在大多数企业方案中，将多个服务组成的 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c601-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="1c601-227">对于这些情况下，可以运行`docker-compose up`命令 (图 4-27)，将使用可能在之前创建的 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="1c601-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="1c601-228">运行此命令将部署及其相关容器的所有组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c601-228">Running this command deploys a composed application with all of its related containers.</span></span>

![控制台输出中的的 docker-compose up 命令。](./media/image27.png)

<span data-ttu-id="1c601-230">**图 4-27**。</span><span class="sxs-lookup"><span data-stu-id="1c601-230">**Figure 4-27**.</span></span> <span data-ttu-id="1c601-231">运行"docker compose up"命令的结果</span><span class="sxs-lookup"><span data-stu-id="1c601-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="1c601-232">在您运行`docker-compose up`，部署你的应用程序和其相关的容器到 Docker 主机，如图 4-28 所示的 VM 表示形式。</span><span class="sxs-lookup"><span data-stu-id="1c601-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![运行多容器应用程序的虚拟机。](./media/image28.png)

<span data-ttu-id="1c601-234">**图 4-28**。</span><span class="sxs-lookup"><span data-stu-id="1c601-234">**Figure 4-28**.</span></span> <span data-ttu-id="1c601-235">部署了 Docker 容器的 VM</span><span class="sxs-lookup"><span data-stu-id="1c601-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="1c601-236">步骤 6：测试 Docker 应用程序 （在本地，本地 CD VM)</span><span class="sxs-lookup"><span data-stu-id="1c601-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="1c601-237">根据您的应用程序正在执行什么操作，此步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="1c601-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="1c601-238">在简单.NET Core Web API"Hello World"部署为单个容器或服务，只需要通过提供的 DockerFile 中指定的 TCP 端口来访问该服务。</span><span class="sxs-lookup"><span data-stu-id="1c601-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="1c601-239">如果 localhost 未开启，若要导航到你的服务，通过使用此命令为机查找 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="1c601-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="1c601-240">在 Docker 主机上，打开浏览器并导航到该站点;您应该看到你的应用/服务运行，在图 4-29 所示。</span><span class="sxs-lookup"><span data-stu-id="1c601-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![来自 localhost/API/values 的响应的浏览器视图。](./media/image29.png)

<span data-ttu-id="1c601-242">**图 4-29**。</span><span class="sxs-lookup"><span data-stu-id="1c601-242">**Figure 4-29**.</span></span> <span data-ttu-id="1c601-243">测试 Docker 应用程序使用 localhost 在本地</span><span class="sxs-lookup"><span data-stu-id="1c601-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="1c601-244">请注意，则使用端口 80，但在内部它将被重定向到端口 5000，因为这是使用的部署方式`docker run`，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="1c601-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="1c601-245">您可以从终端使用 CURL 进行测试。</span><span class="sxs-lookup"><span data-stu-id="1c601-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="1c601-246">在 Windows 上的 Docker 安装，默认 IP 是为 10.0.75.1，如下图中图 4-30 所示。</span><span class="sxs-lookup"><span data-stu-id="1c601-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![控制台输出中获取 http://10.0.75.1/API/values使用 curl](./media/image30.png)

<span data-ttu-id="1c601-248">**图 4-30**。</span><span class="sxs-lookup"><span data-stu-id="1c601-248">**Figure 4-30**.</span></span> <span data-ttu-id="1c601-249">通过使用 CURL 在本地测试 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="1c601-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="1c601-250">**调试在 Docker 上运行的容器**</span><span class="sxs-lookup"><span data-stu-id="1c601-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="1c601-251">Visual Studio Code 支持调试 Docker，如果您使用的 Node.js 和其他平台，如.NET Core 容器。</span><span class="sxs-lookup"><span data-stu-id="1c601-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="1c601-252">您还可以调试在 Docker 中的.NET Core 或.NET Framework 的容器时使用 Visual Studio 的 Windows 或 Mac 下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="1c601-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="1c601-254">若要了解有关调试 Node.js Docker 容器的详细信息，请转到<https://blog.docker.com/2016/07/live-debugging-docker/>和<https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>。</span><span class="sxs-lookup"><span data-stu-id="1c601-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1c601-255">[上一页](docker-apps-development-environment.md)
>[下一页](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="1c601-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
