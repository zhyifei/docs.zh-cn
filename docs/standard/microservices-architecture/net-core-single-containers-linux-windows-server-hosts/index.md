---
title: "在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用"
description: "适用于容器化 .NET 应用程序的体系结构 | 在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f85b3db6b4ca6d22c4b855c8b96051c1c31350a6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a><span data-ttu-id="85b33-104">在 Linux 或 Windows Nano Server 主机上部署基于单容器的 .NET Core Web 应用</span><span class="sxs-lookup"><span data-stu-id="85b33-104">Deploying Single-Container-Based .NET Core Web Applications on Linux or Windows Nano Server Hosts</span></span>

<span data-ttu-id="85b33-105">*对于简单 Web 应用的整体部署，可以使用 Docker 容器。这样可以改进持续集成和连续部署管道，并有助于成功实现部署到生产。不再出现“为什么可以在我的计算机上正常运行，却不能在生产中正常运行？”的问题。*</span><span class="sxs-lookup"><span data-stu-id="85b33-105">*You can use Docker containers for monolithic deployment of simpler web applications. This improves continuous integration and continuous deployment pipelines and helps achieve deployment-to-production success. No more “It works in my machine, why does not work in production?”*</span></span>

<span data-ttu-id="85b33-106">基于微服务的体系结构具有许多优势，但以增加复杂性为代价。</span><span class="sxs-lookup"><span data-stu-id="85b33-106">A microservices-based architecture has many benefits, but those benefits come at a cost of increased complexity.</span></span> <span data-ttu-id="85b33-107">在某些情况下，付出的代价比得到的优势更为重大，在单个或少量容器中运行的单片式部署应用程序更为实用。</span><span class="sxs-lookup"><span data-stu-id="85b33-107">In some cases, the costs outweigh the benefits, and you will be better served with a monolithic deployment application running in a single container or in just a few containers.</span></span> 

<span data-ttu-id="85b33-108">单片式应用程序可能不易分解到独立性良好的微服务。</span><span class="sxs-lookup"><span data-stu-id="85b33-108">A monolithic application might not be easily decomposable into well-separated microservices.</span></span> <span data-ttu-id="85b33-109">你已经了解到，应按功能对微服务进行分区：微服务应彼此独立地运行，以提供恢复能力更强的应用程序。</span><span class="sxs-lookup"><span data-stu-id="85b33-109">You have learned that these should be partitioned by function: microservices should work independently of each other to provide a more resilient application.</span></span> <span data-ttu-id="85b33-110">如果不能实现应用程序功能切片，将其分离只会增加复杂性。</span><span class="sxs-lookup"><span data-stu-id="85b33-110">If you cannot deliver feature slices of the application, separating it only adds complexity.</span></span>

<span data-ttu-id="85b33-111">应用程序可能尚不需要独立地扩展功能。</span><span class="sxs-lookup"><span data-stu-id="85b33-111">An application might not yet need to scale features independently.</span></span> <span data-ttu-id="85b33-112">假设在 eShopOnContainers 引用应用程序生命周期的前期，流量并未将分离的功能调整到不同的微服务。</span><span class="sxs-lookup"><span data-stu-id="85b33-112">Let’s suppose that early in the life of our eShopOnContainers reference application, the traffic did not justify separating features into different microservices.</span></span> <span data-ttu-id="85b33-113">流量足够小，为一项服务添加资源通常意味着为所有服务添加资源。</span><span class="sxs-lookup"><span data-stu-id="85b33-113">Traffic was small enough that adding resources to one service typically meant adding resources to all services.</span></span> <span data-ttu-id="85b33-114">将应用程序分离到成离散的服务是画蛇添足，提供的优势极小。</span><span class="sxs-lookup"><span data-stu-id="85b33-114">The additional work to separate the application into discrete services provided minimal benefit.</span></span>

<span data-ttu-id="85b33-115">此外，在应用程序开发前期，可能并不确定自然功能边界。</span><span class="sxs-lookup"><span data-stu-id="85b33-115">Also, early in the development of an application you might not have a clear idea where the natural functional boundaries are.</span></span> <span data-ttu-id="85b33-116">开发最小可独立产品时，自然分离可能尚未出现。</span><span class="sxs-lookup"><span data-stu-id="85b33-116">As you develop a minimum viable product, the natural separation might not yet have emerged.</span></span>

<span data-ttu-id="85b33-117">其中一些条件可能是临时的。</span><span class="sxs-lookup"><span data-stu-id="85b33-117">Some of these conditions might be temporary.</span></span> <span data-ttu-id="85b33-118">可首先创建单片式应用程序，稍后再分离要以微服务的形式开发和部署的某些功能。</span><span class="sxs-lookup"><span data-stu-id="85b33-118">You might start by creating a monolithic application, and later separate some features to be developed and deployed as microservices.</span></span> <span data-ttu-id="85b33-119">而另一些条件可能对应用程序的容错空间至关重要，这意味着应用程序可能永远无法分解到多个微服务。</span><span class="sxs-lookup"><span data-stu-id="85b33-119">Other conditions might be essential to the application’s problem space, meaning that the application might never be broken into multiple microservices.</span></span>

<span data-ttu-id="85b33-120">将应用程序分离到多个离散进程还会带来开销。</span><span class="sxs-lookup"><span data-stu-id="85b33-120">Separating an application into many discrete processes also introduces overhead.</span></span> <span data-ttu-id="85b33-121">将功能分离到不同的进程则更复杂。</span><span class="sxs-lookup"><span data-stu-id="85b33-121">There is more complexity in separating features into different processes.</span></span> <span data-ttu-id="85b33-122">通信协议会变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="85b33-122">The communication protocols become more complex.</span></span> <span data-ttu-id="85b33-123">在服务之间必须使用异步通信，而不得使用方法调用。</span><span class="sxs-lookup"><span data-stu-id="85b33-123">Instead of method calls, you must use asynchronous communications between services.</span></span> <span data-ttu-id="85b33-124">移动到微服务体系结构时，需要添加许多在 eShopOnContainers 应用程序的微服务版本中实现的构建基块：事件总线处理、消息恢复和重试、最终一致性等。</span><span class="sxs-lookup"><span data-stu-id="85b33-124">As you move to a microservices architecture, you need to add many of the building blocks implemented in the microservices version of the eShopOnContainers application: event bus handling, message resiliency and retries, eventual consistency, and more.</span></span>

<span data-ttu-id="85b33-125">极简版的 eShopOnContainers（名为 [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic)包含在同一 GitHub 存储库中）作为单片式 MVC 应用程序运行，如上所述，选择这种设计带来了各种优势。</span><span class="sxs-lookup"><span data-stu-id="85b33-125">A much-simplified version of eShopOnContainers (named [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) and included in the same GitHub repo) runs as a monolithic MVC application, and as just described, there are advantages offered by that design choice.</span></span> <span data-ttu-id="85b33-126">可从 GitHub 下载此应用程序的源代码，并在本地运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-126">You can download the source for this application from GitHub and run it locally.</span></span> <span data-ttu-id="85b33-127">即使是这一单片式应用程序，在容器环境中部署也是有益的。</span><span class="sxs-lookup"><span data-stu-id="85b33-127">Even this monolithic application benefits from being deployed in a container environment.</span></span>

<span data-ttu-id="85b33-128">其一，容器化部署意味着应用程序的每个实例都在同一环境中运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-128">For one, the containerized deployment means that every instance of the application runs in the same environment.</span></span> <span data-ttu-id="85b33-129">这包括用于前期测试和开发的开发人员环境。</span><span class="sxs-lookup"><span data-stu-id="85b33-129">This includes the developer environment where early testing and development take place.</span></span> <span data-ttu-id="85b33-130">开发团队可在与生产环境完全相同的容器化环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="85b33-130">The development team can run the application in a containerized environment that matches the production environment.</span></span>

<span data-ttu-id="85b33-131">此外，容器化应用程序横向扩展成本较低。</span><span class="sxs-lookup"><span data-stu-id="85b33-131">In addition, containerized applications scale out at lower cost.</span></span> <span data-ttu-id="85b33-132">如上文所示，容器环境比传统 VM 环境更有利于资源共享。</span><span class="sxs-lookup"><span data-stu-id="85b33-132">As you saw earlier, the container environment enables greater resource sharing than traditional VM environments.</span></span>

<span data-ttu-id="85b33-133">最后，容器化应用程序会强制分离业务逻辑和存储服务器。</span><span class="sxs-lookup"><span data-stu-id="85b33-133">Finally, containerizing the application forces a separation between the business logic and the storage server.</span></span> <span data-ttu-id="85b33-134">应用程序横向扩展时，多个容器将全部依赖于单个物理存储介质。</span><span class="sxs-lookup"><span data-stu-id="85b33-134">As the application scales out, the multiple containers will all rely on a single physical storage medium.</span></span> <span data-ttu-id="85b33-135">这通常是运行 SQL Server 数据库的高可用性服务器。</span><span class="sxs-lookup"><span data-stu-id="85b33-135">This would typically be a high-availability server running a SQL Server database.</span></span>

## <a name="application-tour"></a><span data-ttu-id="85b33-136">应用程序教程</span><span class="sxs-lookup"><span data-stu-id="85b33-136">Application tour</span></span>

<span data-ttu-id="85b33-137">[eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 应用程序代表着某些作为单片式应用程序运行的 eShopOnContainers 应用程序，即在 .NET Core 上运行的基于 ASP.NET Core MVC 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="85b33-137">The [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) application represents some of the eShopOnContainers application running as a monolithic application—an ASP.NET Core MVC based application running on .NET Core.</span></span> <span data-ttu-id="85b33-138">它主要提供前几节所述的目录浏览功能。</span><span class="sxs-lookup"><span data-stu-id="85b33-138">It mainly provides the catalog browsing capabilities that we described in earlier sections.</span></span>

<span data-ttu-id="85b33-139">该应用程序使用 SQL Server 数据库实现目录存储。</span><span class="sxs-lookup"><span data-stu-id="85b33-139">The application uses a SQL Server database for the catalog storage.</span></span> <span data-ttu-id="85b33-140">在基于容器的部署中，此单片式应用程序与基于微服务的应用程序可访问相同的数据存储。</span><span class="sxs-lookup"><span data-stu-id="85b33-140">In container-based deployments, this monolithic application can access the same data store as the microservices-based application.</span></span> <span data-ttu-id="85b33-141">该应用程序配置为在与单片式应用程序并列的容器中运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="85b33-141">The application is configured to run SQL Server in a container alongside the monolithic application.</span></span> <span data-ttu-id="85b33-142">在生产环境中，SQL Server 会在 Docker 主机以外的高可用性计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-142">In a production environment, SQL Server would run on a high-availability machine, outside of the Docker host.</span></span> <span data-ttu-id="85b33-143">为方便起见，在开发或测试环境中，建议在专用容器中运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="85b33-143">For convenience in a dev or test environment, we recommend running SQL Server in its own container.</span></span>

<span data-ttu-id="85b33-144">初始功能集仅提供浏览目录的功能。</span><span class="sxs-lookup"><span data-stu-id="85b33-144">The initial feature set only enables browsing the catalog.</span></span> <span data-ttu-id="85b33-145">通过更新实现容器化应用程序的完整功能集。</span><span class="sxs-lookup"><span data-stu-id="85b33-145">Updates would enable the full feature set of the containerized application.</span></span> <span data-ttu-id="85b33-146">[ASP.NET Web 应用体系结构实践](https://aka.ms/webappebook)电子书和相关 [eShopOnWeb 示例应用程序](http://aka.ms/WebAppArchitecture)中介绍了更高级的单片式 Web 应用体系结构，尽管由于该方案重点介绍的是使用 ASP.NET Core 的纯 Web 开发，所以示例中的体系结构不在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-146">A more advanced monolithic web application architecture is described in the [ASP.NET Web Application architecture practices](https://aka.ms/webappebook) e-book and related [eShopOnWeb sample application](http://aka.ms/WebAppArchitecture), although in that case it is not running on Docker containers because that scenario focuses on plain web development with ASP.NET Core.</span></span>

<span data-ttu-id="85b33-147">但是，eShopOnContainers (eShopWeb) 中提供的简化版本在 Docker 容器中运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-147">However, the simplified version available in eShopOnContainers (eShopWeb) runs in a Docker container.</span></span>

## <a name="docker-support"></a><span data-ttu-id="85b33-148">Docker 支持</span><span class="sxs-lookup"><span data-stu-id="85b33-148">Docker support</span></span>

<span data-ttu-id="85b33-149">eShopOnWeb 项目在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-149">The eShopOnWeb project runs on .NET Core.</span></span> <span data-ttu-id="85b33-150">因此，该项目可以在基于 Linux 或 Windows 的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-150">Therefore, it can run in either Linux-based or Windows-based containers.</span></span> <span data-ttu-id="85b33-151">请注意，在 Docker 部署中，请对 SQL Server 使用相同的主机类型。</span><span class="sxs-lookup"><span data-stu-id="85b33-151">Note that for Docker deployment, you want to use the same host type for SQL Server.</span></span> <span data-ttu-id="85b33-152">基于 Linux 的容器占用较小，是首选方案。</span><span class="sxs-lookup"><span data-stu-id="85b33-152">Linux-based containers allow a smaller footprint and are preferred.</span></span>

<span data-ttu-id="85b33-153">Visual Studio 提供了项目模板，可在解决方案中添加对 Docker 的支持。</span><span class="sxs-lookup"><span data-stu-id="85b33-153">Visual Studio provides a project template that adds support for Docker to a solution.</span></span> <span data-ttu-id="85b33-154">右键单击该项目，单击“Docker 支持”前的“添加”。</span><span class="sxs-lookup"><span data-stu-id="85b33-154">You right-click the project, click **Add** followed by **Docker Support**.</span></span> <span data-ttu-id="85b33-155">该模板会在项目中添加 Dockerfile，还会添加新的 **docker-compose** 项目，该项目可提供初始 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="85b33-155">The template adds a Dockerfile to your project, and a new **docker-compose** project that provides a starter docker-compose.yml file.</span></span> <span data-ttu-id="85b33-156">从 GitHub 下载的 eShopOnWeb 项目中已完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="85b33-156">This step has already been done in the eShopOnWeb project downloaded from GitHub.</span></span> <span data-ttu-id="85b33-157">可以看到该解决方案包含 **eShopOnWeb** 项目和 **docker-compose** 项目，如图 6-1 所示。</span><span class="sxs-lookup"><span data-stu-id="85b33-157">You will see that the solution contains the **eShopOnWeb** project and the **docker-compose** project as shown in Figure 6-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="85b33-158">**图 6-1**.</span><span class="sxs-lookup"><span data-stu-id="85b33-158">**Figure 6-1**.</span></span> <span data-ttu-id="85b33-159">单容器 Web 应用中的 **docker-compose** 项目</span><span class="sxs-lookup"><span data-stu-id="85b33-159">The **docker-compose** project in a single-container web application</span></span>

<span data-ttu-id="85b33-160">这些文件是标准 docker-compose 文件，与任何 Docker 项目一致。</span><span class="sxs-lookup"><span data-stu-id="85b33-160">These files are standard docker-compose files, consistent with any Docker project.</span></span> <span data-ttu-id="85b33-161">可通过 Visual Studio 或命令行使用这些文件。</span><span class="sxs-lookup"><span data-stu-id="85b33-161">You can use them with Visual Studio or from the command line.</span></span> <span data-ttu-id="85b33-162">此应用程序在 .NET Core 上运行，并使用 Linux 容器，因此还可在 Mac 或 Linux 计算机上编码、生成和运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-162">This application runs on .NET Core and uses Linux containers, so you can also code, build, and run on a Mac or on a Linux machine.</span></span>

<span data-ttu-id="85b33-163">docker-compose.yml 文件包含有关要生成的映像和要启动的容器的信息。</span><span class="sxs-lookup"><span data-stu-id="85b33-163">The docker-compose.yml file contains information about what images to build and what containers to launch.</span></span> <span data-ttu-id="85b33-164">模板指定如何生成 eshopweb 映像并启动应用程序的容器。</span><span class="sxs-lookup"><span data-stu-id="85b33-164">The templates specify how to build the eshopweb image and launch the application’s containers.</span></span> <span data-ttu-id="85b33-165">需要通过包含 SQL Server 的映像（例如 mssql-server-linux）添加对 SQL Server 的依赖性，并添加针对 sql.data 映像的服务，使 Docker 生成并和启动该容器。</span><span class="sxs-lookup"><span data-stu-id="85b33-165">You need to add the dependency on SQL Server by including an image for it (for example, mssql-server-linux), and a service for the sql.data image for Docker to build and launch that container.</span></span> <span data-ttu-id="85b33-166">这些设置如下例所示：</span><span class="sxs-lookup"><span data-stu-id="85b33-166">These settings are shown in the following example:</span></span>

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

<span data-ttu-id="85b33-167">depends\_on 指令会告知 Docker：eShopWeb 映像依赖于 sql.data 映像。</span><span class="sxs-lookup"><span data-stu-id="85b33-167">The depends\_on directive tells Docker that the eShopWeb image depends on the sql.data image.</span></span> <span data-ttu-id="85b33-168">其下各行是生成指令，将指示使用 microsoft/mssql-server-linux 映像生成标记为 sql.data 的映像。</span><span class="sxs-lookup"><span data-stu-id="85b33-168">Lines below that are the instructions to build an image tagged sql.data using the microsoft/mssql-server-linux image.</span></span>

<span data-ttu-id="85b33-169">**docker-compose** 项目会在 docker-compose.yml 主节点下显示其他 docker-compose 文件，从视觉上指示这些文件相关。</span><span class="sxs-lookup"><span data-stu-id="85b33-169">The **docker-compose** project displays the other docker-compose files under the main docker-compose.yml node to provide a visual indication that these files are related.</span></span> <span data-ttu-id="85b33-170">docker-compose-override.yml 文件包含适用于这两个服务的设置，如连接字符串和其他应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="85b33-170">The docker-compose-override.yml file contains settings for both services, such as connection strings and other application settings.</span></span>

<span data-ttu-id="85b33-171">下面的示例演示 docker-compose.vs.debug.yml 文件，其中包含用于在 Visual Studio 中进行调试的设置。</span><span class="sxs-lookup"><span data-stu-id="85b33-171">The following example shows the docker-compose.vs.debug.yml file, which contains settings used for debugging in Visual Studio.</span></span> <span data-ttu-id="85b33-172">在该文件中，eshopweb 映像中附加了 dev 标记。</span><span class="sxs-lookup"><span data-stu-id="85b33-172">In that file, the eshopweb image has the dev tag appended to it.</span></span> <span data-ttu-id="85b33-173">这样有助于分离调试与发布映像，避免意外将调试信息部署到生产环境：</span><span class="sxs-lookup"><span data-stu-id="85b33-173">That helps separate debug from release images so that you do not accidentally deploy the debug information to a production environment:</span></span>

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

<span data-ttu-id="85b33-174">添加的最后一个文件是 docker-compose.ci.build.yml。</span><span class="sxs-lookup"><span data-stu-id="85b33-174">The last file added is docker-compose.ci.build.yml.</span></span> <span data-ttu-id="85b33-175">在命令行中使用该文件，可以从 CI 服务器生成项目。</span><span class="sxs-lookup"><span data-stu-id="85b33-175">This would be used from the command line to build the project from a CI server.</span></span> <span data-ttu-id="85b33-176">此组成文件会启动一个 Docker 容器，该容器将生成应用程序所需的映像。</span><span class="sxs-lookup"><span data-stu-id="85b33-176">This compose file starts a Docker container that builds the images needed for your application.</span></span> <span data-ttu-id="85b33-177">下面的示例演示 docker-compose.ci.build.yml 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="85b33-177">The following example shows the contents of the docker-compose.ci.build.yml file.</span></span>

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

<span data-ttu-id="85b33-178">注意：从 .NET Core 2.0 开始，dotnet publish 执行时自动执行 dotnet restore 命令。</span><span class="sxs-lookup"><span data-stu-id="85b33-178">**Note**: Starting with .NET Core 2.0, the dotnet restore command executes automatically when dotnet publish is executed.</span></span>

<span data-ttu-id="85b33-179">请注意，该映像是 ASP.NET Core 生成映像。</span><span class="sxs-lookup"><span data-stu-id="85b33-179">Notice that the image is an ASP.NET Core build image.</span></span> <span data-ttu-id="85b33-180">该映像包括用于生成应用程序并创建所需映像的 SDK 和生成工具。</span><span class="sxs-lookup"><span data-stu-id="85b33-180">That image includes the SDK and build tools to build your application and create the required images.</span></span> <span data-ttu-id="85b33-181">使用此文件运行 **docker-compose** 项目，会从映像启动生成容器，然后在该容器中生成应用程序的映像。</span><span class="sxs-lookup"><span data-stu-id="85b33-181">Running the **docker-compose** project using this file starts the build container from the image, then builds your application’s image in that container.</span></span> <span data-ttu-id="85b33-182">在命令行中 docker-compose 文件，在 Docker 容器中生成应用程序，然后启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="85b33-182">You specify that docker-compose file as part of the command line to build your application in a Docker container, then launch it.</span></span>

<span data-ttu-id="85b33-183">在 Visual Studio 中，可以在 Docker 容器中运行应用程序，具体方法是选择 **docker-compose** 项目作为启动项目，然后按 Ctrl+F5（F5 用于调试），像在其他任何应用程序中操作一样。</span><span class="sxs-lookup"><span data-stu-id="85b33-183">In Visual Studio, you can run your application in Docker containers by selecting the **docker-compose** project as the startup project, and then pressing Ctrl+F5 (F5 to debug), as you can with any other application.</span></span> <span data-ttu-id="85b33-184">启动 **docker-compose** 项目时，Visual Studio 会使用 docker-compose.yml 文件、docker-compose.override.yml 文件，以及其中一个 docker-compose.vs.\* 文件运行 **docker-compose**。</span><span class="sxs-lookup"><span data-stu-id="85b33-184">When you start the **docker-compose** project, Visual Studio runs **docker-compose** using the docker-compose.yml file, the docker-compose.override.yml file, and one of the docker-compose.vs.\* files.</span></span> <span data-ttu-id="85b33-185">启动应用程序后，Visual Studio 将启动浏览器。</span><span class="sxs-lookup"><span data-stu-id="85b33-185">Once the application has started, Visual Studio launches the browser for you.</span></span>

<span data-ttu-id="85b33-186">如果在调试器中启动应用程序，则 Visual Studio 会附加到 Docker 中正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="85b33-186">If you launch the application in the debugger, Visual Studio will attach to the running application in Docker.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="85b33-187">疑难解答</span><span class="sxs-lookup"><span data-stu-id="85b33-187">Troubleshooting</span></span>

<span data-ttu-id="85b33-188">本节介绍本地运行容器时可能出现的一些问题，并提出了一些修复建议。</span><span class="sxs-lookup"><span data-stu-id="85b33-188">This section describes a few issues that might arise when your run containers locally and suggests some fixes.</span></span>

### <a name="stopping-docker-containers"></a><span data-ttu-id="85b33-189">停止 Docker 容器</span><span class="sxs-lookup"><span data-stu-id="85b33-189">Stopping Docker containers</span></span> 

<span data-ttu-id="85b33-190">启动容器化应用程序后，即使你停止调试，容器仍会继续运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-190">After you launch the containerized application, the containers continue to run, even after you have stopped debugging.</span></span> <span data-ttu-id="85b33-191">可从命令行运行 docker ps 命令，查看运行中的容器。</span><span class="sxs-lookup"><span data-stu-id="85b33-191">You can run the docker ps command from the command line to see which containers are running.</span></span> <span data-ttu-id="85b33-192">docker stop 命令可停止正在运行的容器，如图 6-2 所示。</span><span class="sxs-lookup"><span data-stu-id="85b33-192">The docker stop command stops a running container, as shown in Figure 6-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="85b33-193">**图 6-2**.</span><span class="sxs-lookup"><span data-stu-id="85b33-193">**Figure 6-2**.</span></span> <span data-ttu-id="85b33-194">使用 docker ps 和 docker stop CLI 命令列出和停止容器</span><span class="sxs-lookup"><span data-stu-id="85b33-194">Listing and stopping containers with the docker ps and docker stop CLI commands</span></span>

<span data-ttu-id="85b33-195">在不同的配置间切换时，可能需要停止正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="85b33-195">You might need to stop running processes when you switch between different configurations.</span></span> <span data-ttu-id="85b33-196">否则，运行 Web 应用的容器会使用应用程序的端口（此例中为 5106）。</span><span class="sxs-lookup"><span data-stu-id="85b33-196">Otherwise, the container that is running the web application is using the port for your application (5106 in this example).</span></span>

### <a name="adding-docker-to-your-projects"></a><span data-ttu-id="85b33-197">将 Docker 添加到项目</span><span class="sxs-lookup"><span data-stu-id="85b33-197">Adding Docker to your projects</span></span>

<span data-ttu-id="85b33-198">添加 Docker 支持的向导会与正在运行的 Docker 进程通信。</span><span class="sxs-lookup"><span data-stu-id="85b33-198">The wizard that adds Docker support communicates with the running Docker process.</span></span> <span data-ttu-id="85b33-199">如果启动向导时 Docker 未处于运行状态，则向导无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="85b33-199">The wizard will not run correctly if Docker is not running when you start the wizard.</span></span> <span data-ttu-id="85b33-200">此外，向导会检查当前的容器选择，添加正确的 Docker 支持。</span><span class="sxs-lookup"><span data-stu-id="85b33-200">In addition, the wizard examines your current container choice to add the correct Docker support.</span></span> <span data-ttu-id="85b33-201">若要为 Windows 容器添加支持，需在配置了 Windows 容器的 Docker 运行时运行向导。</span><span class="sxs-lookup"><span data-stu-id="85b33-201">If you want to add support for Windows Containers, you need to run the wizard while you have Docker running with Windows Containers configured.</span></span> <span data-ttu-id="85b33-202">若要为 Linux 容器添加支持，则运行向导，同时运行配置有 Linux 容器的 Docker。</span><span class="sxs-lookup"><span data-stu-id="85b33-202">If you want to add support for Linux containers, run the wizard while you have Docker running with Linux containers configured.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="85b33-203">[上一页] (../docker-application-development-process/docker-app-development-workflow.md) [下一页] (../containerize-net-framework-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="85b33-203">[Previous] (../docker-application-development-process/docker-app-development-workflow.md) [Next] (../containerize-net-framework-applications/index.md)</span></span>
