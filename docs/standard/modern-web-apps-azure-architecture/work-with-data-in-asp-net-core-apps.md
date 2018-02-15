---
title: "在 ASP.NET 核心应用程序中处理数据"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |在 asp 中使用数据"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="afecd-103">使用 ASP.NET Core 应用中的数据</span><span class="sxs-lookup"><span data-stu-id="afecd-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="afecd-104">"数据是宝贵和将持续时间长于系统本身。"</span><span class="sxs-lookup"><span data-stu-id="afecd-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="afecd-105">Tim Berners Lee</span><span class="sxs-lookup"><span data-stu-id="afecd-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="afecd-106">摘要</span><span class="sxs-lookup"><span data-stu-id="afecd-106">Summary</span></span>

<span data-ttu-id="afecd-107">数据访问是几乎任何软件应用程序的一个重要部分。</span><span class="sxs-lookup"><span data-stu-id="afecd-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="afecd-108">ASP.NET 核心支持多种数据访问选项，包括实体框架核心 （和 Entity Framework 6），并且可以工作的任何.NET 数据访问框架。</span><span class="sxs-lookup"><span data-stu-id="afecd-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="afecd-109">其中数据访问框架能够使用的选择取决于应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="afecd-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="afecd-110">它从 ApplicationCore 和 UI 项目中，这些选项和封装基础结构中的实现详细信息可帮助生成松散耦合的、 可测试的软件。</span><span class="sxs-lookup"><span data-stu-id="afecd-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="afecd-111">实体框架核心 （适用于关系数据库）</span><span class="sxs-lookup"><span data-stu-id="afecd-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="afecd-112">如果要编写的新的 ASP.NET Core 应用程序需要处理关系数据，实体框架核心 （EF 核） 将是于你的应用程序访问其数据的建议的方法。</span><span class="sxs-lookup"><span data-stu-id="afecd-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="afecd-113">EF 核心是对象关系映射器 (O/RM)，使.NET 开发人员来持久保存对象与其他数据源。</span><span class="sxs-lookup"><span data-stu-id="afecd-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="afecd-114">它消除了对大多数开发人员通常需要编写数据访问代码的需求。</span><span class="sxs-lookup"><span data-stu-id="afecd-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="afecd-115">如 ASP.NET Core 已重新 EF 核心从头到支持模块化的跨平台应用中编写。</span><span class="sxs-lookup"><span data-stu-id="afecd-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="afecd-116">将其添加到你的应用程序作为 NuGet 程序包、 启动时，对其进行配置和通过依赖关系注入进行请求，只要你需要它。</span><span class="sxs-lookup"><span data-stu-id="afecd-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="afecd-117">若要使用 SQL Server 数据库的 EF 核心，运行以下 dotnet CLI 命令：</span><span class="sxs-lookup"><span data-stu-id="afecd-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="afecd-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="afecd-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="afecd-119">若要添加 InMemory 数据源，用于测试的支持：</span><span class="sxs-lookup"><span data-stu-id="afecd-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="afecd-120">dotnet 添加包 Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="afecd-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="afecd-121">DbContext</span><span class="sxs-lookup"><span data-stu-id="afecd-121">The DbContext</span></span>

<span data-ttu-id="afecd-122">若要使用 EF 核心，你需要 DbContext 的子类。</span><span class="sxs-lookup"><span data-stu-id="afecd-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="afecd-123">此类包含表示你的应用程序会使用的实体的集合的属性。</span><span class="sxs-lookup"><span data-stu-id="afecd-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="afecd-124">EShopOnWeb 示例包括与集合的项、 品牌、 和类型 CatalogContext:</span><span class="sxs-lookup"><span data-stu-id="afecd-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="afecd-125">你 DbContext 必须具有接受 DbContextOptions 的构造函数，并将此自变量传递给基 DbContext 构造函数。</span><span class="sxs-lookup"><span data-stu-id="afecd-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="afecd-126">请注意，如果只有一个 DbContext 中你的应用程序时，你可以将的实例传递 DbContextOptions，但是如果你有多个你必须使用泛型 DbContextOptions<T>类型，在您的 DbContext 类型作为泛型参数中传递。</span><span class="sxs-lookup"><span data-stu-id="afecd-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="afecd-127">配置 EF 核心</span><span class="sxs-lookup"><span data-stu-id="afecd-127">Configuring EF Core</span></span>

<span data-ttu-id="afecd-128">在 ASP.NET Core 应用程序，你通常将 ConfigureServices 方法中配置 EF 核心。</span><span class="sxs-lookup"><span data-stu-id="afecd-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="afecd-129">EF 核心使用 DbContextOptionsBuilder，它支持几个有用的扩展方法来简化其配置。</span><span class="sxs-lookup"><span data-stu-id="afecd-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="afecd-130">若要配置 CatalogContext 要用于在配置中定义的连接字符串的 SQL Server 数据库，则要添加到 ConfigureServices 下面的代码：</span><span class="sxs-lookup"><span data-stu-id="afecd-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="afecd-131">若要使用内存中数据库：</span><span class="sxs-lookup"><span data-stu-id="afecd-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="afecd-132">一旦安装 EF 核心，创建 DbContext 子类型，并将其配置中 ConfigureServices 后，你就可以使用 EF 核心。</span><span class="sxs-lookup"><span data-stu-id="afecd-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="afecd-133">你可以请求中的任何服务都需要它，你 DbContext 类型的实例并开始使用你使用 LINQ，就像它们是只需在集合中的持久化实体。</span><span class="sxs-lookup"><span data-stu-id="afecd-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="afecd-134">EF 核心执行的工作的转换成 SQL 查询来存储和检索你的数据将 LINQ 表达式。</span><span class="sxs-lookup"><span data-stu-id="afecd-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="afecd-135">你可以看到 EF 核心执行通过配置一个记录器，并确保其级别至少设置为查询的信息，如图 8-1 中所示。</span><span class="sxs-lookup"><span data-stu-id="afecd-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="afecd-136">图 8-1 到控制台的日志记录 EF 核心查询</span><span class="sxs-lookup"><span data-stu-id="afecd-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="afecd-137">正在提取和存储数据</span><span class="sxs-lookup"><span data-stu-id="afecd-137">Fetching and Storing Data</span></span>

<span data-ttu-id="afecd-138">若要从 EF 核心检索数据，你访问相应的属性，并使用 LINQ 来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="afecd-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="afecd-139">LINQ 还可用于执行投影，转换到另一种类型的结果。</span><span class="sxs-lookup"><span data-stu-id="afecd-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="afecd-140">下面的示例将检索 CatalogBrands，按名称排序、 其 Enabled 属性中，按筛选和投影到 SelectListItem 类型：</span><span class="sxs-lookup"><span data-stu-id="afecd-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="afecd-141">务必在上面的示例将添加到 ToListAsync 调用，以立即执行查询。</span><span class="sxs-lookup"><span data-stu-id="afecd-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="afecd-142">否则，该语句将分配 IQueryable<SelectListItem>到 brandItems，这将不会执行之前在枚举。</span><span class="sxs-lookup"><span data-stu-id="afecd-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="afecd-143">有优点和缺点到从方法返回 IQueryable 结果。</span><span class="sxs-lookup"><span data-stu-id="afecd-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="afecd-144">它允许 EF 核心将构造以进行进一步的修改，但也可以仅在运行时，发生的错误导致，如果将操作添加到 EF 核心无法转换的查询的查询。</span><span class="sxs-lookup"><span data-stu-id="afecd-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="afecd-145">它是通常更安全地将任何筛选器传递给执行数据访问方法和回到内存中的集合 (例如，列出<T>) 作为结果。</span><span class="sxs-lookup"><span data-stu-id="afecd-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="afecd-146">EF 核心跟踪会从持久性获取的实体上的更改。</span><span class="sxs-lookup"><span data-stu-id="afecd-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="afecd-147">若要将更改保存到被跟踪实体，你只需调用 SaveChanges 方法 DbContext，确保它相同的 DbContext 实例用于提取该实体。</span><span class="sxs-lookup"><span data-stu-id="afecd-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="afecd-148">添加和删除实体是直接在相应 DbSet 的属性，再次使用 SaveChanges 的调用来执行数据库命令。</span><span class="sxs-lookup"><span data-stu-id="afecd-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="afecd-149">下面的示例演示添加、 更新和删除实体从永久性存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="afecd-150">EF 核心支持同步和异步方法提取并保存。</span><span class="sxs-lookup"><span data-stu-id="afecd-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="afecd-151">在 web 应用程序具有建议使用异步/等待模式和异步方法，以便在等待数据访问操作完成时，不会阻止 web 服务器线程。</span><span class="sxs-lookup"><span data-stu-id="afecd-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="afecd-152">提取相关的数据</span><span class="sxs-lookup"><span data-stu-id="afecd-152">Fetching Related Data</span></span>

<span data-ttu-id="afecd-153">当 EF 核心检索实体时，它将填充所有存储直接与数据库中该实体的属性。</span><span class="sxs-lookup"><span data-stu-id="afecd-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="afecd-154">导航属性，例如相关实体的列表不会，因此可能具有其值设置为 null。</span><span class="sxs-lookup"><span data-stu-id="afecd-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="afecd-155">这可确保 EF 核心不提取更多的数据多于所需，这是特别重要的 web 应用程序，必须快速处理请求并有效地返回响应。</span><span class="sxs-lookup"><span data-stu-id="afecd-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="afecd-156">若要包含与实体使用关系*预先加载*，你指定基于该查询，使用包含扩展方法的属性，如所示：</span><span class="sxs-lookup"><span data-stu-id="afecd-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="afecd-157">您可以包含多个关系，并且您还可以包含子关系使用 ThenInclude。</span><span class="sxs-lookup"><span data-stu-id="afecd-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="afecd-158">EF 核心将执行单个查询检索生成的实体集。</span><span class="sxs-lookup"><span data-stu-id="afecd-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="afecd-159">用于加载相关的数据的另一个选项是使用*显式加载*。</span><span class="sxs-lookup"><span data-stu-id="afecd-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="afecd-160">可以使用显式加载其他数据加载到已检索的实体。</span><span class="sxs-lookup"><span data-stu-id="afecd-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="afecd-161">由于这涉及到数据库的单独请求，因此不建议对于 web 应用程序，应尽量减少的数据库数进行每个请求的往返。</span><span class="sxs-lookup"><span data-stu-id="afecd-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="afecd-162">*延迟加载*是一种功能，因为它被引用应用程序将自动加载相关的数据。</span><span class="sxs-lookup"><span data-stu-id="afecd-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="afecd-163">它目前不支持通过 EF 核心，但作为显式加载应通常为禁用该 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="afecd-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="afecd-164">可恢复的连接</span><span class="sxs-lookup"><span data-stu-id="afecd-164">Resilient Connections</span></span>

<span data-ttu-id="afecd-165">外部资源，就像 SQL 数据库有时可能不可用。</span><span class="sxs-lookup"><span data-stu-id="afecd-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="afecd-166">中的暂时不可用的情况下，应用程序可以使用重试逻辑来避免引发异常。</span><span class="sxs-lookup"><span data-stu-id="afecd-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="afecd-167">此方法通常称为*连接复原*。</span><span class="sxs-lookup"><span data-stu-id="afecd-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="afecd-168">你可以实现你[自己重试使用指数退让](https://docs.microsoft.com/azure/architecture/patterns/retry)通过尝试到使用按指数增长的等待时间，重试，直到已达到最大重试计数的技术。</span><span class="sxs-lookup"><span data-stu-id="afecd-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="afecd-169">此方法包含这样一个事实，云资源间歇性可能不可用的时间，从而导致失败的某些请求的短时间。</span><span class="sxs-lookup"><span data-stu-id="afecd-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="afecd-170">对于 Azure SQL DB，实体框架核心已经提供了内部数据库连接复原和重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="afecd-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="afecd-171">但你需要启用每个 DbContext 连接的实体框架执行策略，如果你想要具有可恢复的 EF 核心连接。</span><span class="sxs-lookup"><span data-stu-id="afecd-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="afecd-172">例如，下面的代码位于 EF 核心连接级别启用可恢复将重试，如果连接失败的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="afecd-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.EnableRetryOnFailure(
            maxRetryCount: 5,
            maxRetryDelay: TimeSpan.FromSeconds(30), 
            errorNumbersToAdd: null); 
        });
    });
}
//...
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="afecd-173">执行策略和使用 BeginTransaction 和多个 Dbcontext 的显式事务</span><span class="sxs-lookup"><span data-stu-id="afecd-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="afecd-174">当在 EF 核心连接中启用了重试时，使用 EF 核心执行每个操作将成为其自己的可重试操作。</span><span class="sxs-lookup"><span data-stu-id="afecd-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="afecd-175">每个查询和 SaveChanges 每次调用将重试作为一个单元如果发生暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="afecd-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="afecd-176">但是，如果你的代码启动事务使用 BeginTransaction，你要定义你自己的一组操作需要被视为一个单元 — 发生故障时，已回滚事务内的所有内容。</span><span class="sxs-lookup"><span data-stu-id="afecd-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="afecd-177">如果你尝试执行该事务时使用 EF 执行策略 （重试策略） 并将从多个 Dbcontext 的几个 SaveChanges 包括在它，你将看到如下所示的异常。</span><span class="sxs-lookup"><span data-stu-id="afecd-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="afecd-178">System.InvalidOperationException： 配置的执行策略 SqlServerRetryingExecutionStrategy 不支持用户启动事务。</span><span class="sxs-lookup"><span data-stu-id="afecd-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="afecd-179">使用 DbContext.Database.CreateExecutionStrategy() 返回的执行策略在作为可重试单元事务中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="afecd-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="afecd-180">解决方案是使用委托表示的所有内容，需要执行手动调用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="afecd-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="afecd-181">如果发生暂时性故障，则执行策略将再次调用委托。</span><span class="sxs-lookup"><span data-stu-id="afecd-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="afecd-182">下面的代码演示如何实现此方法：</span><span class="sxs-lookup"><span data-stu-id="afecd-182">The following code shows how to implement this approach:</span></span>

```csharp
// Use of an EF Core resiliency strategy when using multiple DbContexts
// within an explicit transaction
// See:
// https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
var strategy = _catalogContext.Database.CreateExecutionStrategy(); 
await strategy.ExecuteAsync(async () =>
{
    // Achieving atomicity between original Catalog database operation and the
    // IntegrationEventLog thanks to a local transaction
    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);
        await _catalogContext.SaveChangesAsync();
        
        // Save to EventLog only if product price changed
        if (raiseProductPriceChangedEvent)
        await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
    }
});
```

<span data-ttu-id="afecd-183">第一个 DbContext 是\_DbContext catalogContext，第二位于\_integrationEventLogService 对象。</span><span class="sxs-lookup"><span data-stu-id="afecd-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="afecd-184">最后，的提交操作将被执行多个 Dbcontext，并使用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="afecd-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="afecd-185">引用 – 实体框架核心</span><span class="sxs-lookup"><span data-stu-id="afecd-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="afecd-186">**EF 核心文档**</span><span class="sxs-lookup"><span data-stu-id="afecd-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="afecd-187"><https://docs.microsoft.com/ef/></span><span class="sxs-lookup"><span data-stu-id="afecd-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="afecd-188">**EF 核心： 相关的数据**</span><span class="sxs-lookup"><span data-stu-id="afecd-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="afecd-189"><https://docs.microsoft.com/ef/core/querying/related-data></span><span class="sxs-lookup"><span data-stu-id="afecd-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="afecd-190">**避免在 ASPNET 应用程序中的延迟加载实体**</span><span class="sxs-lookup"><span data-stu-id="afecd-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="afecd-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span><span class="sxs-lookup"><span data-stu-id="afecd-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="afecd-192">EF 核心或微型 ORM？</span><span class="sxs-lookup"><span data-stu-id="afecd-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="afecd-193">虽然 EF 核心是一个不错的选择用于管理持久性，并在大多数情况下封装数据库从应用程序开发人员的详细信息，这不是唯一选择。</span><span class="sxs-lookup"><span data-stu-id="afecd-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="afecd-194">另一个受欢迎的开源方法是[Dapper](https://github.com/StackExchange/Dapper)，所谓的微型 ORM。</span><span class="sxs-lookup"><span data-stu-id="afecd-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="afecd-195">微型 ORM 是一种轻型，小于齐全将对象映射到数据结构的工具。</span><span class="sxs-lookup"><span data-stu-id="afecd-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="afecd-196">Dapper 时，对于目标主要性能，而不是完全封装基础查询该其设计用于检索和更新数据。</span><span class="sxs-lookup"><span data-stu-id="afecd-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="afecd-197">因为它不抽象 SQL 开发人员，Dapper"更接近于配置文件"，并允许开发人员编写准确查询他们想要用于给定的数据访问操作。</span><span class="sxs-lookup"><span data-stu-id="afecd-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="afecd-198">EF 核心具有两个重要的功能，它提供了它与 Dapper 隔开，但还将添加到其性能开销。</span><span class="sxs-lookup"><span data-stu-id="afecd-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="afecd-199">第一种是从 LINQ 表达式 SQL 转换的转换。</span><span class="sxs-lookup"><span data-stu-id="afecd-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="afecd-200">将缓存这些翻译，但即便如此开销中执行这些第一次。</span><span class="sxs-lookup"><span data-stu-id="afecd-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="afecd-201">第二个是 （以便可以生成高效的 update 语句），更改跟踪实体。</span><span class="sxs-lookup"><span data-stu-id="afecd-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="afecd-202">此行为可以关闭特定查询使用 AsNotTracking 扩展。</span><span class="sxs-lookup"><span data-stu-id="afecd-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="afecd-203">EF 核心还会生成通常是非常高效和在任何情况下完全可以从性能角度看，接受的 SQL 查询，但如果您需要精确地控制要执行精确查询，你可以在自定义 SQL 中传递 （或执行存储的过程） 使用 EF核心，太。</span><span class="sxs-lookup"><span data-stu-id="afecd-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="afecd-204">在这种情况下，Dapper 仍优于 EF 核心，但很小。</span><span class="sxs-lookup"><span data-stu-id="afecd-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="afecd-205">在她一些性能数据可能 2016 MSDN 文章 Julie Lerman 显示[Dapper、 实体框架和混合应用程序](https://msdn.microsoft.com/magazine/mt703432.aspx)。</span><span class="sxs-lookup"><span data-stu-id="afecd-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="afecd-206">上找不到各种不同的数据访问方法的其他性能基准数据[Dapper 站点](https://github.com/StackExchange/Dapper)。</span><span class="sxs-lookup"><span data-stu-id="afecd-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="afecd-207">若要查看如何从 EF 核心而变化 Dapper 的语法，请考虑用于检索的项列表的相同方法这两个版本：</span><span class="sxs-lookup"><span data-stu-id="afecd-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="afecd-208">如果你需要生成更复杂的对象图，使用 Dapper 时，你需要自己编写的关联的查询 （而不是添加 Include，就像在 EF 核心）。</span><span class="sxs-lookup"><span data-stu-id="afecd-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="afecd-209">通过各种语法，包括一种称为多映射，可将单独的行映射到多个映射对象通过该功能支持此功能。</span><span class="sxs-lookup"><span data-stu-id="afecd-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="afecd-210">例如，给定类型的类 Post 属性所有者与用户，以下 SQL 将返回所有必要的数据：</span><span class="sxs-lookup"><span data-stu-id="afecd-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="afecd-211">每个返回的行包含用户和 Post 数据。</span><span class="sxs-lookup"><span data-stu-id="afecd-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="afecd-212">因为用户数据应附加到其所有者属性通过 Post 数据，所以会使用以下函数：</span><span class="sxs-lookup"><span data-stu-id="afecd-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="afecd-213">将返回的公告的集合，其中使用关联的用户数据进行填充其所有者属性的完整代码列表：</span><span class="sxs-lookup"><span data-stu-id="afecd-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="afecd-214">因为它提供更少封装，Dapper 要求开发人员知道有关其数据的存储方式的详细信息如何有效地，对其进行查询和写入更多代码以提取它。</span><span class="sxs-lookup"><span data-stu-id="afecd-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="afecd-215">在模型更改，而不是只需创建一个新的迁移 （另一个 EF 核心功能），和/或更新某一位置中，创建的 DbContext 的映射信息时必须更新会受到影响的每个查询。</span><span class="sxs-lookup"><span data-stu-id="afecd-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="afecd-216">这些查询具有未编译时间保证，因此它们可能会中断在运行时以响应更改的模型或数据库，使错误更难以进行快速检测到。</span><span class="sxs-lookup"><span data-stu-id="afecd-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="afecd-217">以这些利弊，交换 Dapper 提供极快的性能。</span><span class="sxs-lookup"><span data-stu-id="afecd-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="afecd-218">对于大多数应用程序和的几乎所有应用程序的大多数部件，EF 核心提供可接受的性能。</span><span class="sxs-lookup"><span data-stu-id="afecd-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="afecd-219">因此，其开发人员工作效率优势很可能超过其性能开销。</span><span class="sxs-lookup"><span data-stu-id="afecd-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="afecd-220">对于可以得益于缓存的查询，可能仅执行实际的查询的时间，使相对较小的小百分比查询性能差异没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="afecd-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="afecd-221">SQL 或 NoSQL</span><span class="sxs-lookup"><span data-stu-id="afecd-221">SQL or NoSQL</span></span>

<span data-ttu-id="afecd-222">传统上，类似于 SQL Server 关系数据库具有持续取决于应用商店为永久性数据存储，但它们不是唯一可用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="afecd-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="afecd-223">NoSQL 数据库喜欢[MongoDB](https://www.mongodb.com/what-is-mongodb)提供存储对象的不同方法。</span><span class="sxs-lookup"><span data-stu-id="afecd-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="afecd-224">而不是将对象映射到表和行，另一种方法是序列化整个对象图中，并将结果存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="afecd-225">此方法的优点至少在开始，是简单和性能。</span><span class="sxs-lookup"><span data-stu-id="afecd-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="afecd-226">当然简单得比要分解成多个表关系对象的密钥存储的单个序列化的对象，并从数据库检索更新和自上一次对象可能已更改的行。</span><span class="sxs-lookup"><span data-stu-id="afecd-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="afecd-227">同样，提取和反序列化的基于密钥的存储区中的单个对象通常是更加快速、 轻松比复杂联接或完全撰写关系数据库中的相同对象所需的多个数据库查询。</span><span class="sxs-lookup"><span data-stu-id="afecd-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="afecd-228">缺少锁或事务或固定的架构也使得 NoSQL 数据库非常适用于许多机，支持大型数据集之间的伸缩。</span><span class="sxs-lookup"><span data-stu-id="afecd-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="afecd-229">另一方面，NoSQL 数据库 （如通常称为） 有其缺点。</span><span class="sxs-lookup"><span data-stu-id="afecd-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="afecd-230">关系数据库使用规范化来强制实施一致性并避免重复的数据。</span><span class="sxs-lookup"><span data-stu-id="afecd-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="afecd-231">这减少了数据库的总大小，并确保立即在整个数据库有对共享数据的更新。</span><span class="sxs-lookup"><span data-stu-id="afecd-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="afecd-232">在关系数据库中，地址表可能引用国家/地区表按 ID，这样，如果更改了国家/地区的名称，地址记录会带来好处更新而无需自己无需进行更新。</span><span class="sxs-lookup"><span data-stu-id="afecd-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="afecd-233">但是，在 NoSQL 数据库中，地址和其关联的国家/地区可能进行序列化多个存储对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="afecd-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="afecd-234">国家/地区名称的更新需要将所有此类的对象，以更新，而不是单个行。</span><span class="sxs-lookup"><span data-stu-id="afecd-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="afecd-235">关系数据库还可通过强制执行规则如外键来确保关系的完整性。</span><span class="sxs-lookup"><span data-stu-id="afecd-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="afecd-236">NoSQL 数据库通常不提供此类约束对其数据。</span><span class="sxs-lookup"><span data-stu-id="afecd-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="afecd-237">另一个复杂性 NoSQL 数据库必须处理是版本控制。</span><span class="sxs-lookup"><span data-stu-id="afecd-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="afecd-238">当对象的属性更改时，它可能无法从存储的过去版本反序列化。</span><span class="sxs-lookup"><span data-stu-id="afecd-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="afecd-239">因此，必须更新已序列化的对象 （早期） 版本的所有现有对象，以符合其新的架构。</span><span class="sxs-lookup"><span data-stu-id="afecd-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="afecd-240">这不是从概念上讲不同于关系数据库，其中架构更改有时需要更新脚本或映射更新。</span><span class="sxs-lookup"><span data-stu-id="afecd-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="afecd-241">但是，必须修改的条目数通常是很多占用更多的 NoSQL 方法，因为没有数据的多个副本。</span><span class="sxs-lookup"><span data-stu-id="afecd-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="afecd-242">在 NoSQL 数据库来存储对象的多个版本中，也可以是固定的架构的关系数据库通常不支持。</span><span class="sxs-lookup"><span data-stu-id="afecd-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="afecd-243">但是，在这种情况下你的应用程序代码将需要帐户存在以前版本的对象，添加额外的复杂性。</span><span class="sxs-lookup"><span data-stu-id="afecd-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="afecd-244">NoSQL 数据库通常不会强制使用[ACID](http://en.wikipedia.org/wiki/ACID)，这意味着它们具有在关系数据库的性能和可扩展性优势。</span><span class="sxs-lookup"><span data-stu-id="afecd-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="afecd-245">它们非常适合极大型数据集并不是适合于规范化的表结构中的存储对象。</span><span class="sxs-lookup"><span data-stu-id="afecd-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="afecd-246">没有为什么单个应用程序不能充分利用这两者的关系和 NoSQL 数据库，使用每个最佳适合的理由。</span><span class="sxs-lookup"><span data-stu-id="afecd-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="afecd-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="afecd-247">Azure DocumentDB</span></span>

<span data-ttu-id="afecd-248">Azure DocumentDB 是完全托管的 NoSQL 数据库服务提供基于云的无架构数据存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="afecd-249">DocumentDB 为快速和可预测性能、 高可用性、 弹性缩放和全局通讯组生成。</span><span class="sxs-lookup"><span data-stu-id="afecd-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="afecd-250">尽管一种 NoSQL 数据库，开发人员可以使用 JSON 数据的丰富且熟悉 SQL 查询功能。</span><span class="sxs-lookup"><span data-stu-id="afecd-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="afecd-251">作为 JSON 文档存储在 DocumentDB 中的所有资源。</span><span class="sxs-lookup"><span data-stu-id="afecd-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="afecd-252">作为资源进行管理*项*，后者是包含元数据，文档和*馈送*，它们的项的集合。</span><span class="sxs-lookup"><span data-stu-id="afecd-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="afecd-253">图 8-2 显示不同的 DocumentDB 资源之间的关系。</span><span class="sxs-lookup"><span data-stu-id="afecd-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![DocumentDB，NoSQL JSON 数据库中的资源之间的层次结构关系](./media/image8-2.png)

<span data-ttu-id="afecd-255">**图 8-2。**</span><span class="sxs-lookup"><span data-stu-id="afecd-255">**Figure 8-2.**</span></span> <span data-ttu-id="afecd-256">DocumentDB 资源组织。</span><span class="sxs-lookup"><span data-stu-id="afecd-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="afecd-257">DocumentDB 查询语言是用于查询 JSON 文档的简单但强大接口。</span><span class="sxs-lookup"><span data-stu-id="afecd-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="afecd-258">语言支持 ANSI SQL 语法的子集，并将添加的 JavaScript 对象、 数组、 对象构造和函数调用的深度集成。</span><span class="sxs-lookup"><span data-stu-id="afecd-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="afecd-259">**引用 – DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="afecd-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="afecd-260">DocumentDB Introduction\\</span><span class="sxs-lookup"><span data-stu-id="afecd-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="afecd-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span><span class="sxs-lookup"><span data-stu-id="afecd-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="afecd-262">其他持久性选项</span><span class="sxs-lookup"><span data-stu-id="afecd-262">Other Persistence Options</span></span>

<span data-ttu-id="afecd-263">在添加到关系和 NoSQL 存储选项中，ASP.NET Core 应用程序可以使用 Azure 存储空间将各种数据格式和文件存储在一种基于云的、 可缩放的方式。</span><span class="sxs-lookup"><span data-stu-id="afecd-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="afecd-264">Azure 存储是可大规模缩放，以便你可以启动出存储少量数据，并增加到存储数百或兆兆字节，如果你的应用程序需要它。</span><span class="sxs-lookup"><span data-stu-id="afecd-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="afecd-265">Azure 存储空间支持四种类型的数据：</span><span class="sxs-lookup"><span data-stu-id="afecd-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="afecd-266">非结构化的文本或二进制存储，也称为对象存储的 blob 存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="afecd-267">结构化数据集，可通过行键访问的表存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="afecd-268">可靠的基于队列的消息传送的队列存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="afecd-269">Azure 虚拟机和本地应用程序之间共享的文件访问的文件存储。</span><span class="sxs-lookup"><span data-stu-id="afecd-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="afecd-270">**引用 – Azure 存储空间**</span><span class="sxs-lookup"><span data-stu-id="afecd-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="afecd-271">Azure 存储 Introduction\\</span><span class="sxs-lookup"><span data-stu-id="afecd-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="afecd-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span><span class="sxs-lookup"><span data-stu-id="afecd-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="afecd-273">缓存</span><span class="sxs-lookup"><span data-stu-id="afecd-273">Caching</span></span>

<span data-ttu-id="afecd-274">在 web 应用程序，应在尽可能最短时间内完成每个 web 请求。</span><span class="sxs-lookup"><span data-stu-id="afecd-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="afecd-275">一种方法来实现此目的是限制的服务器必须做出无法完成请求的外部调用数。</span><span class="sxs-lookup"><span data-stu-id="afecd-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="afecd-276">缓存与服务器上存储数据的副本 （或另一个数据存储，它是与数据源轻松查询的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="afecd-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="afecd-277">Web 应用程序和特别是非 SPA 传统 web 应用程序，需要生成与每个请求的整个用户界面。</span><span class="sxs-lookup"><span data-stu-id="afecd-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="afecd-278">这通常涉及到进行很多相同数据库的查询从一个用户请求重复到下一步。</span><span class="sxs-lookup"><span data-stu-id="afecd-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="afecd-279">在大多数情况下，此数据很少更改使有很少需要不断地从数据库中请求它。</span><span class="sxs-lookup"><span data-stu-id="afecd-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="afecd-280">ASP.NET 核心支持响应缓存，用于缓存整个页面和数据缓存，支持更精细的缓存行为。</span><span class="sxs-lookup"><span data-stu-id="afecd-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="afecd-281">在实施缓存时，务必将保留在考虑分离问题。</span><span class="sxs-lookup"><span data-stu-id="afecd-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="afecd-282">避免在数据访问逻辑，或你的用户界面中实现缓存逻辑。</span><span class="sxs-lookup"><span data-stu-id="afecd-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="afecd-283">相反，封装在其自己的类中，缓存并使用配置来管理其行为。</span><span class="sxs-lookup"><span data-stu-id="afecd-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="afecd-284">这打开/关闭和单独责任原则，并将使你更轻松地管理你如何使用它随着你的应用程序中的缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="afecd-285">ASP.NET 核心响应缓存</span><span class="sxs-lookup"><span data-stu-id="afecd-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="afecd-286">ASP.NET 核心支持两个级别的响应缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="afecd-287">第一个级别不会在服务器上，任何内容进行缓存，但将指示客户端和代理服务器缓存响应的 HTTP 标头添加。</span><span class="sxs-lookup"><span data-stu-id="afecd-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="afecd-288">这是通过将 ResponseCache 属性添加到单个控制器或操作实现：</span><span class="sxs-lookup"><span data-stu-id="afecd-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="afecd-289">响应缓存中间件将自动缓存响应基于一组条件，可以自定义的条件。</span><span class="sxs-lookup"><span data-stu-id="afecd-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="afecd-290">默认情况下，通过 GET 或 HEAD 方法请求的仅 200 （正常） 响应进行缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="afecd-291">此外，请求必须具有与缓存控件的响应： 公共标头，并且不能包括授权或集 Cookie 标头。</span><span class="sxs-lookup"><span data-stu-id="afecd-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="afecd-292">请参阅[由缓存中间件的响应的缓存条件的完整列表](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching)。</span><span class="sxs-lookup"><span data-stu-id="afecd-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="afecd-293">数据缓存</span><span class="sxs-lookup"><span data-stu-id="afecd-293">Data Caching</span></span>

<span data-ttu-id="afecd-294">而不是 （或除了） 缓存完整的 web 响应，你可以缓存单个数据查询的结果。</span><span class="sxs-lookup"><span data-stu-id="afecd-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="afecd-295">为此，你可以使用在内存缓存中，在 web 服务器上，或使用[分布式的缓存](https://docs.microsoft.com/aspnet/core/performance/caching/distributed)。</span><span class="sxs-lookup"><span data-stu-id="afecd-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="afecd-296">本部分将演示如何实现在内存中缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="afecd-297">添加对内存的支持 （或分布式） 在缓存中 ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="afecd-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="afecd-298">请务必添加 Microsoft.Extensions.Caching.Memory NuGet 包以及。</span><span class="sxs-lookup"><span data-stu-id="afecd-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="afecd-299">一旦你已添加该服务，你请求 IMemoryCache 通过依赖关系注入只要你需要访问缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="afecd-300">在此示例中，CachedCatalogService 使用代理服务器 （或修饰器） 设计模式中，通过提供 ICatalogService 用于控制对的访问 （或添加到行为） 的其他实现的基础 CatalogService 实现。</span><span class="sxs-lookup"><span data-stu-id="afecd-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="afecd-301">若要配置应用程序以使用缓存的版本的服务，但仍允许服务来获取的 CatalogService 它需要在其构造函数中的实例，则要 ConfigureServices 中添加以下：</span><span class="sxs-lookup"><span data-stu-id="afecd-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="afecd-302">与此就地，数据库调用提取目录数据，则只会发出一次每分钟，而不是对每个请求。</span><span class="sxs-lookup"><span data-stu-id="afecd-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="afecd-303">具体取决于发送到网站的流量，这会对数据库和当前依赖于此服务公开的查询的所有三个主页上的平均页面加载时间对执行的查询数的有非常显著的影响。</span><span class="sxs-lookup"><span data-stu-id="afecd-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="afecd-304">当缓存实现时，出现一个问题是*过时的数据*– 也就是说，在源但过期的版本已更改的数据保留在缓存。</span><span class="sxs-lookup"><span data-stu-id="afecd-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="afecd-305">若要缓解此问题，一种简单的方法是使用小缓存持续时间，因为对于繁忙的应用程序没有将扩展缓存数据的长度限制另一个好处。</span><span class="sxs-lookup"><span data-stu-id="afecd-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="afecd-306">例如，考虑一个页，使单次数据库查询，并每秒 10 倍的请求。</span><span class="sxs-lookup"><span data-stu-id="afecd-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="afecd-307">如果此页为一分钟缓存，则将导致每分钟进行从 600 降为 1，99.8%的减少的数据库查询数。</span><span class="sxs-lookup"><span data-stu-id="afecd-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="afecd-308">如果改为将缓存持续时间进行了一小时，全面降低将 99.997%，但现在的过时数据的可能性和潜在期限同时增加了更显著。</span><span class="sxs-lookup"><span data-stu-id="afecd-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="afecd-309">另一种方法是主动更新所包含的数据时删除缓存项。</span><span class="sxs-lookup"><span data-stu-id="afecd-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="afecd-310">如果知道其密钥，则可以删除任何单个条目。</span><span class="sxs-lookup"><span data-stu-id="afecd-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="afecd-311">如果你的应用程序公开更新其缓存的项的功能，则可以在执行更新代码中删除对应的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="afecd-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="afecd-312">有时可能有许多依赖于一组特定的数据的不同项。</span><span class="sxs-lookup"><span data-stu-id="afecd-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="afecd-313">在这种情况下，它可用于创建缓存项，通过使用 CancellationChangeToken 之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="afecd-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="afecd-314">与 CancellationChangeToken，可以通过取消令牌同时终止多个缓存条目。</span><span class="sxs-lookup"><span data-stu-id="afecd-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="afecd-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="afecd-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
