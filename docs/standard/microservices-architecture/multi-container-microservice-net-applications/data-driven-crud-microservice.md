---
title: "创建简单的数据驱动 CRUD 微服务"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |创建简单的数据驱动 CRUD 微服务"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>创建简单的数据驱动 CRUD 微服务

此部分概述了如何创建一个简单执行的微服务创建，读取、 更新和删除 (CRUD) 操作对数据源。

## <a name="designing-a-simple-crud-microservice"></a>设计简单 CRUD 微服务

从设计的角度来看，这种类型的容器化微服务是非常简单。 要解决的问题可能是很简单，或可能的实现是只是证明概念。

![](./media/image4.png)

**图 8-4**。 简单 CRUD 微服务的的内部设计

这种简单的数据驱动器服务的一个示例是从 eShopOnContainers 示例应用程序目录微服务。 此类型的服务实现其功能包括用于其数据模型、 其业务逻辑和其数据访问代码类的单个 ASP.NET 核心 Web API 项目中。 它还将其相关的数据存储中 （作为另一个容器用于开发/测试目的），在 SQL Server 中运行的数据库，但是也可以是任何常规的 SQL Server 主机，如图 8-5 中所示。

![](./media/image5.png)

**图 8-5**。 简单的数据驱动/CRUD microservice 设计

当你正在开发这种服务时，只需[ASP.NET Core](https://docs.microsoft.com/aspnet/core/)和数据访问 API 或 ORM 如[实体框架核心](https://docs.microsoft.com/ef/core/index)。 你还可以生成[Swagger](http://swagger.io/)元数据自动通过[Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore)提供你的服务提供的说明下, 一节中所述。

请注意，运行 Docker 容器中的 SQL Server 适用于开发环境中，因为最多可以有所有依赖项一样的数据库服务器，而无需设置中的云或本地数据库运行。 当运行集成测试时，这是非常方便。 但是，对于生产环境中，在容器中运行的数据库服务器不建议，因为你通常不会获得高可用性功能，这种方法。 对于在 Azure 中生产环境中，建议你使用 Azure SQL 数据库或任何其他可提供高可用性和高扩展性的数据库技术。 例如，对于一种 NoSQL 方法，可以选择 DocumentDB。

最后，通过编辑 Dockerfile 并将其 docker-compose.yml 元数据文件，你可以配置如何将创建此容器的映像-将使用，并加上设计设置，例如内部和外部名称和 TCP 端口哪些基本映像。 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>与 ASP.NET 核心实现简单 CRUD 微服务

若要实现使用.NET 核心和 Visual Studio 简单 CRUD 微服务，你首先创建一个简单的 ASP.NET 核心 Web API 项目 （在上运行.NET 核心以便它可以在 Linux Docker 主机上运行） 中, 所示为图 8 6。

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  ![](./media/image6.png)   ![](./media/image7.png)
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

**图 8-6**。 在 Visual Studio 中创建 ASP.NET 核心 Web API 项目

创建项目之后，你可以实现你的 MVC 控制器，就像在任何其他 Web API 项目中，使用实体框架 API 或其他 API。 在 eShopOnContainers.Catalog.API 项目中，你可以看到该微服务的主要依赖关系 ASP.NET Core 本身、 实体框架和 Swashbuckle，图 8-7 中所示。

![](./media/image8.PNG)

**图 8-7**。 简单 CRUD Web API 微服务中的依赖关系

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>实现与实体框架核心的 CRUD Web API 服务

实体框架 (EF) 核心是一种轻型，可扩展的并跨平台版本的受欢迎的实体框架数据访问技术。 EF 核心是对象关系映射器 (ORM)，使.NET 开发人员可以使用.NET 对象的数据库使用。

目录 microservice 使用 EF 和 SQL Server 提供程序，因为在具有适用于 Linux 的 Docker 映像的容器中运行其数据库。 但是，无法将数据库部署到任何 SQL Server，如 Windows 本地或 Azure SQL DB。 唯一需要更改是 ASP.NET Web API 微服务中的连接字符串。

#### <a name="add-entity-framework-core-to-your-dependencies"></a>将实体框架核心添加到您的依赖关系

你可以为你想要使用，在此情况下 SQL Server，从 Visual Studio IDE 中或使用 NuGet 控制台数据库提供程序安装 NuGet 包。 使用以下命令：

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a>数据模型

与 EF 核心数据访问执行使用模型。 模型由实体类和派生的上下文表示与数据库，使你可以查询并将数据保存的会话组成。 可以从现有数据库生成模型、 手动代码模型以匹配您的数据库，或使用 EF 迁移从您的模型创建数据库 （以及它随为您的模型随着时间推移而变化）。 为目录微服务中，我们将使用最后一个方法。 你可以看到举例说明 CatalogItem 实体类在以下代码示例中，这是一个简单的普通旧 CLR 对象 ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) 实体类。

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

你还需要表示与数据库的会话的 DbContext。 为目录 microservice，CatalogContext 类派生自 DbContext 基类，如下面的示例中所示：

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }

    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

你可以附加代码在 DbContext 实现。 例如，在示例应用程序，我们有 OnModelCreating 方法的 CatalogContext 类中自动填充示例数据第一次尝试访问数据库。 此方法可用于演示数据。 你还可用于 OnModelCreating 方法自定义与许多其他对象/数据库实体映射[EF 扩展性点](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/)。

你可以查看更多详细信息中的 OnModelCreating[实现与实体框架核心基础结构持久性层](#implementing_infrastructure_persistence)本书后面一节。

##### <a name="querying-data-from-web-api-controllers"></a>从 Web API 控制器查询数据

通常使用语言集成查询 (LINQ)，从数据库检索的实体类的实例，如下面的示例中所示：

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
    [FromQuery]int pageIndex = 0)
    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();
        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();
        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);
        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);
        return Ok(model);
    } 

    //...
}
```

##### <a name="saving-data"></a>保存数据

创建数据、 将其删除，并在使用实体类的实例数据库中修改。 你可以添加代码，如下例所示硬编码 （模拟数据，在此情况下） 到你的 Web API 控制器。

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>ASP.NET 核心应用程序和 Web API 控制器中的依赖关系注入

在 ASP.NET 核心可以使用现成的依赖关系注入 (DI)。 你不需要设置第三方控制反向 (IoC) 容器，尽管你可以插入到 ASP.NET 核心基础结构你首选的 IoC 容器，如果你想。 在这种情况下，这意味着，可以直接插入所需的 EF DBContext 或通过控制器构造函数的其他存储库。 在上面的 CatalogController 类的示例，我们会将注入 CatalogContext 类型的对象以及其他通过 CatalogController 的构造函数的对象。

具有重要的配置，以便在 Web API 项目设置是 DbContext 类注册到服务的 IoC 容器。 则通常中执行此 Startup 类通过调用服务。AddDbContext 方法在 ConfigureServices 方法中，如下面的示例中所示：

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
               typeof(Startup).
               GetTypeInfo().
               Assembly.
               GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...

}
```

### <a name="additional-resources"></a>其他资源

-   **查询数据**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)

-   **保存数据**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>使用 Docker 容器的数据库连接字符串和环境变量

你可以使用 ASP.NET 核心设置并将 ConnectionString 属性添加到你 settings.json 文件，如下面的示例中所示：

```csharp
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

Settings.json 文件可以具有默认值为 ConnectionString 属性或任何其他属性。 但是，这些属性将替代在 docker compose.override.yml 文件中指定的环境变量的值。

从 docker-compose.yml 或 docker compose.override.yml 文件，你可以初始化这些环境变量以便 Docker 将它们作为 OS 环境变量为你设置，如以下 docker compose.override.yml 文件 （连接中所示字符串和其他行包装在此示例中，但在你自己的文件将不自动换行）。

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

解决方法级别的 docker-compose.yml 文件不只是比在项目或微服务级别中，配置文件更灵活，但也更加安全。 请考虑每个微服务生成的 Docker 映像不会包含 docker-compose.yml 文件，仅二进制文件和每个微服务，包括 Dockerfile 的配置文件。 但 docker-compose.yml 文件未部署你的应用程序; 以及它仅在部署时使用。 因此，环境变量值置于这些 docker-compose.yml 文件 （即使没有加密值） 是比将这些值放在与你的代码一起部署的正则.NET 配置文件中更安全的。

最后，你可以获取该值在代码中使用配置\["ConnectionString"\]，在前面的代码示例中的 ConfigureServices 方法中所示。

但是，对于生产环境中，你可能希望资源管理器如何存储连接字符串类似的机密的其他方法。 通常，将由你选 orchestrator，就像可以与[Docker Swarm 机密管理](https://docs.docker.com/engine/swarm/secrets/)。

### <a name="implementing-versioning-in-aspnet-web-apis"></a>在 ASP.NET Web Api 中实现版本控制

随着业务需求变化，可能添加新的资源集合、 资源之间的关系可能会更改，和资源中的数据的结构可能会修改。 更新 Web API 来处理新的要求是一个相对比较简单的过程，但必须考虑此类更改将对使用 Web API 的客户端应用程序的影响。 尽管设计和实现 Web API，开发人员可以完全控制该 API，开发人员没有相同的大程度上控制可能由远程运营的第三方组织生成的客户端应用程序。

版本控制使 Web API，以指示的功能和它公开的资源。 客户端应用程序然后可以提交到特定版本的功能或资源的请求。 有几种方法来实施版本控制：

-   URI 版本控制

-   查询字符串版本控制

-   标头版本控制

查询字符串和 URI 版本控制是最简单的方法实现。 标头版本控制是一种好方法。 但是，不显式地 URI 版本控制一样简单的标头版本控制。 由于 URL 版本控制，是最简单、 最显式 eShopOnContainers 示例应用程序使用 URI 版本控制。

使用 URI 版本控制，如下所示 eShopOnContainers 示例应用程序中，向每个资源的 URI 添加版本号每次修改 Web API 或更改资源的架构。 现有的 Uri 应继续像以前一样，使符合的资源返回到请求的版本匹配的架构运行。

下面的代码示例中所示，可以通过在 Web API，从而使显式 URI 中的版本中使用的 Route 属性设置版本 (在此情况下 v1)。

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

此版本控制机制很简单，取决于将请求路由到相应的终结点的服务器。 但是，对于更复杂的版本控制的最佳方法使用 REST 时，应使用超媒体并实现[HATEOAS （超文本作为应用程序引擎状态）](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources)。

### <a name="additional-resources"></a>其他资源

-   **Scott Hanselman。ASP.NET 核心 RESTful Web API 版本控制变得更容易**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)

-   **版本控制 RESTful web API**

    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding。版本控制、 超媒体和 REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>从 ASP.NET 核心 Web API 生成 Swagger 描述元数据 

[Swagger](http://swagger.io/)是一个常用的开放源代码框架，支持通过大型的生态系统的工具，可帮助你的设计、 生成、 文档，并使用 RESTful Api。 变得越来越 Api 说明元数据域的标准。 你应包括 Swagger 描述元数据与任何类型的微服务，数据驱动的微服务或多个高级域驱动微服务 （如在下一节中所述）。

Swagger 的核心是 Swagger 规范，这是 JSON 或 YAML 文件中的 API 描述元数据。 规范创建你的 API，详细列出所有其资源和操作更轻松的开发、 发现和集成这两个用户-和 machine-readable 格式的 RESTful 协定。

是基础的 OpenAPI 规范 (OAS) 和在标准化 RESTful 接口定义的方式打开、 透明，和协作社区中开发的规范。

规范定义的结构如何可以发现服务以及如何理解其功能。 有关详细信息，包括 web 编辑器和示例的 Swagger 规范从公司 Spotify、 Uber、 Slack，等 Microsoft，请参阅 Swagger 站点 (<http://swagger.io>)。

### <a name="why-use-swagger"></a>为何使用 Swagger？

若要为您的 Api 生成 Swagger 元数据的主要原因如下所示。

**若要自动使用并将你的 Api 集成其他产品的能力**。 多个产品和[商业工具](http://swagger.io/commercial-tools/)和许多[库和框架](http://swagger.io/open-source-integrations/)支持 Swagger。 Microsoft 具有高级产品和工具，可以自动使用基于 Swagger 的 Api，如下所示：

-   [AutoRest](https://github.com/Azure/AutoRest)。 你可以自动生成用于调用 Swagger 的.NET 客户端类。 这

-   可以从 CLI 使用工具，并且它也与 Visual Studio 集成以便能够轻松使用通过 GUI。

-   [Microsoft Flow](https://flow.microsoft.com/en-us/)。 您可以自动[使用和集成你的 API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/)到高级 Microsoft Flow 工作流，而无编程所需的技能。

-   [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)。 你可以自动使用你的 API 从[PowerApps 移动应用](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/)用生成[PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/)，与所需的任何编程技能。

-   [Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps)。 您可以自动[使用并将你的 API 集成到 Azure App Service 逻辑应用](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api)，与所需的任何编程技能。

**能够自动生成 API 文档**。 当你创建大规模的 RESTful Api，如复杂基于微服务构成的应用程序，你需要处理具有不同的数据模型中的请求和响应负载使用多个终结点。 具有正确的文档并具有稳定的 API 管理器中，如您获得 Swagger，以及是成功的 API，由开发人员采用的密钥。

Swagger 的元数据是 Microsoft Flow、 PowerApps 和 Azure 逻辑应用使用的内容以了解如何使用 Api 和连接到它们。

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>如何自动执行使用 Swashbuckle NuGet 包 API Swagger 元数据生成

生成手动 （在 JSON 或 YAML 文件中） 的 Swagger 元数据可以是需要很长时间工作。 但是，您可以通过使用自动化的 ASP.NET Web API 服务的 API 发现[Swashbuckle NuGet 包](http://aka.ms/swashbuckledotnetcore)动态生成 Swagger API 元数据。

Swashbuckle 自动生成你的 ASP.NET Web API 项目的 Swagger 元数据。 它支持 ASP.NET 核心 Web API 项目和传统的 ASP.NET Web API 和任何其他风格，如 Azure API 应用程序，Azure 移动应用程序，基于 ASP.NET 的 Azure Service Fabric 微服务。 它还支持在容器上部署作为中引用应用程序的普通 Web API。

Swashbuckle 将 API 资源管理器和 Swagger 合并或[swagger ui](https://github.com/swagger-api/swagger-ui)提供丰富的发现和文档的 API 使用者体验。 除了其 Swagger 元数据生成器引擎，Swashbuckle 还包含 swagger-ui，它将自动提供安装 Swashbuckle 后的嵌入式的版本。

这意味着可补充你的 API 使用 nice 发现 UI，以帮助开发人员使用你的 API。 它需要大量的代码和维护的很小，因为它自动生成，从而可以专注于生成你的 API。 API 资源管理器的结果看起来像图 8-8。

![](./media/image9.png)

**图 8-8**。 Swashbuckle API 资源管理器基于 Swagger 元数据-eShopOnContainers 目录微服务

API 资源管理器不是最重要的事情。 之后可以描述自身 Swagger 元数据中的 Web API 后，你的 API 可以无缝地使用从基于 Swagger 的工具，包括可以面向多个平台的客户端代理类代码生成器。 例如，作为提到的那样， [AutoRest](https://github.com/Azure/AutoRest)自动生成.NET 客户端类。 但其他工具如[swagger codegen](https://github.com/swagger-api/swagger-codegen)是否也可用，它允许 API 客户端的代码生成自动库、 服务器存根 （stub） 和文档。

当前，Swashbuckle 所包含的两个 NuGet 包： Swashbuckle.SwaggerGen 和 Swashbuckle.SwaggerUi。 前者提供功能直接从你的 API 实现中生成一个或多个 Swagger 文档，并将它们公开 JSON 终结点。 后者提供了嵌入的版本的 swagger ui 工具，它可以由你的应用程序提供服务并由生成的 Swagger 文档，来描述你的 API 提供支持。 但是，Swashbuckle 的最新版本包装这些与 Swashbuckle.AspNetCore metapackage。

请注意，对于.NET 核心 Web API 项目，你都需要使用[Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0)版本 1.0.0 或更高版本。

Web API 项目中安装这些 NuGet 包后，你需要配置 Swagger 中 Startup 类，如以下代码所示：

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
            });
        });
        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUi();
    }
}
```

完成此操作后，你可以启动你的应用程序，并浏览使用类似这样的 Url 的以下的 Swagger JSON 和 UI 终结点：

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

你以前看到的生成的 UI 如 http:// url 由 Swashbuckle&lt;你根 url &gt; /swagger/ui。 图 8-9 中你还可以看到如何测试任何 API 方法。

![](./media/image10.png)

**图 8-9**。 Swashbuckle 的 UI 测试的目录/项 API 方法

图 8-10 演示从 eShopOnContainers 微服务生成的 Swagger JSON 元数据 （这是工具使用下方） 当请求&lt;你根 url&gt;/swagger/v1/swagger.json 使用[Postman](https://www.getpostman.com/).

![](./media/image11.png)

**图 8-10**。 Swagger JSON 元数据

就这么简单。 因为它自动生成的当你将更多的功能添加到你的 API 将增长 Swagger 元数据。

### <a name="additional-resources"></a>其他资源

-   **ASP.NET Web API 帮助页使用 Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)


>[!div class="step-by-step"]
[以前](微服务构成的应用程序-design.md) [下一步] (多-container-应用程序的 docker-compose.md)
