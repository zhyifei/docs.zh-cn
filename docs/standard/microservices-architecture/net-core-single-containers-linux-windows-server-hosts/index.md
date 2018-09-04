---
title: 在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用
description: 适用于容器化 .NET 应用程序的体系结构 | 在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: 45be99a86a52ed450b795ca5f91c01ab82c7da47
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539694"
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a><span data-ttu-id="19492-103">在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用</span><span class="sxs-lookup"><span data-stu-id="19492-103">Deploying Single-Container-Based .NET Core Web Applications on Linux or Windows Nano Server Hosts</span></span>

<span data-ttu-id="19492-104">_对于简单 Web 应用的整体部署，可以使用 Docker 容器。这样可以改进持续集成和持续部署管道，并有助于成功实现部署到生产环境。不再出现“为什么可以在我的计算机上正常运行，却不能在生产环境中正常运行？”的问题_</span><span class="sxs-lookup"><span data-stu-id="19492-104">_You can use Docker containers for monolithic deployment of simpler web applications. This improves continuous integration and continuous deployment pipelines and helps achieve deployment-to-production success. No more “It works in my machine, why does it not work in production?”_</span></span>

<span data-ttu-id="19492-105">基于微服务的体系结构具有许多优势，但以增加复杂性为代价。</span><span class="sxs-lookup"><span data-stu-id="19492-105">A microservices-based architecture has many benefits, but those benefits come at a cost of increased complexity.</span></span> <span data-ttu-id="19492-106">在某些情况下，成本超过了收益，在单个或几个容器中运行的单片式部署应用程序更为实用。</span><span class="sxs-lookup"><span data-stu-id="19492-106">In some cases, the costs outweigh the benefits and a monolithic deployment application running in one or a few containers is a better option.</span></span>

<span data-ttu-id="19492-107">单片式应用程序可能不易分解到独立性良好的微服务。</span><span class="sxs-lookup"><span data-stu-id="19492-107">A monolithic application might not be easily decomposable into well-separated microservices.</span></span> <span data-ttu-id="19492-108">你已经了解到，应按功能对微服务进行分区：它们应彼此独立运行，以提供复原能力更强的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19492-108">You've learned that these microservices should be partitioned by function: they should work independently of each other to provide a more resilient application.</span></span> <span data-ttu-id="19492-109">如果无法实现应用程序功能切片，将其分离只会增加复杂性。</span><span class="sxs-lookup"><span data-stu-id="19492-109">If you can't deliver feature slices of the application, separating it only adds complexity.</span></span>

<span data-ttu-id="19492-110">应用程序可能尚不需要独立地扩展功能。</span><span class="sxs-lookup"><span data-stu-id="19492-110">An application might not yet need to scale features independently.</span></span> <span data-ttu-id="19492-111">假设在 `eShopOnContainers` 参考应用程序的早期阶段，流量并未将分离的功能分配到不同的微服务。</span><span class="sxs-lookup"><span data-stu-id="19492-111">Let’s suppose that in the early stages of the `eShopOnContainers` reference application, the traffic didn't justify separating features into different microservices.</span></span> <span data-ttu-id="19492-112">流量足够小，为一项服务添加资源通常意味着为所有服务添加资源。</span><span class="sxs-lookup"><span data-stu-id="19492-112">Traffic was small enough that adding resources to one service typically meant adding resources to all services.</span></span> <span data-ttu-id="19492-113">将应用程序分离到成离散的服务是画蛇添足，提供的优势极小。</span><span class="sxs-lookup"><span data-stu-id="19492-113">The additional work to separate the application into discrete services provided minimal benefit.</span></span>

<span data-ttu-id="19492-114">此外，在应用程序开发前期，可能并不确定自然功能边界。</span><span class="sxs-lookup"><span data-stu-id="19492-114">Also, early in the development of an application you might not have a clear idea where the natural functional boundaries are.</span></span> <span data-ttu-id="19492-115">开发最小可独立产品时，自然分离可能尚未出现。</span><span class="sxs-lookup"><span data-stu-id="19492-115">As you develop a minimum viable product, the natural separation might not yet have emerged.</span></span>

<span data-ttu-id="19492-116">其中一些条件可能是临时的。</span><span class="sxs-lookup"><span data-stu-id="19492-116">Some of these conditions might be temporary.</span></span> <span data-ttu-id="19492-117">可首先创建单片式应用程序，稍后再分离要以微服务的形式开发和部署的某些功能。</span><span class="sxs-lookup"><span data-stu-id="19492-117">You might start by creating a monolithic application, and later separate some features to be developed and deployed as microservices.</span></span> <span data-ttu-id="19492-118">而另一些条件可能对应用程序的容错空间至关重要，这意味着应用程序可能永远无法分解到多个微服务。</span><span class="sxs-lookup"><span data-stu-id="19492-118">Other conditions might be essential to the application’s problem space, meaning that the application might never be broken into multiple microservices.</span></span>

<span data-ttu-id="19492-119">将应用程序分离到多个离散进程还会带来开销。</span><span class="sxs-lookup"><span data-stu-id="19492-119">Separating an application into many discrete processes also introduces overhead.</span></span> <span data-ttu-id="19492-120">将功能分离到不同的进程则更复杂。</span><span class="sxs-lookup"><span data-stu-id="19492-120">There's more complexity in separating features into different processes.</span></span> <span data-ttu-id="19492-121">通信协议会变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="19492-121">The communication protocols become more complex.</span></span> <span data-ttu-id="19492-122">在服务之间必须使用异步通信，而不得使用方法调用。</span><span class="sxs-lookup"><span data-stu-id="19492-122">Instead of method calls, you must use asynchronous communications between services.</span></span> <span data-ttu-id="19492-123">移动到微服务体系结构时，需要添加在 `eShopOnContainers` 应用程序的微服务版本中实现的许多构建基块：事件总线处理、消息复原和重试、最终一致性等。</span><span class="sxs-lookup"><span data-stu-id="19492-123">As you move to a microservices architecture, you need to add many of the building blocks implemented in the microservices version of the `eShopOnContainers` application: event bus handling, message resiliency and retries, eventual consistency, and more.</span></span>

<span data-ttu-id="19492-124">极简版的 eShopOnContainers（名为 [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 并包含在同一 GitHub 存储库中）作为单片式 MVC 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="19492-124">A much-simplified version of eShopOnContainers (named [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) and included in the same GitHub repository) runs as a monolithic MVC application.</span></span> <span data-ttu-id="19492-125">如上所述，选择这种设计带来了各种优势。</span><span class="sxs-lookup"><span data-stu-id="19492-125">As described, there are advantages offered by that design choice.</span></span> <span data-ttu-id="19492-126">可从 GitHub 下载此应用程序的源代码，并在本地运行。</span><span class="sxs-lookup"><span data-stu-id="19492-126">You can download the source for this application from GitHub and run it locally.</span></span> <span data-ttu-id="19492-127">即使是这一单片式应用程序，在容器环境中部署也是有益的。</span><span class="sxs-lookup"><span data-stu-id="19492-127">Even this monolithic application benefits from being deployed in a container environment.</span></span>

<span data-ttu-id="19492-128">其一，容器化部署意味着应用程序的每个实例都在同一环境中运行。</span><span class="sxs-lookup"><span data-stu-id="19492-128">For one, the containerized deployment means that every instance of the application runs in the same environment.</span></span> <span data-ttu-id="19492-129">这包括用于前期测试和开发的开发人员环境。</span><span class="sxs-lookup"><span data-stu-id="19492-129">This includes the developer environment where early testing and development take place.</span></span> <span data-ttu-id="19492-130">开发团队可在与生产环境完全相同的容器化环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="19492-130">The development team can run the application in a containerized environment that matches the production environment.</span></span>

<span data-ttu-id="19492-131">此外，容器化应用程序扩大成本较低。</span><span class="sxs-lookup"><span data-stu-id="19492-131">Also, containerized applications scale out at lower cost.</span></span> <span data-ttu-id="19492-132">如上文所示，容器环境比传统 VM 环境更有利于资源共享。</span><span class="sxs-lookup"><span data-stu-id="19492-132">As you saw earlier, the container environment enables greater resource sharing than traditional VM environments.</span></span>

<span data-ttu-id="19492-133">最后，容器化应用程序会强制分离业务逻辑和存储服务器。</span><span class="sxs-lookup"><span data-stu-id="19492-133">Finally, containerizing the application forces a separation between the business logic and the storage server.</span></span> <span data-ttu-id="19492-134">应用程序扩大时，各种容器将全部依赖于单个物理存储介质。</span><span class="sxs-lookup"><span data-stu-id="19492-134">As the application scales out, the various containers will all rely on a single physical storage medium.</span></span> <span data-ttu-id="19492-135">此存储通常是运行 SQL Server 数据库的高可用性服务器。</span><span class="sxs-lookup"><span data-stu-id="19492-135">This storage would typically be a high-availability server running a SQL Server database.</span></span>

## <a name="application-tour"></a><span data-ttu-id="19492-136">应用程序教程</span><span class="sxs-lookup"><span data-stu-id="19492-136">Application tour</span></span>

<span data-ttu-id="19492-137">[eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 应用程序代表着某些作为单片式应用程序运行的 eShopOnContainers 应用程序，即在 .NET Core 上运行的基于 ASP.NET Core MVC 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19492-137">The [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) application represents some of the eShopOnContainers application running as a monolithic application — an ASP.NET Core MVC-based application running on .NET Core.</span></span> <span data-ttu-id="19492-138">它主要提供前几节所述的目录浏览功能。</span><span class="sxs-lookup"><span data-stu-id="19492-138">It mainly provides the catalog browsing capabilities as described in earlier sections.</span></span>

<span data-ttu-id="19492-139">该应用程序使用 SQL Server 数据库实现目录存储。</span><span class="sxs-lookup"><span data-stu-id="19492-139">The application uses a SQL Server database for the catalog storage.</span></span> <span data-ttu-id="19492-140">在基于容器的部署中，此单片式应用程序与基于微服务的应用程序可访问相同的数据存储。</span><span class="sxs-lookup"><span data-stu-id="19492-140">In container-based deployments, this monolithic application can access the same data store as the microservices-based application.</span></span> <span data-ttu-id="19492-141">该应用程序配置为在与单片式应用程序并列的容器中运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="19492-141">The application is configured to run SQL Server in a container alongside the monolithic application.</span></span> <span data-ttu-id="19492-142">在生产环境中，SQL Server 会在 Docker 主机以外的高可用性计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="19492-142">In a production environment, SQL Server would run on a high-availability machine, outside of the Docker host.</span></span> <span data-ttu-id="19492-143">为方便起见，在开发或测试环境中，建议在自己的容器中运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="19492-143">For convenience, in a development or test environment, running SQL Server in its own container is recommended.</span></span>

<span data-ttu-id="19492-144">初始功能集仅提供浏览目录的功能。</span><span class="sxs-lookup"><span data-stu-id="19492-144">The initial feature set only enables browsing the catalog.</span></span> <span data-ttu-id="19492-145">通过更新实现容器化应用程序的完整功能集。</span><span class="sxs-lookup"><span data-stu-id="19492-145">Updates would enable the full feature set of the containerized application.</span></span> <span data-ttu-id="19492-146">在 [ASP.NET Web 应用体系结构实践](https://aka.ms/webappebook)电子书和相关 [eShopOnWeb 示例应用程序](https://aka.ms/WebAppArchitecture)中介绍了更高级的单片式 Web 应用体系结构。</span><span class="sxs-lookup"><span data-stu-id="19492-146">A more advanced monolithic web application architecture is described in the [ASP.NET Web Application architecture practices](https://aka.ms/webappebook) e-book and related [eShopOnWeb sample application](https://aka.ms/WebAppArchitecture).</span></span>

## <a name="docker-support"></a><span data-ttu-id="19492-147">Docker 支持</span><span class="sxs-lookup"><span data-stu-id="19492-147">Docker support</span></span>

<span data-ttu-id="19492-148">eShopOnWeb 项目在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="19492-148">The eShopOnWeb project runs on .NET Core.</span></span> <span data-ttu-id="19492-149">这意味着该项目可在基于 Linux 或基于 Windows 的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="19492-149">That means it can run in either Linux-based or Windows-based containers.</span></span> <span data-ttu-id="19492-150">请注意，在 Docker 部署中，请对 SQL Server 使用相同的主机类型。</span><span class="sxs-lookup"><span data-stu-id="19492-150">Note that for Docker deployment, you want to use the same host type for SQL Server.</span></span> <span data-ttu-id="19492-151">基于 Linux 的容器占用较小，是首选方案。</span><span class="sxs-lookup"><span data-stu-id="19492-151">Linux-based containers allow a smaller footprint and are preferred.</span></span>

<span data-ttu-id="19492-152">Visual Studio 提供了项目模板，可在解决方案中添加对 Docker 的支持。</span><span class="sxs-lookup"><span data-stu-id="19492-152">Visual Studio provides a project template that adds support for Docker to a solution.</span></span> <span data-ttu-id="19492-153">右键单击该项目，单击“Docker 支持”前的“添加”。</span><span class="sxs-lookup"><span data-stu-id="19492-153">You right-click the project, click **Add** followed by **Docker Support**.</span></span> <span data-ttu-id="19492-154">该模板会在项目中添加 Dockerfile 以及一个可提供初始 docker-compose.yml 文件的新 docker-compose 项目。</span><span class="sxs-lookup"><span data-stu-id="19492-154">The template adds a Dockerfile to your project, and a new **docker-compose** project that provides a starter *docker-compose.yml* file.</span></span> <span data-ttu-id="19492-155">从 GitHub 下载的 eShopOnWeb 项目中已完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="19492-155">This step has already been done in the eShopOnWeb project downloaded from GitHub.</span></span> <span data-ttu-id="19492-156">可看到该解决方案包含 eShopOnWeb 项目和 docker-compose 项目，如图 6-1 所示。</span><span class="sxs-lookup"><span data-stu-id="19492-156">You can see that the solution contains the **eShopOnWeb** project and the **docker-compose** project as shown in Figure 6-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="19492-157">**图 6-1**.</span><span class="sxs-lookup"><span data-stu-id="19492-157">**Figure 6-1**.</span></span> <span data-ttu-id="19492-158">单容器 Web 应用中的 **docker-compose** 项目</span><span class="sxs-lookup"><span data-stu-id="19492-158">The **docker-compose** project in a single-container web application</span></span>

<span data-ttu-id="19492-159">这些文件是标准 docker-compose 文件，与任何 Docker 项目一致。</span><span class="sxs-lookup"><span data-stu-id="19492-159">These files are standard docker-compose files, consistent with any Docker project.</span></span> <span data-ttu-id="19492-160">可通过 Visual Studio 或命令行使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="19492-160">You can use them with Visual Studio or from the command line.</span></span> <span data-ttu-id="19492-161">此应用程序在 .NET Core 上运行并使用 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="19492-161">This application runs on .NET Core and uses Linux containers.</span></span> <span data-ttu-id="19492-162">因此，还可在 Mac 或 Linux 计算机上对其进行编码、生成和运行。</span><span class="sxs-lookup"><span data-stu-id="19492-162">So, you can also code, build, and run it on a Mac or on a Linux machine.</span></span>

<span data-ttu-id="19492-163">docker-compose.yml 文件包含有关要生成的映像和要启动的容器的信息。</span><span class="sxs-lookup"><span data-stu-id="19492-163">The *docker-compose.yml* file contains information about what images to build and what containers to launch.</span></span> <span data-ttu-id="19492-164">模板指定如何生成 `eshopweb` 映像并启动应用程序的容器。</span><span class="sxs-lookup"><span data-stu-id="19492-164">The templates specify how to build the `eshopweb` image and launch the application’s containers.</span></span> <span data-ttu-id="19492-165">需要通过包含 SQL Server 的映像（例如 `mssql-server-linux`）添加对 SQL Server 的依赖项，并添加针对 sql.data 映像的服务，用于 Docker 生成并启动该容器。</span><span class="sxs-lookup"><span data-stu-id="19492-165">You need to add the dependency on SQL Server by including an image for it (for example, `mssql-server-linux`), and a service for the sql.data image for Docker to build and launch that container.</span></span> <span data-ttu-id="19492-166">这些设置如下例所示：</span><span class="sxs-lookup"><span data-stu-id="19492-166">These settings are shown in the following example:</span></span>

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

<span data-ttu-id="19492-167">`depends_on` 指令会告知 Docker：eShopWeb 映像依赖于 sql.data 映像。</span><span class="sxs-lookup"><span data-stu-id="19492-167">The `depends_on` directive tells Docker that the eShopWeb image depends on the sql.data image.</span></span> <span data-ttu-id="19492-168">`depends_on` 下面的行是使用 `microsoft/mssql-server-linux` 映像来生成标记为 `sql.data` 的映像的指令。</span><span class="sxs-lookup"><span data-stu-id="19492-168">The lines below `depends_on` are the instructions to build an image tagged `sql.data` using the `microsoft/mssql-server-linux` image.</span></span>

<span data-ttu-id="19492-169">docker-compose 项目会在 docker-compose.yml 主节点下显示其他 docker-compose 文件，从视觉上指示这些文件相关联。</span><span class="sxs-lookup"><span data-stu-id="19492-169">The **docker-compose** project displays the other docker-compose files under the main *docker-compose.yml* node to provide a visual indication that these files are related.</span></span> <span data-ttu-id="19492-170">docker-compose-override.yml 文件包含适用于这两个服务的设置，如连接字符串和其他应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="19492-170">The *docker-compose-override.yml* file contains settings for both services, such as connection strings and other application settings.</span></span>

<span data-ttu-id="19492-171">下面的示例演示 docker-compose.vs.debug.yml 文件，其中包含用于在 Visual Studio 中进行调试的设置。</span><span class="sxs-lookup"><span data-stu-id="19492-171">The following example shows the *docker-compose.vs.debug.yml* file, which contains settings used for debugging in Visual Studio.</span></span> <span data-ttu-id="19492-172">在该文件中，eshopweb 映像中附加了 dev 标记。</span><span class="sxs-lookup"><span data-stu-id="19492-172">In that file, the eshopweb image has the dev tag appended to it.</span></span> <span data-ttu-id="19492-173">这有助于分离调试与发布映像，避免意外将调试信息部署到生产环境：</span><span class="sxs-lookup"><span data-stu-id="19492-173">That helps separate debug from release images so that you don't accidentally deploy the debug information to a production environment:</span></span>

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

<span data-ttu-id="19492-174">添加的最后一个文件是 docker-compose.ci.build.yml。</span><span class="sxs-lookup"><span data-stu-id="19492-174">The last file added is *docker-compose.ci.build.yml*.</span></span> <span data-ttu-id="19492-175">在命令行中使用该文件，以便从 CI 服务器生成项目。</span><span class="sxs-lookup"><span data-stu-id="19492-175">This file would be used from the command line to build the project from a CI server.</span></span> <span data-ttu-id="19492-176">此组成文件会启动一个 Docker 容器，该容器将生成应用程序所需的映像。</span><span class="sxs-lookup"><span data-stu-id="19492-176">This compose file starts a Docker container that builds the images needed for your application.</span></span> <span data-ttu-id="19492-177">下面的示例演示了 docker-compose.ci.build.yml 文件的内容：</span><span class="sxs-lookup"><span data-stu-id="19492-177">The following example shows the contents of the *docker-compose.ci.build.yml* file:</span></span>

```yml
version: '2'

services:
  ci-build:
    image: microsoft/aspnetcore-build:latest
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

> [!NOTE]
> <span data-ttu-id="19492-178">从 .NET Core SDK 2.0 开始，执行 [dotnet publish](../../../core/tools/dotnet-publish.md) 时，[dotnet restore](../../../core/tools/dotnet-restore.md) 命令将自动执行。</span><span class="sxs-lookup"><span data-stu-id="19492-178">Starting with .NET Core SDK 2.0, the [dotnet restore](../../../core/tools/dotnet-restore.md) command executes automatically when [dotnet publish](../../../core/tools/dotnet-publish.md) is executed.</span></span>

<span data-ttu-id="19492-179">请注意，该映像是 ASP.NET Core 生成映像。</span><span class="sxs-lookup"><span data-stu-id="19492-179">Notice that the image is an ASP.NET Core build image.</span></span> <span data-ttu-id="19492-180">该映像包括用于生成应用程序并创建所需映像的 SDK 和生成工具。</span><span class="sxs-lookup"><span data-stu-id="19492-180">That image includes the SDK and build tools to build your application and create the required images.</span></span> <span data-ttu-id="19492-181">使用此文件运行 **docker-compose** 项目，会从映像启动生成容器，然后在该容器中生成应用程序的映像。</span><span class="sxs-lookup"><span data-stu-id="19492-181">Running the **docker-compose** project using this file starts the build container from the image, then builds your application’s image in that container.</span></span> <span data-ttu-id="19492-182">在将 docker-compose 文件指定为命令行的一部分以在 Docker 容器中生成应用程序，然后启动。</span><span class="sxs-lookup"><span data-stu-id="19492-182">You specify that *docker-compose* file as part of the command line to build your application in a Docker container, then launch it.</span></span>

<span data-ttu-id="19492-183">在 Visual Studio 中，可以在 Docker 容器中运行应用程序，具体方法是选择 **docker-compose** 项目作为启动项目，然后按 Ctrl+F5（F5 用于调试），像在其他任何应用程序中操作一样。</span><span class="sxs-lookup"><span data-stu-id="19492-183">In Visual Studio, you can run your application in Docker containers by selecting the **docker-compose** project as the startup project, and then pressing Ctrl+F5 (F5 to debug), as you can with any other application.</span></span> <span data-ttu-id="19492-184">启动 docker-compose 项目时，Visual Studio 会使用 docker-compose.yml 文件、docker-compose.override.yml 文件，以及某个 docker-compose.vs.\* 文件来运行 docker-compose。</span><span class="sxs-lookup"><span data-stu-id="19492-184">When you start the **docker-compose** project, Visual Studio runs **docker-compose** using the *docker-compose.yml* file, the *docker-compose.override.yml* file, and one of the docker-compose.vs.\* files.</span></span> <span data-ttu-id="19492-185">启动应用程序后，Visual Studio 将启动浏览器。</span><span class="sxs-lookup"><span data-stu-id="19492-185">Once the application has started, Visual Studio launches the browser for you.</span></span>

<span data-ttu-id="19492-186">如果在调试程序中启动应用程序，Visual Studio 会附加到 Docker 中正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19492-186">If you launch the application in the debugger, Visual Studio attaches to the running application in Docker.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="19492-187">疑难解答</span><span class="sxs-lookup"><span data-stu-id="19492-187">Troubleshooting</span></span>

<span data-ttu-id="19492-188">本节介绍本地运行容器时可能出现的一些问题，并提出了一些修复建议。</span><span class="sxs-lookup"><span data-stu-id="19492-188">This section describes a few issues that might arise when your run containers locally and suggests some fixes.</span></span>

### <a name="stop-docker-containers"></a><span data-ttu-id="19492-189">停止 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="19492-189">Stop Docker containers</span></span>

<span data-ttu-id="19492-190">启动容器化应用程序后，即使你停止调试，容器仍会继续运行。</span><span class="sxs-lookup"><span data-stu-id="19492-190">After you launch the containerized application, the containers continue to run, even after you have stopped debugging.</span></span> <span data-ttu-id="19492-191">可从命令行运行 `docker ps` 命令，查看运行中的容器。</span><span class="sxs-lookup"><span data-stu-id="19492-191">You can run the `docker ps` command from the command line to see which containers are running.</span></span> <span data-ttu-id="19492-192">`docker stop` 命令可停止正在运行的容器，如图 6-2 所示。</span><span class="sxs-lookup"><span data-stu-id="19492-192">The `docker stop` command stops a running container, as shown in Figure 6-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="19492-193">**图 6-2**.</span><span class="sxs-lookup"><span data-stu-id="19492-193">**Figure 6-2**.</span></span> <span data-ttu-id="19492-194">使用 docker ps 和 docker stop CLI 命令列出和停止容器</span><span class="sxs-lookup"><span data-stu-id="19492-194">Listing and stopping containers with the docker ps and docker stop CLI commands</span></span>

<span data-ttu-id="19492-195">在不同的配置间切换时，可能需要停止正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="19492-195">You might need to stop running processes when you switch between different configurations.</span></span> <span data-ttu-id="19492-196">否则，运行 Web 应用的容器会使用应用程序的端口（此例中为 5106）。</span><span class="sxs-lookup"><span data-stu-id="19492-196">Otherwise, the container that is running the web application is using the port for your application (5106 in this example).</span></span>

### <a name="add-docker-to-your-projects"></a><span data-ttu-id="19492-197">将 Docker 添加到项目</span><span class="sxs-lookup"><span data-stu-id="19492-197">Add Docker to your projects</span></span>

<span data-ttu-id="19492-198">添加 Docker 支持的向导会与正在运行的 Docker 进程通信。</span><span class="sxs-lookup"><span data-stu-id="19492-198">The wizard that adds Docker support communicates with the running Docker process.</span></span> <span data-ttu-id="19492-199">如果启动向导时 Docker 未处于运行状态，则向导无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="19492-199">If Docker isn't running when you start the wizard, the wizard won't run correctly.</span></span> <span data-ttu-id="19492-200">向导会检查当前的容器选择以添加正确的 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="19492-200">The wizard examines your current container choice to add the correct Docker support.</span></span> <span data-ttu-id="19492-201">若要添加对 Windows 容器的支持，请在配置了 Windows 容器的 Docker 运行的同时运行向导。</span><span class="sxs-lookup"><span data-stu-id="19492-201">To add support for Windows Containers, run the wizard while you have Docker running with Windows Containers configured.</span></span> <span data-ttu-id="19492-202">若要添加对 Linux 容器的支持，请在配置了 Linux 容器的 Docker 运行的同时运行向导。</span><span class="sxs-lookup"><span data-stu-id="19492-202">To add support for Linux containers, run the wizard while you have Docker running with Linux containers configured.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="19492-203">[上一页](../docker-application-development-process/docker-app-development-workflow.md)
[下一页](../containerize-net-framework-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="19492-203">[Previous](../docker-application-development-process/docker-app-development-workflow.md)
[Next](../containerize-net-framework-applications/index.md)</span></span>
