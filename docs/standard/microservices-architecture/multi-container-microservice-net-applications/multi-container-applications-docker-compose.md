---
title: 使用 docker-compose.yml 定义多容器应用程序
description: 用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 docker-compose.yml 定义多容器应用程序
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: ded2e5399938be25005776963b0310b6a49d0353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>使用 docker-compose.yml 定义多容器应用程序 

本指南中，[docker-compose.yml](https://docs.docker.com/compose/compose-file/) 文件在[步骤 4.生成多容器 Docker 应用程序时，在 docker-compose.yml 中定义服务](#step4_define_svcs_in_docker_compose_yml)部分中介绍。 但还有其他方式可使用 docker-compose 文件，这值得进一步探索。

例如，可明确描述希望如何在 docker-compose.yml 文件中部署多容器应用程序。 此外，也可以描述将如何生成自定义 Docker 映像。 （也可以使用 Docker CLI 生成自定义 Docker 映像。）

基本上，开发人员需定义想要部署的每个容器以及每个容器部署的某些特征。 拥有多容器部署说明文件后，即可通过由 [docker-compose up](https://docs.docker.com/compose/overview/) CLI 命令编制的单个操作部署整个解决方案，也可简单从 Visual Studio 进行部署。 否则，就需要在命令行中使用 docker run 命令，通过 Docker CLI 经多个步骤部署每个容器。 因此，docker-compose.yml 中定义的每个服务都必须指定一个映像或生成映像。 其他键是可选的，且类似于其 docker run 命令行对应项。

以下 YAML 代码是 eShopOnContainers 示例的单个 docker-compose.yml 文件的定义，文件可能是全局文件。 这不是来自 eShopOnContainers 的实际 docker-compose 文件。 相反，简化和合并后的单个文件，这不是使用 docker-compose 文件的最佳方式，稍后将对此进行解释。

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

此文件中的根密钥是服务。 在该密钥下，可以在执行 docker-compose up 命令或使用此 docker-compose.yml 文件从 Visual Studio 进行部署时，定义要部署和运行的服务。 在这种情况下，docker-compose.yml 文件定义了多个服务，如以下列表所述。

-   webmvc 容器包括从服务器端 C\# 使用微服务的 ASP.NET Core MVC 应用程序

-   catalog.api 容器包括 Catalog ASP.NET Core Web API 微服务

-   ordering.api 容器包括 Ordering ASP.NET Core Web API 微服务

-   sql.data 容器运行适用于 Linux 的 SQL Server，保存微服务数据库

-   basket.api 容器含 Basket ASP.NET Core Web API 微服务

-   basket.data 容器运行 REDIS 缓存服务，将篮数据库作为 REDIS 缓存

### <a name="a-simple-web-service-api-container"></a>简单的 Web 服务 API 容器

关注单个容器，catalog.api 容器微服务的定义很简单：

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

这种容器化服务具有以下基本配置：

-   它基于自定义 eshop/catalog.api 映像。 为简单起见，文件中没有 build: 键设置。 这意味着，必须事先生成（使用 docker build 命令）映像或从任何 Docker 注册表下载（使用 docker pull 命令）映像。

-   它定义了一个名为 ConnectionString 的环境变量，Entity Framework 使用连接字符串用来访问包含目录数据模型的 SQL Server 实例。 在这种情况下，同一 SQL Server 容器拥有多个数据库。 因此，开发 Docker 时所需计算机内存减少。 但是，开发人员也可以为每个微服务数据库部署一个 SQL Server 容器。

-   SQL Server 的名称是 sql.data，与运行适用于 Linux 的 SQL Server 实例的容器的名称相同。 这很方便，因为使用此名称解析（Docker 主机内部）可解析网络地址，这样从其他容器访问容器时，无需了解受访容器的内部 IP。

由于连接字符串由环境变量定义，因此可在不同的时间通过不同机制设置该变量。 例如，在最终主机中部署到生产时，可设置不同的连接字符串，或通过 VSTS 中的 CI/CD 管道或喜爱的 DevOps 系统来完成。

-   它公开了端口 80，用于对 Docker 主机中的 catalog.api 服务进行内部访问。 目前的主机是 Linux VM，因为它以适用于 Linux 的 Docker 映像为基础，但开发人员可配置该容器，使其在 Windows 映像上运行。

-   它将容器上公开的端口 80 转接到 Docker 主机 (Linux VM) 上的端口 5101。

-   它将 Web 服务链接到 sql.data 服务（在容器中运行的 Linux 数据库的 SQL Server 实例）。 指定此依赖项时，在 sql.data 容器启动后，catalog.api 容器才会启动；这一点很重要，因为 catalog.api 需要先启动并运行 SQL Server 数据库。 但是，在许多情况下，这种容器依赖项不足，因为 Docker 只能在容器级别进行检查。 有时服务（在此情况下为 SQL Server）可能还未准备就绪，因此建议在客户端微服务中实施具有指数回退的重试逻辑。 这样一来，如果依赖项容器在短时间内未准备就绪，应用程序仍然可以复原。

-   它被配置为允许访问外部服务器：extra\_hosts 设置允许访问 Docker 主机之外的外部服务器或计算机（即作为开发 Docker 主机的默认 Linux VM 以外的），例如开发计算机上的本地 SQL Server 实例。

此外，还有其他更高级的 docker-compose.yml 设置，我们将在下面的部分介绍。

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>针对多个环境使用 docker-compose 文件

docker-compose.yml 文件是定义文件，可供多种支持该格式的基础结构使用。 最简单的工具是 docker-compose 命令，但诸如业务流程协调程序（例如 Docker Swarm）等其他工具也支持该文件。

因此，可针对以下主要方案使用 docker-compose 命令。

#### <a name="development-environments"></a>开发环境

开发应用程序时，能够在独立开发环境中运行应用程序非常重要。 开发人员可使用 docker-compose CLI 命令来创建该环境，或使用在后台使用 docker-compose 的 Visual Studio。

docker-compose.yml 文件可配置和记录所有应用程序的服务依赖项（其他服务、缓存、数据库、队列等）。 通过 docker-compose CLI 命令，可使用单个命令 (docker-compose up) 为每个依赖项创建并启动一个或多个容器。

docker-compose.yml 文件是由 Docker 引擎解释的配置文件，但也可作为有关多容器应用程序组成的方便文档文件。

#### <a name="testing-environments"></a>测试环境

任何持续部署 (CD) 或持续集成 (CI) 过程都离不开单元测试和集成测试。 这些自动化测试需要独立的环境，以便它们不受用户或应用程序数据变化的影响。

使用 Docker Compose，可通过命令提示符或脚本中的几条命令非常轻松地创建和摧毁该独立环境，如以下命令：

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>生产部署

开发人员还可使用 Compose 部署到远程 Docker 引擎。 部署到单个 Docker 主机实例（例如配置了 [Docker Machine](https://docs.docker.com/machine/overview/) 的生产 VM 或服务器）就是一个典型的例子。 但它也可能是整个 [Docker Swarm](https://docs.docker.com/swarm/overview/) 集群，因为集群也与 docker-compose.yml 文件兼容。

如果正在使用任何其他业务流程协调程序（Azure Service Fabric、Mesos DC/OS、Kubernetes 等），则可能需要添加如 docker-compose.yml 中的设置和元数据配置设置，但需采用其他业务流程协调程序所需的格式。

在任何情况下，docker-compose 都是用于开发、测试和生产工作流的便捷工具和元数据格式，但生产工作流可能因使用的业务流程协调程序而异。

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>使用多个 docker-compose 文件来处理多个环境

针对不同环境时，应使用多个 compose 文件。 这样可以根据环境创建多个配置变体。

#### <a name="overriding-the-base-docker-compose-file"></a>重写基本 docker-compose 文件

开发人员可使用单个 docker-compose.yml 文件，如前面部分中的简化示例所示。 但是，对于大多数应用程序不建议这样做。

默认情况下，Compose 读取两个文件，docker-compose.yml 和可选的 docker-compose.override.yml 文件。 如图 8-11 所示，使用 Visual Studio 并启用 Docker 支持时，Visual Studio 还会创建一个额外的 docker-compose.ci.build,yml 文件，以供开发人员在 CI/CD 管道（如 VSTS）中使用。

![](./media/image12.png)

**图 8-11**。 Visual Studio 2017 中的 docker-compose 文件

用户可使用任何编辑器（如 Visual Studio Code 或 Sublime）编辑 docker-compose 文件，并使用 docker-compose up 命令运行该应用程序。

按照约定，docker-compose.yml 文件包含基本配置和其他静态设置。 这意味着服务配置不应该根据所针对的部署环境而改变。

顾名思义，docker-compose.override.yml 文件包含替代基本配置的配置设置，例如依赖于部署环境的配置。 用户也可以拥有具有不同名称的多个重写文件。 重写文件通常包含应用程序所需的但特定于环境或部署的其他信息。

#### <a name="targeting-multiple-environments"></a>针对多个环境

典型的用例是定义多个 compose 文件时，可针对多个环境，如生产、暂存、CI 或开发环境。 为支持这些差异，可将 Compose 配置拆分成多个文件，如图 8-12 所示。

![](./media/image13.png)

**图 8-12**。 重写基本 docker-compose.yml 文件中的值的多个 docker-compose 文件

从基本 docker-compose.yml 文件开始。 此基本文件必须包含不会根据环境更改的基本或静态配置设置。 例如，eShopOnContainers 将以下 docker-compose.yml 文件作为基本文件。

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
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

基本 docker-compose.yml 文件中的值不应因目标部署环境不同而不同。

例如，如果专注于 webmvc 服务定义，则可以看到无论目标环境如何，这些信息都相同。 会看到以下信息：

-   服务名称：webmvc。

-   容器的自定义映像：eshop/webmvc。

-   生成自定义 Docker 映像的命令，指示要使用的 Dockerfile。

-   其他服务依赖项，所以此容器在其他依赖项容器启动之前不会启动。

开发人员可进行其他配置，但重要的一点是，在基本 docker-compose.yml 文件中，只需设置各环境的共同信息。 然后，在 docker-compose.override.yml 或用于生产或暂存的类似文件中，应配置特定于每个环境的配置。

通常，docker-compose.override.yml 适用于开发环境，如 eShopOnContainers 中的以下示例所示：

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

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
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
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
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
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

在此示例中，开发替代配置向主机公开一些端口，使用重定向 URL 定义环境变量，并为开发环境指定连接字符串。 这些设置都只针对开发环境。

运行 `docker-compose up`（或从 Visual Studio 启动它时）时，该命令会自动读取替代内容，就像它已合并这两个文件。

假设想为生产环境使用具有不同配置值、端口或连接字符串的另一个 Compose 文件。 可创建另一个重写文件，如具有不同设置和环境变量的名为 `docker-compose.prod.yml` 的文件。  该文件可能存储在不同 Git 存储库中，或由其他团队管理和保护。

#### <a name="how-to-deploy-with-a-specific-override-file"></a>如何使用特定重写文件进行部署

若要使用多个重写文件或具有不同名称的重写文件，可通过 docker-compose 命令使用 -f 选项并指定文件。 按照合并文件在命令行上的指定顺序进行撰写。 以下示例演示如何使用重写文件进行部署。

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>在 docker-compose 文件中使用环境变量

如前面的示例所示，开发人员可方便地从环境变量中获取配置信息，尤其是在生产环境中。 可使用语法 \${MY\_VAR} 在 docker-compose 文件中引用环境变量。 docker-compose.prod.yml 文件中的以下行显示如何引用环境变量的值。

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

创建和初始化环境变量的方式不同，具体取决于主机环境（Linux、Windows、云集群等）。 但是，便捷方法是使用 .env 文件。 docker-compose 文件支持在 .env 文件中声明默认环境变量。 这些环境变量的值是默认值。 但开发人员在每个环境（主机操作系统或群集中的环境变量）中定义的值可重写这些默认值。 将此 .env 文件放置在执行 docker-compose 命令的文件夹中。

以下示例展示了 .env 文件，例如用于 eShopOnContainers 应用程序的 [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) 文件。

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose 要求 .env 文件中的每行都是 &lt;variable&gt;=&lt;value&gt; 格式。

请注意，运行时环境中设置的值始终会重写 .env 文件中定义的值。 同样，通过命令行命令参数传递的值也会重写 .env 文件中设置的默认值。

#### <a name="additional-resources"></a>其他资源

-   **Docker Compose 概述**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **多个 Compose 文件**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>生成优化的 ASP.NET Core Docker 映像

如果查看 Internet 上源代码的 Docker 和 .NET Core ，则会发现 Dockerfiles 会将源代码源复制到容器，展现生成 Docker 映像的简单性。 这些示例表明，使用简单配置，即可拥有 Docker 映像，同时应用程序还会带有环境。 以下示例显示在此情况下的简单 Dockerfile。

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

这样的 Dockerfile 为有效 Dockerfile。 但开发人员可以大幅优化映像，尤其是生产映像。

开发人员会在容器和微服务模型中不断启动容器。 使用容器时，通常不会重启睡眠容器，因为该容器为一次性容器。 业务流程协调程序（如 Docker Swarm、Kubernetes、DCOS 或 Azure Service Fabric）只需创建映像的新实例。 这意味着，需要在生成应用程序时，通过预编译应用程序进行优化，这样可加快实例化过程。 当容器启动时，它应已准备好运行。 开发人员不应在运行时使用 dotnet CLI 中的 dotnet restore 和 dotnet build 命令进行还原和编译，正如许多有关 .NET Core 和 Docker 的博客文章所述。

.NET 团队一直致力于使 .NET Core 和 ASP.NET Core 成为容器优化的框架。 .NET Core 是一个轻型框架，不仅是内存占用量小，该团队还专注于其启动性能，与常规 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) 或 [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) 映像相比，该团队生产的 Docker 映像更优，例如 [Docker 中心](https://hub.docker.com/r/microsoft/aspnetcore/) 提供的 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 映像。 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 映像提供了 aspnetcore\_urls 到端口 80 的自动设置和程序集的 pre-ngend 缓存；这两个设置都可以加快启动速度。

#### <a name="additional-resources"></a>其他资源

-   **使用 ASP.NET Core 生成优化的 Docker 映像**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>从生成 (CI) 容器构建应用程序

Docker 的另一个好处是，可以从预配置的容器中构建应用程序，如图 8-13 所示，因此开发人员无需创建构建应用程序的生成计算机或 VM。 可在开发计算机中运行生成容器来使用或测试该容器。 但更有趣的是，开发人员可以在 CI（持续集成）管道中使用相同生成容器。

![](./media/image14.png)

**图 8-13**。 编译 .NET 二进制文件的 Docker 生成容器 

在此方案中，我们提供了可用于编译和构建 ASP.NET Core 应用的 [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) 映像。 如前文所述，输出位于基于 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 映像（优化的运行时映像）的映像中。

aspnetcore-build 映像包含编译 ASP.NET Core 应用程序所需的一切，包括 .NET Core、ASP.NET SDK、npm、Bower、Gulp 等。

我们在构建时需要这些依赖项。 但是我们不想在运行时将这些包含在应用程序中，因为这会使映像无谓的变大。 在 eShopOnContainers 应用程序中，只需运行以下 docker-compose 命令即可从容器构建应用程序。

```
  docker-compose -f docker-compose.ci.build.yml up
```

图 8-14 演示在命令行运行的此命令。

![](./media/image15.png)

**图 8-14**。 从容器构建 .NET 应用程序

如图所示，正在运行的容器是 ci-build\_1 容器。 这基于 aspnetcore-build 映像，因此它可以从该容器而不是从计算机编译和构建整个应用程序。 实际上，这就是它为何在 Linux 中构建和编译 .NET Core 项目的原因，因为该容器在默认 Docker Linux 主机上运行。

该映像的 [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) 文件（eShopOnContainers 的一部分）包含以下代码。 可以看到它使用 [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) 映像启动生成容器。

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* 从 .NET Core 2.0 开始，执行 `dotnet publish` 命令时，会自动执行 `dotnet restore` 命令。

生成容器启动并运行后，它将针对解决方案中的所有项目运行 .NET SDK dotnet restore 和 dotnet publish 命令，以编译 .NET 位。 在这种情况下，因为 eShopOnContainers 也为客户端代码提供了基于 TypeScript 和 Angular 的 SPA，所以它还需要使用 npm 检查 JavaScript 依赖项，但该操作与 .NET 位无关。

dotnet publish 命令构建每个项目文件夹内的编译输出，并将其发布到 ../obj/Docker/publish 文件夹，如图 8-15 所示。

![](./media/image16.png)

**图 8-15**。 由 dotnet publish 命令生成的二进制文件

#### <a name="creating-the-docker-images-from-the-cli"></a>从 CLI 创建 Docker 映像

一旦应用程序输出发布到相关文件夹（在每个项目中），下一步就是实际生成 Docker 映像。 要执行此操作，请使用 docker-compose build 和 docker-compose up 命令，如图 8-16 所示。

![](./media/image17.png)

**图 8-16**。 生成 Docker 映像并运行容器

图 8-17 展示了 docker-compose build 命令是如何运行的。

![](./media/image18.png)

**图 8-17**。 使用 docker-compose build 命令生成 Docker 映像

docker-compose build 和 docker-compose up 命令之间的区别在于，docker-compose up 能生成并启动映像。

使用 Visual Studio 时，所有这些步骤均在后台执行。 Visual Studio 编译 .NET 应用程序，创建 Docker 映像，并将容器部署到 Docker 主机。 Visual Studio 提供了附加功能，如直接从 Visual Studio 调试在 Docker 中运行的容器。

此处采用的总体方法是，像使用 CI/CD 管道构建应用程序一样，从容器而不是本地计算机构建应用程序。 创建映像后，只需使用 docker-compose up 命令运行 Docker 映像。

#### <a name="additional-resources"></a>其他资源

-   **从容器生成位：在 Windows CLI 环境（dotnet CLI、Docker CLI 和 VS Code）中设置 eShopOnContainers 解决方案**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[上一篇] (data-driven-crud-microservice.md) [下一篇] (database-server-container.md)
