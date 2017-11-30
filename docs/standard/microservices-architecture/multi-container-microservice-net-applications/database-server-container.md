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
# <a name="using-a-database-server-running-as-a-container"></a>使用运行的容器的数据库服务器

你的数据库 （SQL Server、 PostgreSQL、 MySQL 等） 可以对正则独立服务器，在本地群集中，或在云中的 Azure SQL DB 等 PaaS 服务。 但是，对于开发和测试环境，你作为容器运行的数据库是方便，因为你没有任何外部依赖关系，并只需运行 docker compose 命令启动整个应用程序。 这些数据库作为容器功能也很强大集成测试，因为数据库将在容器中启动，并且始终填充使用相同的示例数据，因此，测试可能会更可预测。

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>作为的容器运行与 microservice 相关数据库的 SQL Server

在 eShopOnContainers，没有名为 sql.data 中定义的容器[docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml)运行适用于 Linux 的 SQL Server 使用所需的微服务的所有 SQL Server 数据库的文件。 （你也可以为每个数据库的一个 SQL Server 容器，但这将需要更多的内存分配给 Docker）。在微服务重要的一点是，每个微服务拥有其相关的数据，因此其相关的 SQL 数据库在这种情况下。 但是，数据库可以在任何地方。

在示例应用程序的容器配置替换为以下 YAML 代码在 docker-compose.yml 文件中，运行时执行的 SQL 服务器 docker-构成向上。 请注意 YAML 代码进行整合泛型 docker-compose.yml 文件和 docker compose.override.yml 文件中的配置信息。 （通常你会独立与 SQL Server 映像相关的基或静态信息中的环境设置。）

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

以下 docker run 命令可以运行该容器：

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

但是，如果你要部署多容器应用程序，如 eShopOnContainers，则更方便地使用命令，以便将应用程序所需的所有容器中都部署 docker compose。

当你首次启动此 SQL Server 容器时，容器将初始化替换为你提供的密码的 SQL Server。 后 SQL Server 正在运行的容器，可以通过从 SQL Server Management Studio、 Visual Studio 中或 C 如连接通过任何正则的 SQL 连接，来更新数据库\#代码。

下一节中所述，eShopOnContainers 应用程序通过使用在启动时，数据进行种子设定初始化示例数据与每个微服务数据库。

具有运行作为容器的 SQL Server 不是不仅可用于一个演示，你可能没有访问 SQL Server 的实例。 特别说明，还有适用于开发和测试环境，以便可以轻松运行集成测试从干净的 SQL Server 映像和已知的种子设定新示例数据的数据。

#### <a name="additional-resources"></a>其他资源

-   **在 Linux、 Mac 或 Windows 上运行 SQL Server Docker 映像**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **连接和查询在 Linux 上的 SQL Server 使用 sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>使用在 Web 应用程序启动的测试数据种子设定

若要将数据添加到数据库中，在应用程序启动时，可以将类似于下面的代码添加到 Web API 项目的启动类中的配置方法中：

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

自定义的 CatalogContextSeed 类中的以下代码填充数据。

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

运行集成测试时，具有一种方法来生成集成测试与一致的数据非常有用。 能够从头开始创建的所有内容，包括运行的容器上的 SQL Server 的实例是非常适合于测试环境。

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>EF 核心 InMemory 数据库而不是作为的容器运行的 SQL Server

另一个不错的选择运行测试时是使用实体框架 InMemory 数据库提供程序。 Web API 项目中，你可以在启动类 ConfigureServices 方法中指定该配置：

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

存在有重要的问题。 内存中数据库不支持特定于特定数据库的许多约束。 例如，您可能 EF 核心模型中在列上添加一个唯一索引和针对你要检查，它不允许您添加重复的值的内存中数据库写入测试。 但当你使用的内存中数据库，不能处理在列上的唯一索引。 因此，内存中数据库的行为与实际的 SQL Server 数据库完全相同-不会模拟特定于数据库的约束。

即便如此，内存中数据库是仍可用于测试和原型制作的。 但如果你想要创建考虑特定数据库实现的行为的准确的集成测试，你需要使用实际类似于 SQL Server 数据库。 出于这个目的，在容器中运行 SQL Server 是出色 choice 比且更精确的 EF 核心 InMemory 数据库提供程序。

### <a name="using-a-redis-cache-service-running-in-a-container"></a>使用在容器中运行的 Redis 缓存服务

你可以在一个容器，尤其是针对开发和测试和概念证明方案上运行 Redis。 这种情况下很方便，因为你可以在容器上运行所有依赖项-不只是对于你的本地开发计算机，但针对你 CI/CD 管道中的测试环境。

但是，在生产环境中运行 Redis 时，它是更好的做法寻找如 Redis Microsoft Azure，它作为 PaaS （平台即服务） 运行的高可用性解决方案。 在代码中，只需更改连接字符串。

Redis 提供使用 Redis 的 Docker 映像。 该映像是从 Docker Hub 此 URL 处可用：

<https://hub.docker.com/_/redis/>

通过在命令提示符处执行以下 Docker CLI 命令，你可以直接运行 Docker Redis 容器：

```
  docker run --name some-redis -d redis
```

Redis 映像包括公开： 6379 （Redis 使用的端口），因此标准容器链接将使其自动可供链接的容器。

在 eShopOnContainers，basket.api microservice 使用 Redis 缓存作为容器运行。 该 basket.data 容器可以定义为属于多容器 docker-compose.yml 文件，如以下示例所示：

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

此代码中 docker-compose.yml 定义名为 basket.data 基于 redis 映像和发布端口 6379 内部，这意味着它将只能从在 Docker 主机内运行的其他容器访问的容器。

最后，在 docker compose.override.yml 文件中，eShopOnContainers 示例 basket.api microservice 定义要用于该 Redis 容器的连接字符串：

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[以前](多-container-应用程序的 docker-compose.md) [下一步] (集成-事件-基于-microservice-communications.md)
