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
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>定义与 docker-compose.yml 多容器应用程序 

本指南中， [docker-compose.yml](https://docs.docker.com/compose/compose-file/)文件的部分中引入了[步骤 4。构建多容器 Docker 应用程序时在 docker-compose.yml 中定义你的服务](#step4_define_svcs_in_docker_compose_yml)。 但是，还有其他方式，若要使用的进一步详细浏览值得 docker-compose 文件。

例如，你可以明确描述你想要部署多容器应用程序 docker-compose.yml 文件中。 （可选） 你可以描述如何生成自定义的 Docker 映像。 （自定义 Docker 映像也可以生成使用 Docker CLI。）

基本上，你定义每个你想要部署的容器以及为每个容器部署某些特征。 一个多容器部署说明文件之后，你可以部署在单一操作由协调整个解决方案[docker compose 向上](https://docs.docker.com/compose/overview/)CLI 命令，也可以将其部署以透明方式从 Visual Studio。 否则，你将需要使用 Docker CLI 使用 docker run 命令从命令行部署多个步骤中的容器的容器。 因此，在 docker-compose.yml 中定义的每个服务必须指定恰好一个映像，或生成。 其他密钥是可选的并且类似于其 docker 运行命令行对等项。

下面的 YAML 代码是 eShopOnContainers 示例的可能全局但单个 docker-compose.yml 文件的定义。 这不是从 eShopOnContainers 的实际 docker-compose 文件。 相反，它是在单个文件，不是最佳的简化和统一版本方式来使用 docker-编写文件，如将更高版本所述。

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

此文件中的根密钥是服务。 该注册表项下定义你想要部署和运行时执行的服务 docker compose 命令或当你从 Visual Studio 部署通过使用此 docker-compose.yml 文件。 在这种情况下，docker-compose.yml 文件具有多个服务定义，以下列表中所述。

-   webmvc 包括 ASP.NET 核心 MVC 应用程序使用从服务器端 C 微服务容器\#

-   catalog.api 包括目录 ASP.NET 核心 Web API 微服务容器

-   ordering.api 包括排序 ASP.NET 核心 Web API 微服务容器

-   sql.data 适用于 Linux，保存微服务数据库运行 SQL Server 容器

-   与购物篮 ASP.NET 核心 Web API microservice basket.api 容器

-   basket.data 运行与购物篮数据库作为 REDIS 缓存的 REDIS 缓存服务中容器

### <a name="a-simple-web-service-api-container"></a>简单的 Web 服务 API 容器

着重于单个容器，catalog.api 容器微服务都有一个简单的定义：

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

此容器化的服务具有以下基本配置：

-   它基于自定义 eshop/catalog.api 映像。 为简单起见，没有任何编录生成： 密钥文件中的设置。 这意味着将映像必须具有已 （通过构建 docker 生成），或从任何 Docker 注册表 （使用 docker 请求命令） 下载。

-   它定义要用于实体框架访问包含目录数据模型的 SQL Server 实例的连接字符串的名为 ConnectionString 的环境变量。 在这种情况下，同一个 SQL Server 容器保存多个数据库。 因此，需要较少的内存中你的开发计算机 Docker。 但是，你还可以部署为每个微服务数据库的一个 SQL Server 容器。

-   SQL Server 名称是 sql.data，这是用于正在运行的 SQL Server 实例，对于 Linux 容器相同的名称。 此方法很方便;能够使用此名称解析 （内部到 Docker 主机） 将解析的网络地址，因此无需知道从其他容器访问的容器的内部 IP。

由于连接字符串定义的环境变量，你可以通过不同的机制和在不同时间设置该变量。 例如，你无法部署到生产环境中的最后一个主机，或通过执行 VSTS 或你首选的 DevOps 系统中你 CI/CD 管道中时设置不同的连接字符串。

-   它公开有关内部访问 catalog.api 服务对 Docker 主机中的端口 80。 主机当前是 Linux VM，因为它基于 Docker 映像对于 Linux，但你可以配置要改为运行在 Windows 映像上的容器。

-   它会将转发公开的端口 80 上向 Docker 主机计算机 (Linux VM) 上的端口 5101 容器。

-   它链接到 sql.data 服务 （运行在容器中的 Linux 数据库的 SQL Server 实例） 的 web 服务。 指定此依赖关系时之前已经启动了 sql.data 容器; 不会启动 catalog.api 容器第一次这是因为 catalog.api 需要最多有 SQL Server 数据库重要和正在运行。 但是，这种类型的容器依赖项是不够的在许多情况下，因为仅在容器级别检查 Docker。 有时 （此大小写的 SQL Server) 中的服务可能仍不是准备就绪，因此最好在客户端微服务中实现具有指数回退重试逻辑。 这样一来，如果依赖项容器未准备好进行短时间内，将仍能够处理应用程序。

-   它被配置为允许访问外部服务器： 额外\_主机设置允许你访问外部服务器或外部的 Docker 主机计算机 （即，外部默认 Linux VM，这是一个开发 Docker 主机），如本地 SQL对开发计算机上的服务器实例。

此外，还有下列部分中，我们将讨论其他，更高级的 docker-compose.yml 设置。

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>使用 docker-撰写文件以面向多个环境

Docker-compose.yml 文件是定义文件，并且可由多个基础结构，了解该格式。 最简单的工具是 docker-编写命令，但其他像 orchestrators (例如，Docker Swarm) 还了解该文件的工具。

因此，通过使用 docker compose 命令，你可以面向以下主要方案。

#### <a name="development-environments"></a>开发环境

当你开发应用程序时，务必能够独立的开发环境中运行应用程序。 你可以使用 docker compose CLI 命令，以创建该环境或使用 Visual Studio 可使用 docker 的撰写在后台。

Docker-compose.yml 文件，可配置并记录应用程序的所有服务依赖项 （其他服务、 缓存、 数据库、 队列等。）。 使用 docker compose CLI 命令，则可以创建并使用单个命令启动一个或多个容器的每个依赖项 （docker-撰写向上）。

Docker-compose.yml 文件是由 Docker 引擎解释的配置文件，但还充当有关组合的多容器应用程序的方便文档文件。

#### <a name="testing-environments"></a>测试环境

任何连续部署 (CD) 或持续集成 (CI) 过程的重要组成部分是单元测试和集成测试。 这些自动的测试需要一个独立的环境，因此它们不受影响的用户或应用程序的数据中的任何其他更改。

通过 Docker Compose 可以创建和销毁该隔离的环境，很容易中几个命令从命令提示符或脚本，如以下命令：

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>生产部署

你还可以使用 Compose 将部署到远程 Docker 引擎。 一种典型情况是将部署到单个的 Docker 主机实例 (如生产 VM 或使用设置服务器[Docker 机](https://docs.docker.com/machine/overview/))。 但它也可以是整个[Docker Swarm](https://docs.docker.com/swarm/overview/)群集，因为群集也是兼容 docker-compose.yml 文件。

如果你使用的任何其他 orchestrator （Azure Service Fabric、 Mesos DC/OS、 Kubernetes 等），你可能需要添加安装程序和元数据配置设置，如在 docker-compose.yml，但在通过其他 orchestrator 所需的格式。

在任何情况下，docker compose 是一种方便的工具和元数据格式，开发、 测试和生产的工作流，虽然制作工作流可能会在你使用 orchestrator 上不同。

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>使用多个 docker-撰写文件来处理多个环境

如果目标不同的环境，应使用多个构成文件。 这允许您创建根据环境的多个配置变体。

#### <a name="overriding-the-base-docker-compose-file"></a>重写基 docker-compose 文件

你可以使用单个 docker-compose.yml 文件如下所示前面部分中所示的简化示例。 但是，不建议使用该对于大多数应用程序。

默认情况下，Compose 读取两个文件、 docker-compose.yml 和可选的 docker compose.override.yml 文件。 如下所示在图 8-11 中，当你使用 Visual Studio 且启用 Docker 支持，Visual Studio 还会创建这些文件以及其他一些用于调试的文件。

![](./media/image12.png)

**图 8-11**。 docker compose Visual Studio 自 2017 年中的文件

你可以使用任何编辑器，如 Visual Studio Code 或 Sublime，编辑 docker-compose 文件和运行的应用程序 docker compose 向上命令。

按照约定，docker-compose.yml 文件包含的基本配置和其他静态设置。 这意味着，具体取决于你面向的部署环境不应更改服务配置。

Docker compose.override.yml 文件中，顾名思义，包含重写的基本配置，如依赖于部署环境的配置的配置设置。 你还可以具有不同名称的多个重写文件。 重写文件通常包含对环境或部署但特定应用所需的其他信息。

#### <a name="targeting-multiple-environments"></a>面向多个环境

典型的用例是在定义多个构成文件以便你可以面向多个环境，如生产环境，暂存，CI 使用，请或开发。 若要支持这些差异，你可以在图 8-12 中所示拆分到多个文件，您撰写的配置。

![](./media/image13.png)

**图 8-12**。 多个 docker compose 文件重写基 docker-compose.yml 文件中的值

你开始基 docker-compose.yml 文件。 此基本文件必须包含不会更改根据环境的基或静态配置设置。 例如，eShopOnContainers 与基文件具有以下 docker-compose.yml 文件。

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

由于不同的目标部署环境，不应更改基 docker-compose.yml 文件中的值。

如果你专注于 webmvc 服务定义，例如，可以看到该信息的无论何种环境，你可能会以目标大致相同的方式。 具有以下信息：

-   服务名称： webmvc。

-   容器的自定义映像： 电子商店/webmvc。

-   若要生成自定义的 Docker 映像、 要使用哪些 Dockerfile，该值指示该命令。

-   其他服务，因此此容器才会启动其他依赖项容器的依赖关系。

你可以有其他配置，但重要的一点是，在基 docker-compose.yml 文件中，你只是想要设置其能够在环境之间通用的信息。 然后在 docker compose.override.yml 或生产或过渡的类似文件中，应设置为每个环境特定的配置。

通常情况下，docker compose.override.yml 用于你的开发环境，如 eShopOnContainers 的以下示例所示：

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

在此示例中，开发替代配置公开到主机某些端口、 定义环境变量重定向 Url，并指定开发环境的连接字符串。 这些设置适用于开发环境的所有对象都是。

当你运行 docker compose 向上 （或启动从 Visual Studio），该命令读取替代自动就像它已合并这两个文件。

假设你想为生产环境中，使用不同的配置值的另一个 Compose 文件。 你可以创建另一个重写文件，如下所示。 （此文件可能是不同的 Git 存储库中存储或管理和保护的其他团队。）

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

#### <a name="how-to-deploy-with-a-specific-override-file"></a>如何使用特定重写文件进行部署

若要使用不同的名称中使用多个重写文件或重写文件，你可以使用-f 选项与 docker compose 命令并指定的文件。 构成合并文件在命令行指定的顺序。 下面的示例演示如何使用替代文件进行部署。

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>使用环境变量在 docker-撰写文件

可以很方便，尤其是在生产环境中，若要能够从环境变量中获取的配置信息，如我们具有前面示例中所示。 在你 docker-compose 文件中使用的语法引用环境变量\${MY\_VAR}。 Docker compose.prod.yml 文件的以下行显示了如何引用环境变量的值。

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

创建和初始化在不同的方式，具体取决于宿主环境中环境变量 (Linux、 Windows，云群集等。)。 但是，方便的方法是使用.env 文件。 Docker-compose 文件支持声明.env 文件中的默认环境变量。 这些环境变量的值是默认值。 但可以重写它们可能会在你的环境 （主机操作系统或从你的群集的环境变量） 的每个定义的值。 将此.env 文件放置在文件夹中其中 docker compose 从执行命令。

下面的示例演示类似.env 文件[.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) eShopOnContainers 应用程序文件。

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker compose 要求的格式为.env 文件中的每个行&lt;变量&gt;=&lt;值&gt;。

请注意，始终在运行时环境中设置的值覆盖.env 文件内定义的值。 以类似的方式，通过命令行命令自变量传递的值还重写.env 文件中设置的默认值。

#### <a name="additional-resources"></a>其他资源

-   **概述 Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **多个 Compose 文件**
    [*https://docs.docker.com/compose/extends/\#多个构成文件*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>构建优化 ASP.NET 核心 Docker 映像

如果在 Internet 上的源上浏览 Docker 和.NET 核心，则会发现演示通过将你的源复制到容器中生成的 Docker 映像的简单的 Dockerfile。 这些示例建议通过使用简单的配置，您可以有的 Docker 映像与你的应用程序一起打包的环境。 下面的示例演示了在此情况下的简单 Dockerfile。

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

如下 Dockerfile 起作用。 但是，你可以大大优化你的映像，尤其是你的生产映像。

在容器和微服务模型中，你不断地开始容器。 使用容器的典型方法不重新启动睡眠的容器，因为容器是可释放。 Orchestrators （如 Docker Swarm、 Kubernetes、 DCOS 或 Azure Service Fabric） 只需创建映像的新的实例。 这意味着，你将需要通过预编译应用程序，以便实例化过程会更快生成时优化。 当启动容器时，它应该已准备好运行。 不应还原，并在运行时编译，使用 dotnet 还原和 dotnet 生成从 dotnet CLI 命令，正如你所看到的有关.NET 核心和 Docker 的多篇博客文章中。

.NET 团队具有已进行重要的工作来进行.NET Core 和 ASP.NET Core 容器优化 framework。 使用小的内存需求量; 一个轻型框架不只是.NET 核心团队未侧重于启动性能而产生一些优化的 Docker 映像，如[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)映像在[Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/)，与常规相比[microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)或[microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile)映像。 [Microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)图显示了自动设置 aspnetcore\_url 对端口 80 和 pre ngend 缓存的程序集; 这两种设置导致启动速度更快。

#### <a name="additional-resources"></a>其他资源

-   **构建优化与 ASP.NET 核心的 Docker 映像**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>生成从生成 (CI) 容器应用程序

Docker 的另一个好处是，你可以生成应用程序从预配置的容器，如所示图 8-13，因此不需要创建的生成计算机或 VM 都生成应用程序。 你可以使用或通过运行在你的开发计算机中测试该生成容器。 但更有趣的是你可以从 CI （持续集成） 管道中使用相同的生成容器。

![](./media/image14.png)

**图 8-13**。 生成.NET bits 从容器的组件

对于此方案中，我们提供[microsoft/aspnetcore-生成](https://hub.docker.com/r/microsoft/aspnetcore-build/)映像，可用于编译和生成 ASP.NET Core 应用。 在基于映像放置输出[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)映像，这是一个优化运行时映像，如前文所述。

Aspnetcore 生成映像包含所需的一切以便编译 ASP.NET Core 应用程序，包括.NET 核心、 ASP.NET SDK、 npm Bower、 Gulp，等等。

在生成时，我们需要这些依赖关系。 但我们不希望执行这些与应用程序在运行时，因为这会使图像不必要的大型。 在 eShopOnContainers 应用程序，可以生成应用程序从容器通过只需运行以下 docker-编写命令。

```
  docker-compose -f docker-compose.ci.build.yml up
```

图 8-14 显示在命令行运行此命令。

![](./media/image15.png)

**图 8-14。** 生成.NET 应用程序从容器

如你所见，正在运行的容器是 ci 生成\_1 容器。 这基于 aspnetcore 生成映像，以便它可以编译并生成从您的电脑的整个从应用程序而不是该容器中。 就是为什么实际上它是生成和编译在 Linux 中的.NET 核心项目，因为在默认 Docker Linux 主机上运行该容器。

[Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml)文件 （eShopOnContainers 的一部分） 该映像包含下面的代码。 你可以看到，它会开始生成容器使用[microsoft/aspnetcore-生成](https://hub.docker.com/r/microsoft/aspnetcore-build/)映像。

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

* 从开始**.NET 核心 2.0**，`dotnet restore`自动执行命令时`dotnet publish`执行命令。

启动并正在运行的生成容器后，它运行.NET SDK dotnet 还原和 dotnet 中发布针对的所有项目的命令在解决方案中，以便编译的.NET 位。 在这种情况下，由于 eShopOnContainers 还具有基于 TypeScript 和角适用于客户端代码 SPA，它还需要检查与 npm，JavaScript 依赖关系，但操作不相关的.NET 位。

Dotnet publish 命令生成并发布到的每个项目的文件夹中编译的输出.../obj/Docker/publish 文件夹，如图 8-15 中所示。

![](./media/image16.png)

**图 8-15。** 由 dotnet 生成的二进制文件发布命令

#### <a name="creating-the-docker-images-from-the-cli"></a>从 CLI 创建 Docker 映像

一旦应用程序输出发布到相关的文件夹 （在每个项目） 下, 一步是实际生成的 Docker 映像。 要执行此操作，请使用 docker-compose 生成，并向上命令，如所示图 8-16 docker compose。

![](./media/image17.png)

**图 8-16。** 构建 Docker 映像和正在运行的容器

在图 8-17 中，你可以看到如何 docker-compose 生成命令运行。

![](./media/image18.png)

**图 8-17**。 使用 docker 生成的 Docker 映像-编写生成命令

Docker-compose 之间的差异生成并向上 docker compose 命令是 docker compose 生成和启动映像。

当你使用 Visual Studio 时，所有这些步骤将在后台执行。 Visual Studio 编译你的.NET 应用程序，创建的 Docker 映像，并将容器部署到 Docker 主机。 Visual Studio 提供了附加功能，如调试你直接从 Visual Studio 在 Docker 中运行的容器的功能。

总体 takeway 此处是是否可以生成应用程序相同的方式 CI/CD 管道应生成 — 从容器，而不是从本地计算机。 创建的映像后，那么你只需运行使用 docker 的 Docker 映像的命令编写。

#### <a name="additional-resources"></a>其他资源

-   **生成从容器的 bits： 在 Windows CLI 环境 (dotnet 为 CLI，Docker CLI 和 VS Code) 中设置 eShopOnContainers 解决方案**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[以前](数据-驱动的 crud-microservice.md) [下一步] (数据库的服务器-container.md)
