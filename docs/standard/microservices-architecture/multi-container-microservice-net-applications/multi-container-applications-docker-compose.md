---
title: "定义与 docker-compose.yml 多容器应用程序"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |定义与 docker-compose.yml 多容器应用程序"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="05092-104">定义与 docker-compose.yml 多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="05092-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="05092-105">本指南中， [docker-compose.yml](https://docs.docker.com/compose/compose-file/)文件的部分中引入了[步骤 4。构建多容器 Docker 应用程序时在 docker-compose.yml 中定义你的服务](#step4_define_svcs_in_docker_compose_yml)。</span><span class="sxs-lookup"><span data-stu-id="05092-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="05092-106">但是，还有其他方式，若要使用的进一步详细浏览值得 docker-compose 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="05092-107">例如，你可以明确描述你想要部署多容器应用程序 docker-compose.yml 文件中。</span><span class="sxs-lookup"><span data-stu-id="05092-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="05092-108">（可选） 你可以描述如何生成自定义的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="05092-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="05092-109">（自定义 Docker 映像也可以生成使用 Docker CLI。）</span><span class="sxs-lookup"><span data-stu-id="05092-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="05092-110">基本上，你定义每个你想要部署的容器以及为每个容器部署某些特征。</span><span class="sxs-lookup"><span data-stu-id="05092-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="05092-111">一个多容器部署说明文件之后，你可以部署在单一操作由协调整个解决方案[docker compose 向上](https://docs.docker.com/compose/overview/)CLI 命令，也可以将其部署以透明方式从 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="05092-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="05092-112">否则，你将需要使用 Docker CLI 使用 docker run 命令从命令行部署多个步骤中的容器的容器。</span><span class="sxs-lookup"><span data-stu-id="05092-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="05092-113">因此，在 docker-compose.yml 中定义的每个服务必须指定恰好一个映像，或生成。</span><span class="sxs-lookup"><span data-stu-id="05092-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="05092-114">其他密钥是可选的并且类似于其 docker 运行命令行对等项。</span><span class="sxs-lookup"><span data-stu-id="05092-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="05092-115">下面的 YAML 代码是 eShopOnContainers 示例的可能全局但单个 docker-compose.yml 文件的定义。</span><span class="sxs-lookup"><span data-stu-id="05092-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="05092-116">这不是从 eShopOnContainers 的实际 docker-compose 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="05092-117">相反，它是在单个文件，不是最佳的简化和统一版本方式来使用 docker-编写文件，如将更高版本所述。</span><span class="sxs-lookup"><span data-stu-id="05092-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

<span data-ttu-id="05092-118">此文件中的根密钥是服务。</span><span class="sxs-lookup"><span data-stu-id="05092-118">The root key in this file is services.</span></span> <span data-ttu-id="05092-119">该注册表项下定义你想要部署和运行时执行的服务 docker compose 命令或当你从 Visual Studio 部署通过使用此 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="05092-120">在这种情况下，docker-compose.yml 文件具有多个服务定义，以下列表中所述。</span><span class="sxs-lookup"><span data-stu-id="05092-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="05092-121">webmvc 包括 ASP.NET 核心 MVC 应用程序使用从服务器端 C 微服务容器\#</span><span class="sxs-lookup"><span data-stu-id="05092-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="05092-122">catalog.api 包括目录 ASP.NET 核心 Web API 微服务容器</span><span class="sxs-lookup"><span data-stu-id="05092-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="05092-123">ordering.api 包括排序 ASP.NET 核心 Web API 微服务容器</span><span class="sxs-lookup"><span data-stu-id="05092-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="05092-124">sql.data 适用于 Linux，保存微服务数据库运行 SQL Server 容器</span><span class="sxs-lookup"><span data-stu-id="05092-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="05092-125">与购物篮 ASP.NET 核心 Web API microservice basket.api 容器</span><span class="sxs-lookup"><span data-stu-id="05092-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="05092-126">basket.data 运行与购物篮数据库作为 REDIS 缓存的 REDIS 缓存服务中容器</span><span class="sxs-lookup"><span data-stu-id="05092-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="05092-127">简单的 Web 服务 API 容器</span><span class="sxs-lookup"><span data-stu-id="05092-127">A simple Web Service API container</span></span>

<span data-ttu-id="05092-128">着重于单个容器，catalog.api 容器微服务都有一个简单的定义：</span><span class="sxs-lookup"><span data-stu-id="05092-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

<span data-ttu-id="05092-129">此容器化的服务具有以下基本配置：</span><span class="sxs-lookup"><span data-stu-id="05092-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="05092-130">它基于自定义 eshop/catalog.api 映像。</span><span class="sxs-lookup"><span data-stu-id="05092-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="05092-131">为简单起见，没有任何编录生成： 密钥文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="05092-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="05092-132">这意味着将映像必须具有已 （通过构建 docker 生成），或从任何 Docker 注册表 （使用 docker 请求命令） 下载。</span><span class="sxs-lookup"><span data-stu-id="05092-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="05092-133">它定义要用于实体框架访问包含目录数据模型的 SQL Server 实例的连接字符串的名为 ConnectionString 的环境变量。</span><span class="sxs-lookup"><span data-stu-id="05092-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="05092-134">在这种情况下，同一个 SQL Server 容器保存多个数据库。</span><span class="sxs-lookup"><span data-stu-id="05092-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="05092-135">因此，需要较少的内存中你的开发计算机 Docker。</span><span class="sxs-lookup"><span data-stu-id="05092-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="05092-136">但是，你还可以部署为每个微服务数据库的一个 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="05092-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="05092-137">SQL Server 名称是 sql.data，这是用于正在运行的 SQL Server 实例，对于 Linux 容器相同的名称。</span><span class="sxs-lookup"><span data-stu-id="05092-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="05092-138">此方法很方便;能够使用此名称解析 （内部到 Docker 主机） 将解析的网络地址，因此无需知道从其他容器访问的容器的内部 IP。</span><span class="sxs-lookup"><span data-stu-id="05092-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="05092-139">由于连接字符串定义的环境变量，你可以通过不同的机制和在不同时间设置该变量。</span><span class="sxs-lookup"><span data-stu-id="05092-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="05092-140">例如，你无法部署到生产环境中的最后一个主机，或通过执行 VSTS 或你首选的 DevOps 系统中你 CI/CD 管道中时设置不同的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="05092-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="05092-141">它公开有关内部访问 catalog.api 服务对 Docker 主机中的端口 80。</span><span class="sxs-lookup"><span data-stu-id="05092-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="05092-142">主机当前是 Linux VM，因为它基于 Docker 映像对于 Linux，但你可以配置要改为运行在 Windows 映像上的容器。</span><span class="sxs-lookup"><span data-stu-id="05092-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="05092-143">它会将转发公开的端口 80 上向 Docker 主机计算机 (Linux VM) 上的端口 5101 容器。</span><span class="sxs-lookup"><span data-stu-id="05092-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="05092-144">它链接到 sql.data 服务 （运行在容器中的 Linux 数据库的 SQL Server 实例） 的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="05092-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="05092-145">指定此依赖关系时之前已经启动了 sql.data 容器; 不会启动 catalog.api 容器第一次这是因为 catalog.api 需要最多有 SQL Server 数据库重要和正在运行。</span><span class="sxs-lookup"><span data-stu-id="05092-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="05092-146">但是，这种类型的容器依赖项是不够的在许多情况下，因为仅在容器级别检查 Docker。</span><span class="sxs-lookup"><span data-stu-id="05092-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="05092-147">有时 （此大小写的 SQL Server) 中的服务可能仍不是准备就绪，因此最好在客户端微服务中实现具有指数回退重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="05092-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="05092-148">这样一来，如果依赖项容器未准备好进行短时间内，将仍能够处理应用程序。</span><span class="sxs-lookup"><span data-stu-id="05092-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="05092-149">它被配置为允许访问外部服务器： 额外\_主机设置允许你访问外部服务器或外部的 Docker 主机计算机 （即，外部默认 Linux VM，这是一个开发 Docker 主机），如本地 SQL对开发计算机上的服务器实例。</span><span class="sxs-lookup"><span data-stu-id="05092-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="05092-150">此外，还有下列部分中，我们将讨论其他，更高级的 docker-compose.yml 设置。</span><span class="sxs-lookup"><span data-stu-id="05092-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="05092-151">使用 docker-撰写文件以面向多个环境</span><span class="sxs-lookup"><span data-stu-id="05092-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="05092-152">Docker-compose.yml 文件是定义文件，并且可由多个基础结构，了解该格式。</span><span class="sxs-lookup"><span data-stu-id="05092-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="05092-153">最简单的工具是 docker-编写命令，但其他像 orchestrators (例如，Docker Swarm) 还了解该文件的工具。</span><span class="sxs-lookup"><span data-stu-id="05092-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="05092-154">因此，通过使用 docker compose 命令，你可以面向以下主要方案。</span><span class="sxs-lookup"><span data-stu-id="05092-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="05092-155">开发环境</span><span class="sxs-lookup"><span data-stu-id="05092-155">Development environments</span></span>

<span data-ttu-id="05092-156">当你开发应用程序时，务必能够独立的开发环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="05092-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="05092-157">你可以使用 docker compose CLI 命令，以创建该环境或使用 Visual Studio 可使用 docker 的撰写在后台。</span><span class="sxs-lookup"><span data-stu-id="05092-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="05092-158">Docker-compose.yml 文件，可配置并记录应用程序的所有服务依赖项 （其他服务、 缓存、 数据库、 队列等。）。</span><span class="sxs-lookup"><span data-stu-id="05092-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="05092-159">使用 docker compose CLI 命令，则可以创建并使用单个命令启动一个或多个容器的每个依赖项 （docker-撰写向上）。</span><span class="sxs-lookup"><span data-stu-id="05092-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="05092-160">Docker-compose.yml 文件是由 Docker 引擎解释的配置文件，但还充当有关组合的多容器应用程序的方便文档文件。</span><span class="sxs-lookup"><span data-stu-id="05092-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="05092-161">测试环境</span><span class="sxs-lookup"><span data-stu-id="05092-161">Testing environments</span></span>

<span data-ttu-id="05092-162">任何连续部署 (CD) 或持续集成 (CI) 过程的重要组成部分是单元测试和集成测试。</span><span class="sxs-lookup"><span data-stu-id="05092-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="05092-163">这些自动的测试需要一个独立的环境，因此它们不受影响的用户或应用程序的数据中的任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="05092-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="05092-164">通过 Docker Compose 可以创建和销毁该隔离的环境，很容易中几个命令从命令提示符或脚本，如以下命令：</span><span class="sxs-lookup"><span data-stu-id="05092-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="05092-165">生产部署</span><span class="sxs-lookup"><span data-stu-id="05092-165">Production deployments</span></span>

<span data-ttu-id="05092-166">你还可以使用 Compose 将部署到远程 Docker 引擎。</span><span class="sxs-lookup"><span data-stu-id="05092-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="05092-167">一种典型情况是将部署到单个的 Docker 主机实例 (如生产 VM 或使用设置服务器[Docker 机](https://docs.docker.com/machine/overview/))。</span><span class="sxs-lookup"><span data-stu-id="05092-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="05092-168">但它也可以是整个[Docker Swarm](https://docs.docker.com/swarm/overview/)群集，因为群集也是兼容 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="05092-169">如果你使用的任何其他 orchestrator （Azure Service Fabric、 Mesos DC/OS、 Kubernetes 等），你可能需要添加安装程序和元数据配置设置，如在 docker-compose.yml，但在通过其他 orchestrator 所需的格式。</span><span class="sxs-lookup"><span data-stu-id="05092-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="05092-170">在任何情况下，docker compose 是一种方便的工具和元数据格式，开发、 测试和生产的工作流，虽然制作工作流可能会在你使用 orchestrator 上不同。</span><span class="sxs-lookup"><span data-stu-id="05092-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="05092-171">使用多个 docker-撰写文件来处理多个环境</span><span class="sxs-lookup"><span data-stu-id="05092-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="05092-172">如果目标不同的环境，应使用多个构成文件。</span><span class="sxs-lookup"><span data-stu-id="05092-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="05092-173">这允许您创建根据环境的多个配置变体。</span><span class="sxs-lookup"><span data-stu-id="05092-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="05092-174">重写基 docker-compose 文件</span><span class="sxs-lookup"><span data-stu-id="05092-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="05092-175">你可以使用单个 docker-compose.yml 文件如下所示前面部分中所示的简化示例。</span><span class="sxs-lookup"><span data-stu-id="05092-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="05092-176">但是，不建议使用该对于大多数应用程序。</span><span class="sxs-lookup"><span data-stu-id="05092-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="05092-177">默认情况下，Compose 读取两个文件、 docker-compose.yml 和可选的 docker compose.override.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="05092-178">如下所示在图 8-11 中，当你使用 Visual Studio 且启用 Docker 支持，Visual Studio 还会创建这些文件以及其他一些用于调试的文件。</span><span class="sxs-lookup"><span data-stu-id="05092-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="05092-179">**图 8-11**。</span><span class="sxs-lookup"><span data-stu-id="05092-179">**Figure 8-11**.</span></span> <span data-ttu-id="05092-180">docker compose Visual Studio 自 2017 年中的文件</span><span class="sxs-lookup"><span data-stu-id="05092-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="05092-181">你可以使用任何编辑器，如 Visual Studio Code 或 Sublime，编辑 docker-compose 文件和运行的应用程序 docker compose 向上命令。</span><span class="sxs-lookup"><span data-stu-id="05092-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="05092-182">按照约定，docker-compose.yml 文件包含的基本配置和其他静态设置。</span><span class="sxs-lookup"><span data-stu-id="05092-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="05092-183">这意味着，具体取决于你面向的部署环境不应更改服务配置。</span><span class="sxs-lookup"><span data-stu-id="05092-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="05092-184">Docker compose.override.yml 文件中，顾名思义，包含重写的基本配置，如依赖于部署环境的配置的配置设置。</span><span class="sxs-lookup"><span data-stu-id="05092-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="05092-185">你还可以具有不同名称的多个重写文件。</span><span class="sxs-lookup"><span data-stu-id="05092-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="05092-186">重写文件通常包含对环境或部署但特定应用所需的其他信息。</span><span class="sxs-lookup"><span data-stu-id="05092-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="05092-187">面向多个环境</span><span class="sxs-lookup"><span data-stu-id="05092-187">Targeting multiple environments</span></span>

<span data-ttu-id="05092-188">典型的用例是在定义多个构成文件以便你可以面向多个环境，如生产环境，暂存，CI 使用，请或开发。</span><span class="sxs-lookup"><span data-stu-id="05092-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="05092-189">若要支持这些差异，你可以在图 8-12 中所示拆分到多个文件，您撰写的配置。</span><span class="sxs-lookup"><span data-stu-id="05092-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="05092-190">**图 8-12**。</span><span class="sxs-lookup"><span data-stu-id="05092-190">**Figure 8-12**.</span></span> <span data-ttu-id="05092-191">多个 docker compose 文件重写基 docker-compose.yml 文件中的值</span><span class="sxs-lookup"><span data-stu-id="05092-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="05092-192">你开始基 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="05092-193">此基本文件必须包含不会更改根据环境的基或静态配置设置。</span><span class="sxs-lookup"><span data-stu-id="05092-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="05092-194">例如，eShopOnContainers 与基文件具有以下 docker-compose.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

<span data-ttu-id="05092-195">由于不同的目标部署环境，不应更改基 docker-compose.yml 文件中的值。</span><span class="sxs-lookup"><span data-stu-id="05092-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="05092-196">如果你专注于 webmvc 服务定义，例如，可以看到该信息的无论何种环境，你可能会以目标大致相同的方式。</span><span class="sxs-lookup"><span data-stu-id="05092-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="05092-197">具有以下信息：</span><span class="sxs-lookup"><span data-stu-id="05092-197">You have the following information:</span></span>

-   <span data-ttu-id="05092-198">服务名称： webmvc。</span><span class="sxs-lookup"><span data-stu-id="05092-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="05092-199">容器的自定义映像： 电子商店/webmvc。</span><span class="sxs-lookup"><span data-stu-id="05092-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="05092-200">若要生成自定义的 Docker 映像、 要使用哪些 Dockerfile，该值指示该命令。</span><span class="sxs-lookup"><span data-stu-id="05092-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="05092-201">其他服务，因此此容器才会启动其他依赖项容器的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="05092-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="05092-202">你可以有其他配置，但重要的一点是，在基 docker-compose.yml 文件中，你只是想要设置其能够在环境之间通用的信息。</span><span class="sxs-lookup"><span data-stu-id="05092-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="05092-203">然后在 docker compose.override.yml 或生产或过渡的类似文件中，应设置为每个环境特定的配置。</span><span class="sxs-lookup"><span data-stu-id="05092-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="05092-204">通常情况下，docker compose.override.yml 用于你的开发环境，如 eShopOnContainers 的以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="05092-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="05092-205">在此示例中，开发替代配置公开到主机某些端口、 定义环境变量重定向 Url，并指定开发环境的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="05092-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="05092-206">这些设置适用于开发环境的所有对象都是。</span><span class="sxs-lookup"><span data-stu-id="05092-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="05092-207">当你运行 docker compose 向上 （或启动从 Visual Studio），该命令读取替代自动就像它已合并这两个文件。</span><span class="sxs-lookup"><span data-stu-id="05092-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="05092-208">假设你想为生产环境中，使用不同的配置值的另一个 Compose 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="05092-209">你可以创建另一个重写文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="05092-209">You can create another override file, like the following.</span></span> <span data-ttu-id="05092-210">（此文件可能是不同的 Git 存储库中存储或管理和保护的其他团队。）</span><span class="sxs-lookup"><span data-stu-id="05092-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="05092-211">如何使用特定重写文件进行部署</span><span class="sxs-lookup"><span data-stu-id="05092-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="05092-212">若要使用不同的名称中使用多个重写文件或重写文件，你可以使用-f 选项与 docker compose 命令并指定的文件。</span><span class="sxs-lookup"><span data-stu-id="05092-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="05092-213">构成合并文件在命令行指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="05092-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="05092-214">下面的示例演示如何使用替代文件进行部署。</span><span class="sxs-lookup"><span data-stu-id="05092-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="05092-215">使用环境变量在 docker-撰写文件</span><span class="sxs-lookup"><span data-stu-id="05092-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="05092-216">可以很方便，尤其是在生产环境中，若要能够从环境变量中获取的配置信息，如我们具有前面示例中所示。</span><span class="sxs-lookup"><span data-stu-id="05092-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="05092-217">在你 docker-compose 文件中使用的语法引用环境变量\${MY\_VAR}。</span><span class="sxs-lookup"><span data-stu-id="05092-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="05092-218">Docker compose.prod.yml 文件的以下行显示了如何引用环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="05092-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="05092-219">创建和初始化在不同的方式，具体取决于宿主环境中环境变量 (Linux、 Windows，云群集等。)。</span><span class="sxs-lookup"><span data-stu-id="05092-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="05092-220">但是，方便的方法是使用.env 文件。</span><span class="sxs-lookup"><span data-stu-id="05092-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="05092-221">Docker-compose 文件支持声明.env 文件中的默认环境变量。</span><span class="sxs-lookup"><span data-stu-id="05092-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="05092-222">这些环境变量的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="05092-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="05092-223">但可以重写它们可能会在你的环境 （主机操作系统或从你的群集的环境变量） 的每个定义的值。</span><span class="sxs-lookup"><span data-stu-id="05092-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="05092-224">将此.env 文件放置在文件夹中其中 docker compose 从执行命令。</span><span class="sxs-lookup"><span data-stu-id="05092-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="05092-225">下面的示例演示类似.env 文件[.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) eShopOnContainers 应用程序文件。</span><span class="sxs-lookup"><span data-stu-id="05092-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="05092-226">Docker compose 要求的格式为.env 文件中的每个行&lt;变量&gt;=&lt;值&gt;。</span><span class="sxs-lookup"><span data-stu-id="05092-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="05092-227">请注意，始终在运行时环境中设置的值覆盖.env 文件内定义的值。</span><span class="sxs-lookup"><span data-stu-id="05092-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="05092-228">以类似的方式，通过命令行命令自变量传递的值还重写.env 文件中设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="05092-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="05092-229">其他资源</span><span class="sxs-lookup"><span data-stu-id="05092-229">Additional resources</span></span>

-   <span data-ttu-id="05092-230">**概述 Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="05092-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="05092-231">**多个 Compose 文件**
    [*https://docs.docker.com/compose/extends/\#多个构成文件*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="05092-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="05092-232">构建优化 ASP.NET 核心 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="05092-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="05092-233">如果在 Internet 上的源上浏览 Docker 和.NET 核心，则会发现演示通过将你的源复制到容器中生成的 Docker 映像的简单的 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="05092-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="05092-234">这些示例建议通过使用简单的配置，您可以有的 Docker 映像与你的应用程序一起打包的环境。</span><span class="sxs-lookup"><span data-stu-id="05092-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="05092-235">下面的示例演示了在此情况下的简单 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="05092-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="05092-236">如下 Dockerfile 起作用。</span><span class="sxs-lookup"><span data-stu-id="05092-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="05092-237">但是，你可以大大优化你的映像，尤其是你的生产映像。</span><span class="sxs-lookup"><span data-stu-id="05092-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="05092-238">在容器和微服务模型中，你不断地开始容器。</span><span class="sxs-lookup"><span data-stu-id="05092-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="05092-239">使用容器的典型方法不重新启动睡眠的容器，因为容器是可释放。</span><span class="sxs-lookup"><span data-stu-id="05092-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="05092-240">Orchestrators （如 Docker Swarm、 Kubernetes、 DCOS 或 Azure Service Fabric） 只需创建映像的新的实例。</span><span class="sxs-lookup"><span data-stu-id="05092-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="05092-241">这意味着，你将需要通过预编译应用程序，以便实例化过程会更快生成时优化。</span><span class="sxs-lookup"><span data-stu-id="05092-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="05092-242">当启动容器时，它应该已准备好运行。</span><span class="sxs-lookup"><span data-stu-id="05092-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="05092-243">不应还原，并在运行时编译，使用 dotnet 还原和 dotnet 生成从 dotnet CLI 命令，正如你所看到的有关.NET 核心和 Docker 的多篇博客文章中。</span><span class="sxs-lookup"><span data-stu-id="05092-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="05092-244">.NET 团队具有已进行重要的工作来进行.NET Core 和 ASP.NET Core 容器优化 framework。</span><span class="sxs-lookup"><span data-stu-id="05092-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="05092-245">使用小的内存需求量; 一个轻型框架不只是.NET 核心团队未侧重于启动性能而产生一些优化的 Docker 映像，如[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)映像在[Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/)，与常规相比[microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)或[microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile)映像。</span><span class="sxs-lookup"><span data-stu-id="05092-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="05092-246">[Microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)图显示了自动设置 aspnetcore\_url 对端口 80 和 pre ngend 缓存的程序集; 这两种设置导致启动速度更快。</span><span class="sxs-lookup"><span data-stu-id="05092-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="05092-247">其他资源</span><span class="sxs-lookup"><span data-stu-id="05092-247">Additional resources</span></span>

-   <span data-ttu-id="05092-248">**构建优化与 ASP.NET 核心的 Docker 映像**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="05092-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="05092-249">生成从生成 (CI) 容器应用程序</span><span class="sxs-lookup"><span data-stu-id="05092-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="05092-250">Docker 的另一个好处是，你可以生成应用程序从预配置的容器，如所示图 8-13，因此不需要创建的生成计算机或 VM 都生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="05092-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="05092-251">你可以使用或通过运行在你的开发计算机中测试该生成容器。</span><span class="sxs-lookup"><span data-stu-id="05092-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="05092-252">但更有趣的是你可以从 CI （持续集成） 管道中使用相同的生成容器。</span><span class="sxs-lookup"><span data-stu-id="05092-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="05092-253">**图 8-13**。</span><span class="sxs-lookup"><span data-stu-id="05092-253">**Figure 8-13**.</span></span> <span data-ttu-id="05092-254">生成.NET bits 从容器的组件</span><span class="sxs-lookup"><span data-stu-id="05092-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="05092-255">对于此方案中，我们提供[microsoft/aspnetcore-生成](https://hub.docker.com/r/microsoft/aspnetcore-build/)映像，可用于编译和生成 ASP.NET Core 应用。</span><span class="sxs-lookup"><span data-stu-id="05092-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="05092-256">在基于映像放置输出[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)映像，这是一个优化运行时映像，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="05092-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="05092-257">Aspnetcore 生成映像包含所需的一切以便编译 ASP.NET Core 应用程序，包括.NET 核心、 ASP.NET SDK、 npm Bower、 Gulp，等等。</span><span class="sxs-lookup"><span data-stu-id="05092-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="05092-258">在生成时，我们需要这些依赖关系。</span><span class="sxs-lookup"><span data-stu-id="05092-258">We need these dependencies at build time.</span></span> <span data-ttu-id="05092-259">但我们不希望执行这些与应用程序在运行时，因为这会使图像不必要的大型。</span><span class="sxs-lookup"><span data-stu-id="05092-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="05092-260">在 eShopOnContainers 应用程序，可以生成应用程序从容器通过只需运行以下 docker-编写命令。</span><span class="sxs-lookup"><span data-stu-id="05092-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="05092-261">图 8-14 显示在命令行运行此命令。</span><span class="sxs-lookup"><span data-stu-id="05092-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="05092-262">**图 8-14。**</span><span class="sxs-lookup"><span data-stu-id="05092-262">**Figure 8-14.**</span></span> <span data-ttu-id="05092-263">生成.NET 应用程序从容器</span><span class="sxs-lookup"><span data-stu-id="05092-263">Building your .NET application from a container</span></span>

<span data-ttu-id="05092-264">如你所见，正在运行的容器是 ci 生成\_1 容器。</span><span class="sxs-lookup"><span data-stu-id="05092-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="05092-265">这基于 aspnetcore 生成映像，以便它可以编译并生成从您的电脑的整个从应用程序而不是该容器中。</span><span class="sxs-lookup"><span data-stu-id="05092-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="05092-266">就是为什么实际上它是生成和编译在 Linux 中的.NET 核心项目，因为在默认 Docker Linux 主机上运行该容器。</span><span class="sxs-lookup"><span data-stu-id="05092-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="05092-267">[Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml)文件 （eShopOnContainers 的一部分） 该映像包含下面的代码。</span><span class="sxs-lookup"><span data-stu-id="05092-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="05092-268">你可以看到，它会开始生成容器使用[microsoft/aspnetcore-生成](https://hub.docker.com/r/microsoft/aspnetcore-build/)映像。</span><span class="sxs-lookup"><span data-stu-id="05092-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* <span data-ttu-id="05092-269">从开始**.NET 核心 2.0**，`dotnet restore`自动执行命令时`dotnet publish`执行命令。</span><span class="sxs-lookup"><span data-stu-id="05092-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="05092-270">启动并正在运行的生成容器后，它运行.NET SDK dotnet 还原和 dotnet 中发布针对的所有项目的命令在解决方案中，以便编译的.NET 位。</span><span class="sxs-lookup"><span data-stu-id="05092-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="05092-271">在这种情况下，由于 eShopOnContainers 还具有基于 TypeScript 和角适用于客户端代码 SPA，它还需要检查与 npm，JavaScript 依赖关系，但操作不相关的.NET 位。</span><span class="sxs-lookup"><span data-stu-id="05092-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="05092-272">Dotnet publish 命令生成并发布到的每个项目的文件夹中编译的输出.../obj/Docker/publish 文件夹，如图 8-15 中所示。</span><span class="sxs-lookup"><span data-stu-id="05092-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="05092-273">**图 8-15。**</span><span class="sxs-lookup"><span data-stu-id="05092-273">**Figure 8-15.**</span></span> <span data-ttu-id="05092-274">由 dotnet 生成的二进制文件发布命令</span><span class="sxs-lookup"><span data-stu-id="05092-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="05092-275">从 CLI 创建 Docker 映像</span><span class="sxs-lookup"><span data-stu-id="05092-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="05092-276">一旦应用程序输出发布到相关的文件夹 （在每个项目） 下, 一步是实际生成的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="05092-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="05092-277">要执行此操作，请使用 docker-compose 生成，并向上命令，如所示图 8-16 docker compose。</span><span class="sxs-lookup"><span data-stu-id="05092-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="05092-278">**图 8-16。**</span><span class="sxs-lookup"><span data-stu-id="05092-278">**Figure 8-16.**</span></span> <span data-ttu-id="05092-279">构建 Docker 映像和正在运行的容器</span><span class="sxs-lookup"><span data-stu-id="05092-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="05092-280">在图 8-17 中，你可以看到如何 docker-compose 生成命令运行。</span><span class="sxs-lookup"><span data-stu-id="05092-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="05092-281">**图 8-17**。</span><span class="sxs-lookup"><span data-stu-id="05092-281">**Figure 8-17**.</span></span> <span data-ttu-id="05092-282">使用 docker 生成的 Docker 映像-编写生成命令</span><span class="sxs-lookup"><span data-stu-id="05092-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="05092-283">Docker-compose 之间的差异生成并向上 docker compose 命令是 docker compose 生成和启动映像。</span><span class="sxs-lookup"><span data-stu-id="05092-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="05092-284">当你使用 Visual Studio 时，所有这些步骤将在后台执行。</span><span class="sxs-lookup"><span data-stu-id="05092-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="05092-285">Visual Studio 编译你的.NET 应用程序，创建的 Docker 映像，并将容器部署到 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="05092-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="05092-286">Visual Studio 提供了附加功能，如调试你直接从 Visual Studio 在 Docker 中运行的容器的功能。</span><span class="sxs-lookup"><span data-stu-id="05092-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="05092-287">总体 takeway 此处是是否可以生成应用程序相同的方式 CI/CD 管道应生成 — 从容器，而不是从本地计算机。</span><span class="sxs-lookup"><span data-stu-id="05092-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="05092-288">创建的映像后，那么你只需运行使用 docker 的 Docker 映像的命令编写。</span><span class="sxs-lookup"><span data-stu-id="05092-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="05092-289">其他资源</span><span class="sxs-lookup"><span data-stu-id="05092-289">Additional resources</span></span>

-   <span data-ttu-id="05092-290">**生成从容器的 bits： 在 Windows CLI 环境 (dotnet 为 CLI，Docker CLI 和 VS Code) 中设置 eShopOnContainers 解决方案**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="05092-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="05092-291">[以前](数据-驱动的 crud-microservice.md) [下一步] (数据库的服务器-container.md)</span><span class="sxs-lookup"><span data-stu-id="05092-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
