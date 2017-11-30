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
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="955e9-104">创建简单的数据驱动 CRUD 微服务</span><span class="sxs-lookup"><span data-stu-id="955e9-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="955e9-105">此部分概述了如何创建一个简单执行的微服务创建，读取、 更新和删除 (CRUD) 操作对数据源。</span><span class="sxs-lookup"><span data-stu-id="955e9-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="955e9-106">设计简单 CRUD 微服务</span><span class="sxs-lookup"><span data-stu-id="955e9-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="955e9-107">从设计的角度来看，这种类型的容器化微服务是非常简单。</span><span class="sxs-lookup"><span data-stu-id="955e9-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="955e9-108">要解决的问题可能是很简单，或可能的实现是只是证明概念。</span><span class="sxs-lookup"><span data-stu-id="955e9-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="955e9-109">**图 8-4**。</span><span class="sxs-lookup"><span data-stu-id="955e9-109">**Figure 8-4**.</span></span> <span data-ttu-id="955e9-110">简单 CRUD 微服务的的内部设计</span><span class="sxs-lookup"><span data-stu-id="955e9-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="955e9-111">这种简单的数据驱动器服务的一个示例是从 eShopOnContainers 示例应用程序目录微服务。</span><span class="sxs-lookup"><span data-stu-id="955e9-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="955e9-112">此类型的服务实现其功能包括用于其数据模型、 其业务逻辑和其数据访问代码类的单个 ASP.NET 核心 Web API 项目中。</span><span class="sxs-lookup"><span data-stu-id="955e9-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="955e9-113">它还将其相关的数据存储中 （作为另一个容器用于开发/测试目的），在 SQL Server 中运行的数据库，但是也可以是任何常规的 SQL Server 主机，如图 8-5 中所示。</span><span class="sxs-lookup"><span data-stu-id="955e9-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="955e9-114">**图 8-5**。</span><span class="sxs-lookup"><span data-stu-id="955e9-114">**Figure 8-5**.</span></span> <span data-ttu-id="955e9-115">简单的数据驱动/CRUD microservice 设计</span><span class="sxs-lookup"><span data-stu-id="955e9-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="955e9-116">当你正在开发这种服务时，只需[ASP.NET Core](https://docs.microsoft.com/aspnet/core/)和数据访问 API 或 ORM 如[实体框架核心](https://docs.microsoft.com/ef/core/index)。</span><span class="sxs-lookup"><span data-stu-id="955e9-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="955e9-117">你还可以生成[Swagger](http://swagger.io/)元数据自动通过[Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore)提供你的服务提供的说明下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="955e9-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="955e9-118">请注意，运行 Docker 容器中的 SQL Server 适用于开发环境中，因为最多可以有所有依赖项一样的数据库服务器，而无需设置中的云或本地数据库运行。</span><span class="sxs-lookup"><span data-stu-id="955e9-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="955e9-119">当运行集成测试时，这是非常方便。</span><span class="sxs-lookup"><span data-stu-id="955e9-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="955e9-120">但是，对于生产环境中，在容器中运行的数据库服务器不建议，因为你通常不会获得高可用性功能，这种方法。</span><span class="sxs-lookup"><span data-stu-id="955e9-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="955e9-121">对于在 Azure 中生产环境中，建议你使用 Azure SQL 数据库或任何其他可提供高可用性和高扩展性的数据库技术。</span><span class="sxs-lookup"><span data-stu-id="955e9-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="955e9-122">例如，对于一种 NoSQL 方法，可以选择 DocumentDB。</span><span class="sxs-lookup"><span data-stu-id="955e9-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="955e9-123">最后，通过编辑 Dockerfile 并将其 docker-compose.yml 元数据文件，你可以配置如何将创建此容器的映像-将使用，并加上设计设置，例如内部和外部名称和 TCP 端口哪些基本映像。</span><span class="sxs-lookup"><span data-stu-id="955e9-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="955e9-124">与 ASP.NET 核心实现简单 CRUD 微服务</span><span class="sxs-lookup"><span data-stu-id="955e9-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="955e9-125">若要实现使用.NET 核心和 Visual Studio 简单 CRUD 微服务，你首先创建一个简单的 ASP.NET 核心 Web API 项目 （在上运行.NET 核心以便它可以在 Linux Docker 主机上运行） 中, 所示为图 8 6。</span><span class="sxs-lookup"><span data-stu-id="955e9-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="955e9-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="955e9-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="955e9-127">**图 8-6**。</span><span class="sxs-lookup"><span data-stu-id="955e9-127">**Figure 8-6**.</span></span> <span data-ttu-id="955e9-128">在 Visual Studio 中创建 ASP.NET 核心 Web API 项目</span><span class="sxs-lookup"><span data-stu-id="955e9-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="955e9-129">创建项目之后，你可以实现你的 MVC 控制器，就像在任何其他 Web API 项目中，使用实体框架 API 或其他 API。</span><span class="sxs-lookup"><span data-stu-id="955e9-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="955e9-130">在 eShopOnContainers.Catalog.API 项目中，你可以看到该微服务的主要依赖关系 ASP.NET Core 本身、 实体框架和 Swashbuckle，图 8-7 中所示。</span><span class="sxs-lookup"><span data-stu-id="955e9-130">In the eShopOnContainers.Catalog.API project, you can see that the main dependencies for that microservice are just ASP.NET Core itself, Entity Framework, and Swashbuckle, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="955e9-131">**图 8-7**。</span><span class="sxs-lookup"><span data-stu-id="955e9-131">**Figure 8-7**.</span></span> <span data-ttu-id="955e9-132">简单 CRUD Web API 微服务中的依赖关系</span><span class="sxs-lookup"><span data-stu-id="955e9-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="955e9-133">实现与实体框架核心的 CRUD Web API 服务</span><span class="sxs-lookup"><span data-stu-id="955e9-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="955e9-134">实体框架 (EF) 核心是一种轻型，可扩展的并跨平台版本的受欢迎的实体框架数据访问技术。</span><span class="sxs-lookup"><span data-stu-id="955e9-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="955e9-135">EF 核心是对象关系映射器 (ORM)，使.NET 开发人员可以使用.NET 对象的数据库使用。</span><span class="sxs-lookup"><span data-stu-id="955e9-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="955e9-136">目录 microservice 使用 EF 和 SQL Server 提供程序，因为在具有适用于 Linux 的 Docker 映像的容器中运行其数据库。</span><span class="sxs-lookup"><span data-stu-id="955e9-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="955e9-137">但是，无法将数据库部署到任何 SQL Server，如 Windows 本地或 Azure SQL DB。</span><span class="sxs-lookup"><span data-stu-id="955e9-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="955e9-138">唯一需要更改是 ASP.NET Web API 微服务中的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="955e9-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="add-entity-framework-core-to-your-dependencies"></a><span data-ttu-id="955e9-139">将实体框架核心添加到您的依赖关系</span><span class="sxs-lookup"><span data-stu-id="955e9-139">Add Entity Framework Core to your dependencies</span></span>

<span data-ttu-id="955e9-140">你可以为你想要使用，在此情况下 SQL Server，从 Visual Studio IDE 中或使用 NuGet 控制台数据库提供程序安装 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="955e9-140">You can install the NuGet package for the database provider you want to use, in this case SQL Server, from within the Visual Studio IDE or with the NuGet console.</span></span> <span data-ttu-id="955e9-141">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="955e9-141">Use the following command:</span></span>

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a><span data-ttu-id="955e9-142">数据模型</span><span class="sxs-lookup"><span data-stu-id="955e9-142">The data model</span></span>

<span data-ttu-id="955e9-143">与 EF 核心数据访问执行使用模型。</span><span class="sxs-lookup"><span data-stu-id="955e9-143">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="955e9-144">模型由实体类和派生的上下文表示与数据库，使你可以查询并将数据保存的会话组成。</span><span class="sxs-lookup"><span data-stu-id="955e9-144">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="955e9-145">可以从现有数据库生成模型、 手动代码模型以匹配您的数据库，或使用 EF 迁移从您的模型创建数据库 （以及它随为您的模型随着时间推移而变化）。</span><span class="sxs-lookup"><span data-stu-id="955e9-145">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="955e9-146">为目录微服务中，我们将使用最后一个方法。</span><span class="sxs-lookup"><span data-stu-id="955e9-146">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="955e9-147">你可以看到举例说明 CatalogItem 实体类在以下代码示例中，这是一个简单的普通旧 CLR 对象 ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) 实体类。</span><span class="sxs-lookup"><span data-stu-id="955e9-147">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

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

<span data-ttu-id="955e9-148">你还需要表示与数据库的会话的 DbContext。</span><span class="sxs-lookup"><span data-stu-id="955e9-148">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="955e9-149">为目录 microservice，CatalogContext 类派生自 DbContext 基类，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-149">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

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

<span data-ttu-id="955e9-150">你可以附加代码在 DbContext 实现。</span><span class="sxs-lookup"><span data-stu-id="955e9-150">You can have additional code in the DbContext implementation.</span></span> <span data-ttu-id="955e9-151">例如，在示例应用程序，我们有 OnModelCreating 方法的 CatalogContext 类中自动填充示例数据第一次尝试访问数据库。</span><span class="sxs-lookup"><span data-stu-id="955e9-151">For example, in the sample application, we have an OnModelCreating method in the CatalogContext class that automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="955e9-152">此方法可用于演示数据。</span><span class="sxs-lookup"><span data-stu-id="955e9-152">This method is useful for demo data.</span></span> <span data-ttu-id="955e9-153">你还可用于 OnModelCreating 方法自定义与许多其他对象/数据库实体映射[EF 扩展性点](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/)。</span><span class="sxs-lookup"><span data-stu-id="955e9-153">You can also use the OnModelCreating method to customize object/database entity mappings with many other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

<span data-ttu-id="955e9-154">你可以查看更多详细信息中的 OnModelCreating[实现与实体框架核心基础结构持久性层](#implementing_infrastructure_persistence)本书后面一节。</span><span class="sxs-lookup"><span data-stu-id="955e9-154">You can see further details about OnModelCreating in the [Implementing the infrastructure-persistence layer with Entity Framework Core](#implementing_infrastructure_persistence) section later in this book.</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="955e9-155">从 Web API 控制器查询数据</span><span class="sxs-lookup"><span data-stu-id="955e9-155">Querying data from Web API controllers</span></span>

<span data-ttu-id="955e9-156">通常使用语言集成查询 (LINQ)，从数据库检索的实体类的实例，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-156">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

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

##### <a name="saving-data"></a><span data-ttu-id="955e9-157">保存数据</span><span class="sxs-lookup"><span data-stu-id="955e9-157">Saving data</span></span>

<span data-ttu-id="955e9-158">创建数据、 将其删除，并在使用实体类的实例数据库中修改。</span><span class="sxs-lookup"><span data-stu-id="955e9-158">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="955e9-159">你可以添加代码，如下例所示硬编码 （模拟数据，在此情况下） 到你的 Web API 控制器。</span><span class="sxs-lookup"><span data-stu-id="955e9-159">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="955e9-160">ASP.NET 核心应用程序和 Web API 控制器中的依赖关系注入</span><span class="sxs-lookup"><span data-stu-id="955e9-160">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="955e9-161">在 ASP.NET 核心可以使用现成的依赖关系注入 (DI)。</span><span class="sxs-lookup"><span data-stu-id="955e9-161">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="955e9-162">你不需要设置第三方控制反向 (IoC) 容器，尽管你可以插入到 ASP.NET 核心基础结构你首选的 IoC 容器，如果你想。</span><span class="sxs-lookup"><span data-stu-id="955e9-162">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="955e9-163">在这种情况下，这意味着，可以直接插入所需的 EF DBContext 或通过控制器构造函数的其他存储库。</span><span class="sxs-lookup"><span data-stu-id="955e9-163">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="955e9-164">在上面的 CatalogController 类的示例，我们会将注入 CatalogContext 类型的对象以及其他通过 CatalogController 的构造函数的对象。</span><span class="sxs-lookup"><span data-stu-id="955e9-164">In the example above of the CatalogController class, we are injecting an object of CatalogContext type plus other objects through the CatalogController constructor.</span></span>

<span data-ttu-id="955e9-165">具有重要的配置，以便在 Web API 项目设置是 DbContext 类注册到服务的 IoC 容器。</span><span class="sxs-lookup"><span data-stu-id="955e9-165">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="955e9-166">则通常中执行此 Startup 类通过调用服务。AddDbContext 方法在 ConfigureServices 方法中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-166">You typically do so in the Startup class by calling the services.AddDbContext method inside the ConfigureServices method, as shown in the following example:</span></span>

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

### <a name="additional-resources"></a><span data-ttu-id="955e9-167">其他资源</span><span class="sxs-lookup"><span data-stu-id="955e9-167">Additional resources</span></span>

-   <span data-ttu-id="955e9-168">**查询数据**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="955e9-168">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="955e9-169">**保存数据**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="955e9-169">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="955e9-170">使用 Docker 容器的数据库连接字符串和环境变量</span><span class="sxs-lookup"><span data-stu-id="955e9-170">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="955e9-171">你可以使用 ASP.NET 核心设置并将 ConnectionString 属性添加到你 settings.json 文件，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-171">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

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

<span data-ttu-id="955e9-172">Settings.json 文件可以具有默认值为 ConnectionString 属性或任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="955e9-172">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="955e9-173">但是，这些属性将替代在 docker compose.override.yml 文件中指定的环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="955e9-173">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file.</span></span>

<span data-ttu-id="955e9-174">从 docker-compose.yml 或 docker compose.override.yml 文件，你可以初始化这些环境变量以便 Docker 将它们作为 OS 环境变量为你设置，如以下 docker compose.override.yml 文件 （连接中所示字符串和其他行包装在此示例中，但在你自己的文件将不自动换行）。</span><span class="sxs-lookup"><span data-stu-id="955e9-174">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

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

<span data-ttu-id="955e9-175">解决方法级别的 docker-compose.yml 文件不只是比在项目或微服务级别中，配置文件更灵活，但也更加安全。</span><span class="sxs-lookup"><span data-stu-id="955e9-175">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure.</span></span> <span data-ttu-id="955e9-176">请考虑每个微服务生成的 Docker 映像不会包含 docker-compose.yml 文件，仅二进制文件和每个微服务，包括 Dockerfile 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="955e9-176">Consider that the Docker images that you build per microservice do not contain the docker-compose.yml files, only binary files and configuration files for each microservice, including the Dockerfile.</span></span> <span data-ttu-id="955e9-177">但 docker-compose.yml 文件未部署你的应用程序; 以及它仅在部署时使用。</span><span class="sxs-lookup"><span data-stu-id="955e9-177">But the docker-compose.yml file is not deployed along with your application; it is used only at deployment time.</span></span> <span data-ttu-id="955e9-178">因此，环境变量值置于这些 docker-compose.yml 文件 （即使没有加密值） 是比将这些值放在与你的代码一起部署的正则.NET 配置文件中更安全的。</span><span class="sxs-lookup"><span data-stu-id="955e9-178">Therefore, placing environment variables values in those docker-compose.yml files (even without encrypting the values) is more secure than placing those values in regular .NET configuration files that are deployed with your code.</span></span>

<span data-ttu-id="955e9-179">最后，你可以获取该值在代码中使用配置\["ConnectionString"\]，在前面的代码示例中的 ConfigureServices 方法中所示。</span><span class="sxs-lookup"><span data-stu-id="955e9-179">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="955e9-180">但是，对于生产环境中，你可能希望资源管理器如何存储连接字符串类似的机密的其他方法。</span><span class="sxs-lookup"><span data-stu-id="955e9-180">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="955e9-181">通常，将由你选 orchestrator，就像可以与[Docker Swarm 机密管理](https://docs.docker.com/engine/swarm/secrets/)。</span><span class="sxs-lookup"><span data-stu-id="955e9-181">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="955e9-182">在 ASP.NET Web Api 中实现版本控制</span><span class="sxs-lookup"><span data-stu-id="955e9-182">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="955e9-183">随着业务需求变化，可能添加新的资源集合、 资源之间的关系可能会更改，和资源中的数据的结构可能会修改。</span><span class="sxs-lookup"><span data-stu-id="955e9-183">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="955e9-184">更新 Web API 来处理新的要求是一个相对比较简单的过程，但必须考虑此类更改将对使用 Web API 的客户端应用程序的影响。</span><span class="sxs-lookup"><span data-stu-id="955e9-184">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="955e9-185">尽管设计和实现 Web API，开发人员可以完全控制该 API，开发人员没有相同的大程度上控制可能由远程运营的第三方组织生成的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="955e9-185">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="955e9-186">版本控制使 Web API，以指示的功能和它公开的资源。</span><span class="sxs-lookup"><span data-stu-id="955e9-186">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="955e9-187">客户端应用程序然后可以提交到特定版本的功能或资源的请求。</span><span class="sxs-lookup"><span data-stu-id="955e9-187">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="955e9-188">有几种方法来实施版本控制：</span><span class="sxs-lookup"><span data-stu-id="955e9-188">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="955e9-189">URI 版本控制</span><span class="sxs-lookup"><span data-stu-id="955e9-189">URI versioning</span></span>

-   <span data-ttu-id="955e9-190">查询字符串版本控制</span><span class="sxs-lookup"><span data-stu-id="955e9-190">Query string versioning</span></span>

-   <span data-ttu-id="955e9-191">标头版本控制</span><span class="sxs-lookup"><span data-stu-id="955e9-191">Header versioning</span></span>

<span data-ttu-id="955e9-192">查询字符串和 URI 版本控制是最简单的方法实现。</span><span class="sxs-lookup"><span data-stu-id="955e9-192">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="955e9-193">标头版本控制是一种好方法。</span><span class="sxs-lookup"><span data-stu-id="955e9-193">Header versioning is a good approach.</span></span> <span data-ttu-id="955e9-194">但是，不显式地 URI 版本控制一样简单的标头版本控制。</span><span class="sxs-lookup"><span data-stu-id="955e9-194">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="955e9-195">由于 URL 版本控制，是最简单、 最显式 eShopOnContainers 示例应用程序使用 URI 版本控制。</span><span class="sxs-lookup"><span data-stu-id="955e9-195">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="955e9-196">使用 URI 版本控制，如下所示 eShopOnContainers 示例应用程序中，向每个资源的 URI 添加版本号每次修改 Web API 或更改资源的架构。</span><span class="sxs-lookup"><span data-stu-id="955e9-196">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="955e9-197">现有的 Uri 应继续像以前一样，使符合的资源返回到请求的版本匹配的架构运行。</span><span class="sxs-lookup"><span data-stu-id="955e9-197">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="955e9-198">下面的代码示例中所示，可以通过在 Web API，从而使显式 URI 中的版本中使用的 Route 属性设置版本 (在此情况下 v1)。</span><span class="sxs-lookup"><span data-stu-id="955e9-198">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="955e9-199">此版本控制机制很简单，取决于将请求路由到相应的终结点的服务器。</span><span class="sxs-lookup"><span data-stu-id="955e9-199">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="955e9-200">但是，对于更复杂的版本控制的最佳方法使用 REST 时，应使用超媒体并实现[HATEOAS （超文本作为应用程序引擎状态）](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources)。</span><span class="sxs-lookup"><span data-stu-id="955e9-200">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="955e9-201">其他资源</span><span class="sxs-lookup"><span data-stu-id="955e9-201">Additional resources</span></span>

-   <span data-ttu-id="955e9-202">**Scott Hanselman。ASP.NET 核心 RESTful Web API 版本控制变得更容易**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="955e9-202">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="955e9-203">**版本控制 RESTful web API**</span><span class="sxs-lookup"><span data-stu-id="955e9-203">**Versioning a RESTful web API**</span></span>

    [<span data-ttu-id="955e9-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span><span class="sxs-lookup"><span data-stu-id="955e9-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   <span data-ttu-id="955e9-205">**Roy Fielding。版本控制、 超媒体和 REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="955e9-205">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="955e9-206">从 ASP.NET 核心 Web API 生成 Swagger 描述元数据</span><span class="sxs-lookup"><span data-stu-id="955e9-206">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="955e9-207">[Swagger](http://swagger.io/)是一个常用的开放源代码框架，支持通过大型的生态系统的工具，可帮助你的设计、 生成、 文档，并使用 RESTful Api。</span><span class="sxs-lookup"><span data-stu-id="955e9-207">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="955e9-208">变得越来越 Api 说明元数据域的标准。</span><span class="sxs-lookup"><span data-stu-id="955e9-208">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="955e9-209">你应包括 Swagger 描述元数据与任何类型的微服务，数据驱动的微服务或多个高级域驱动微服务 （如在下一节中所述）。</span><span class="sxs-lookup"><span data-stu-id="955e9-209">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="955e9-210">Swagger 的核心是 Swagger 规范，这是 JSON 或 YAML 文件中的 API 描述元数据。</span><span class="sxs-lookup"><span data-stu-id="955e9-210">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="955e9-211">规范创建你的 API，详细列出所有其资源和操作更轻松的开发、 发现和集成这两个用户-和 machine-readable 格式的 RESTful 协定。</span><span class="sxs-lookup"><span data-stu-id="955e9-211">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="955e9-212">是基础的 OpenAPI 规范 (OAS) 和在标准化 RESTful 接口定义的方式打开、 透明，和协作社区中开发的规范。</span><span class="sxs-lookup"><span data-stu-id="955e9-212">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="955e9-213">规范定义的结构如何可以发现服务以及如何理解其功能。</span><span class="sxs-lookup"><span data-stu-id="955e9-213">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="955e9-214">有关详细信息，包括 web 编辑器和示例的 Swagger 规范从公司 Spotify、 Uber、 Slack，等 Microsoft，请参阅 Swagger 站点 (<http://swagger.io>)。</span><span class="sxs-lookup"><span data-stu-id="955e9-214">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="955e9-215">为何使用 Swagger？</span><span class="sxs-lookup"><span data-stu-id="955e9-215">Why use Swagger?</span></span>

<span data-ttu-id="955e9-216">若要为您的 Api 生成 Swagger 元数据的主要原因如下所示。</span><span class="sxs-lookup"><span data-stu-id="955e9-216">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="955e9-217">**若要自动使用并将你的 Api 集成其他产品的能力**。</span><span class="sxs-lookup"><span data-stu-id="955e9-217">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="955e9-218">多个产品和[商业工具](http://swagger.io/commercial-tools/)和许多[库和框架](http://swagger.io/open-source-integrations/)支持 Swagger。</span><span class="sxs-lookup"><span data-stu-id="955e9-218">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="955e9-219">Microsoft 具有高级产品和工具，可以自动使用基于 Swagger 的 Api，如下所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-219">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="955e9-220">[AutoRest](https://github.com/Azure/AutoRest)。</span><span class="sxs-lookup"><span data-stu-id="955e9-220">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="955e9-221">你可以自动生成用于调用 Swagger 的.NET 客户端类。</span><span class="sxs-lookup"><span data-stu-id="955e9-221">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="955e9-222">这</span><span class="sxs-lookup"><span data-stu-id="955e9-222">This</span></span>

-   <span data-ttu-id="955e9-223">可以从 CLI 使用工具，并且它也与 Visual Studio 集成以便能够轻松使用通过 GUI。</span><span class="sxs-lookup"><span data-stu-id="955e9-223">tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="955e9-224">[Microsoft Flow](https://flow.microsoft.com/en-us/)。</span><span class="sxs-lookup"><span data-stu-id="955e9-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="955e9-225">您可以自动[使用和集成你的 API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/)到高级 Microsoft Flow 工作流，而无编程所需的技能。</span><span class="sxs-lookup"><span data-stu-id="955e9-225">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="955e9-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)。</span><span class="sxs-lookup"><span data-stu-id="955e9-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="955e9-227">你可以自动使用你的 API 从[PowerApps 移动应用](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/)用生成[PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/)，与所需的任何编程技能。</span><span class="sxs-lookup"><span data-stu-id="955e9-227">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="955e9-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps)。</span><span class="sxs-lookup"><span data-stu-id="955e9-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="955e9-229">您可以自动[使用并将你的 API 集成到 Azure App Service 逻辑应用](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api)，与所需的任何编程技能。</span><span class="sxs-lookup"><span data-stu-id="955e9-229">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="955e9-230">**能够自动生成 API 文档**。</span><span class="sxs-lookup"><span data-stu-id="955e9-230">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="955e9-231">当你创建大规模的 RESTful Api，如复杂基于微服务构成的应用程序，你需要处理具有不同的数据模型中的请求和响应负载使用多个终结点。</span><span class="sxs-lookup"><span data-stu-id="955e9-231">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="955e9-232">具有正确的文档并具有稳定的 API 管理器中，如您获得 Swagger，以及是成功的 API，由开发人员采用的密钥。</span><span class="sxs-lookup"><span data-stu-id="955e9-232">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="955e9-233">Swagger 的元数据是 Microsoft Flow、 PowerApps 和 Azure 逻辑应用使用的内容以了解如何使用 Api 和连接到它们。</span><span class="sxs-lookup"><span data-stu-id="955e9-233">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="955e9-234">如何自动执行使用 Swashbuckle NuGet 包 API Swagger 元数据生成</span><span class="sxs-lookup"><span data-stu-id="955e9-234">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="955e9-235">生成手动 （在 JSON 或 YAML 文件中） 的 Swagger 元数据可以是需要很长时间工作。</span><span class="sxs-lookup"><span data-stu-id="955e9-235">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="955e9-236">但是，您可以通过使用自动化的 ASP.NET Web API 服务的 API 发现[Swashbuckle NuGet 包](http://aka.ms/swashbuckledotnetcore)动态生成 Swagger API 元数据。</span><span class="sxs-lookup"><span data-stu-id="955e9-236">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="955e9-237">Swashbuckle 自动生成你的 ASP.NET Web API 项目的 Swagger 元数据。</span><span class="sxs-lookup"><span data-stu-id="955e9-237">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="955e9-238">它支持 ASP.NET 核心 Web API 项目和传统的 ASP.NET Web API 和任何其他风格，如 Azure API 应用程序，Azure 移动应用程序，基于 ASP.NET 的 Azure Service Fabric 微服务。</span><span class="sxs-lookup"><span data-stu-id="955e9-238">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="955e9-239">它还支持在容器上部署作为中引用应用程序的普通 Web API。</span><span class="sxs-lookup"><span data-stu-id="955e9-239">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="955e9-240">Swashbuckle 将 API 资源管理器和 Swagger 合并或[swagger ui](https://github.com/swagger-api/swagger-ui)提供丰富的发现和文档的 API 使用者体验。</span><span class="sxs-lookup"><span data-stu-id="955e9-240">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="955e9-241">除了其 Swagger 元数据生成器引擎，Swashbuckle 还包含 swagger-ui，它将自动提供安装 Swashbuckle 后的嵌入式的版本。</span><span class="sxs-lookup"><span data-stu-id="955e9-241">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="955e9-242">这意味着可补充你的 API 使用 nice 发现 UI，以帮助开发人员使用你的 API。</span><span class="sxs-lookup"><span data-stu-id="955e9-242">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="955e9-243">它需要大量的代码和维护的很小，因为它自动生成，从而可以专注于生成你的 API。</span><span class="sxs-lookup"><span data-stu-id="955e9-243">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="955e9-244">API 资源管理器的结果看起来像图 8-8。</span><span class="sxs-lookup"><span data-stu-id="955e9-244">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="955e9-245">**图 8-8**。</span><span class="sxs-lookup"><span data-stu-id="955e9-245">**Figure 8-8**.</span></span> <span data-ttu-id="955e9-246">Swashbuckle API 资源管理器基于 Swagger 元数据-eShopOnContainers 目录微服务</span><span class="sxs-lookup"><span data-stu-id="955e9-246">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="955e9-247">API 资源管理器不是最重要的事情。</span><span class="sxs-lookup"><span data-stu-id="955e9-247">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="955e9-248">之后可以描述自身 Swagger 元数据中的 Web API 后，你的 API 可以无缝地使用从基于 Swagger 的工具，包括可以面向多个平台的客户端代理类代码生成器。</span><span class="sxs-lookup"><span data-stu-id="955e9-248">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="955e9-249">例如，作为提到的那样， [AutoRest](https://github.com/Azure/AutoRest)自动生成.NET 客户端类。</span><span class="sxs-lookup"><span data-stu-id="955e9-249">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="955e9-250">但其他工具如[swagger codegen](https://github.com/swagger-api/swagger-codegen)是否也可用，它允许 API 客户端的代码生成自动库、 服务器存根 （stub） 和文档。</span><span class="sxs-lookup"><span data-stu-id="955e9-250">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="955e9-251">当前，Swashbuckle 所包含的两个 NuGet 包： Swashbuckle.SwaggerGen 和 Swashbuckle.SwaggerUi。</span><span class="sxs-lookup"><span data-stu-id="955e9-251">Currently, Swashbuckle consists of two NuGet packages: Swashbuckle.SwaggerGen and Swashbuckle.SwaggerUi.</span></span> <span data-ttu-id="955e9-252">前者提供功能直接从你的 API 实现中生成一个或多个 Swagger 文档，并将它们公开 JSON 终结点。</span><span class="sxs-lookup"><span data-stu-id="955e9-252">The former provides functionality to generate one or more Swagger documents directly from your API implementation and expose them as JSON endpoints.</span></span> <span data-ttu-id="955e9-253">后者提供了嵌入的版本的 swagger ui 工具，它可以由你的应用程序提供服务并由生成的 Swagger 文档，来描述你的 API 提供支持。</span><span class="sxs-lookup"><span data-stu-id="955e9-253">The latter provides an embedded version of the swagger-ui tool that can be served by your application and powered by the generated Swagger documents to describe your API.</span></span> <span data-ttu-id="955e9-254">但是，Swashbuckle 的最新版本包装这些与 Swashbuckle.AspNetCore metapackage。</span><span class="sxs-lookup"><span data-stu-id="955e9-254">However, the latest versions of Swashbuckle wrap these with the Swashbuckle.AspNetCore metapackage.</span></span>

<span data-ttu-id="955e9-255">请注意，对于.NET 核心 Web API 项目，你都需要使用[Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0)版本 1.0.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="955e9-255">Note that for .NET Core Web API projects, you need to use [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) version 1.0.0 or later.</span></span>

<span data-ttu-id="955e9-256">Web API 项目中安装这些 NuGet 包后，你需要配置 Swagger 中 Startup 类，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="955e9-256">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

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

<span data-ttu-id="955e9-257">完成此操作后，你可以启动你的应用程序，并浏览使用类似这样的 Url 的以下的 Swagger JSON 和 UI 终结点：</span><span class="sxs-lookup"><span data-stu-id="955e9-257">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

<span data-ttu-id="955e9-258">你以前看到的生成的 UI 如 http:// url 由 Swashbuckle&lt;你根 url &gt; /swagger/ui。</span><span class="sxs-lookup"><span data-stu-id="955e9-258">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="955e9-259">图 8-9 中你还可以看到如何测试任何 API 方法。</span><span class="sxs-lookup"><span data-stu-id="955e9-259">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="955e9-260">**图 8-9**。</span><span class="sxs-lookup"><span data-stu-id="955e9-260">**Figure 8-9**.</span></span> <span data-ttu-id="955e9-261">Swashbuckle 的 UI 测试的目录/项 API 方法</span><span class="sxs-lookup"><span data-stu-id="955e9-261">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="955e9-262">图 8-10 演示从 eShopOnContainers 微服务生成的 Swagger JSON 元数据 （这是工具使用下方） 当请求&lt;你根 url&gt;/swagger/v1/swagger.json 使用[Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="955e9-262">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="955e9-263">**图 8-10**。</span><span class="sxs-lookup"><span data-stu-id="955e9-263">**Figure 8-10**.</span></span> <span data-ttu-id="955e9-264">Swagger JSON 元数据</span><span class="sxs-lookup"><span data-stu-id="955e9-264">Swagger JSON metadata</span></span>

<span data-ttu-id="955e9-265">就这么简单。</span><span class="sxs-lookup"><span data-stu-id="955e9-265">It is that simple.</span></span> <span data-ttu-id="955e9-266">因为它自动生成的当你将更多的功能添加到你的 API 将增长 Swagger 元数据。</span><span class="sxs-lookup"><span data-stu-id="955e9-266">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="955e9-267">其他资源</span><span class="sxs-lookup"><span data-stu-id="955e9-267">Additional resources</span></span>

-   <span data-ttu-id="955e9-268">**ASP.NET Web API 帮助页使用 Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="955e9-268">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="955e9-269">[以前](微服务构成的应用程序-design.md) [下一步] (多-container-应用程序的 docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="955e9-269">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
