---
title: "对于 Docker 应用程序的内部循环开发工作流"
description: "使用 Microsoft 平台和工具的 Docker 容器化应用程序生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 30c10b2407ab643e04eb44c00ddf4a89d369a025
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="82a84-104">对于 Docker 应用程序的内部循环开发工作流</span><span class="sxs-lookup"><span data-stu-id="82a84-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="82a84-105">触发跨越整个 DevOps 外部循环工作流之前重启，所有它开始每个开发人员的计算机上，编码在应用程序、 使用其首选的语言或平台，以及本地测试 (图 4-14)。</span><span class="sxs-lookup"><span data-stu-id="82a84-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using his preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="82a84-106">但在这些情况下，你将具有非常重要的一点共同点，无论你选择何种语言、 框架或平台。</span><span class="sxs-lookup"><span data-stu-id="82a84-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="82a84-107">在此特定的工作流，你始终开发和测试 Docker 容器，但却在本地。</span><span class="sxs-lookup"><span data-stu-id="82a84-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="82a84-108">图 4-14： 内部循环开发上下文</span><span class="sxs-lookup"><span data-stu-id="82a84-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="82a84-109">容器或 Docker 映像的实例将包含这些组件：</span><span class="sxs-lookup"><span data-stu-id="82a84-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="82a84-110">操作系统选择 （例如，一种 Linux 分发或 Windows）</span><span class="sxs-lookup"><span data-stu-id="82a84-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="82a84-111">由开发人员 （例如，应用程序二进制文件） 添加文件</span><span class="sxs-lookup"><span data-stu-id="82a84-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="82a84-112">配置 （例如，环境设置及依赖关系）</span><span class="sxs-lookup"><span data-stu-id="82a84-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="82a84-113">流程的说明，若要运行的 Docker</span><span class="sxs-lookup"><span data-stu-id="82a84-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="82a84-114">你可以将作为进程 （在下一部分中所述） 使用 Docker 的内部循环开发工作流设置。</span><span class="sxs-lookup"><span data-stu-id="82a84-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="82a84-115">考虑设置环境的初始步骤不包括在内，因为你需要为此，只需一次。</span><span class="sxs-lookup"><span data-stu-id="82a84-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="82a84-116">生成使用 Visual Studio Code 和 Docker CLI Docker 容器中的单个应用程序</span><span class="sxs-lookup"><span data-stu-id="82a84-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="82a84-117">应用程序从你自己的服务以及其他库 （依赖关系） 组成。</span><span class="sxs-lookup"><span data-stu-id="82a84-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="82a84-118">图 4-15 显示通常需要在生成 Docker 应用程序，每个步骤的详细说明后跟时执行的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="82a84-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="82a84-119">图 4-15： 使用 Docker CLI Docker 容器化应用程序生命周期的高级工作流</span><span class="sxs-lookup"><span data-stu-id="82a84-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="82a84-120">步骤 1： 使用 Visual Studio Code 中开始编码，并创建初始应用程序/服务基线</span><span class="sxs-lookup"><span data-stu-id="82a84-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="82a84-121">开发应用程序的方法是不 Docker 工作方式非常相似。</span><span class="sxs-lookup"><span data-stu-id="82a84-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="82a84-122">区别是，在开发时，你部署和测试您的应用程序或服务在放置在本地环境 （如 Windows 或 Linux VM） 的 Docker 容器内运行。</span><span class="sxs-lookup"><span data-stu-id="82a84-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="82a84-123">**设置本地环境**</span><span class="sxs-lookup"><span data-stu-id="82a84-123">**Setting up your local environment**</span></span>

<span data-ttu-id="82a84-124">适用于 Mac 和 Windows 的 Docker 的最新版本，它是比以往若开发 Docker 应用程序，并且安装程序直接。</span><span class="sxs-lookup"><span data-stu-id="82a84-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="82a84-125">**详细信息** 有关用于 Windows 的 Docker 设置的说明，请转到[https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="82a84-126">有关设置适用于 Mac 的 Docker 的说明，请转到<https://docs.docker.com/docker-for-mac/>。</span><span class="sxs-lookup"><span data-stu-id="82a84-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="82a84-127">此外，你将需要代码编辑器，以便您实际上可以开发你的应用程序时使用 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="82a84-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="82a84-128">Microsoft 提供了 Visual Studio 代码，这是在 Mac、 Windows 和 Linux 上支持并提供包含 IntelliSense 的轻量代码编辑器[处理很多语言支持](https://code.visualstudio.com/docs/languages/overview)(JavaScript、.NET、 转到、 Java、 Ruby、 Python 和大多数现代的语言），[调试](https://code.visualstudio.com/Docs/editor/debugging)，[集成 Git 与](https://code.visualstudio.com/Docs/editor/versioncontrol)和[扩展支持](https://code.visualstudio.com/docs/extensions/overview)。</span><span class="sxs-lookup"><span data-stu-id="82a84-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="82a84-129">此编辑器是非常适合于 Mac 和 Linux 的开发人员。</span><span class="sxs-lookup"><span data-stu-id="82a84-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="82a84-130">在 Windows 中，你还可以使用完整的 Visual Studio 应用程序。</span><span class="sxs-lookup"><span data-stu-id="82a84-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="82a84-131">**详细信息** 安装 Visual Studio for Windows、 Mac 或 Linux 的说明，请转到[http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="82a84-132">您可以使用 Docker CLI 和写入你的代码使用任何代码编辑器中，但如果你使用 Visual Studio 代码，它使用户可以轻松对作者 Dockerfile 和 docker-compose.yml 文件在工作区中。</span><span class="sxs-lookup"><span data-stu-id="82a84-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="82a84-133">此外，你可以从 IDE 它会提示用户可以使用下方的 Docker CLI 的详细的操作运行的脚本运行 Visual Studio Code 任务。</span><span class="sxs-lookup"><span data-stu-id="82a84-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="82a84-134">通过扩展，你将需要安装提供了 visual Studio 代码。</span><span class="sxs-lookup"><span data-stu-id="82a84-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="82a84-135">为此，请按 Ctrl + Shift + P，键入**ext 安装**，然后运行扩展： 安装的扩展插件命令以显示应用商店扩展列表。</span><span class="sxs-lookup"><span data-stu-id="82a84-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="82a84-136">接下来，键入**docker**要筛选的结果，然后选择 Dockerfile 和 Docker Compose 文件 (yml) 支持扩展，如下图所示图 4-16。</span><span class="sxs-lookup"><span data-stu-id="82a84-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="82a84-137">图 4-16： 在 Visual Studio Code 中安装 Docker 扩展</span><span class="sxs-lookup"><span data-stu-id="82a84-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="82a84-138">步骤 2： 创建与现有映像 （纯 OS 或开发人员环境类似于.NET 核心、 Node.js 和 Ruby） 相关的 DockerFile</span><span class="sxs-lookup"><span data-stu-id="82a84-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="82a84-139">你将需要每个要生成的自定义图像和每个要部署的容器的 DockerFile，因此，如果你的应用程序组成单个自定义服务，你将需要单个 DockerFile。</span><span class="sxs-lookup"><span data-stu-id="82a84-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="82a84-140">但是，如果你的应用程序组成 （如所示的微服务体系结构） 的多个服务，你将需要每个服务的一个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="82a84-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="82a84-141">DockerFile 通常放置在你的应用或服务的根文件夹内，并包含所需的命令，这样该 Docker 就知道如何设置和运行该应用程序或服务。</span><span class="sxs-lookup"><span data-stu-id="82a84-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="82a84-142">你可以创建 DockerFile 并将其添加到你的项目以及你的代码 (node.js，.NET 核心等)，或者，如果你不熟悉的环境，看一看以下提示。</span><span class="sxs-lookup"><span data-stu-id="82a84-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="82a84-143">你可以使用命令行工具调用[则 docker](https://github.com/Microsoft/generator-docker)，其中的基架你项目中，选择并添加所需的 Docker 配置文件的语言中的文件。</span><span class="sxs-lookup"><span data-stu-id="82a84-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="82a84-144">基本上，以帮助开发人员入门，它创建相应的 DockerFile，docker-compose.yml 和其他关联的脚本，以生成并运行你的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="82a84-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="82a84-145">此 yeoman 生成器将提示你使用几个问题，要求你所选的开发语言和目标容器主机。</span><span class="sxs-lookup"><span data-stu-id="82a84-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![则 docker](./media/image21.png)

<span data-ttu-id="82a84-147">例如，图 4-17 显示终端中的两个屏幕快照，在 Windows 中，在 Mac 上，在这两种情况下，运行则 docker，将生成的示例代码项目 （当前.NET 核心、 Golang 和 Node.js 用作受支持的语言） 已配置为在上工作Docker 的顶部。</span><span class="sxs-lookup"><span data-stu-id="82a84-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="82a84-148">图 4-17： 则 docker 命令在 Windows （左） 和在 Mac 上的工具</span><span class="sxs-lookup"><span data-stu-id="82a84-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="82a84-149">图 4-18 提供了示例则 docker 后使用你的位置，以将基架的一个现有的.NET 核心项目。</span><span class="sxs-lookup"><span data-stu-id="82a84-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="82a84-150">图 4-18： 则使用现有的.NET 核心 docker 项目就地</span><span class="sxs-lookup"><span data-stu-id="82a84-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="82a84-151">从此 DockerFile，你指定哪些基本的 Docker 映像，你将使用 （如使用"发件人 microsoft/dotnet:1.0.0-core"）。</span><span class="sxs-lookup"><span data-stu-id="82a84-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="82a84-152">你通常将生成你在你可以从在任何官方存储库获取的基本映像之上的自定义映像[Docker Hub 注册表](https://hub.docker.com/)(如[.NET Core 的映像](https://hub.docker.com/r/microsoft/dotnet/)或一个[for Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="82a84-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="82a84-153">***选项 a： 使用现有的官方 Docker 映像***</span><span class="sxs-lookup"><span data-stu-id="82a84-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="82a84-154">使用版本号语言堆栈的官方存储库，可确保相同的语言功能是可用 （包括开发、 测试和生产） 的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="82a84-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="82a84-155">以下是示例 DockerFile.NET 核心容器：</span><span class="sxs-lookup"><span data-stu-id="82a84-155">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="82a84-156">在这种情况下，它适用于 Linux 名为 microsoft/aspnetcore:1.0.1 使用正式的 ASP.NET 核心 Docker 映像的版本 1.0.1。</span><span class="sxs-lookup"><span data-stu-id="82a84-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="82a84-157">有关更多详细信息，请查阅[ASP.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/aspnetcore/)和[.NET Core Docker 映像页](https://hub.docker.com/r/microsoft/dotnet/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="82a84-158">你还可能正在使用另一可比较的映像，如节点： 4-Node.js，或对于开发语言，可在许多其他预配置的映像的 onbuild [Docker Hub](https://hub.docker.com/explore/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="82a84-159">DockerFile，还需要指示 Docker 侦听到将在运行时 （如端口 80） 使用的 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="82a84-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="82a84-160">有其他行的这样 Docker 就知道如何运行该应用程序可以在具体取决于你使用的，语言/框架 DockerFile 中添加的配置。</span><span class="sxs-lookup"><span data-stu-id="82a84-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="82a84-161">例如，你需要使用的入口点行\["dotnet"，"MyCustomMicroservice.dll"\]运行.NET 核心应用程序中，虽然您可以有多个不同版本，具体取决于生成并运行你的服务的方法。</span><span class="sxs-lookup"><span data-stu-id="82a84-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="82a84-162">如果你正在使用的 SDK 和 dotnet CLI 生成并运行.NET 应用程序，则将为略有不同。</span><span class="sxs-lookup"><span data-stu-id="82a84-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="82a84-163">底部行是入口点行加上其他行将无法为应用程序选择的语言/平台而异。</span><span class="sxs-lookup"><span data-stu-id="82a84-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="82a84-164">**详细信息** 有关构建.NET Core 应用程序的 Docker 映像的信息，请转到<https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>。</span><span class="sxs-lookup"><span data-stu-id="82a84-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="82a84-165">若要了解有关生成你自己的映像的详细信息，请转到[https://docs.docker.com/engine/ \教程/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="82a84-166">**多平台映像存储库**</span><span class="sxs-lookup"><span data-stu-id="82a84-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="82a84-167">当 Windows 容器变得更为普遍，到单个存储库可以包含平台的不同版本，如的 Linux 和 Windows 映像。</span><span class="sxs-lookup"><span data-stu-id="82a84-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="82a84-168">这是即将在使供应商可以使用单个存储库来涵盖多个平台，例如的 Docker 中的新功能[microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)存储库，则可以从 DockerHub 注册表。</span><span class="sxs-lookup"><span data-stu-id="82a84-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="82a84-169">如功能处于活动状态时，从 Windows 主机提取此映像将请求的 Windows 变体，而从 Linux 主机提取相同的映像名称将请求 Linux 变体。</span><span class="sxs-lookup"><span data-stu-id="82a84-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="82a84-170">***选项 b： 创建您从零开始的基础映像***</span><span class="sxs-lookup"><span data-stu-id="82a84-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="82a84-171">你可以从头开始创建你自己 Docker 的基本映像这中所述[文章](https://docs.docker.com/engine/userguide/eng-image/baseimages/)从 Docker。</span><span class="sxs-lookup"><span data-stu-id="82a84-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="82a84-172">这是如果您刚开始使用 Docker，则可能不适合你的方案，但如果你想要设置自己的基本映像的特定位，你可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="82a84-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="82a84-173">步骤 3： 创建自定义 Docker 映像中嵌入你的服务</span><span class="sxs-lookup"><span data-stu-id="82a84-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="82a84-174">对于每个自定义服务，它包含你的应用程序，你将需要创建相关的映像。</span><span class="sxs-lookup"><span data-stu-id="82a84-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="82a84-175">如果你的应用程序进行的单个服务或 web 应用程序，你将需要单个映像。</span><span class="sxs-lookup"><span data-stu-id="82a84-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="82a84-176">时考虑到"外部循环 DevOps workflow"，图像将创建由自动的生成过程以便将该全局环境中创建映像到 Git 存储库 （持续集成） 推送你的源代码时从你源代码。</span><span class="sxs-lookup"><span data-stu-id="82a84-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="82a84-177">但是，我们考虑转到该外部循环路由之前，我们需要确保该 Docker 应用程序实际正常工作，以便它们不推送到源代码管理系统 （Git 等） 可能无法正常工作的代码。</span><span class="sxs-lookup"><span data-stu-id="82a84-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="82a84-178">因此，每个开发人员首先需要为整个的内部循环过程，以本地测试，并在继续开发直到他们想要推送完整的功能或将更改为源代码管理系统。</span><span class="sxs-lookup"><span data-stu-id="82a84-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="82a84-179">若要在本地环境和使用 DockerFile 创建映像，你可以使用 docker 生成命令，在图 4-19 中所示 (你还可以运行 docker compose 向上-生成适用于由多个容器/服务的应用程序)。</span><span class="sxs-lookup"><span data-stu-id="82a84-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="82a84-180">图 4-19： 运行 docker 生成</span><span class="sxs-lookup"><span data-stu-id="82a84-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="82a84-181">（可选） 而不是直接运行 docker 生成从项目的文件夹，则第一次可以生成可部署文件夹与通过使用运行的 dotnet 将发布命令，以及然后运行 docker 生成所需的.NET 库。</span><span class="sxs-lookup"><span data-stu-id="82a84-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="82a84-182">在此示例中，这将创建的 Docker 映像名称 cesardl/netcore webapi-微服务构成的 docker： 第一个 (: 首先是一个标记，如特定版本)。</span><span class="sxs-lookup"><span data-stu-id="82a84-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="82a84-183">你可以执行每个自定义映像与多个容器的 Docker 应用程序由你需要创建此步骤。</span><span class="sxs-lookup"><span data-stu-id="82a84-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="82a84-184">你可以找到现有的映像在本地存储库 （你的开发计算机） 使用 docker 映像命令，在图 4-20 中所示。</span><span class="sxs-lookup"><span data-stu-id="82a84-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="82a84-185">图 4-20： 查看现有的映像使用 docker 映像</span><span class="sxs-lookup"><span data-stu-id="82a84-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="82a84-186">步骤 4: （可选） 定义中 docker-compose.yml 生成包含多个服务的组合的 Docker 应用程序时你的服务</span><span class="sxs-lookup"><span data-stu-id="82a84-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="82a84-187">与 docker-compose.yml 文件可以定义一组相关的服务，若要部署为一个由应用程序使用部署命令下, 一步的步骤节中所述。</span><span class="sxs-lookup"><span data-stu-id="82a84-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="82a84-188">你需要创建该文件在你 main 中的或根解决方案文件夹;它应该类似内容以下 docker-compose.yml 文件：</span><span class="sxs-lookup"><span data-stu-id="82a84-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="82a84-189">在此特定情况下，此文件定义两个服务： web 服务 （你的自定义服务） 和 redis 服务 （常用缓存服务）。</span><span class="sxs-lookup"><span data-stu-id="82a84-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="82a84-190">将作为容器，部署每个服务，因此我们需要使用每个具体的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="82a84-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="82a84-191">对于此特定的 web 服务，映像将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82a84-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="82a84-192">中的当前目录中 DockerFile 生成</span><span class="sxs-lookup"><span data-stu-id="82a84-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="82a84-193">转发的公开的端口 80 容器主机上的端口 81 上</span><span class="sxs-lookup"><span data-stu-id="82a84-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="82a84-194">使你能够修改代码而无需重新生成映像的容器内的 /code 到主机上装载项目目录</span><span class="sxs-lookup"><span data-stu-id="82a84-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="82a84-195">链接到 redis 服务的 web 服务</span><span class="sxs-lookup"><span data-stu-id="82a84-195">Link the web service to the redis service</span></span>

<span data-ttu-id="82a84-196">Redis 服务使用[最新的公共 redis 映像](https://hub.docker.com/_/redis/)从 Docker Hub 注册表中提取。</span><span class="sxs-lookup"><span data-stu-id="82a84-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="82a84-197">[redis](http://redis.io/)是一个非常受欢迎的缓存系统，用于服务器端应用程序。</span><span class="sxs-lookup"><span data-stu-id="82a84-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="82a84-198">步骤 5： 生成并运行你的 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="82a84-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="82a84-199">如果你的应用程序仅单个容器，你只需通过将其部署到你的 Docker 主机 （VM 或物理服务器） 中运行它。</span><span class="sxs-lookup"><span data-stu-id="82a84-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="82a84-200">但是，如果你的应用程序由多个服务组成，则需要*拆分组合*也。</span><span class="sxs-lookup"><span data-stu-id="82a84-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="82a84-201">我们来看的不同选项。</span><span class="sxs-lookup"><span data-stu-id="82a84-201">Let's see the different options.</span></span>

<span data-ttu-id="82a84-202">***选项 a： 运行单个容器或服务***</span><span class="sxs-lookup"><span data-stu-id="82a84-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="82a84-203">你可以通过使用 docker 运行命令，如下所示运行 Docker 映像：</span><span class="sxs-lookup"><span data-stu-id="82a84-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="82a84-204">请注意，对于此特定的部署，我们将会重定向请求发送到端口 80 到内部端口 5000。</span><span class="sxs-lookup"><span data-stu-id="82a84-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="82a84-205">现在，应用程序正在侦听的外部端口 80 主机级别。</span><span class="sxs-lookup"><span data-stu-id="82a84-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="82a84-206">***选项 b: Compose 和运行多个容器应用程序***</span><span class="sxs-lookup"><span data-stu-id="82a84-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="82a84-207">在大多数的企业方案中，Docker 应用程序将组成多个服务。</span><span class="sxs-lookup"><span data-stu-id="82a84-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="82a84-208">对于这些情况下，你可以运行命令 docker compose 向上 (图 4-21)，它将使用先前可能已创建 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="82a84-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="82a84-209">运行此命令将部署一个由具有其所有相关容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="82a84-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="82a84-210">图 4-21： 的运行"docker-撰写向上"命令的结果</span><span class="sxs-lookup"><span data-stu-id="82a84-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="82a84-211">在运行 docker 后-向上撰写，你将部署你的应用程序和其相关的容器到 Docker 主机中, 所示在图 4-22，VM 表示形式。</span><span class="sxs-lookup"><span data-stu-id="82a84-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="82a84-212">图 4-22: VM 与部署的 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="82a84-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="82a84-213">请注意 docker-撰写向上和 docker 运行可能足够用于测试你的容器在开发环境中，但你可能根本不使用它们如果你预期使用 Docker 群集和 orchestrators 喜欢 Docker Swarm、 Mesosphere DC/OS 或 Kubernetes为了能够向上扩展。</span><span class="sxs-lookup"><span data-stu-id="82a84-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="82a84-214">如果你使用的群集，例如[Docker Swarm 模式](https://docs.docker.com/engine/swarm/)（在用于 Windows 的 Docker 和 Mac 自之后可用版本 1.12），你需要部署和测试与其他命令，例如 docker 服务创建为单个服务，或者如果已部署应用程序组成几个容器，使用 docker compose 捆绑和 docker 通过文章中所述，作为堆栈，部署由应用程序部署 myBundleFile，[分布式应用程序捆绑包](https://blog.docker.com/2016/06/docker-app-bundle/)从 Docker。</span><span class="sxs-lookup"><span data-stu-id="82a84-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="82a84-215">有关[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/)和[Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment)你会使用不同的部署命令和脚本，以及。</span><span class="sxs-lookup"><span data-stu-id="82a84-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="82a84-216">步骤 6： 测试 Docker 应用程序 （在本地，你的本地 CD VM)</span><span class="sxs-lookup"><span data-stu-id="82a84-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="82a84-217">此步骤根据你的应用程序正在执行什么操作会有所不同。</span><span class="sxs-lookup"><span data-stu-id="82a84-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="82a84-218">在非常简单.NET 核心 Web API"Hello World"部署为单个容器或服务，你只需通过提供 DockerFile 中指定的 TCP 端口访问服务。</span><span class="sxs-lookup"><span data-stu-id="82a84-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="82a84-219">如果 localhost 未打开，以导航到你的服务，则使用此命令的 IP 地址查找机：</span><span class="sxs-lookup"><span data-stu-id="82a84-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="82a84-220">docker 机 ip*你的容器名称*</span><span class="sxs-lookup"><span data-stu-id="82a84-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="82a84-221">在 Docker 主机上，打开浏览器并导航到该站点;图 4-23 所示，你应该看到你的应用程序/服务正在运行、。</span><span class="sxs-lookup"><span data-stu-id="82a84-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="82a84-222">图 4-23： 测试本地使用 localhost Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="82a84-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="82a84-223">请注意，则使用端口 80，但它已在内部重定向到端口 5000，因为这是它的部署方式使用 docker 运行，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="82a84-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="82a84-224">你可以通过从终端使用 CURL 来测试此。</span><span class="sxs-lookup"><span data-stu-id="82a84-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="82a84-225">在 Windows 上的 Docker 安装，默认 IP 是 10.0.75.1，如下图所示图 4-24。</span><span class="sxs-lookup"><span data-stu-id="82a84-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="82a84-226">图 4-24： 通过使用 CURL 在本地测试 Docker 应用程序</span><span class="sxs-lookup"><span data-stu-id="82a84-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="82a84-227">**调试在 Docker 上运行的容器**</span><span class="sxs-lookup"><span data-stu-id="82a84-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="82a84-228">Visual Studio Code 支持调试 Docker，如果你使用 Node.js 和其他平台，如.NET Core 容器。</span><span class="sxs-lookup"><span data-stu-id="82a84-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="82a84-229">你还可以调试在 Docker 中的.NET Core 容器时使用 Visual Studio 中下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="82a84-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="82a84-230">**详细信息：** 若要了解有关调试 Node.js Docker 容器的详细信息，请转到<https://blog.docker.com/2016/07/live-debugging-docker/>和[https://blogs.msdn.microsoft.com/\ 用户\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)。</span><span class="sxs-lookup"><span data-stu-id="82a84-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="82a84-231">[以前](docker-应用程序的开发-environment.md) [下一步] (visual-studio 的工具的对于-docker.md)</span><span class="sxs-lookup"><span data-stu-id="82a84-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
