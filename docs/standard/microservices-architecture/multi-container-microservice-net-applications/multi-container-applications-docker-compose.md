---
title: 使用 docker-compose.yml 定义多容器应用程序
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 如何使用 docker-compose.yml 为多容器应用程序指定微服务组合。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: dc9149cb1a17e3af66abd995fd2a2196109e0e05
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145249"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="40b80-103">使用 docker-compose.yml 定义多容器应用程序</span><span class="sxs-lookup"><span data-stu-id="40b80-103">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="40b80-104">本指南中，[docker-compose.yml](https://docs.docker.com/compose/compose-file/) 文件在[步骤 4.生成多容器 Docker 应用程序时，在 docker-compose.yml 中定义服务](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application)部分中介绍。</span><span class="sxs-lookup"><span data-stu-id="40b80-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="40b80-105">但还有其他方式可使用 docker-compose 文件，这值得进一步探索。</span><span class="sxs-lookup"><span data-stu-id="40b80-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="40b80-106">例如，可明确描述希望如何在 docker-compose.yml 文件中部署多容器应用程序。</span><span class="sxs-lookup"><span data-stu-id="40b80-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="40b80-107">此外，也可以描述将如何生成自定义 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="40b80-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="40b80-108">（也可以使用 Docker CLI 生成自定义 Docker 映像。）</span><span class="sxs-lookup"><span data-stu-id="40b80-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="40b80-109">基本上，开发人员需定义想要部署的每个容器以及每个容器部署的某些特征。</span><span class="sxs-lookup"><span data-stu-id="40b80-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="40b80-110">拥有多容器部署说明文件后，即可通过由 [docker-compose up](https://docs.docker.com/compose/overview/) CLI 命令编制的单个操作部署整个解决方案，也可简单从 Visual Studio 进行部署。</span><span class="sxs-lookup"><span data-stu-id="40b80-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="40b80-111">否则，需要在命令行中使用 `docker run` 命令，通过 Docker CLI 经多个步骤逐个部署容器。</span><span class="sxs-lookup"><span data-stu-id="40b80-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="40b80-112">因此，docker-compose.yml 中定义的每个服务都必须指定一个映像或生成映像。</span><span class="sxs-lookup"><span data-stu-id="40b80-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="40b80-113">其他为可选密钥，且类似于其 `docker run` 命令行对应项。</span><span class="sxs-lookup"><span data-stu-id="40b80-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="40b80-114">以下 YAML 代码是 eShopOnContainers 示例的单个 docker-compose.yml 文件的定义，文件可能是全局文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="40b80-115">这不是来自 eShopOnContainers 的实际 docker-compose 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="40b80-116">相反，简化和合并后的单个文件，这不是使用 docker-compose 文件的最佳方式，稍后将对此进行解释。</span><span class="sxs-lookup"><span data-stu-id="40b80-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

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

<span data-ttu-id="40b80-117">此文件中的根密钥是服务。</span><span class="sxs-lookup"><span data-stu-id="40b80-117">The root key in this file is services.</span></span> <span data-ttu-id="40b80-118">在该密钥下，可在执行 `docker-compose up` 命令或使用此 docker-compose.yml 文件从 Visual Studio 进行部署时，定义要部署和运行的服务。</span><span class="sxs-lookup"><span data-stu-id="40b80-118">Under that key you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="40b80-119">在这种情况下，docker-compose.yml 文件定义了多个服务，如以下表所述。</span><span class="sxs-lookup"><span data-stu-id="40b80-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="40b80-120">服务名称</span><span class="sxs-lookup"><span data-stu-id="40b80-120">Service name</span></span> | <span data-ttu-id="40b80-121">说明</span><span class="sxs-lookup"><span data-stu-id="40b80-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="40b80-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="40b80-122">webmvc</span></span>       | <span data-ttu-id="40b80-123">容器，包括从服务器端 C\# 使用微服务的 ASP.NET Core MVC 应用程序</span><span class="sxs-lookup"><span data-stu-id="40b80-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="40b80-124">catalog.api</span><span class="sxs-lookup"><span data-stu-id="40b80-124">catalog.api</span></span>  | <span data-ttu-id="40b80-125">容器，包括 Catalog ASP.NET Core Web API 微服务</span><span class="sxs-lookup"><span data-stu-id="40b80-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="40b80-126">ordering.api</span><span class="sxs-lookup"><span data-stu-id="40b80-126">ordering.api</span></span> | <span data-ttu-id="40b80-127">容器，包括 Ordering ASP.NET Core Web API 微服务</span><span class="sxs-lookup"><span data-stu-id="40b80-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="40b80-128">sql.data</span><span class="sxs-lookup"><span data-stu-id="40b80-128">sql.data</span></span>     | <span data-ttu-id="40b80-129">容器，运行适用于 Linux 的 SQL Server，并保存微服务数据库</span><span class="sxs-lookup"><span data-stu-id="40b80-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="40b80-130">basket.api</span><span class="sxs-lookup"><span data-stu-id="40b80-130">basket.api</span></span>   | <span data-ttu-id="40b80-131">容器，包含有 Basket ASP.NET Core Web API 微服务</span><span class="sxs-lookup"><span data-stu-id="40b80-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="40b80-132">basket.data</span><span class="sxs-lookup"><span data-stu-id="40b80-132">basket.data</span></span>  | <span data-ttu-id="40b80-133">容器，运行 REDIS 缓存服务，并将篮数据库作为 REDIS 缓存</span><span class="sxs-lookup"><span data-stu-id="40b80-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="40b80-134">简单的 Web 服务 API 容器</span><span class="sxs-lookup"><span data-stu-id="40b80-134">A simple Web Service API container</span></span>

<span data-ttu-id="40b80-135">关注单个容器，catalog.api 容器微服务的定义很简单：</span><span class="sxs-lookup"><span data-stu-id="40b80-135">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
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
```

<span data-ttu-id="40b80-136">这种容器化服务具有以下基本配置：</span><span class="sxs-lookup"><span data-stu-id="40b80-136">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="40b80-137">它基于自定义 eshop/catalog.api 映像。</span><span class="sxs-lookup"><span data-stu-id="40b80-137">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="40b80-138">为简便起见，文件中没有 build: key 设置。</span><span class="sxs-lookup"><span data-stu-id="40b80-138">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="40b80-139">这意味着，必须事先生成（使用 docker build 命令）映像或从任何 Docker 注册表下载（使用 docker pull 命令）映像。</span><span class="sxs-lookup"><span data-stu-id="40b80-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="40b80-140">它定义了一个名为 ConnectionString 的环境变量，Entity Framework 使用连接字符串用来访问包含目录数据模型的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="40b80-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="40b80-141">在这种情况下，同一 SQL Server 容器拥有多个数据库。</span><span class="sxs-lookup"><span data-stu-id="40b80-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="40b80-142">因此，开发 Docker 时所需计算机内存减少。</span><span class="sxs-lookup"><span data-stu-id="40b80-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="40b80-143">但是，开发人员也可以为每个微服务数据库部署一个 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="40b80-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="40b80-144">SQL Server 的名称是 sql.data，与运行适用于 Linux 的 SQL Server 实例的容器的名称相同。</span><span class="sxs-lookup"><span data-stu-id="40b80-144">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="40b80-145">这很方便，因为使用此名称解析（Docker 主机内部）可解析网络地址，这样从其他容器访问容器时，无需了解受访容器的内部 IP。</span><span class="sxs-lookup"><span data-stu-id="40b80-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="40b80-146">由于连接字符串由环境变量定义，因此可在不同的时间通过不同机制设置该变量。</span><span class="sxs-lookup"><span data-stu-id="40b80-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="40b80-147">例如，在最终主机中部署到生产时，可设置不同的连接字符串，或通过 Azure DevOps Services 中的 CI/CD 管道或喜爱的 DevOps 系统来完成。</span><span class="sxs-lookup"><span data-stu-id="40b80-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

-   <span data-ttu-id="40b80-148">它公开了端口 80，用于对 Docker 主机中的 catalog.api 服务进行内部访问。</span><span class="sxs-lookup"><span data-stu-id="40b80-148">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="40b80-149">目前的主机是 Linux VM，因为它以适用于 Linux 的 Docker 映像为基础，但开发人员可配置该容器，使其在 Windows 映像上运行。</span><span class="sxs-lookup"><span data-stu-id="40b80-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="40b80-150">它将容器上公开的端口 80 转接到 Docker 主机 (Linux VM) 上的端口 5101。</span><span class="sxs-lookup"><span data-stu-id="40b80-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="40b80-151">它将 Web 服务链接到 sql.data 服务（在容器中运行的 Linux 数据库的 SQL Server 实例）。</span><span class="sxs-lookup"><span data-stu-id="40b80-151">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="40b80-152">指定此依赖项时，在 sql.data 容器启动后，catalog.api 容器才会启动；这一点很重要，因为 catalog.api 需要先启动并运行 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="40b80-152">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="40b80-153">但是，在许多情况下，这种容器依赖项不足，因为 Docker 只能在容器级别进行检查。</span><span class="sxs-lookup"><span data-stu-id="40b80-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="40b80-154">有时服务（在此情况下为 SQL Server）可能还未准备就绪，因此建议在客户端微服务中实施具有指数回退的重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="40b80-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="40b80-155">这样一来，如果依赖项容器在短时间内未准备就绪，应用程序仍然可以复原。</span><span class="sxs-lookup"><span data-stu-id="40b80-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="40b80-156">它被配置为允许访问外部服务器：extra\_hosts 设置允许访问 Docker 主机之外的外部服务器或计算机（即作为开发 Docker 主机的默认 Linux VM 以外的），例如开发计算机上的本地 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="40b80-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="40b80-157">此外，还有其他更高级的 docker-compose.yml 设置，我们将在下面的部分介绍。</span><span class="sxs-lookup"><span data-stu-id="40b80-157">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="40b80-158">针对多个环境使用 docker-compose 文件</span><span class="sxs-lookup"><span data-stu-id="40b80-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="40b80-159">docker-compose.yml 文件是定义文件，可供多种支持该格式的基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="40b80-159">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="40b80-160">最简单的工具是 docker-compose 命令。</span><span class="sxs-lookup"><span data-stu-id="40b80-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="40b80-161">因此，可针对以下主要方案使用 docker-compose 命令。</span><span class="sxs-lookup"><span data-stu-id="40b80-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="40b80-162">开发环境</span><span class="sxs-lookup"><span data-stu-id="40b80-162">Development environments</span></span>

<span data-ttu-id="40b80-163">开发应用程序时，能够在独立开发环境中运行应用程序非常重要。</span><span class="sxs-lookup"><span data-stu-id="40b80-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="40b80-164">开发人员可使用 docker-compose CLI 命令来创建该环境，或使用在后台使用 docker-compose 的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="40b80-164">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="40b80-165">docker-compose.yml 文件可配置和记录所有应用程序的服务依赖项（其他服务、缓存、数据库、队列等）。</span><span class="sxs-lookup"><span data-stu-id="40b80-165">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="40b80-166">使用 docker-compose CLI 命令，可通过单个命令 (docker-compose up) 为每个依赖项创建并启动一个或多个容器。</span><span class="sxs-lookup"><span data-stu-id="40b80-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="40b80-167">docker-compose.yml 文件是由 Docker 引擎解释的配置文件，但也可作为有关多容器应用程序组成的方便文档文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="40b80-168">测试环境</span><span class="sxs-lookup"><span data-stu-id="40b80-168">Testing environments</span></span>

<span data-ttu-id="40b80-169">任何持续部署 (CD) 或持续集成 (CI) 过程都离不开单元测试和集成测试。</span><span class="sxs-lookup"><span data-stu-id="40b80-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="40b80-170">这些自动化测试需要独立的环境，以便它们不受用户或应用程序数据变化的影响。</span><span class="sxs-lookup"><span data-stu-id="40b80-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="40b80-171">使用 Docker Compose，可通过命令提示符或脚本中的几条命令非常轻松地创建和摧毁该独立环境，如以下命令：</span><span class="sxs-lookup"><span data-stu-id="40b80-171">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose.test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="40b80-172">生产部署</span><span class="sxs-lookup"><span data-stu-id="40b80-172">Production deployments</span></span>

<span data-ttu-id="40b80-173">开发人员还可使用 Compose 部署到远程 Docker 引擎。</span><span class="sxs-lookup"><span data-stu-id="40b80-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="40b80-174">部署到单个 Docker 主机实例（例如配置了 [Docker Machine](https://docs.docker.com/machine/overview/) 的生产 VM 或服务器）就是一个典型的例子。</span><span class="sxs-lookup"><span data-stu-id="40b80-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="40b80-175">如果正在使用任何其他业务流程协调程序（Azure Service Fabric、Kubernetes 等），则可能需要添加如 docker-compose.yml 中的设置和元数据配置设置，但需采用其他业务流程协调程序所需的格式。</span><span class="sxs-lookup"><span data-stu-id="40b80-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="40b80-176">在任何情况下，docker-compose 都是用于开发、测试和生产工作流的便捷工具和元数据格式，但生产工作流可能因使用的业务流程协调程序而异。</span><span class="sxs-lookup"><span data-stu-id="40b80-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="40b80-177">使用多个 docker-compose 文件来处理多个环境</span><span class="sxs-lookup"><span data-stu-id="40b80-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="40b80-178">针对不同环境时，应使用多个 compose 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="40b80-179">这样可以根据环境创建多个配置变体。</span><span class="sxs-lookup"><span data-stu-id="40b80-179">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="40b80-180">重写基本 docker-compose 文件</span><span class="sxs-lookup"><span data-stu-id="40b80-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="40b80-181">开发人员可使用单个 docker-compose.yml 文件，如前面部分中的简化示例所示。</span><span class="sxs-lookup"><span data-stu-id="40b80-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="40b80-182">但是，对于大多数应用程序不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="40b80-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="40b80-183">默认情况下，Compose 读取两个文件，docker-compose.yml 和可选的 docker-compose.override.yml 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="40b80-184">如图 6-11 所示，使用 Visual Studio 并启用 Docker 支持时，Visual Studio 还会创建另一个用于调试应用程序的 docker compose.vs.debug.g.yml 文件，可在主解决方案文件夹的 obj\\Docker\\ 文件夹中查看此文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![docker-compose 项目文件结构：.dockerignore，用于忽略文件；docker-compose.yml，用于组合微服务；docker-compose.override.yml，用于配置微服务环境。](./media/image12.png)

<span data-ttu-id="40b80-186">图 6-11。</span><span class="sxs-lookup"><span data-stu-id="40b80-186">**Figure 6-11**.</span></span> <span data-ttu-id="40b80-187">Visual Studio 2017 中的 docker-compose 文件</span><span class="sxs-lookup"><span data-stu-id="40b80-187">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="40b80-188">可使用任何编辑器（如 Visual Studio Code 或 Sublime）编辑 docker-compose 文件，并使用 docker-compose up 命令运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="40b80-188">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="40b80-189">按照约定，docker-compose.yml 文件包含基本配置和其他静态设置。</span><span class="sxs-lookup"><span data-stu-id="40b80-189">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="40b80-190">这意味着服务配置不应该根据所针对的部署环境而改变。</span><span class="sxs-lookup"><span data-stu-id="40b80-190">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="40b80-191">顾名思义，docker-compose.override.yml 文件包含替代基本配置的配置设置，例如依赖于部署环境的配置。</span><span class="sxs-lookup"><span data-stu-id="40b80-191">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="40b80-192">用户也可以拥有具有不同名称的多个重写文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-192">You can have multiple override files with different names also.</span></span> <span data-ttu-id="40b80-193">重写文件通常包含应用程序所需的但特定于环境或部署的其他信息。</span><span class="sxs-lookup"><span data-stu-id="40b80-193">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="40b80-194">针对多个环境</span><span class="sxs-lookup"><span data-stu-id="40b80-194">Targeting multiple environments</span></span>

<span data-ttu-id="40b80-195">典型的用例是定义多个 compose 文件时，可针对多个环境，如生产、暂存、CI 或开发环境。</span><span class="sxs-lookup"><span data-stu-id="40b80-195">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="40b80-196">为支持这些差异，可将 Compose 配置拆分成多个文件，如图 6-12 所示。</span><span class="sxs-lookup"><span data-stu-id="40b80-196">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![可组合多个 docker compose\*.fml 文件来应对不同的环境。](./media/image13.png)

<span data-ttu-id="40b80-198">图 6-12。</span><span class="sxs-lookup"><span data-stu-id="40b80-198">**Figure 6-12**.</span></span> <span data-ttu-id="40b80-199">重写基本 docker-compose.yml 文件中的值的多个 docker-compose 文件</span><span class="sxs-lookup"><span data-stu-id="40b80-199">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="40b80-200">从基本 docker-compose.yml 文件开始。</span><span class="sxs-lookup"><span data-stu-id="40b80-200">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="40b80-201">此基本文件必须包含不会根据环境更改的基本或静态配置设置。</span><span class="sxs-lookup"><span data-stu-id="40b80-201">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="40b80-202">例如，eShopOnContainers 将以下 docker-compose.yml 文件（使用少量服务以进行简化）作为基本文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-202">For example, the eShopOnContainers has the following docker-compose.yml file (simplified with less services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="40b80-203">基本 docker-compose.yml 文件中的值不应因目标部署环境不同而不同。</span><span class="sxs-lookup"><span data-stu-id="40b80-203">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="40b80-204">例如，如果专注于 webmvc 服务定义，则可以看到无论目标环境如何，这些信息都相同。</span><span class="sxs-lookup"><span data-stu-id="40b80-204">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="40b80-205">会看到以下信息：</span><span class="sxs-lookup"><span data-stu-id="40b80-205">You have the following information:</span></span>

-   <span data-ttu-id="40b80-206">服务名称：webmvc。</span><span class="sxs-lookup"><span data-stu-id="40b80-206">The service name: webmvc.</span></span>

-   <span data-ttu-id="40b80-207">容器的自定义映像：eshop/webmvc。</span><span class="sxs-lookup"><span data-stu-id="40b80-207">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="40b80-208">生成自定义 Docker 映像的命令，指示要使用的 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="40b80-208">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="40b80-209">其他服务依赖项，所以此容器在其他依赖项容器启动之前不会启动。</span><span class="sxs-lookup"><span data-stu-id="40b80-209">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="40b80-210">开发人员可进行其他配置，但重要的一点是，在基本 docker-compose.yml 文件中，只需设置各环境的共同信息。</span><span class="sxs-lookup"><span data-stu-id="40b80-210">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="40b80-211">然后，在 docker-compose.override.yml 或用于生产或暂存的类似文件中，应配置特定于每个环境的配置。</span><span class="sxs-lookup"><span data-stu-id="40b80-211">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="40b80-212">通常，docker-compose.override.yml 适用于开发环境，如 eShopOnContainers 中的以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="40b80-212">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}      
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}   
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}         
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="40b80-213">在此示例中，开发替代配置向主机公开一些端口，使用重定向 URL 定义环境变量，并为开发环境指定连接字符串。</span><span class="sxs-lookup"><span data-stu-id="40b80-213">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="40b80-214">这些设置都只针对开发环境。</span><span class="sxs-lookup"><span data-stu-id="40b80-214">These settings are all just for the development environment.</span></span>

<span data-ttu-id="40b80-215">运行 `docker-compose up`（或从 Visual Studio 启动它时）时，该命令会自动读取替代内容，就像它已合并这两个文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-215">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="40b80-216">假设想为生产环境使用具有不同配置值、端口或连接字符串的另一个 Compose 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-216">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="40b80-217">可创建另一个重写文件，如具有不同设置和环境变量的名为 `docker-compose.prod.yml` 的文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-217">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span>  <span data-ttu-id="40b80-218">该文件可能存储在不同 Git 存储库中，或由其他团队管理和保护。</span><span class="sxs-lookup"><span data-stu-id="40b80-218">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="40b80-219">如何使用特定重写文件进行部署</span><span class="sxs-lookup"><span data-stu-id="40b80-219">How to deploy with a specific override file</span></span>

<span data-ttu-id="40b80-220">若要使用多个重写文件或具有不同名称的重写文件，可通过 docker-compose 命令使用 -f 选项并指定文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-220">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="40b80-221">按照合并文件在命令行上的指定顺序进行撰写。</span><span class="sxs-lookup"><span data-stu-id="40b80-221">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="40b80-222">以下示例演示如何使用重写文件进行部署。</span><span class="sxs-lookup"><span data-stu-id="40b80-222">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="40b80-223">在 docker-compose 文件中使用环境变量</span><span class="sxs-lookup"><span data-stu-id="40b80-223">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="40b80-224">如前面的示例所示，开发人员可方便地从环境变量中获取配置信息，尤其是在生产环境中。</span><span class="sxs-lookup"><span data-stu-id="40b80-224">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="40b80-225">可使用语法 ${MY\_VAR} 在 docker-compose 文件中引用环境变量。</span><span class="sxs-lookup"><span data-stu-id="40b80-225">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="40b80-226">docker-compose.prod.yml 文件中的以下行显示如何引用环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="40b80-226">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="40b80-227">创建和初始化环境变量的方式不同，具体取决于主机环境（Linux、Windows、云集群等）。</span><span class="sxs-lookup"><span data-stu-id="40b80-227">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="40b80-228">但是，便捷方法是使用 .env 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-228">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="40b80-229">docker-compose 文件支持在 .env 文件中声明默认环境变量。</span><span class="sxs-lookup"><span data-stu-id="40b80-229">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="40b80-230">这些环境变量的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="40b80-230">These values for the environment variables are the default values.</span></span> <span data-ttu-id="40b80-231">但开发人员在每个环境（主机操作系统或群集中的环境变量）中定义的值可重写这些默认值。</span><span class="sxs-lookup"><span data-stu-id="40b80-231">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="40b80-232">将此 .env 文件放置在执行 docker-compose 命令的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="40b80-232">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="40b80-233">以下示例展示了 .env 文件，例如用于 eShopOnContainers 应用程序的 [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) 文件。</span><span class="sxs-lookup"><span data-stu-id="40b80-233">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="40b80-234">Docker-compose 要求 .env 文件中的每行都是 \<variable\>=\<value\> 格式。</span><span class="sxs-lookup"><span data-stu-id="40b80-234">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="40b80-235">请注意，运行时环境中设置的值始终会重写 .env 文件中定义的值。</span><span class="sxs-lookup"><span data-stu-id="40b80-235">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="40b80-236">同样，通过命令行命令参数传递的值也会重写 .env 文件中设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="40b80-236">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="40b80-237">其他资源</span><span class="sxs-lookup"><span data-stu-id="40b80-237">Additional resources</span></span>

-   <span data-ttu-id="40b80-238">**Docker Compose 概述**</span><span class="sxs-lookup"><span data-stu-id="40b80-238">**Overview of Docker Compose**</span></span> <br/>
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   <span data-ttu-id="40b80-239">**多个 Compose 文件**</span><span class="sxs-lookup"><span data-stu-id="40b80-239">**Multiple Compose files**</span></span> <br/>
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="40b80-240">生成优化的 ASP.NET Core Docker 映像</span><span class="sxs-lookup"><span data-stu-id="40b80-240">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="40b80-241">如果查看 Internet 上源代码的 Docker 和 .NET Core ，则会发现 Dockerfiles 会将源代码源复制到容器，展现生成 Docker 映像的简单性。</span><span class="sxs-lookup"><span data-stu-id="40b80-241">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="40b80-242">这些示例表明，使用简单配置，即可拥有 Docker 映像，同时应用程序还会带有环境。</span><span class="sxs-lookup"><span data-stu-id="40b80-242">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="40b80-243">以下示例显示在此情况下的简单 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="40b80-243">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="40b80-244">这样的 Dockerfile 为有效 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="40b80-244">A Dockerfile like this will work.</span></span> <span data-ttu-id="40b80-245">但开发人员可以大幅优化映像，尤其是生产映像。</span><span class="sxs-lookup"><span data-stu-id="40b80-245">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="40b80-246">开发人员会在容器和微服务模型中不断启动容器。</span><span class="sxs-lookup"><span data-stu-id="40b80-246">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="40b80-247">使用容器时，通常不会重启睡眠容器，因为该容器为一次性容器。</span><span class="sxs-lookup"><span data-stu-id="40b80-247">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="40b80-248">业务流程协调程序（如 Kubernetes 和 Azure Service Fabric）只创建映像的新实例。</span><span class="sxs-lookup"><span data-stu-id="40b80-248">Orchestrators (like Kubernetes and Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="40b80-249">这意味着，需要在生成应用程序时，通过预编译应用程序进行优化，这样可加快实例化过程。</span><span class="sxs-lookup"><span data-stu-id="40b80-249">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="40b80-250">当容器启动时，它应已准备好运行。</span><span class="sxs-lookup"><span data-stu-id="40b80-250">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="40b80-251">不应在运行时使用 dotnet CLI 中的 `dotnet restore` 和 `dotnet build` 命令进行还原和编译，正如许多有关 .NET Core 和 Docker 的博客文章所述。</span><span class="sxs-lookup"><span data-stu-id="40b80-251">You should not restore and compile at run time, using `dotnet restore` and `dotnet build` commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="40b80-252">.NET 团队一直致力于使 .NET Core 和 ASP.NET Core 成为容器优化的框架。</span><span class="sxs-lookup"><span data-stu-id="40b80-252">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="40b80-253">.NET Core 不仅是一个内存占用少的轻量级框架；该团队还致力于针对三种主要方案优化了 Docker 映像，并在版本 2.1 及更高版本中，在 <span class="underline">microsoft/dotnet</span> 的 Docker 中心注册表中发布了这些映像：</span><span class="sxs-lookup"><span data-stu-id="40b80-253">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at <span class="underline">microsoft/dotnet</span>, beginning with version 2.1:</span></span>

1.  <span data-ttu-id="40b80-254">**开发**：实现快速迭代和调试更改为优先事项，大小次之。</span><span class="sxs-lookup"><span data-stu-id="40b80-254">**Development**: Where the priority is the ability to quickly interate and debug changes and size is secondary.</span></span>

2.  <span data-ttu-id="40b80-255">**生成**：优先事项是编译应用程序，包括二进制文件和其他可优化二进制文件的依赖项。</span><span class="sxs-lookup"><span data-stu-id="40b80-255">**Build**: The priority is compiling the application and includes binaries and other dependencies to optimize binaries.</span></span>

3.  <span data-ttu-id="40b80-256">**生产**：其重点是实现快速部署和容器启动，所以这些映像仅限于二进制文件和运行应用程序所需的嵌入内容。</span><span class="sxs-lookup"><span data-stu-id="40b80-256">**Production**: Where the focus is fast deploying and starting of containers, so these images are limited to the binaries and the content nedded to run the application.</span></span>

<span data-ttu-id="40b80-257">为实现此目的，.NET 团队在 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)（位于 Docker 中心）中提供了三个基本变体：</span><span class="sxs-lookup"><span data-stu-id="40b80-257">To achieve this, the .NET team is providing three basic variants in [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) (at Docker Hub):</span></span>

1.  <span data-ttu-id="40b80-258">**sdk**：用于开发和生成方案。</span><span class="sxs-lookup"><span data-stu-id="40b80-258">**sdk**: for the development and build scenarios.</span></span>
2.  <span data-ttu-id="40b80-259">**runtime**：用于生产方案</span><span class="sxs-lookup"><span data-stu-id="40b80-259">**runtime**: for the production scenario and</span></span>
3.  <span data-ttu-id="40b80-260">**runtime-deps**：用于[自包含应用程序](https://docs.microsoft.com/dotnet/core/deploying/index#self-contained-deployments-scd)的生产方案。</span><span class="sxs-lookup"><span data-stu-id="40b80-260">**runtime-deps**: for the production scenario of [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index#self-contained-deployments-scd).</span></span>

<span data-ttu-id="40b80-261">Runtime 映像还提供了端口 80 的 aspnetcore\_urls 自动设置和程序集的 pre-ngend 缓存，以帮助加快启动速度。</span><span class="sxs-lookup"><span data-stu-id="40b80-261">Runtime images also provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; to help in getting faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="40b80-262">其他资源</span><span class="sxs-lookup"><span data-stu-id="40b80-262">Additional resources</span></span>

-   <span data-ttu-id="40b80-263">**Building Optimized Docker Images with ASP.NET Core**（使用 ASP.NET Core 生成优化的 Docker 映像）</span><span class="sxs-lookup"><span data-stu-id="40b80-263">**Building Optimized Docker Images with ASP.NET Core**</span></span> <br/>
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

-   <span data-ttu-id="40b80-264">**为 .NET Core 应用程序生成 Docker 映像**</span><span class="sxs-lookup"><span data-stu-id="40b80-264">**Building Docker Images for .NET Core Applications**</span></span> <br/>
    [*https://docs.microsoft.com/en-us/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/en-us/dotnet/core/docker/building-net-docker-images)

>[!div class="step-by-step"]
><span data-ttu-id="40b80-265">[上一页](data-driven-crud-microservice.md)
>[下一页](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="40b80-265">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>