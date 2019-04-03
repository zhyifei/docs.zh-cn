---
title: 使用作为容器而运行的数据库服务器
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 仅出于开发目的使用作为容器运行的数据库服务器！ 了解原因。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 2adc58339012095c9dc58d633a9b3815cf7aba3f
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463340"
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="1b07e-104">使用作为容器而运行的数据库服务器</span><span class="sxs-lookup"><span data-stu-id="1b07e-104">Using a database server running as a container</span></span>

<span data-ttu-id="1b07e-105">你可以将自己的数据库（SQL Server、PostgreSQL、MySQL 等）放在常规独立服务器、本地群集或云中的 PaaS 服务（如 Azure SQL DB）中。</span><span class="sxs-lookup"><span data-stu-id="1b07e-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="1b07e-106">但对于开发和测试环境来说，将数据库作为容器运行很方便，因为没有任何外部依赖项，只需运行 `docker-compose up` 命令，即可启动整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b07e-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="1b07e-107">将这些数据库作为容器也有利于集成测试，因为数据库在容器中启动，并且始终填充相同的样本数据，因此预测测试也就更容易了。</span><span class="sxs-lookup"><span data-stu-id="1b07e-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="1b07e-108">SQL Server 作为包含微服务相关数据库的容器运行</span><span class="sxs-lookup"><span data-stu-id="1b07e-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="1b07e-109">在 eShopOnContainers 中，运行 SQL Server for Linux 的 [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) 文件中有一个名为 sql.data 的容器，包含微服务所需的所有 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="1b07e-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="1b07e-110">（也可以为每个数据库设置一个 SQL Server 容器，但这会占用更多分配给 Docker 的内存。）微服务中重要的一点是每个微服务都有其相关数据，因此在这里是相关 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="1b07e-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="1b07e-111">不过，这些数据库可以置于任何位置。</span><span class="sxs-lookup"><span data-stu-id="1b07e-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="1b07e-112">示例应用程序中的 SQL Server 容器在 docker-compose.yml 文件中配置有下列 YAML 代码，这些代码在运行 `docker-compose up` 时执行。</span><span class="sxs-lookup"><span data-stu-id="1b07e-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="1b07e-113">请注意，YAML 代码整合了来自通用 docker-compose.yml 文件和 docker-compose.override.yml 文件的配置信息。</span><span class="sxs-lookup"><span data-stu-id="1b07e-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="1b07e-114">（你通常会分离环境设置与 SQL Server 映像的相关基本信息或静态信息。）</span><span class="sxs-lookup"><span data-stu-id="1b07e-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="1b07e-115">按照类似的方法，不使用 `docker-compose`，而使用下列 `docker run` 命令便可运行该容器：</span><span class="sxs-lookup"><span data-stu-id="1b07e-115">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

<span data-ttu-id="1b07e-116">但是，如果要部署多容器应用程序（如 eShopOnContainers），使用 `docker-compose up` 命令为应用程序部署所有必需的容器会更方便。</span><span class="sxs-lookup"><span data-stu-id="1b07e-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="1b07e-117">首次启动此 SQL Server 容器时，容器使用提供的密码初始化 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="1b07e-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="1b07e-118">SQL Server 作为容器运行后，可以通过连接任何常规 SQL 连接（例如 SQL Server Management Studio、Visual Studio 或 C\# 代码）来更新数据库。</span><span class="sxs-lookup"><span data-stu-id="1b07e-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="1b07e-119">eShopOnContainers 应用程序提供在启动时在数据库中设定数据，使用样本数据来初始化每个微服务数据库，如下文所述。</span><span class="sxs-lookup"><span data-stu-id="1b07e-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="1b07e-120">将 SQL Server 作为容器运行不仅可用于无法访问 SQL Server 实例的演示。</span><span class="sxs-lookup"><span data-stu-id="1b07e-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="1b07e-121">如前所述，对开发和测试环境也非常有用，因为可以通过设定新的样本数据轻松地从清晰的 SQL Server 映像以及已知数据开始运行集成测试。</span><span class="sxs-lookup"><span data-stu-id="1b07e-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="1b07e-122">其他资源</span><span class="sxs-lookup"><span data-stu-id="1b07e-122">Additional resources</span></span>

- <span data-ttu-id="1b07e-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** \（在 Linux、Mac 或 Windows 上运行 SQL Server Docker 映像）</span><span class="sxs-lookup"><span data-stu-id="1b07e-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** \\</span></span>
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

- <span data-ttu-id="1b07e-124">**Connect and query SQL Server on Linux with sqlcmd** \（使用 sqlcmd 连接和查询 Linux 上的 SQL Server）</span><span class="sxs-lookup"><span data-stu-id="1b07e-124">**Connect and query SQL Server on Linux with sqlcmd** \\</span></span>
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="1b07e-125">在 Web 应用程序启动时设定测试数据</span><span class="sxs-lookup"><span data-stu-id="1b07e-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="1b07e-126">要在应用程序启动时向数据库添加数据，可以将以下代码添加到 Web API 项目 Startup 类中的 Configure 方法中：</span><span class="sxs-lookup"><span data-stu-id="1b07e-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="1b07e-127">自定义 CatalogContextSeed 类中的以下代码可填充数据。</span><span class="sxs-lookup"><span data-stu-id="1b07e-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="1b07e-128">运行集成测试时，可以生成与集成测试一致的数据很有用。</span><span class="sxs-lookup"><span data-stu-id="1b07e-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="1b07e-129">能够从头开始创建所有内容（包括在容器上运行的 SQL Server 实例）对测试环境非常有用。</span><span class="sxs-lookup"><span data-stu-id="1b07e-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="1b07e-130">EF Core InMemory 数据库与作为容器运行的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b07e-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="1b07e-131">运行测试时，另一个不错的选择是使用 Entity Framework InMemory 数据库提供程序。</span><span class="sxs-lookup"><span data-stu-id="1b07e-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="1b07e-132">可以在 Web API 项目 Startup 类的 ConfigureServices 方法中指定该配置：</span><span class="sxs-lookup"><span data-stu-id="1b07e-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }
  
    // Other Startup code ...

}
```

<span data-ttu-id="1b07e-133">不过，存在一个重要的问题。</span><span class="sxs-lookup"><span data-stu-id="1b07e-133">There is an important catch, though.</span></span> <span data-ttu-id="1b07e-134">内存数据库不支持指定于特定数据库的许多约束。</span><span class="sxs-lookup"><span data-stu-id="1b07e-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="1b07e-135">例如，在 EF Core 模型的列中添加唯一索引，以及针对内存数据库编写测试，检查其是否允许添加重复值。</span><span class="sxs-lookup"><span data-stu-id="1b07e-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="1b07e-136">但是，使用内存数据库时，无法处理列上的唯一索引。</span><span class="sxs-lookup"><span data-stu-id="1b07e-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="1b07e-137">因此，内存数据库与真正 SQL Server 数据库的工作方式不完全相同 - 前者不会模拟特定于数据库的约束。</span><span class="sxs-lookup"><span data-stu-id="1b07e-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="1b07e-138">即便如此，内存数据库仍然可用于测试和原型设计。</span><span class="sxs-lookup"><span data-stu-id="1b07e-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="1b07e-139">但如果想要创建考虑特定数据库实现行为的准确集成测试，则需要使用像 SQL Server 这样真正的数据库。</span><span class="sxs-lookup"><span data-stu-id="1b07e-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="1b07e-140">为此，在容器中运行 SQL Server 是一个不错的选择，它比 EF Core InMemory 数据库提供程序更准确。</span><span class="sxs-lookup"><span data-stu-id="1b07e-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="1b07e-141">使用在容器中运行的 Redis 缓存服务</span><span class="sxs-lookup"><span data-stu-id="1b07e-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="1b07e-142">可以在容器上运行 Redis，特别是用于开发和测试以及概念验证方案。</span><span class="sxs-lookup"><span data-stu-id="1b07e-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="1b07e-143">这种方案很方便，因为可以在容器上运行所有依赖项 - 不仅适用于本地开发机器，还适用于 CI/CD 管道中的环境测试。</span><span class="sxs-lookup"><span data-stu-id="1b07e-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="1b07e-144">但是，如果生产环境中运行 Redis，则最好是寻找像 Redis Microsoft Azure 这样的高可用性解决方案，该解决方案作为 PaaS（平台即服务）运行。</span><span class="sxs-lookup"><span data-stu-id="1b07e-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="1b07e-145">你只需在代码中更改连接字符串。</span><span class="sxs-lookup"><span data-stu-id="1b07e-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="1b07e-146">Redis 提供使用 Redis 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="1b07e-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="1b07e-147">该映像可在 Docker 中心获得，请访问此 URL：</span><span class="sxs-lookup"><span data-stu-id="1b07e-147">That image is available from Docker Hub at this URL:</span></span>

[https://hub.docker.com/_/redis/](https://hub.docker.com/_/redis/)

<span data-ttu-id="1b07e-148">可在命令提示符中执行以下 Docker CLI 命令来直接运行 Docker Redis 容器：</span><span class="sxs-lookup"><span data-stu-id="1b07e-148">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="1b07e-149">Redis 映像包含公开：6379（Redis 使用的端口），因此链接容器可自动使用标准容器链接。</span><span class="sxs-lookup"><span data-stu-id="1b07e-149">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="1b07e-150">eShopOnContainers 中，basket.api microservice 使用作为容器运行的 Redis 缓存。</span><span class="sxs-lookup"><span data-stu-id="1b07e-150">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="1b07e-151">此 basket.data 容器被定义为 multi-container docker-compose.yml 文件的一部分，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="1b07e-151">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="1b07e-152">docker-compose.yml 中的这段代码基于 redis 映像定义了一个名为 basket.data 的容器，并在内部发布端口 6379，这意味着其只能从 Docker 主机中运行的其他容器进行访问。</span><span class="sxs-lookup"><span data-stu-id="1b07e-152">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="1b07e-153">最后，在 docker-compose.override.yml 文件中，eShopOnContainers 示例的 basket.api 微服务定义了用于该 Redis 容器的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="1b07e-153">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="1b07e-154">如前文所述，微服务的名称“asket.data”通过 docker 的内部网络 DNS 进行解析。</span><span class="sxs-lookup"><span data-stu-id="1b07e-154">As mentioned before, the name of the microservice "basket.data" is resolved by docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1b07e-155">[上一页](multi-container-applications-docker-compose.md)
>[下一页](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="1b07e-155">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
