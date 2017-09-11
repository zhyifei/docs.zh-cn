---
title: "生成 .NET Core Docker 映像"
description: "了解 Docker 映像和 .NET Core"
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: zh-cn
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="a0742-104">为 .NET Core 应用程序生成 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="a0742-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="a0742-105">我们正在更新 .NET Core 2.0。</span><span class="sxs-lookup"><span data-stu-id="a0742-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="a0742-106">以下说明不是最新版本。</span><span class="sxs-lookup"><span data-stu-id="a0742-106">The instructions below are out of date.</span></span> <span data-ttu-id="a0742-107">对于带来的任何不便，我们深表歉意！</span><span class="sxs-lookup"><span data-stu-id="a0742-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="a0742-108">若要了解如何将 .NET Core 和 Docker 配合使用，首先必须了解所提供的不同 Docker 映像以及何时使用才是正确的。</span><span class="sxs-lookup"><span data-stu-id="a0742-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="a0742-109">下面将介绍所提供的变体、生成 ASP.NET Core Web API，使用 Yeoman Docker 工具以创建可调试容器的内容，以及快速浏览了 Visual Studio Code 如何在该过程中起到辅助的作用。</span><span class="sxs-lookup"><span data-stu-id="a0742-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="a0742-110">Docker 映像优化</span><span class="sxs-lookup"><span data-stu-id="a0742-110">Docker Image Optimizations</span></span>

<span data-ttu-id="a0742-111">为开发人员生成 Docker 映像时，侧重于以下三种主要方案：</span><span class="sxs-lookup"><span data-stu-id="a0742-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="a0742-112">用于开发 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="a0742-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="a0742-113">用于生成 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="a0742-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="a0742-114">用于运行 .NET Core 应用的映像</span><span class="sxs-lookup"><span data-stu-id="a0742-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="a0742-115">为什么是三个映像？</span><span class="sxs-lookup"><span data-stu-id="a0742-115">Why three images?</span></span>
<span data-ttu-id="a0742-116">因为在开发、生成和运行容器化应用程序时，具有不同的优先级。</span><span class="sxs-lookup"><span data-stu-id="a0742-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="a0742-117">**开发：**决定循环访问更改的速度以及调试更改的能力。</span><span class="sxs-lookup"><span data-stu-id="a0742-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="a0742-118">与更改代码并且快速查看相比，映像的大小则不是那么重要。</span><span class="sxs-lookup"><span data-stu-id="a0742-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="a0742-119">一些用于 Visual Studio Code 的工具（如 [yo docker](https://aka.ms/yodocker)）在开发期间使用此映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="a0742-120">**生成：**编译应用所需的内容。</span><span class="sxs-lookup"><span data-stu-id="a0742-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="a0742-121">这包括编译器和任何优化二进制文件的其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0742-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="a0742-122">此映像不是部署的映像，而是用于生成放置在生产映像中的内容的映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="a0742-123">此映像将用于持续集成或者生成环境中。</span><span class="sxs-lookup"><span data-stu-id="a0742-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="a0742-124">例如，生成代理会以生成映像为实例，使用生成包含在映像内的应用所需的全部依赖项来编译应用程序，而不是直接在生成代理上安装所有的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0742-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="a0742-125">生成代理只需要了解如何运行此 Docker 映像即可。</span><span class="sxs-lookup"><span data-stu-id="a0742-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="a0742-126">**生产：**决定部署和启动映像的速度。</span><span class="sxs-lookup"><span data-stu-id="a0742-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="a0742-127">此映像很小，因此可以快速地通过网络从 Docker 注册表传输到 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="a0742-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="a0742-128">已准备运行内容，以此实现从 Docker 运行到处理结果的最快时间。</span><span class="sxs-lookup"><span data-stu-id="a0742-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="a0742-129">在不可变 Docker 模型中，不需要动态编译代码。</span><span class="sxs-lookup"><span data-stu-id="a0742-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="a0742-130">放置在此映像中的内容将限制为运行应用程序所需的二进制文件和内容。</span><span class="sxs-lookup"><span data-stu-id="a0742-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="a0742-131">例如，使用 `dotnet publish` 的已发布输出，其中包含已编译的二进制文件、映像、.js 和 .css 文件。</span><span class="sxs-lookup"><span data-stu-id="a0742-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="a0742-132">随着时间的推移，用户将看到包含预实时编译的包。</span><span class="sxs-lookup"><span data-stu-id="a0742-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="a0742-133">虽然 .NET Core 映像有多个版本，但它们全都共享一个或多个层。</span><span class="sxs-lookup"><span data-stu-id="a0742-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="a0742-134">存储所需的磁盘空间量或从注册表中拉取的增量比整个磁盘空间量要小得多，因为所有映像都共享同一基本层，或可能共享其他层。</span><span class="sxs-lookup"><span data-stu-id="a0742-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="a0742-135">Docker 映像变体</span><span class="sxs-lookup"><span data-stu-id="a0742-135">Docker image variations</span></span>

<span data-ttu-id="a0742-136">为了实现上述目标，我们在 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) 下提供了映像变体。</span><span class="sxs-lookup"><span data-stu-id="a0742-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="a0742-137">`microsoft/dotnet:<version>-sdk`：即 **microsoft/dotnet:1.0.0-preview2-sdk**，此映像包含带有 .NET Core 和命令行工具 (CLI) 的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="a0742-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="a0742-138">此映像将映射到**开发方案**。</span><span class="sxs-lookup"><span data-stu-id="a0742-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="a0742-139">使用此映像进行本地开发、调试和单元测试。</span><span class="sxs-lookup"><span data-stu-id="a0742-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="a0742-140">例如，在签入代码前进行的所有开发。</span><span class="sxs-lookup"><span data-stu-id="a0742-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="a0742-141">此映像还可用于**生成**方案。</span><span class="sxs-lookup"><span data-stu-id="a0742-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="a0742-142">`microsoft/dotnet:<version>-core`：即 **microsoft/dotnet:1.0.0-core**，它是运行[可移植 .NET Core 应用程序](../deploying/index.md)的映像，并且针对在**生产**中运行应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="a0742-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="a0742-143">它不包含 SDK，并且会使用 `dotnet publish` 的优化输出。</span><span class="sxs-lookup"><span data-stu-id="a0742-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="a0742-144">可移植运行时非常适合 Docker 容器方案，因为共享的映像层利于运行多个容器。</span><span class="sxs-lookup"><span data-stu-id="a0742-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="a0742-145">备用映像</span><span class="sxs-lookup"><span data-stu-id="a0742-145">Alternative images</span></span>

<span data-ttu-id="a0742-146">除了开发、生成和生产的优化方案外，我们还提供了其他映像：</span><span class="sxs-lookup"><span data-stu-id="a0742-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="a0742-147">`microsoft/dotnet:<version>-onbuild`：即 **microsoft/dotnet:1.0.0-preview2-onbuild**，其中包含 [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) 触发器。</span><span class="sxs-lookup"><span data-stu-id="a0742-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="a0742-148">生成将 [COPY](https://docs.docker.com/engine/reference/builder/#/copy)（复制）应用程序，运行 `dotnet restore` 并创建 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` 指令，以在运行 Docker 映像时运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0742-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="a0742-149">在使用未针对生产进行优化的映像时，某些用户可能发现只将源代码复制到映像中并运行它会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="a0742-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="a0742-150">`microsoft/dotnet:<version>-core-deps`：即 **microsoft/dotnet:1.0.0-core-deps**，请在希望运行独立应用程序时使用此映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="a0742-151">它包括具有 .NET Core 所需的所有本机依赖项的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a0742-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="a0742-152">此映像也可用作自己自定义 CoreFX 或 CoreCLR 版本的基本映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="a0742-153">虽然 onbuild 变量已优化为只将代码放入映像并运行它，但此映像已优化为只包含运行 .NET Core 应用程序（将 .NET 运行时与应用程序一起打包）所需的操作系统依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0742-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="a0742-154">通常，优化此映像不是为了在同一主机上运行多个 .NET Core 容器，因为每个映像在应用程序内都具有 .NET Core 运行时，映像分层则不会带来益处。</span><span class="sxs-lookup"><span data-stu-id="a0742-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="a0742-155">每个变体的最新版本：</span><span class="sxs-lookup"><span data-stu-id="a0742-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="a0742-156">`microsoft/dotnet` 或 `microsoft/dotnet:latest`（包括 SDK）</span><span class="sxs-lookup"><span data-stu-id="a0742-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="a0742-157">以下是开发计算机上使用 `docker pull <imagename>` 命令后出现的映像列表，其中显示多个映像的大小。</span><span class="sxs-lookup"><span data-stu-id="a0742-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="a0742-158">请注意，其中开发/生成变体 `microsoft/dotnet:1.0.0-preview2-sdk` 较大，因为它包含用于开发和生成应用程序的 SDK。</span><span class="sxs-lookup"><span data-stu-id="a0742-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="a0742-159">生产变体 `microsoft/dotnet:core` 较小，因为它仅包含 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="a0742-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="a0742-160">虽然能够在 Linux 上使用的最小映像 `core-deps` 较小，但应用程序仍需要使用它复制 .NET 运行时的私有副本。</span><span class="sxs-lookup"><span data-stu-id="a0742-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="a0742-161">由于容器已是私有的隔离屏障，因此运行多个基于 dotnet 的容器时优化会失效。</span><span class="sxs-lookup"><span data-stu-id="a0742-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="a0742-162">先决条件</span><span class="sxs-lookup"><span data-stu-id="a0742-162">Prerequisites</span></span>

<span data-ttu-id="a0742-163">若要生成和运行，需要安装以下几个程序：</span><span class="sxs-lookup"><span data-stu-id="a0742-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="a0742-164">.NET Core</span><span class="sxs-lookup"><span data-stu-id="a0742-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="a0742-165">[Docker](https://www.docker.com/products/docker)：能够在本地运行 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="a0742-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="a0742-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="a0742-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="a0742-167">[适用于 ASP.NET 的 Yeoman 生成器](https://github.com/omnisharp/generator-aspnet)：用于创建 Web API 应用程序</span><span class="sxs-lookup"><span data-stu-id="a0742-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="a0742-168">来自 Microsoft 的[适用于 Docker 的 Yeoman 生成器](http://aka.ms/yodocker)</span><span class="sxs-lookup"><span data-stu-id="a0742-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="a0742-169">使用 npm 安装适用于 ASP.NET Core 和 Docker 的 Yeoman 生成器</span><span class="sxs-lookup"><span data-stu-id="a0742-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="a0742-170">此示例将使用适用于编辑器的 [Visual Studio Code](http://code.visualstudio.com)。</span><span class="sxs-lookup"><span data-stu-id="a0742-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="a0742-171">创建 Web API 应用程序</span><span class="sxs-lookup"><span data-stu-id="a0742-171">Creating the Web API application</span></span>

<span data-ttu-id="a0742-172">对于引用点，在容器化应用程序之前，请先在本地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0742-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="a0742-173">完成的应用程序位于 [GitHub 上的 dotnet/docs 存储库](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images)。</span><span class="sxs-lookup"><span data-stu-id="a0742-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="a0742-174">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。</span><span class="sxs-lookup"><span data-stu-id="a0742-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a0742-175">为应用程序创建目录。</span><span class="sxs-lookup"><span data-stu-id="a0742-175">Create a directory for your application.</span></span>

<span data-ttu-id="a0742-176">打开命令或该目录中的终端会话，然后通过键入以下内容使用 ASP.NET Yeoman 生成器：</span><span class="sxs-lookup"><span data-stu-id="a0742-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="a0742-177">选择“Web API 应用程序”，键入应用名称的 **api**，然后点击进入。</span><span class="sxs-lookup"><span data-stu-id="a0742-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="a0742-178">搭建好应用程序后，更改为 `/api` 目录，并使用 `dotnet restore` 还原 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0742-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="a0742-179">使用 `dotnet run` 测试应用程序并浏览到 **http://localhost:5000/api/values**</span><span class="sxs-lookup"><span data-stu-id="a0742-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="a0742-180">使用 `Ctrl+C` 停止应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0742-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="a0742-181">添加 Docker 支持</span><span class="sxs-lookup"><span data-stu-id="a0742-181">Adding Docker support</span></span>

<span data-ttu-id="a0742-182">使用来自 Microsoft 的 Yeoman 生成器可向项目添加 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="a0742-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="a0742-183">目前它通过创建有助于在容器内生成并运行项目的 Dockerfile 和脚本，以支持 .NET Core、Node.js 和 Go 项目。</span><span class="sxs-lookup"><span data-stu-id="a0742-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="a0742-184">还添加了特定于 Visual Studio Code 的文件（launch.json、tasks.json），用于编辑器调试和命令面板支持。</span><span class="sxs-lookup"><span data-stu-id="a0742-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="a0742-185">选择 `.NET Core` 作为项目类型</span><span class="sxs-lookup"><span data-stu-id="a0742-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="a0742-186">`rtm` 用作 .NET Core 的版本</span><span class="sxs-lookup"><span data-stu-id="a0742-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="a0742-187">`Y` 表示项目使用 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="a0742-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="a0742-188">`5000` 是 Web API 应用程序正在侦听的端口数 (http://localhost:5000)</span><span class="sxs-lookup"><span data-stu-id="a0742-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="a0742-189">`api` 用作映像名称</span><span class="sxs-lookup"><span data-stu-id="a0742-189">`api` for the image name</span></span>
- <span data-ttu-id="a0742-190">`api` 用作服务名称</span><span class="sxs-lookup"><span data-stu-id="a0742-190">`api` for the service name</span></span>
- <span data-ttu-id="a0742-191">`api` 用作组成项目</span><span class="sxs-lookup"><span data-stu-id="a0742-191">`api` for the compose project</span></span> 
- <span data-ttu-id="a0742-192">`Y` 表示要覆盖当前 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a0742-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="a0742-193">完成生成器时，以下文件将添加到项目中</span><span class="sxs-lookup"><span data-stu-id="a0742-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="a0742-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="a0742-194">.vscode/launch.json</span></span>
- <span data-ttu-id="a0742-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="a0742-195">Dockerfile.debug</span></span>
- <span data-ttu-id="a0742-196">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a0742-196">Dockerfile</span></span>
- <span data-ttu-id="a0742-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="a0742-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="a0742-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="a0742-198">docker-compose.yml</span></span>
- <span data-ttu-id="a0742-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="a0742-199">dockerTask.ps1</span></span>
- <span data-ttu-id="a0742-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="a0742-200">dockerTask.sh</span></span>
- <span data-ttu-id="a0742-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="a0742-201">.vscode/tasks.json</span></span>

<span data-ttu-id="a0742-202">生成器将创建两个 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="a0742-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="a0742-203">**Dockerfile.debug** - 此文件基于从映像变体的列表中的 **microsoft/dotnet:1.0.0-preview2-sdk** 映像（如有注意到），其中包括 SDK、CLI 和.NET Core，而这是用于开发和调试 (F5) 的映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="a0742-204">包括所有这些组件将生成大约为 540MB 的较大映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="a0742-205">**Dockerfile** - 此映像是基于 **microsoft/dotnet:1.0.0-core** 的发布映像，并且应该用于生产。</span><span class="sxs-lookup"><span data-stu-id="a0742-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="a0742-206">此映像生成时大约为 253MB。</span><span class="sxs-lookup"><span data-stu-id="a0742-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="a0742-207">创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="a0742-207">Creating the Docker images</span></span>
<span data-ttu-id="a0742-208">使用 `dockerTask.sh` 或 `dockerTask.ps1` 脚本，可以生成或编写用于特定环境的 **api** 应用程序的映像和容器。</span><span class="sxs-lookup"><span data-stu-id="a0742-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="a0742-209">运行以下命令生成**调试**映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="a0742-210">映像将生成 ASP.NET 应用程序，运行 `dotnet restore`，将调试程序添加到映像，设置 `ENTRYPOINT`，最后将应用复制到该映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="a0742-211">结果是名为 *api* 的 Docker 映像，并且具有 *debug* 的 `TAG`。</span><span class="sxs-lookup"><span data-stu-id="a0742-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="a0742-212">使用 `docker images` 查看计算机上的映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="a0742-213">生成映像并在 Docker 容器内运行应用程序的另一种方法是在 Visual Studio Code 中打开该应用程序，然后使用调试工具。</span><span class="sxs-lookup"><span data-stu-id="a0742-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="a0742-214">在 Visual Studio Code 左侧的“视图栏”中，选择“调试”图标。</span><span class="sxs-lookup"><span data-stu-id="a0742-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![vscode 调试图标](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="a0742-216">然后点击“播放”图标或按 F5 生成映像并在容器内启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0742-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="a0742-217">会使用默认的 Web 浏览器在 http://localhost:5000 中启动 Web API。</span><span class="sxs-lookup"><span data-stu-id="a0742-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![VSCode Docker 工具调试](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="a0742-219">可以在应用程序中以及单步调试等过程中设置断点，就如在开发计算机上本地运行应用程序一样，而不是在容器内运行。</span><span class="sxs-lookup"><span data-stu-id="a0742-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="a0742-220">利于在容器内进行调试的映像需要是将部署到生产环境的同一映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="a0742-221">创建发布或生产映像只需从传递 `release` 环境名称的终端中运行命令即可。</span><span class="sxs-lookup"><span data-stu-id="a0742-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="a0742-222">命令会基于较小的 **microsoft / dotnet:core** 基本映像和 [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) 端口 5000 创建映像，为 `dotnet api.dll`设置 [ENTYRPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint)，然后将其复制到 `/app` 目录。</span><span class="sxs-lookup"><span data-stu-id="a0742-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="a0742-223">在如此小的映像中不会生成任何调试程序、SDK 或 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="a0742-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="a0742-224">映像名为 **api**，并且具有**最新**的 `TAG`。</span><span class="sxs-lookup"><span data-stu-id="a0742-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="a0742-225">摘要</span><span class="sxs-lookup"><span data-stu-id="a0742-225">Summary</span></span>

<span data-ttu-id="a0742-226">使用 Docker 生成器将必要的文件添加到 Web API 应用程序，简化了创建映像的开发和生产版本的过程。</span><span class="sxs-lookup"><span data-stu-id="a0742-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="a0742-227">同时通过在对容器内的应用程序提供单步调试的 Windows 和 Visual Studio Code 集成上提供 PowerShell 脚本来达到相同结果，使工具也实现了跨平台。</span><span class="sxs-lookup"><span data-stu-id="a0742-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="a0742-228">通过了解映像变体和目标场景，可以优化内部循环开发过程，同时实现为生产部署优化映像。</span><span class="sxs-lookup"><span data-stu-id="a0742-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



