---
title: 在 ASP.NET Core 应用中使用数据
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用 | 在 ASP.NET Core 应用中使用数据
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 069bfacd1ae08b5c84d6e304b2f12f18e1eecb22
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2018
ms.locfileid: "49122846"
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="a696c-103">在 ASP.NET Core 应用中使用数据</span><span class="sxs-lookup"><span data-stu-id="a696c-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="a696c-104">“数据很宝贵，它的持续时间长于系统本身。”</span><span class="sxs-lookup"><span data-stu-id="a696c-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>
>
> <span data-ttu-id="a696c-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="a696c-105">Tim Berners-Lee</span></span>

<span data-ttu-id="a696c-106">对于几乎任何软件应用程序，数据访问都是重要的部分。</span><span class="sxs-lookup"><span data-stu-id="a696c-106">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="a696c-107">ASP.NET Core 支持各种数据访问选项，包括 Entity Framework Core（以及 Entity Framework 6），并且可使用任何 .NET 数据访问框架。</span><span class="sxs-lookup"><span data-stu-id="a696c-107">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="a696c-108">选择使用哪种数据访问框架，具体取决于应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="a696c-108">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="a696c-109">从 ApplicationCore 和 UI 项目中提取这些选项，并在基础结构中封装实现详细信息，这有助于生成松散耦合的可测试软件。</span><span class="sxs-lookup"><span data-stu-id="a696c-109">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="a696c-110">Entity Framework Core（适用于关系数据库）</span><span class="sxs-lookup"><span data-stu-id="a696c-110">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="a696c-111">如果要编写需要使用关系数据的新的 ASP.NET Core 应用程序，则 Entity Framework Core (EF Core) 是应用程序访问数据的建议方式。</span><span class="sxs-lookup"><span data-stu-id="a696c-111">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="a696c-112">EF Core 是一种支持 .NET 开发人员将对象保存到数据源或从数据源中保存的对象关系映射程序 (O/RM)。</span><span class="sxs-lookup"><span data-stu-id="a696c-112">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="a696c-113">它不要求提供开发人员通常需要编写的大部分数据访问代码。</span><span class="sxs-lookup"><span data-stu-id="a696c-113">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="a696c-114">与 ASP.NET Core 一样，EF Core 经过完全重新编写以支持模块化跨平台应用程序。</span><span class="sxs-lookup"><span data-stu-id="a696c-114">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="a696c-115">将其添加到应用程序作为 NuGet 包，在启动中配置它，并在需要的任何位置通过依赖关系注入请求它。</span><span class="sxs-lookup"><span data-stu-id="a696c-115">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="a696c-116">若要将 EF Core 用于 SQL Server，请运行以下 dotnet CLI 命令：</span><span class="sxs-lookup"><span data-stu-id="a696c-116">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="a696c-117">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span><span class="sxs-lookup"><span data-stu-id="a696c-117">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="a696c-118">若要添加对 InMemory 数据源的支持用于测试，请使用：</span><span class="sxs-lookup"><span data-stu-id="a696c-118">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="a696c-119">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span><span class="sxs-lookup"><span data-stu-id="a696c-119">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="a696c-120">DbContext</span><span class="sxs-lookup"><span data-stu-id="a696c-120">The DbContext</span></span>

<span data-ttu-id="a696c-121">要使用 EF Core，需要 <xref:Microsoft.EntityFrameworkCore.DbContext> 的子类。</span><span class="sxs-lookup"><span data-stu-id="a696c-121">To work with EF Core, you need a subclass of <xref:Microsoft.EntityFrameworkCore.DbContext>.</span></span> <span data-ttu-id="a696c-122">此类可保留表示应用程序将使用的实体集合的属性。</span><span class="sxs-lookup"><span data-stu-id="a696c-122">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="a696c-123">eShopOnWeb 示例包括项目、品牌和类型集合的 CatalogContext：</span><span class="sxs-lookup"><span data-stu-id="a696c-123">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

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

<span data-ttu-id="a696c-124">DbContext 必须包含可接受 DbContextOptions 的构造函数，可将此参数传递给基础 DbContext 构造函数。</span><span class="sxs-lookup"><span data-stu-id="a696c-124">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="a696c-125">注意：如果应用程序中只有一个 DbContext，可传递 DbContextOptions 的实例，但如果有多个 DbContext，则必须使用泛型 DbContextOptions<T>，在 DbContext 类型中作为泛型参数传递。</span><span class="sxs-lookup"><span data-stu-id="a696c-125">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="a696c-126">配置 EF Core</span><span class="sxs-lookup"><span data-stu-id="a696c-126">Configuring EF Core</span></span>

<span data-ttu-id="a696c-127">在 ASP.NET Core 应用程序中，通常在 ConfigureServices 方法配置 EF Core。</span><span class="sxs-lookup"><span data-stu-id="a696c-127">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="a696c-128">EF Core 使用 DbContextOptionsBuilder，可支持多个有用的扩展方法，以简化其配置。</span><span class="sxs-lookup"><span data-stu-id="a696c-128">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="a696c-129">若要将 CatalogContext 配置为与配置中定义的连接字符串一起使用 SQL Server 数据库，需要将以下代码添加到 ConfigureServices：</span><span class="sxs-lookup"><span data-stu-id="a696c-129">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="a696c-130">使用内存中数据库：</span><span class="sxs-lookup"><span data-stu-id="a696c-130">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="a696c-131">安装 EF Core 后，创建 DbContext 子类型，并在 ConfigureServices 中进行配置，然后便可使用 EF Core。</span><span class="sxs-lookup"><span data-stu-id="a696c-131">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="a696c-132">可在需要 DbContext 类型实例的任何服务中进行请求，并通过 LINQ 开始使用持久化实体，就像它们位于集合中一样。</span><span class="sxs-lookup"><span data-stu-id="a696c-132">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="a696c-133">EF Core 负责将 LINQ 表达式转换成 SQL 查询，以存储和检索数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-133">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="a696c-134">可通过配置记录器并确保其级别至少设置为“信息”，查看 EF Core 要执行的查询，如图 8-1 所示。</span><span class="sxs-lookup"><span data-stu-id="a696c-134">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="a696c-135">图 8-1 将 EF Core 查询记录到控制台</span><span class="sxs-lookup"><span data-stu-id="a696c-135">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="a696c-136">提取和存储数据</span><span class="sxs-lookup"><span data-stu-id="a696c-136">Fetching and storing Data</span></span>

<span data-ttu-id="a696c-137">要从 EF Core 中检索数据，请访问相应的属性，并使用 LINQ 筛选结果。</span><span class="sxs-lookup"><span data-stu-id="a696c-137">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="a696c-138">还可以使用 LINQ 执行投影，将结果从一种类型转换为另一种。</span><span class="sxs-lookup"><span data-stu-id="a696c-138">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="a696c-139">下面的示例可检索 CatalogBrands，按名称排序，按 Enabled 属性进行筛选，并投影到 SelectListItem 类型：</span><span class="sxs-lookup"><span data-stu-id="a696c-139">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="a696c-140">请务必在上述示例中添加对 ToListAsync 的调用，以立即执行查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-140">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="a696c-141">否则，语句会将 IQueryable<SelectListItem> 分配给 brandItems，brandItems 在被枚举前不会执行。</span><span class="sxs-lookup"><span data-stu-id="a696c-141">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="a696c-142">从方法中返回 IQueryable 结果有优点，也有缺点。</span><span class="sxs-lookup"><span data-stu-id="a696c-142">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="a696c-143">如果将操作添加到 EF Core 无法转换的查询中，它仍允许对 EF Core 将构造的查询进行进一步修改，但会导致出现仅在运行时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="a696c-143">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="a696c-144">将任何筛选器传递给执行数据访问的方法，并返回内存中集合（例如，List<T>）作为结果，这通常会更安全。</span><span class="sxs-lookup"><span data-stu-id="a696c-144">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="a696c-145">EF Core 可跟踪它从持久性提取的实体上的更改。</span><span class="sxs-lookup"><span data-stu-id="a696c-145">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="a696c-146">要将更改保存到被跟踪实体，只需对 DbContext 调用 SaveChanges 方法，确保它是用于提取实体的同一 DbContext 实例。</span><span class="sxs-lookup"><span data-stu-id="a696c-146">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="a696c-147">直接对相应的 DbSet 属性添加和删除实体，再次通过调用 SaveChanges 执行数据库命令。</span><span class="sxs-lookup"><span data-stu-id="a696c-147">Adding and removing entities is directly done on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="a696c-148">下面的示例演示如何从持久性中添加、更新和删除实体。</span><span class="sxs-lookup"><span data-stu-id="a696c-148">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

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

<span data-ttu-id="a696c-149">EF Core 同时支持用于提取和保存的同步和异步方法。</span><span class="sxs-lookup"><span data-stu-id="a696c-149">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="a696c-150">在 Web 应用程序中，建议将 async/await 模式与异步方法结合使用，以便在等待数据访问操作完成时不会阻止 Web 服务器线程。</span><span class="sxs-lookup"><span data-stu-id="a696c-150">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="a696c-151">提取相关数据</span><span class="sxs-lookup"><span data-stu-id="a696c-151">Fetching related data</span></span>

<span data-ttu-id="a696c-152">EF Core 检索实体时，将填充数据库中直接使用该实体存储的所有属性。</span><span class="sxs-lookup"><span data-stu-id="a696c-152">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="a696c-153">不会填充导航属性（如相关实体列表），且它们的值可能设置为 Null。</span><span class="sxs-lookup"><span data-stu-id="a696c-153">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="a696c-154">这可确保 EF Core 仅提取所需的数据，这对 Web 应用程序格外重要，Web 应用程序必须快速处理请求，并以有效的方式返回响应。</span><span class="sxs-lookup"><span data-stu-id="a696c-154">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="a696c-155">要使用预先加载添加与实体的关系，请指定查询上使用 Include 扩展方法的属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a696c-155">To include relationships with an entity using _eager loading_, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="a696c-156">可添加多种关系，也可使用 ThenInclude 添加子关系。</span><span class="sxs-lookup"><span data-stu-id="a696c-156">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="a696c-157">EF Core 将执行单一查询，检索生成的实体集。</span><span class="sxs-lookup"><span data-stu-id="a696c-157">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="a696c-158">加载相关数据的另一个选项是使用显式加载。</span><span class="sxs-lookup"><span data-stu-id="a696c-158">Another option for loading related data is to use _explicit loading_.</span></span> <span data-ttu-id="a696c-159">通过显式加载，可以将其他数据加载到已检索的实体中。</span><span class="sxs-lookup"><span data-stu-id="a696c-159">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="a696c-160">由于这涉及单独的数据库请求，因此不建议用于 Web 应用程序，Web 应用程序应尽量减少每个请求的数据往返次数。</span><span class="sxs-lookup"><span data-stu-id="a696c-160">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="a696c-161">延迟加载是可在应用程序引用相关数据时自动对其进行加载的一项功能。</span><span class="sxs-lookup"><span data-stu-id="a696c-161">_Lazy loading_ is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="a696c-162">EF Core 2.1 版本中添加了延迟加载支持。</span><span class="sxs-lookup"><span data-stu-id="a696c-162">EF Core has added support for lazy loading in version 2.1.</span></span> <span data-ttu-id="a696c-163">延迟加载默认为不启用，且需要安装 `Microsoft.EntityFrameworkCore.Proxies`。</span><span class="sxs-lookup"><span data-stu-id="a696c-163">Lazy loading is not enabled by default and requires installing the `Microsoft.EntityFrameworkCore.Proxies`.</span></span> <span data-ttu-id="a696c-164">与显式加载相同，通常应对 Web 应用禁用延迟加载，因为使用延迟加载将导致在每个 Web 请求内进行额外的数据库查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-164">As with explicit loading, lazy loading should typically be disabled for web applications, since its use will result in additional database queries being made within each web request.</span></span> <span data-ttu-id="a696c-165">遗憾的是，当延迟较小并且用于测试的数据集通常也较小时，在开发时常常会难以发现延迟加载所产生的开销。</span><span class="sxs-lookup"><span data-stu-id="a696c-165">Unfortunately, the overhead incurred by lazy loading often goes unnoticed at development time, when latency is small and often the data sets used for testing are small.</span></span> <span data-ttu-id="a696c-166">但是，在生产中（涉及更多用户、更多数据和更多延迟），额外的数据库请求常常会导致大量使用延迟加载的 Web 应用性能不佳。</span><span class="sxs-lookup"><span data-stu-id="a696c-166">However, in production, with more users, more data, and more latency, the additional database requests can often result in poor performance for web applications that make heavy use of lazy loading.</span></span>

[<span data-ttu-id="a696c-167">避免延迟加载 Web 应用中的实体</span><span class="sxs-lookup"><span data-stu-id="a696c-167">Avoid Lazy Loading Entities in Web Applications</span></span>](https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications)

### <a name="resilient-connections"></a><span data-ttu-id="a696c-168">弹性连接</span><span class="sxs-lookup"><span data-stu-id="a696c-168">Resilient connections</span></span>

<span data-ttu-id="a696c-169">外部资源（如 SQL 数据库）偶尔可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a696c-169">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="a696c-170">如果暂时不可用，应用程序可使用重试逻辑避免引发异常。</span><span class="sxs-lookup"><span data-stu-id="a696c-170">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="a696c-171">此方法通常称为连接弹性。</span><span class="sxs-lookup"><span data-stu-id="a696c-171">This technique is commonly referred to as _connection resiliency_.</span></span> <span data-ttu-id="a696c-172">可以实现[指数退避算法的重试](https://docs.microsoft.com/azure/architecture/patterns/retry)技术，方法是尝试重试，等待时间呈指数级增长，直到达到最大重试次数。</span><span class="sxs-lookup"><span data-stu-id="a696c-172">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to retry with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="a696c-173">该技术接受以下事实：云资源可能出现短时间间歇性不可用情况，导致某些请求失败。</span><span class="sxs-lookup"><span data-stu-id="a696c-173">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="a696c-174">对于 Azure SQL DB，Entity Framework Core 早已提供了内部数据库连接复原和重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="a696c-174">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="a696c-175">但如果想要复原 EF Core 连接，则需要为每个 DbContext 连接启用 Entity Framework 执行策略。</span><span class="sxs-lookup"><span data-stu-id="a696c-175">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="a696c-176">例如，EF Core 连接级别的下列代码可启用复原 SQL 连接，此连接在连接失败时会重试。</span><span class="sxs-lookup"><span data-stu-id="a696c-176">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

#### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="a696c-177">使用 BeginTransaction 和多个 DbContext 的执行策略和显式事务</span><span class="sxs-lookup"><span data-stu-id="a696c-177">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="a696c-178">在 EF Core 连接中启用重试时，使用 EF Core 执行的每项操作都会成为其自己的可重试操作。</span><span class="sxs-lookup"><span data-stu-id="a696c-178">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="a696c-179">如果发生暂时性故障，每个查询和 SaveChanges 的每次调用都会作为一个单元进行重试。</span><span class="sxs-lookup"><span data-stu-id="a696c-179">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="a696c-180">但是，如果代码使用 BeginTransaction 启动事务，这表示在定义一组自己的操作，这些操作需要被视为一个单元 - 如果发生故障，事务内的所有内容都会回退。</span><span class="sxs-lookup"><span data-stu-id="a696c-180">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="a696c-181">如果在使用 EF 执行策略（重试策略）时尝试执行该事务，并且事务中包含一些来自多个 DbContext 的 SaveChanges，则会看到与下列情况类似的异常。</span><span class="sxs-lookup"><span data-stu-id="a696c-181">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="a696c-182">System.InvalidOperationException：已配置的执行策略“SqlServerRetryingExecutionStrategy”不支持用户启动的事务。</span><span class="sxs-lookup"><span data-stu-id="a696c-182">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="a696c-183">使用由“DbContext.Database.CreateExecutionStrategy()”返回的执行策略执行事务（作为一个可回溯单元）中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="a696c-183">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="a696c-184">该解决方案通过代表所有需要执行的委托来手动调用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="a696c-184">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="a696c-185">如果发生暂时性故障，执行策略会再次调用委托。</span><span class="sxs-lookup"><span data-stu-id="a696c-185">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="a696c-186">下面的代码演示如何实现此方法：</span><span class="sxs-lookup"><span data-stu-id="a696c-186">The following code shows how to implement this approach:</span></span>

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

<span data-ttu-id="a696c-187">第一个 DbContext 是 \_catalogContext，第二个 DbContext 位于 \_integrationEventLogService 对象内。</span><span class="sxs-lookup"><span data-stu-id="a696c-187">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="a696c-188">最后，“提交”操作将执行多个 DbContext，并使用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="a696c-188">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="a696c-189">引用 - Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="a696c-189">References – Entity Framework Core</span></span>
>
> - <span data-ttu-id="a696c-190">**EF Core 文档**</span><span class="sxs-lookup"><span data-stu-id="a696c-190">**EF Core Docs**</span></span>  
>   <https://docs.microsoft.com/ef/>
> - <span data-ttu-id="a696c-191">**EF Core：相关数据**</span><span class="sxs-lookup"><span data-stu-id="a696c-191">**EF Core: Related Data**</span></span>  
>   <https://docs.microsoft.com/ef/core/querying/related-data>
> - <span data-ttu-id="a696c-192">**避免延迟加载 ASPNET 应用程序中的实体**</span><span class="sxs-lookup"><span data-stu-id="a696c-192">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
>   <https://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="a696c-193">选择 EF Core 还是微型 ORM？</span><span class="sxs-lookup"><span data-stu-id="a696c-193">EF Core or micro-ORM?</span></span>

<span data-ttu-id="a696c-194">尽管对于管理持久性以及在大多数情况下封装应用程序开发者提供的数据库详细信息而言，EF Core 是绝佳选择，但它不是唯一的选择。</span><span class="sxs-lookup"><span data-stu-id="a696c-194">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="a696c-195">另一个热门的开源替代选择是一种所谓的微型 ORM，即 [Dapper](https://github.com/StackExchange/Dapper)。</span><span class="sxs-lookup"><span data-stu-id="a696c-195">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="a696c-196">微型 ORM 是不具有完整功能的轻量级工具，用于将对象映射到数据结构。</span><span class="sxs-lookup"><span data-stu-id="a696c-196">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="a696c-197">Dapper 在设计上主要关注性能，而不是完全封装用于检索和更新数据的基础查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-197">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="a696c-198">因为它不提取开发人员的 SQL，Dapper“更接近于原型”，使开发人员可以编写要用于给定数据访问操作的确切查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-198">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="a696c-199">EF Core 具有两个重要功能，使其有别于 Dapper ，并且增加其性能开销。</span><span class="sxs-lookup"><span data-stu-id="a696c-199">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="a696c-200">第一个功能是从 LINQ 表达式转换为 SQL。</span><span class="sxs-lookup"><span data-stu-id="a696c-200">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="a696c-201">将缓存这些转换，但即便如此，首次执行它们时仍会产生开销。</span><span class="sxs-lookup"><span data-stu-id="a696c-201">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="a696c-202">第二个功能是对实体进行更改跟踪（以便生成高效的更新语句）。</span><span class="sxs-lookup"><span data-stu-id="a696c-202">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="a696c-203">通过使用 AsNotTracking 扩展，可对特定查询关闭此行为。</span><span class="sxs-lookup"><span data-stu-id="a696c-203">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="a696c-204">EF Core 还会生成通常非常高效的 SQL 查询，并且从性能角度上看，任何情况下都能完全接受，但如果需要执行对精确查询的精细化控制，也可使用 EF Core 传入自定义 SQL（或执行存储过程）。</span><span class="sxs-lookup"><span data-stu-id="a696c-204">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="a696c-205">在这种情况下，Dapper 的性能仍然优于 EF Core，但只有略微优势。</span><span class="sxs-lookup"><span data-stu-id="a696c-205">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="a696c-206">Julie Lerman 在其 2016 年 5 月的 MSDN 文章 [Dapper、Entity Framework 和混合应用](https://msdn.microsoft.com/magazine/mt703432.aspx)中展示了部分性能数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-206">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="a696c-207">可访问 [Dapper 网站](https://github.com/StackExchange/Dapper)，查看各种数据访问方法的其他性能基准数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-207">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="a696c-208">要查看 Dapper 与 EF Core 语法之间的差异，请考虑用于检索一系列项目的相同方法的两个版本：</span><span class="sxs-lookup"><span data-stu-id="a696c-208">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

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

<span data-ttu-id="a696c-209">要使用 Dapper 生成更复杂的对象图，需要自行编写相关的查询（这与在 EF Core 中添加 Include 不同）。</span><span class="sxs-lookup"><span data-stu-id="a696c-209">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="a696c-210">此功能受到多种语法支持，包括称为“多映射”的功能，该功能允许将各个行映射到多个映射对象中。</span><span class="sxs-lookup"><span data-stu-id="a696c-210">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="a696c-211">例如，给定一个类 Post，其中“所有者”属性是“用户”类型，以下 SQL 将返回所有必要的数据：</span><span class="sxs-lookup"><span data-stu-id="a696c-211">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="a696c-212">返回的每行同时包括“用户”和“Post”数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-212">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="a696c-213">由于“用户”数据应通过其“所有者”属性附加到 Post 数据，因此使用下面的函数：</span><span class="sxs-lookup"><span data-stu-id="a696c-213">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="a696c-214">返回 post 集合的完整代码列表（其中使用相关的用户数据填充其“所有者”属性）为：</span><span class="sxs-lookup"><span data-stu-id="a696c-214">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="a696c-215">因为它提供较少封装，Dapper 要求开发人员深入了解如何存储其数据，如何对其进行高效查询，以及如何编写更多代码来提取它。</span><span class="sxs-lookup"><span data-stu-id="a696c-215">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="a696c-216">模型发生更改时，不是单纯地创建新的迁移（另一种 EF Core 功能），并/或在 DbContext 的某一位置更新映射信息，而是必须更新受影响的所有查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-216">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="a696c-217">这些查询没有编译时间保证，因此它们可能在运行时中断，以应对模型或数据库的更改，增加快速检测错误的难度。</span><span class="sxs-lookup"><span data-stu-id="a696c-217">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="a696c-218">Dapper 可提供极快的性能，以补偿这些方面付出的代价。</span><span class="sxs-lookup"><span data-stu-id="a696c-218">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="a696c-219">对于大多数应用程序和几乎所有应用程序的大多数组件而言，EF Core 提供可接受的性能。</span><span class="sxs-lookup"><span data-stu-id="a696c-219">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="a696c-220">因此，其开发人员工作效率优势很可能大于性能开销这一点上的劣势。</span><span class="sxs-lookup"><span data-stu-id="a696c-220">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="a696c-221">对于可受益于缓存的查询，实际查询执行的时间可能只占很小的百分比，因此可以忽略较小的查询性能差异。</span><span class="sxs-lookup"><span data-stu-id="a696c-221">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="a696c-222">选择 SQL 还是 NoSQL</span><span class="sxs-lookup"><span data-stu-id="a696c-222">SQL or NoSQL</span></span>

<span data-ttu-id="a696c-223">传统上，SQL Server 等关系数据库占领了持久性数据存储的市场，但它们不是唯一可用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="a696c-223">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="a696c-224">NoSQL 数据库（如 [MongoDB](https://www.mongodb.com/what-is-mongodb)）可提供用于存储对象的不同方法。</span><span class="sxs-lookup"><span data-stu-id="a696c-224">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="a696c-225">另一种选择是序列化整个对象图并存储结果，而不是将对象映射到表格和行。</span><span class="sxs-lookup"><span data-stu-id="a696c-225">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="a696c-226">此方法的优点（至少在起初阶段）是简单和高性能。</span><span class="sxs-lookup"><span data-stu-id="a696c-226">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="a696c-227">使用密钥存储单个序列化对象当然比将对象分解为多个表格（其中的关系以及更新和行可能自上次从数据库中检索该对象以来已更改）更简单。</span><span class="sxs-lookup"><span data-stu-id="a696c-227">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="a696c-228">同样，从基于密钥的存储中提取和反序列化单个对象通常比复杂联接或多个数据库查询（完全编写关系数据库中的相同对象所需）更快速、更简单。</span><span class="sxs-lookup"><span data-stu-id="a696c-228">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="a696c-229">此外，由于缺少锁定、事务或固定的架构，这使得 NoSQL 数据库非常适合在多台计算机中缩放，以支持大型数据集。</span><span class="sxs-lookup"><span data-stu-id="a696c-229">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="a696c-230">但是，NoSQL 数据库（人们通常这么称呼该数据库）也有其缺点。</span><span class="sxs-lookup"><span data-stu-id="a696c-230">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="a696c-231">关系数据库利用规范化强制实施一致性并避免数据重复。</span><span class="sxs-lookup"><span data-stu-id="a696c-231">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="a696c-232">这可减少数据库的总大小，确保共享数据更新在整个数据库中立即可用。</span><span class="sxs-lookup"><span data-stu-id="a696c-232">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="a696c-233">在关系数据库中，“地址”表可能按 ID 引用“国家/地区”表，这样一来，如果国家/地区名称发生更改，地址记录将受益于更新，而无需自行更新。</span><span class="sxs-lookup"><span data-stu-id="a696c-233">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="a696c-234">但是，对于 NoSQL 数据库，众多存储对象中的“地址”及其相关的“国家/地区”可能会被序列化。</span><span class="sxs-lookup"><span data-stu-id="a696c-234">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="a696c-235">如果对国家/地区名称进行更新，将需要更新所有此类对象，而不是单独的某行。</span><span class="sxs-lookup"><span data-stu-id="a696c-235">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="a696c-236">关系数据库还可通过强制实施外键等规则，确保关系完整性。</span><span class="sxs-lookup"><span data-stu-id="a696c-236">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="a696c-237">NoSQL 数据库通常不提供此类数据约束。</span><span class="sxs-lookup"><span data-stu-id="a696c-237">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="a696c-238">NoSQL 数据库需要处理的另一复杂性是版本控制。</span><span class="sxs-lookup"><span data-stu-id="a696c-238">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="a696c-239">对象的属性发生更改时，可能无法从存储的过去版本进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="a696c-239">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="a696c-240">因此，需要更新具有对象的序列化（以前）版本的所有现有对象，才能符合其新架构。</span><span class="sxs-lookup"><span data-stu-id="a696c-240">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="a696c-241">从概念上讲，这与关系数据库没有什么差异，架构更改有时需要更新脚本或映射更新。</span><span class="sxs-lookup"><span data-stu-id="a696c-241">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="a696c-242">但是，需要修改的条目数量通常多于 NoSQL 方法，因为存在更多的重复数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-242">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="a696c-243">可以在 NoSQL 数据库中存储多个对象版本，而这是固定架构关系数据库通常不支持的功能。</span><span class="sxs-lookup"><span data-stu-id="a696c-243">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="a696c-244">但是，在这种情况下，应用程序代码需要考虑以前对象版本的存在，这增加了额外的复杂性。</span><span class="sxs-lookup"><span data-stu-id="a696c-244">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="a696c-245">NoSQL 数据库通常不会强制实施 [ACID](https://en.wikipedia.org/wiki/ACID)，这意味着它在性能和可伸缩性方面优于关系数据库。</span><span class="sxs-lookup"><span data-stu-id="a696c-245">NoSQL databases typically do not enforce [ACID](https://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="a696c-246">它们非常适合特别大型的数据集和对象，不适合规范化表格结构中的存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-246">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="a696c-247">根据最适合的情景分别加以利用，单个应用程序能同时获得关系数据库和 NoSQL 数据库带来的好处。</span><span class="sxs-lookup"><span data-stu-id="a696c-247">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="a696c-248">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="a696c-248">Azure DocumentDB</span></span>

<span data-ttu-id="a696c-249">Azure Cosmos DB 是一项完全托管的 NoSQL 数据库服务，可提供基于云的无架构数据存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-249">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="a696c-250">Cosmos DB 旨在实现快速可预测性能、高可用性、弹性缩放和全球分发。</span><span class="sxs-lookup"><span data-stu-id="a696c-250">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="a696c-251">尽管属于 NoSQL 数据库，但开发人员可对 JSON 数据使用熟悉的一系列 SQL 查询功能。</span><span class="sxs-lookup"><span data-stu-id="a696c-251">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="a696c-252">Cosmos DB 中的所有资源均存储为 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="a696c-252">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="a696c-253">资源作为“项目”（包含元数据的文档）和“源”（项目集合）管理。</span><span class="sxs-lookup"><span data-stu-id="a696c-253">Resources are managed as _items_, which are documents containing metadata, and _feeds_, which are collections of items.</span></span> <span data-ttu-id="a696c-254">图 8-2 显示了不同 Cosmos DB 资源之间的关系。</span><span class="sxs-lookup"><span data-stu-id="a696c-254">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>

![Cosmos DB（一种 NoSQL JSON 数据库）的资源之间的层次结构关系](./media/image8-2.png)

<span data-ttu-id="a696c-256">**图 8-2。**</span><span class="sxs-lookup"><span data-stu-id="a696c-256">**Figure 8-2.**</span></span> <span data-ttu-id="a696c-257">Cosmos DB 资源组织。</span><span class="sxs-lookup"><span data-stu-id="a696c-257">DocumentDB resource organization.</span></span>

<span data-ttu-id="a696c-258">Cosmos DB 查询语言是简单而强大的接口，用于查询 JSON 文档。</span><span class="sxs-lookup"><span data-stu-id="a696c-258">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="a696c-259">该语言支持 ANSI SQL 语法的子集，并添加了对 JavaScript 对象、数组、对象结构和函数调用的深度集成。</span><span class="sxs-lookup"><span data-stu-id="a696c-259">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="a696c-260">**参考 - Cosmos DB**</span><span class="sxs-lookup"><span data-stu-id="a696c-260">**References – DocumentDB**</span></span>

- <span data-ttu-id="a696c-261">DocumentDB 简介</span><span class="sxs-lookup"><span data-stu-id="a696c-261">DocumentDB Introduction</span></span>  
  <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a><span data-ttu-id="a696c-262">其他持久性选项</span><span class="sxs-lookup"><span data-stu-id="a696c-262">Other persistence options</span></span>

<span data-ttu-id="a696c-263">除关系数据库和 NoSQL 数据库存储选项外，ASP.NET Core 应用程序还可使用 Azure 存储，以基于云的可缩放方式存储各种数据格式和文件。</span><span class="sxs-lookup"><span data-stu-id="a696c-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="a696c-264">Azure 存储可大规模缩放，因此如果应用程序需要存储少量数据并纵向扩展到存储数百或 TB 级数据，可采用 Azure 存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="a696c-265">Azure 存储支持四种数据：</span><span class="sxs-lookup"><span data-stu-id="a696c-265">Azure Storage supports four kinds of data:</span></span>

- <span data-ttu-id="a696c-266">适用于非结构化文本或二进制储存的 Blob 存储，也称为对象存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

- <span data-ttu-id="a696c-267">适用于结构化数据集的表存储，可通过行键进行访问。</span><span class="sxs-lookup"><span data-stu-id="a696c-267">Table Storage for structured datasets, accessible via row keys.</span></span>

- <span data-ttu-id="a696c-268">适用于可靠且基于队列的消息传送的队列存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-268">Queue Storage for reliable queue-based messaging.</span></span>

- <span data-ttu-id="a696c-269">适用于 Azure 虚拟机和本地应用程序之间的共享文件访问的文件存储。</span><span class="sxs-lookup"><span data-stu-id="a696c-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="a696c-270">**参考 – Azure 存储**</span><span class="sxs-lookup"><span data-stu-id="a696c-270">**References – Azure Storage**</span></span>

- <span data-ttu-id="a696c-271">Azure 存储简介</span><span class="sxs-lookup"><span data-stu-id="a696c-271">Azure Storage Introduction</span></span>  
  <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a><span data-ttu-id="a696c-272">缓存</span><span class="sxs-lookup"><span data-stu-id="a696c-272">Caching</span></span>

<span data-ttu-id="a696c-273">在 Web 应用程序中，应尽可能在最短的时间内完成每个 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="a696c-273">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="a696c-274">实现此目的的一种方法是限制服务器完成请求必须进行的外部调用次数。</span><span class="sxs-lookup"><span data-stu-id="a696c-274">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="a696c-275">缓存涉及在服务器上存储数据副本（或比数据源更易于查询的其他数据存储）。</span><span class="sxs-lookup"><span data-stu-id="a696c-275">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="a696c-276">Web 应用程序，特别是非 SPA 传统 Web 应用程序，需要对每个请求生成整个用户界面。</span><span class="sxs-lookup"><span data-stu-id="a696c-276">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="a696c-277">这通常需要从一个用户请求到下一个用户请求，重复进行多个相同的数据库查询。</span><span class="sxs-lookup"><span data-stu-id="a696c-277">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="a696c-278">在大多数情况下，此类数据很少更改，因此没有必要不断地从数据库进行请求。</span><span class="sxs-lookup"><span data-stu-id="a696c-278">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="a696c-279">ASP.NET Core 支持响应缓存，用于缓存整个页面，以及数据缓存（可支持更精细的缓存行为）。</span><span class="sxs-lookup"><span data-stu-id="a696c-279">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="a696c-280">实现缓存时，请务必记住将问题分离。</span><span class="sxs-lookup"><span data-stu-id="a696c-280">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="a696c-281">避免在数据访问逻辑或用户界面中实现缓存逻辑。</span><span class="sxs-lookup"><span data-stu-id="a696c-281">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="a696c-282">应将缓存封装于其自己的类中，并使用配置管理其行为。</span><span class="sxs-lookup"><span data-stu-id="a696c-282">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="a696c-283">这遵循打开/关闭和单一责任原则，以便用户更轻松地随着应用程序发展管理应用程序的缓存使用方式。</span><span class="sxs-lookup"><span data-stu-id="a696c-283">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="a696c-284">ASP.NET Core 响应缓存</span><span class="sxs-lookup"><span data-stu-id="a696c-284">ASP.NET Core response caching</span></span>

<span data-ttu-id="a696c-285">ASP.NET Core 支持两种级别的响应缓存。</span><span class="sxs-lookup"><span data-stu-id="a696c-285">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="a696c-286">第一种级别不会在服务器上缓存任何内容，但会向缓存响应添加指示客户端和代理服务器的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="a696c-286">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="a696c-287">实现方式是通过向各个控制器或操作添加 ResponseCache 属性：</span><span class="sxs-lookup"><span data-stu-id="a696c-287">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }

    ViewData["Message"] = "Your contact page.";
    return View();
}
```

<span data-ttu-id="a696c-288">上述示例将导致将以下标头添加到响应，同时指示客户端缓存结果（最长 60 秒）。</span><span class="sxs-lookup"><span data-stu-id="a696c-288">The previous example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.</span></span>

<span data-ttu-id="a696c-289">Cache-Control: public,max-age=60</span><span class="sxs-lookup"><span data-stu-id="a696c-289">Cache-Control: public,max-age=60</span></span>

<span data-ttu-id="a696c-290">若要将服务器端内存中缓存添加到应用程序，则必须引用 Microsoft.AspNetCore.ResponseCaching NuGet 包，然后添加响应缓存中间件。</span><span class="sxs-lookup"><span data-stu-id="a696c-290">In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware.</span></span> <span data-ttu-id="a696c-291">ConfigureServices 和 Configure 中的 Startup 中均配置有此中间件：</span><span class="sxs-lookup"><span data-stu-id="a696c-291">This middleware is configured in both ConfigureServices and Configure in Startup:</span></span>

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

<span data-ttu-id="a696c-292">响应缓存中间件将根据一组可自定义的条件自动缓存响应。</span><span class="sxs-lookup"><span data-stu-id="a696c-292">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="a696c-293">默认情况下，仅缓存通过 GET 或 HEAD 方法请求的 200（正常）响应。</span><span class="sxs-lookup"><span data-stu-id="a696c-293">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="a696c-294">此外，请求必须具有包含缓存控件（公共标头）的响应，且不能包含授权标头或 Set-Cookie。</span><span class="sxs-lookup"><span data-stu-id="a696c-294">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="a696c-295">请参阅[响应缓存中间件所用缓存条件的完整列表](/aspnet/core/performance/caching/middleware#conditions-for-caching)。</span><span class="sxs-lookup"><span data-stu-id="a696c-295">See a [complete list of the caching conditions used by the response caching middleware](/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="a696c-296">数据缓存</span><span class="sxs-lookup"><span data-stu-id="a696c-296">Data caching</span></span>

<span data-ttu-id="a696c-297">可以缓存各个数据查询的结果，而不是（或除了）缓存完整 web 响应。</span><span class="sxs-lookup"><span data-stu-id="a696c-297">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="a696c-298">为此，可对 Web 服务器使用内存中缓存，或使用[分布式缓存](/aspnet/core/performance/caching/distributed)。</span><span class="sxs-lookup"><span data-stu-id="a696c-298">For this, you can use in memory caching on the web server, or use [a distributed cache](/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="a696c-299">本节将演示如何实现内存中缓存。</span><span class="sxs-lookup"><span data-stu-id="a696c-299">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="a696c-300">在 ConfigureServices 中添加内存（或分布式）缓存支持：</span><span class="sxs-lookup"><span data-stu-id="a696c-300">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="a696c-301">还需确保添加 Microsoft.Extensions.Caching.Memory NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a696c-301">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="a696c-302">添加服务后，可在需要访问缓存的任何位置，通过依赖关系注入请求 IMemoryCache。</span><span class="sxs-lookup"><span data-stu-id="a696c-302">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="a696c-303">在此示例中，CachedCatalogService 将使用“代理”（或“修饰器”）设计模式，方法是通过提供控制对基础 CatalogService 实现的访问权限（或向其添加行为）的 ICatalogService 的备用实现。</span><span class="sxs-lookup"><span data-stu-id="a696c-303">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

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

<span data-ttu-id="a696c-304">若要配置应用程序，以使用服务的缓存版本，但仍允许服务获取其构造函数中需要的 CatalogService 的实例，请在 ConfigureServices 中添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="a696c-304">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="a696c-305">完成以上操作后，将每分钟执行一次提取目录数据的数据库调用，而不是对每个请求执行。</span><span class="sxs-lookup"><span data-stu-id="a696c-305">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="a696c-306">这可能对向数据库提出的查询数，以及当前依赖于此服务公开的所有三个查询的主页平均加载时间产生非常大的影响，具体取决于网站的流量。</span><span class="sxs-lookup"><span data-stu-id="a696c-306">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="a696c-307">缓存实现时将引发的问题是“数据过时”。也就是说，源中的数据已经更改，但缓存中保留的是过期版本的数据。</span><span class="sxs-lookup"><span data-stu-id="a696c-307">An issue that arises when caching is implemented is _stale data_ – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="a696c-308">缓解此问题的简单方法是使用较短的缓存持续时间，因此对于一个繁忙的应用程序而言，延长数据缓存时长的其他好处非常有限。</span><span class="sxs-lookup"><span data-stu-id="a696c-308">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="a696c-309">例如，假设有一个进行单一数据库查询的网页，每秒对其请求 10 次。</span><span class="sxs-lookup"><span data-stu-id="a696c-309">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="a696c-310">如果此网页缓存一分钟，每分钟执行的数据库查询数将从 600 降为 1，减少了 99.8%。</span><span class="sxs-lookup"><span data-stu-id="a696c-310">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="a696c-311">如果缓存持续时间改为 1 小时，将整体减少 99.997%，但此时过时数据的可能性和潜在期限都可能大幅增加。</span><span class="sxs-lookup"><span data-stu-id="a696c-311">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="a696c-312">另一种方法是在包含的数据更新时主动删除缓存条目。</span><span class="sxs-lookup"><span data-stu-id="a696c-312">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="a696c-313">如果其键已知，可删除任何条目：</span><span class="sxs-lookup"><span data-stu-id="a696c-313">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="a696c-314">如果应用程序公开用于更新其缓存的条目的功能，可在执行更新的代码中删除相应的缓存条目。</span><span class="sxs-lookup"><span data-stu-id="a696c-314">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="a696c-315">有时可能存在众多不同的条目，具体取决于特定数据集。</span><span class="sxs-lookup"><span data-stu-id="a696c-315">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="a696c-316">在这种情况下，使用 CancellationChangeToken 创建缓存条目之间的依赖关系可能非常有用。</span><span class="sxs-lookup"><span data-stu-id="a696c-316">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="a696c-317">使用 CancellationChangeToken，可通过取消令牌同时使多个缓存条目过期。</span><span class="sxs-lookup"><span data-stu-id="a696c-317">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

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

<span data-ttu-id="a696c-318">缓存可以显著提高从数据库重复请求相同值的网页的性能。</span><span class="sxs-lookup"><span data-stu-id="a696c-318">Caching can dramatically improve the performance of web pages that repeatedly request the same values from the database.</span></span> <span data-ttu-id="a696c-319">请确保在应用缓存前测量数据访问和页面性能，并且仅在发现需要改进性能时才应用缓存。</span><span class="sxs-lookup"><span data-stu-id="a696c-319">Be sure to measure data access and page performance before applying caching, and only apply caching where you see a need for improvement.</span></span> <span data-ttu-id="a696c-320">缓存使用 Web 服务器内存资源并增加应用程序的复杂性，因此，不要过早使用此技术进行优化。</span><span class="sxs-lookup"><span data-stu-id="a696c-320">Caching consumes web server memory resources and increases the complexity of the application, so it’s important you don’t prematurely optimize using this technique.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a696c-321">[上一页](develop-asp-net-core-mvc-apps.md)
[下一页](test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a696c-321">[Previous](develop-asp-net-core-mvc-apps.md)
[Next](test-asp-net-core-mvc-apps.md)</span></span>
