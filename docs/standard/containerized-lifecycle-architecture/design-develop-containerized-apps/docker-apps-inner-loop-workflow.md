---
title: Docker 应用的内部循环开发工作流
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: f7acb60e6136c0250d18bdce23ac21fb6aa80b34
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148849"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="3c8ad-103">Docker 应用的内部循环开发工作流</span><span class="sxs-lookup"><span data-stu-id="3c8ad-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="3c8ad-104">触发跨越整个 DevOps 的外部循环工作流之前循环，开始整个过程的每个开发人员的计算机上，应用本身进行编码、 使用其首选的语言或平台，以及本地测试 (图 4-14)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="3c8ad-105">但在所有情况下，你必须非常重要的一点共同点，无论选择何种语言、 框架或平台。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="3c8ad-106">在此特定的工作流，始终是开发和测试 Docker 容器，但却在本地。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="3c8ad-107">图 4-14:内部循环开发上下文</span><span class="sxs-lookup"><span data-stu-id="3c8ad-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="3c8ad-108">容器或 Docker 映像的实例将包含这些组件：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="3c8ad-109">选择 （例如，Linux 分发版或 Windows） 的操作系统</span><span class="sxs-lookup"><span data-stu-id="3c8ad-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="3c8ad-110">由开发人员 （例如，应用程序二进制文件） 添加的文件</span><span class="sxs-lookup"><span data-stu-id="3c8ad-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="3c8ad-111">配置 （例如，环境设置和依赖项）</span><span class="sxs-lookup"><span data-stu-id="3c8ad-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="3c8ad-112">哪些过程操作即可运行 Docker 的说明</span><span class="sxs-lookup"><span data-stu-id="3c8ad-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="3c8ad-113">您可以将设置为 （下一节中所述） 的过程中使用 Docker 的内部循环开发工作流。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="3c8ad-114">考虑设置环境的初始步骤不包括在内，因为您需要为此，只需一次。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="3c8ad-115">构建单个应用程序中使用 Visual Studio Code 和 Docker CLI 的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="3c8ad-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="3c8ad-116">应用是从你自己的服务和附加库 （依赖项） 组成。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="3c8ad-117">图 4-15 显示了通常需要构建 Docker 应用程序后, 跟每个步骤的详细说明时要执行的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="3c8ad-118">图 4 月 15 日：使用 Docker CLI 适用于容器化 Docker 应用程序生命周期的高级工作流</span><span class="sxs-lookup"><span data-stu-id="3c8ad-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="3c8ad-119">步骤 1：开始在 Visual Studio Code 中编写代码并创建初始应用/服务基线</span><span class="sxs-lookup"><span data-stu-id="3c8ad-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="3c8ad-120">开发应用程序的方法是执行不带 Docker 的方式非常类似。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="3c8ad-121">不同之处是，在开发时，在部署和测试应用程序或服务 （如 Windows 或 Linux VM） 在本地环境中放置的 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="3c8ad-122">**设置本地环境**</span><span class="sxs-lookup"><span data-stu-id="3c8ad-122">**Setting up your local environment**</span></span>

<span data-ttu-id="3c8ad-123">使用适用于 Mac 和 Windows 的 Docker 的最新版本，比以往要开发 Docker 应用程序更容易和安装程序非常简单。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="3c8ad-124">**详细信息** 有关 Docker 的 Windows 设置的说明，请转到[ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="3c8ad-125">有关设置 Docker for Mac 的说明，请转到<https://docs.docker.com/docker-for-mac/>。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="3c8ad-126">此外，还需要代码编辑器，以便您可以实际开发正在使用 Docker CLI 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="3c8ad-127">Microsoft 提供了 Visual Studio Code 中，这是一个轻量级代码编辑器，支持在 Mac、 Windows、 和 Linux，并提供与 IntelliSense[支持多种语言](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、 Go、 Java、 Ruby、 Python 和大部分现代语言）、[调试](https://code.visualstudio.com/Docs/editor/debugging)，[与 Git 集成](https://code.visualstudio.com/Docs/editor/versioncontrol)并[扩展插件支持](https://code.visualstudio.com/docs/extensions/overview)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="3c8ad-128">此编辑器是非常适合用于 Mac 和 Linux 的开发人员。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="3c8ad-129">在 Windows 中，您还可以使用完整的 Visual Studio 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="3c8ad-130">**详细信息** 安装 Visual Studio 为 Windows、 Mac 或 Linux 的说明，请转到<https://code.visualstudio.com/docs/setup/setup-overview/>。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>

<span data-ttu-id="3c8ad-131">可以使用 Docker CLI 和写入你的代码使用任何代码编辑器中，但如果使用 Visual Studio Code，可以轻松编写 Dockerfile 和 docker-compose.yml 文件在工作区中。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="3c8ad-132">此外，可以从 IDE 提示可以运行使用下方的 Docker CLI 的详细的操作的脚本运行 Visual Studio Code 任务。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="3c8ad-133">Visual Studio Code 提供的扩展，但需要进行安装。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="3c8ad-134">若要执行此操作，按 Ctrl + Shift + P，键入**ext 安装**，然后运行扩展：安装扩展命令以打开 Marketplace 扩展列表。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="3c8ad-135">接下来，键入**docker**以筛选结果，然后选择 Dockerfile 和 Docker Compose 文件 (yml) 支持扩展，如下图中图 4-16 所示。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="3c8ad-136">图 4-16:在 Visual Studio Code 中安装 Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="3c8ad-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="3c8ad-137">步骤 2：创建到现有映像 （普通 OS 或开发环境，如.NET Core、 Node.js 和 Ruby） 相关的 DockerFile</span><span class="sxs-lookup"><span data-stu-id="3c8ad-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="3c8ad-138">你将需要每个要生成的自定义映像和每个要部署的容器的 DockerFile，因此，如果您的应用程序由一个自定义服务组成，您将需要一个 DockerFile。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="3c8ad-139">但是，如果您的应用程序组成 （如中所示的微服务体系结构） 的多个服务，你将需要一个 Dockerfile，每个服务。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="3c8ad-140">DockerFile 通常放置在你的应用或服务的根文件夹内，并包含所需的命令，这样该 Docker 就知道如何设置和运行该应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="3c8ad-141">你可以创建 DockerFile 并将其添加到你的项目以及你的代码 (node.js，.NET Core 等)，或者，如果你不熟悉的环境，看一看以下提示。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="3c8ad-142">可以使用名为的命令行工具[yo docker](https://github.com/Microsoft/generator-docker)，其中搭建基架以选择并添加所需的 Docker 配置文件的语言中的项目中的文件。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="3c8ad-143">基本上，帮助开发人员入门，创建相应的 DockerFile，docker-compose.yml 和其他相关联的脚本，以生成并运行 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="3c8ad-144">此 yeoman 生成器将提示你使用的一些问题，询问你所选的开发语言和目标容器主机。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![yo docker](./media/image21.png)

<span data-ttu-id="3c8ad-146">例如，图 4-17 显示终端中的两个屏幕快照，在 Windows 中，在 Mac 上，在这两种情况下，运行则 docker，将生成的示例代码项目 （当前.NET Core、 Golang 和 Node.js 用作受支持的语言） 已配置为在上工作Docker 的顶部。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="3c8ad-147">图 4-17: yo docker 命令在 Windows （左） 和 Mac 上的工具</span><span class="sxs-lookup"><span data-stu-id="3c8ad-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="3c8ad-148">图 4-18 提供了示例则 docker 后使用你的位置，以将基架的一个现有的.NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="3c8ad-149">图 4-18： 则使用现有的.NET Core docker 项目就地</span><span class="sxs-lookup"><span data-stu-id="3c8ad-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="3c8ad-150">Dockerfile，您可以指定您将使用 （如使用"发件人 microsoft/dotnet:1.0.0-core"） 的基础 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="3c8ad-151">您通常将生成自定义映像可以从在任何官方存储库获取的基本映像之上[Docker Hub 注册表](https://hub.docker.com/)(如[适用于.NET Core 映像](https://hub.docker.com/r/microsoft/dotnet/)或一个[适用于 Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="3c8ad-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="3c8ad-152">***选项 a:使用现有的官方 Docker 映像***</span><span class="sxs-lookup"><span data-stu-id="3c8ad-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="3c8ad-153">语言堆栈的官方存储库中使用版本号可确保相同的语言功能 （包括开发、 测试和生产） 的所有计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="3c8ad-154">以下是示例 DockerFile.NET Core 容器：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-154">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="3c8ad-155">在这种情况下，它适用于 Linux 名为 microsoft/aspnetcore:1.0.1 使用正式的 ASP.NET Core Docker 映像的版本 1.0.1。 </span><span class="sxs-lookup"><span data-stu-id="3c8ad-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="3c8ad-156">有关更多详细信息，请查阅[ASP.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/aspnetcore/)和[.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="3c8ad-157">你还可能正在使用另一可比较的映像，如节点： 4-Node.js，或对于开发语言，可在许多其他预配置的映像的 onbuild [Docker Hub](https://hub.docker.com/explore/)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="3c8ad-158">在 DockerFile，还需要指示 Docker 侦听 TCP 端口将使用在运行时 （如端口 80）。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="3c8ad-159">有其他行的这样 Docker 就知道如何运行该应用程序可以在具体取决于你使用的，语言/框架 DockerFile 中添加的配置。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="3c8ad-160">例如，你需要使用的入口点行\["dotnet"，"MyCustomMicroservice.dll"\]运行.NET Core 应用程序中，虽然您可以有多个不同版本，具体取决于生成并运行你的服务的方法。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="3c8ad-161">如果你正在使用的 SDK 和 dotnet CLI 生成并运行.NET 应用程序，则将为略有不同。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="3c8ad-162">底部行是入口点行加上其他行将无法为应用程序选择的语言/平台而异。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="3c8ad-163">**详细信息** 有关生成.NET Core 应用程序的 Docker 映像的信息，请转到<https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-163">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="3c8ad-164">若要了解有关构建你自己的映像的详细信息，请转到[ https://docs.docker.com/engine/\ 教程/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="3c8ad-165">**多平台映像存储库**</span><span class="sxs-lookup"><span data-stu-id="3c8ad-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="3c8ad-166">随着 Windows 容器变得更加普遍，单个存储库可以包含平台变量，如 Linux 和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="3c8ad-167">这是一项新功能使得供应商可以使用单个存储库来涵盖多个平台，例如 Docker 中即将推出[microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)存储库，则可以从 DockerHub 注册表。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="3c8ad-168">由于该功能提供处于活动状态，从 Windows 主机拉取此映像会拉取 Windows 变体，而从 Linux 主机拉取同一映像名称会拉取 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="3c8ad-169">***选项 b:从头开始创建您的基础映像***</span><span class="sxs-lookup"><span data-stu-id="3c8ad-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="3c8ad-170">您可以从头开始创建您自己的 Docker 基础映像在此所述[一文](https://docs.docker.com/engine/userguide/eng-image/baseimages/)从 Docker。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="3c8ad-171">这是如果您刚开始使用 Docker，则可能不最适合您的方案，但如果你想要设置的基础映像的特定位，您可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="3c8ad-172">步骤 3：创建自定义 Docker 映像中嵌入你的服务</span><span class="sxs-lookup"><span data-stu-id="3c8ad-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="3c8ad-173">对于每个包含您的应用程序的自定义服务，你将需要创建一个相关的映像。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="3c8ad-174">如果您的应用程序由单个服务或 web 应用的组成，将需要一个映像。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="3c8ad-175">时考虑到"外部循环 DevOps 工作流"，图像将通过自动的生成过程以便将该全局环境中创建映像到 Git 存储库 （持续集成） 推送你的源代码时从创建应用源代码。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="3c8ad-176">但是，我们考虑转到该外部循环路由之前，我们需要确保，Docker 应用程序工作正常，以便它们不推送到源代码管理系统 （Git 等） 可能无法正常工作的代码。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="3c8ad-177">因此，每个开发人员首先需要执行整个的内部循环过程，以在本地测试，继续开发直到他们想要推送完整的功能或将更改为源代码管理系统。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="3c8ad-178">若要在本地环境和使用 DockerFile 创建映像，您可以使用 docker 生成命令，如图 4-19 中所示 (还可以运行 docker compose up--生成的应用程序由多个容器/服务)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="3c8ad-179">图 4-19:正在运行的 docker 生成</span><span class="sxs-lookup"><span data-stu-id="3c8ad-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="3c8ad-180">（可选） 而不是直接运行 docker 生成从项目的文件夹，则第一次可以生成可部署的文件夹具有需要通过运行的 dotnet 发布命令，并运行 docker 生成.NET 库。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="3c8ad-181">在此示例中，这将创建的 Docker 映像名称 cesardl/netcore 端 webapi 微服务使用的 docker： 第一个 (: 首先是一个标记，如特定版本)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="3c8ad-182">可能需要此步骤中的每个自定义映像需要创建组合 Docker 应用程序与多个容器。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="3c8ad-183">你可以找到现有的映像在本地存储库中 （在开发计算机） 使用 docker 映像命令，如图 4 到 20 中所示。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="3c8ad-184">图 4-20:查看现有的映像使用的 docker 映像</span><span class="sxs-lookup"><span data-stu-id="3c8ad-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="3c8ad-185">步骤 4：（可选）生成包含多个服务的组合的 Docker 应用程序时在 docker-compose.yml 中定义服务</span><span class="sxs-lookup"><span data-stu-id="3c8ad-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="3c8ad-186">使用 docker-compose.yml 文件可定义一组相关服务部署为组合应用程序与下一步的步骤部分所述的部署命令。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="3c8ad-187">您需要创建该文件在主或根解决方案文件夹;它应该类似内容以下 docker-compose.yml 文件：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
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

<span data-ttu-id="3c8ad-188">在此特定情况下，此文件定义两个服务： web 服务 （自定义的服务） 和 redis 服务 （受欢迎的缓存服务）。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="3c8ad-189">每个服务将部署为一个容器，因此我们需要为每个使用具体的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="3c8ad-190">对于此特定的 web 服务，该映像将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="3c8ad-191">中的当前目录中的 DockerFile 生成</span><span class="sxs-lookup"><span data-stu-id="3c8ad-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="3c8ad-192">转发的公开的端口 80 上向主机计算机上的端口 81 容器</span><span class="sxs-lookup"><span data-stu-id="3c8ad-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="3c8ad-193">到 /code 在容器中，使你能够修改代码，而无需重新生成映像可能在主机上装载项目目录</span><span class="sxs-lookup"><span data-stu-id="3c8ad-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="3c8ad-194">Web 服务链接到 redis 服务</span><span class="sxs-lookup"><span data-stu-id="3c8ad-194">Link the web service to the redis service</span></span>

<span data-ttu-id="3c8ad-195">Redis 服务使用[最新的公共 redis 映像](https://hub.docker.com/_/redis/)从 Docker 中心注册表中拉取。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="3c8ad-196">[redis](https://redis.io/)是一个非常受欢迎的缓存系统，用于服务器端应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="3c8ad-197">步骤 5：生成并运行 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="3c8ad-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="3c8ad-198">如果您的应用程序具有单个容器，只需通过将其部署到 Docker 主机 （VM 或物理服务器） 运行。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="3c8ad-199">但是，如果您的应用程序由多个服务组成，则需要*compose 它*、 过。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="3c8ad-200">让我们查看不同的选项。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-200">Let's see the different options.</span></span>

<span data-ttu-id="3c8ad-201">***选项 a:运行单个容器或服务***</span><span class="sxs-lookup"><span data-stu-id="3c8ad-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="3c8ad-202">可以通过使用 docker 运行命令，如下所示运行 Docker 映像：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="3c8ad-203">请注意，对于此特定的部署，我们将会将请求重定向发送到端口 80 到内部端口 5000。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="3c8ad-204">现在，该应用程序侦听的外部端口 80 主机级别。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="3c8ad-205">***选项 b:编写和运行多容器应用程序***</span><span class="sxs-lookup"><span data-stu-id="3c8ad-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="3c8ad-206">在大多数企业方案中，将多个服务组成的 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="3c8ad-207">对于这些情况下，可以运行该命令的 docker-compose up (图 4-21)，它将使用可能在之前创建的 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="3c8ad-208">运行此命令将部署及其相关容器的所有组合应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="3c8ad-209">图 4-21:运行"docker compose up"命令的结果</span><span class="sxs-lookup"><span data-stu-id="3c8ad-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="3c8ad-210">在运行 docker 后-compose up，您将部署你的应用程序和其相关的容器到 Docker 主机中，如图 4-22 所示的 VM 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="3c8ad-211">图 4-22:部署了 Docker 容器的 VM</span><span class="sxs-lookup"><span data-stu-id="3c8ad-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="3c8ad-212">请注意 docker compose up 和 docker 运行可能已足够用于测试你的容器中开发环境中，但您可能根本不使用它们如果希望使用 Docker 群集和业务流程协调程序，例如 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes若要纵向扩展将。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="3c8ad-213">如果您使用等集群[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（用于 Docker 的 Windows 和 Mac 自 1.12 版起），您需要部署和测试与其他命令，例如为单个服务，创建 docker 服务，或者后部署多个容器组成的应用，使用 docker compose 捆绑包和 docker 部署 myBundleFile，通过作为堆栈，部署组成的应用，本文中所述[分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)从 Docker。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="3c8ad-214">有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)并[Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment)不同的部署命令和脚本，也会使用。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="3c8ad-215">步骤 6:测试 Docker 应用程序 （在本地，本地 CD VM)</span><span class="sxs-lookup"><span data-stu-id="3c8ad-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="3c8ad-216">根据您的应用程序正在执行什么操作，此步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="3c8ad-217">在非常简单.NET Core Web API"Hello World"部署为单个容器或服务，你只需通过提供 DockerFile 中指定的 TCP 端口访问服务。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="3c8ad-218">如果 localhost 未开启，若要导航到你的服务，通过使用此命令为机查找 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="3c8ad-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="3c8ad-219">docker 计算机 ip*你的容器名称*</span><span class="sxs-lookup"><span data-stu-id="3c8ad-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="3c8ad-220">在 Docker 主机上，打开浏览器并导航到该站点;图 4-23 所示，您应该看到运行，将应用程序/服务。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="3c8ad-221">图 4-23:测试 Docker 应用程序使用 localhost 在本地</span><span class="sxs-lookup"><span data-stu-id="3c8ad-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="3c8ad-222">请注意，则使用端口 80，但在内部它已被重定向到端口 5000，因为这是它的部署方式使用 docker 运行，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="3c8ad-223">您可以从终端使用 CURL 进行测试。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="3c8ad-224">在 Windows 上的 Docker 安装，默认 IP 是为 10.0.75.1，如下图所示在图 4 到 24 个。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="3c8ad-225">图 4-24:通过使用 CURL 在本地测试 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="3c8ad-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="3c8ad-226">**调试在 Docker 上运行的容器**</span><span class="sxs-lookup"><span data-stu-id="3c8ad-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="3c8ad-227">Visual Studio Code 支持调试 Docker，如果您使用的 Node.js 和其他平台，如.NET Core 容器。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="3c8ad-228">您还可以调试在 Docker 中的.NET Core 容器时使用 Visual Studio 中下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="3c8ad-229">**详细信息：** 若要了解有关调试 Node.js Docker 容器的详细信息，请转到<https://blog.docker.com/2016/07/live-debugging-docker/>并[https://blogs.msdn.microsoft.com/\用户\_ed/2016年/02/27 /visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)。</span><span class="sxs-lookup"><span data-stu-id="3c8ad-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3c8ad-230">[上一页](docker-apps-development-environment.md)
>[下一页](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="3c8ad-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>