---
title: "使用运行的容器的数据库服务器"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |使用运行的容器的数据库服务器"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="7c25e-104">使用运行的容器的数据库服务器</span><span class="sxs-lookup"><span data-stu-id="7c25e-104">Using a database server running as a container</span></span>

<span data-ttu-id="7c25e-105">你的数据库 （SQL Server、 PostgreSQL、 MySQL 等） 可以对正则独立服务器，在本地群集中，或在云中的 Azure SQL DB 等 PaaS 服务。</span><span class="sxs-lookup"><span data-stu-id="7c25e-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="7c25e-106">但是，对于开发和测试环境，你作为容器运行的数据库是方便，因为你没有任何外部依赖关系，并只需运行 docker compose 命令启动整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="7c25e-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency, and simply running the docker-compose command starts the whole application.</span></span> <span data-ttu-id="7c25e-107">这些数据库作为容器功能也很强大集成测试，因为数据库将在容器中启动，并且始终填充使用相同的示例数据，因此，测试可能会更可预测。</span><span class="sxs-lookup"><span data-stu-id="7c25e-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="7c25e-108">作为的容器运行与 microservice 相关数据库的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c25e-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="7c25e-109">在 eShopOnContainers，没有名为 sql.data 中定义的容器[docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml)运行适用于 Linux 的 SQL Server 使用所需的微服务的所有 SQL Server 数据库的文件。</span><span class="sxs-lookup"><span data-stu-id="7c25e-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="7c25e-110">（你也可以为每个数据库的一个 SQL Server 容器，但这将需要更多的内存分配给 Docker）。在微服务重要的一点是，每个微服务拥有其相关的数据，因此其相关的 SQL 数据库在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="7c25e-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="7c25e-111">但是，数据库可以在任何地方。</span><span class="sxs-lookup"><span data-stu-id="7c25e-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="7c25e-112">在示例应用程序的容器配置替换为以下 YAML 代码在 docker-compose.yml 文件中，运行时执行的 SQL 服务器 docker-构成向上。</span><span class="sxs-lookup"><span data-stu-id="7c25e-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run docker-compose up.</span></span> <span data-ttu-id="7c25e-113">请注意 YAML 代码进行整合泛型 docker-compose.yml 文件和 docker compose.override.yml 文件中的配置信息。</span><span class="sxs-lookup"><span data-stu-id="7c25e-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="7c25e-114">（通常你会独立与 SQL Server 映像相关的基或静态信息中的环境设置。）</span><span class="sxs-lookup"><span data-stu-id="7c25e-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

<span data-ttu-id="7c25e-115">以下 docker run 命令可以运行该容器：</span><span class="sxs-lookup"><span data-stu-id="7c25e-115">The following docker run command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

<span data-ttu-id="7c25e-116">但是，如果你要部署多容器应用程序，如 eShopOnContainers，则更方便地使用命令，以便将应用程序所需的所有容器中都部署 docker compose。</span><span class="sxs-lookup"><span data-stu-id="7c25e-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the docker-compose up command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="7c25e-117">当你首次启动此 SQL Server 容器时，容器将初始化替换为你提供的密码的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7c25e-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="7c25e-118">后 SQL Server 正在运行的容器，可以通过从 SQL Server Management Studio、 Visual Studio 中或 C 如连接通过任何正则的 SQL 连接，来更新数据库\#代码。</span><span class="sxs-lookup"><span data-stu-id="7c25e-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="7c25e-119">下一节中所述，eShopOnContainers 应用程序通过使用在启动时，数据进行种子设定初始化示例数据与每个微服务数据库。</span><span class="sxs-lookup"><span data-stu-id="7c25e-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="7c25e-120">具有运行作为容器的 SQL Server 不是不仅可用于一个演示，你可能没有访问 SQL Server 的实例。</span><span class="sxs-lookup"><span data-stu-id="7c25e-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="7c25e-121">特别说明，还有适用于开发和测试环境，以便可以轻松运行集成测试从干净的 SQL Server 映像和已知的种子设定新示例数据的数据。</span><span class="sxs-lookup"><span data-stu-id="7c25e-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="7c25e-122">其他资源</span><span class="sxs-lookup"><span data-stu-id="7c25e-122">Additional resources</span></span>

-   <span data-ttu-id="7c25e-123">**在 Linux、 Mac 或 Windows 上运行 SQL Server Docker 映像**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span><span class="sxs-lookup"><span data-stu-id="7c25e-123">**Run the SQL Server Docker image on Linux, Mac, or Windows**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span></span>

-   <span data-ttu-id="7c25e-124">**连接和查询在 Linux 上的 SQL Server 使用 sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="7c25e-124">**Connect and query SQL Server on Linux with sqlcmd**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span></span>

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="7c25e-125">使用在 Web 应用程序启动的测试数据种子设定</span><span class="sxs-lookup"><span data-stu-id="7c25e-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="7c25e-126">若要将数据添加到数据库中，在应用程序启动时，可以将类似于下面的代码添加到 Web API 项目的启动类中的配置方法中：</span><span class="sxs-lookup"><span data-stu-id="7c25e-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

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

<span data-ttu-id="7c25e-127">自定义的 CatalogContextSeed 类中的以下代码填充数据。</span><span class="sxs-lookup"><span data-stu-id="7c25e-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="7c25e-128">运行集成测试时，具有一种方法来生成集成测试与一致的数据非常有用。</span><span class="sxs-lookup"><span data-stu-id="7c25e-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="7c25e-129">能够从头开始创建的所有内容，包括运行的容器上的 SQL Server 的实例是非常适合于测试环境。</span><span class="sxs-lookup"><span data-stu-id="7c25e-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="7c25e-130">EF 核心 InMemory 数据库而不是作为的容器运行的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c25e-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="7c25e-131">另一个不错的选择运行测试时是使用实体框架 InMemory 数据库提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c25e-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="7c25e-132">Web API 项目中，你可以在启动类 ConfigureServices 方法中指定该配置：</span><span class="sxs-lookup"><span data-stu-id="7c25e-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="7c25e-133">存在有重要的问题。</span><span class="sxs-lookup"><span data-stu-id="7c25e-133">There is an important catch, though.</span></span> <span data-ttu-id="7c25e-134">内存中数据库不支持特定于特定数据库的许多约束。</span><span class="sxs-lookup"><span data-stu-id="7c25e-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="7c25e-135">例如，您可能 EF 核心模型中在列上添加一个唯一索引和针对你要检查，它不允许您添加重复的值的内存中数据库写入测试。</span><span class="sxs-lookup"><span data-stu-id="7c25e-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="7c25e-136">但当你使用的内存中数据库，不能处理在列上的唯一索引。</span><span class="sxs-lookup"><span data-stu-id="7c25e-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="7c25e-137">因此，内存中数据库的行为与实际的 SQL Server 数据库完全相同-不会模拟特定于数据库的约束。</span><span class="sxs-lookup"><span data-stu-id="7c25e-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="7c25e-138">即便如此，内存中数据库是仍可用于测试和原型制作的。</span><span class="sxs-lookup"><span data-stu-id="7c25e-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="7c25e-139">但如果你想要创建考虑特定数据库实现的行为的准确的集成测试，你需要使用实际类似于 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="7c25e-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="7c25e-140">出于这个目的，在容器中运行 SQL Server 是出色 choice 比且更精确的 EF 核心 InMemory 数据库提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c25e-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="7c25e-141">使用在容器中运行的 Redis 缓存服务</span><span class="sxs-lookup"><span data-stu-id="7c25e-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="7c25e-142">你可以在一个容器，尤其是针对开发和测试和概念证明方案上运行 Redis。</span><span class="sxs-lookup"><span data-stu-id="7c25e-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="7c25e-143">这种情况下很方便，因为你可以在容器上运行所有依赖项-不只是对于你的本地开发计算机，但针对你 CI/CD 管道中的测试环境。</span><span class="sxs-lookup"><span data-stu-id="7c25e-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="7c25e-144">但是，在生产环境中运行 Redis 时，它是更好的做法寻找如 Redis Microsoft Azure，它作为 PaaS （平台即服务） 运行的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c25e-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="7c25e-145">在代码中，只需更改连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7c25e-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="7c25e-146">Redis 提供使用 Redis 的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="7c25e-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="7c25e-147">该映像是从 Docker Hub 此 URL 处可用：</span><span class="sxs-lookup"><span data-stu-id="7c25e-147">That image is available from Docker Hub at this URL:</span></span>

<span data-ttu-id="7c25e-148"><https://hub.docker.com/_/redis/></span><span class="sxs-lookup"><span data-stu-id="7c25e-148"><https://hub.docker.com/_/redis/></span></span>

<span data-ttu-id="7c25e-149">通过在命令提示符处执行以下 Docker CLI 命令，你可以直接运行 Docker Redis 容器：</span><span class="sxs-lookup"><span data-stu-id="7c25e-149">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="7c25e-150">Redis 映像包括公开： 6379 （Redis 使用的端口），因此标准容器链接将使其自动可供链接的容器。</span><span class="sxs-lookup"><span data-stu-id="7c25e-150">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="7c25e-151">在 eShopOnContainers，basket.api microservice 使用 Redis 缓存作为容器运行。</span><span class="sxs-lookup"><span data-stu-id="7c25e-151">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="7c25e-152">该 basket.data 容器可以定义为属于多容器 docker-compose.yml 文件，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="7c25e-152">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="7c25e-153">此代码中 docker-compose.yml 定义名为 basket.data 基于 redis 映像和发布端口 6379 内部，这意味着它将只能从在 Docker 主机内运行的其他容器访问的容器。</span><span class="sxs-lookup"><span data-stu-id="7c25e-153">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="7c25e-154">最后，在 docker compose.override.yml 文件中，eShopOnContainers 示例 basket.api microservice 定义要用于该 Redis 容器的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="7c25e-154">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
<span data-ttu-id="7c25e-155">[以前](多-container-应用程序的 docker-compose.md) [下一步] (集成-事件-基于-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="7c25e-155">[Previous] (multi-container-applications-docker-compose.md) [Next] (integration-event-based-microservice-communications.md)</span></span>
