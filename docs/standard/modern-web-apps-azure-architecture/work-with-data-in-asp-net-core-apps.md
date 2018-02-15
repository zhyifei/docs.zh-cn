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
# <a name="working-with-data-in-aspnet-core-apps"></a>使用 ASP.NET Core 应用中的数据

> "数据是宝贵和将持续时间长于系统本身。"

Tim Berners Lee

## <a name="summary"></a>摘要

数据访问是几乎任何软件应用程序的一个重要部分。 ASP.NET 核心支持多种数据访问选项，包括实体框架核心 （和 Entity Framework 6），并且可以工作的任何.NET 数据访问框架。 其中数据访问框架能够使用的选择取决于应用程序的需求。 它从 ApplicationCore 和 UI 项目中，这些选项和封装基础结构中的实现详细信息可帮助生成松散耦合的、 可测试的软件。

## <a name="entity-framework-core-for-relational-databases"></a>实体框架核心 （适用于关系数据库）

如果要编写的新的 ASP.NET Core 应用程序需要处理关系数据，实体框架核心 （EF 核） 将是于你的应用程序访问其数据的建议的方法。 EF 核心是对象关系映射器 (O/RM)，使.NET 开发人员来持久保存对象与其他数据源。 它消除了对大多数开发人员通常需要编写数据访问代码的需求。 如 ASP.NET Core 已重新 EF 核心从头到支持模块化的跨平台应用中编写。 将其添加到你的应用程序作为 NuGet 程序包、 启动时，对其进行配置和通过依赖关系注入进行请求，只要你需要它。

若要使用 SQL Server 数据库的 EF 核心，运行以下 dotnet CLI 命令：

dotnet add package Microsoft.EntityFrameworkCore.SqlServer

若要添加 InMemory 数据源，用于测试的支持：

dotnet 添加包 Microsoft.EntityFrameworkCore.InMemory

### <a name="the-dbcontext"></a>DbContext

若要使用 EF 核心，你需要 DbContext 的子类。 此类包含表示你的应用程序会使用的实体的集合的属性。 EShopOnWeb 示例包括与集合的项、 品牌、 和类型 CatalogContext:

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

你 DbContext 必须具有接受 DbContextOptions 的构造函数，并将此自变量传递给基 DbContext 构造函数。 请注意，如果只有一个 DbContext 中你的应用程序时，你可以将的实例传递 DbContextOptions，但是如果你有多个你必须使用泛型 DbContextOptions<T>类型，在您的 DbContext 类型作为泛型参数中传递。

### <a name="configuring-ef-core"></a>配置 EF 核心

在 ASP.NET Core 应用程序，你通常将 ConfigureServices 方法中配置 EF 核心。 EF 核心使用 DbContextOptionsBuilder，它支持几个有用的扩展方法来简化其配置。 若要配置 CatalogContext 要用于在配置中定义的连接字符串的 SQL Server 数据库，则要添加到 ConfigureServices 下面的代码：

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

若要使用内存中数据库：

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

一旦安装 EF 核心，创建 DbContext 子类型，并将其配置中 ConfigureServices 后，你就可以使用 EF 核心。 你可以请求中的任何服务都需要它，你 DbContext 类型的实例并开始使用你使用 LINQ，就像它们是只需在集合中的持久化实体。 EF 核心执行的工作的转换成 SQL 查询来存储和检索你的数据将 LINQ 表达式。

你可以看到 EF 核心执行通过配置一个记录器，并确保其级别至少设置为查询的信息，如图 8-1 中所示。

![](./media/image8-1.png)

图 8-1 到控制台的日志记录 EF 核心查询

### <a name="fetching-and-storing-data"></a>正在提取和存储数据

若要从 EF 核心检索数据，你访问相应的属性，并使用 LINQ 来筛选结果。 LINQ 还可用于执行投影，转换到另一种类型的结果。 下面的示例将检索 CatalogBrands，按名称排序、 其 Enabled 属性中，按筛选和投影到 SelectListItem 类型：

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

务必在上面的示例将添加到 ToListAsync 调用，以立即执行查询。 否则，该语句将分配 IQueryable<SelectListItem>到 brandItems，这将不会执行之前在枚举。 有优点和缺点到从方法返回 IQueryable 结果。 它允许 EF 核心将构造以进行进一步的修改，但也可以仅在运行时，发生的错误导致，如果将操作添加到 EF 核心无法转换的查询的查询。 它是通常更安全地将任何筛选器传递给执行数据访问方法和回到内存中的集合 (例如，列出<T>) 作为结果。

EF 核心跟踪会从持久性获取的实体上的更改。 若要将更改保存到被跟踪实体，你只需调用 SaveChanges 方法 DbContext，确保它相同的 DbContext 实例用于提取该实体。 添加和删除实体是直接在相应 DbSet 的属性，再次使用 SaveChanges 的调用来执行数据库命令。 下面的示例演示添加、 更新和删除实体从永久性存储。

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

EF 核心支持同步和异步方法提取并保存。 在 web 应用程序具有建议使用异步/等待模式和异步方法，以便在等待数据访问操作完成时，不会阻止 web 服务器线程。

### <a name="fetching-related-data"></a>提取相关的数据

当 EF 核心检索实体时，它将填充所有存储直接与数据库中该实体的属性。 导航属性，例如相关实体的列表不会，因此可能具有其值设置为 null。 这可确保 EF 核心不提取更多的数据多于所需，这是特别重要的 web 应用程序，必须快速处理请求并有效地返回响应。 若要包含与实体使用关系*预先加载*，你指定基于该查询，使用包含扩展方法的属性，如所示：

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

您可以包含多个关系，并且您还可以包含子关系使用 ThenInclude。 EF 核心将执行单个查询检索生成的实体集。

用于加载相关的数据的另一个选项是使用*显式加载*。 可以使用显式加载其他数据加载到已检索的实体。 由于这涉及到数据库的单独请求，因此不建议对于 web 应用程序，应尽量减少的数据库数进行每个请求的往返。

*延迟加载*是一种功能，因为它被引用应用程序将自动加载相关的数据。 它目前不支持通过 EF 核心，但作为显式加载应通常为禁用该 web 应用程序。

### <a name="resilient-connections"></a>可恢复的连接

外部资源，就像 SQL 数据库有时可能不可用。 中的暂时不可用的情况下，应用程序可以使用重试逻辑来避免引发异常。 此方法通常称为*连接复原*。 你可以实现你[自己重试使用指数退让](https://docs.microsoft.com/azure/architecture/patterns/retry)通过尝试到使用按指数增长的等待时间，重试，直到已达到最大重试计数的技术。 此方法包含这样一个事实，云资源间歇性可能不可用的时间，从而导致失败的某些请求的短时间。

对于 Azure SQL DB，实体框架核心已经提供了内部数据库连接复原和重试逻辑。 但你需要启用每个 DbContext 连接的实体框架执行策略，如果你想要具有可恢复的 EF 核心连接。

例如，下面的代码位于 EF 核心连接级别启用可恢复将重试，如果连接失败的 SQL 连接。

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

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>执行策略和使用 BeginTransaction 和多个 Dbcontext 的显式事务 
  
  当在 EF 核心连接中启用了重试时，使用 EF 核心执行每个操作将成为其自己的可重试操作。 每个查询和 SaveChanges 每次调用将重试作为一个单元如果发生暂时性故障。
  
  但是，如果你的代码启动事务使用 BeginTransaction，你要定义你自己的一组操作需要被视为一个单元 — 发生故障时，已回滚事务内的所有内容。 如果你尝试执行该事务时使用 EF 执行策略 （重试策略） 并将从多个 Dbcontext 的几个 SaveChanges 包括在它，你将看到如下所示的异常。

System.InvalidOperationException： 配置的执行策略 SqlServerRetryingExecutionStrategy 不支持用户启动事务。 使用 DbContext.Database.CreateExecutionStrategy() 返回的执行策略在作为可重试单元事务中执行所有操作。

解决方案是使用委托表示的所有内容，需要执行手动调用 EF 执行策略。 如果发生暂时性故障，则执行策略将再次调用委托。 下面的代码演示如何实现此方法：

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

第一个 DbContext 是\_DbContext catalogContext，第二位于\_integrationEventLogService 对象。 最后，的提交操作将被执行多个 Dbcontext，并使用 EF 执行策略。

> ### <a name="references--entity-framework-core"></a>引用 – 实体框架核心
> - **EF 核心文档**  
> <https://docs.microsoft.com/ef/>
> - **EF 核心： 相关的数据**  
> <https://docs.microsoft.com/ef/core/querying/related-data>
> - **避免在 ASPNET 应用程序中的延迟加载实体**  
> <http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a>EF 核心或微型 ORM？

虽然 EF 核心是一个不错的选择用于管理持久性，并在大多数情况下封装数据库从应用程序开发人员的详细信息，这不是唯一选择。 另一个受欢迎的开源方法是[Dapper](https://github.com/StackExchange/Dapper)，所谓的微型 ORM。 微型 ORM 是一种轻型，小于齐全将对象映射到数据结构的工具。 Dapper 时，对于目标主要性能，而不是完全封装基础查询该其设计用于检索和更新数据。 因为它不抽象 SQL 开发人员，Dapper"更接近于配置文件"，并允许开发人员编写准确查询他们想要用于给定的数据访问操作。

EF 核心具有两个重要的功能，它提供了它与 Dapper 隔开，但还将添加到其性能开销。 第一种是从 LINQ 表达式 SQL 转换的转换。 将缓存这些翻译，但即便如此开销中执行这些第一次。 第二个是 （以便可以生成高效的 update 语句），更改跟踪实体。 此行为可以关闭特定查询使用 AsNotTracking 扩展。 EF 核心还会生成通常是非常高效和在任何情况下完全可以从性能角度看，接受的 SQL 查询，但如果您需要精确地控制要执行精确查询，你可以在自定义 SQL 中传递 （或执行存储的过程） 使用 EF核心，太。 在这种情况下，Dapper 仍优于 EF 核心，但很小。 在她一些性能数据可能 2016 MSDN 文章 Julie Lerman 显示[Dapper、 实体框架和混合应用程序](https://msdn.microsoft.com/magazine/mt703432.aspx)。 上找不到各种不同的数据访问方法的其他性能基准数据[Dapper 站点](https://github.com/StackExchange/Dapper)。

若要查看如何从 EF 核心而变化 Dapper 的语法，请考虑用于检索的项列表的相同方法这两个版本：

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

如果你需要生成更复杂的对象图，使用 Dapper 时，你需要自己编写的关联的查询 （而不是添加 Include，就像在 EF 核心）。 通过各种语法，包括一种称为多映射，可将单独的行映射到多个映射对象通过该功能支持此功能。 例如，给定类型的类 Post 属性所有者与用户，以下 SQL 将返回所有必要的数据：

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

每个返回的行包含用户和 Post 数据。 因为用户数据应附加到其所有者属性通过 Post 数据，所以会使用以下函数：

```csharp
(post, user) => { post.Owner = user; return post; }
```

将返回的公告的集合，其中使用关联的用户数据进行填充其所有者属性的完整代码列表：

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

因为它提供更少封装，Dapper 要求开发人员知道有关其数据的存储方式的详细信息如何有效地，对其进行查询和写入更多代码以提取它。 在模型更改，而不是只需创建一个新的迁移 （另一个 EF 核心功能），和/或更新某一位置中，创建的 DbContext 的映射信息时必须更新会受到影响的每个查询。 这些查询具有未编译时间保证，因此它们可能会中断在运行时以响应更改的模型或数据库，使错误更难以进行快速检测到。 以这些利弊，交换 Dapper 提供极快的性能。

对于大多数应用程序和的几乎所有应用程序的大多数部件，EF 核心提供可接受的性能。 因此，其开发人员工作效率优势很可能超过其性能开销。 对于可以得益于缓存的查询，可能仅执行实际的查询的时间，使相对较小的小百分比查询性能差异没有任何意义。

## <a name="sql-or-nosql"></a>SQL 或 NoSQL

传统上，类似于 SQL Server 关系数据库具有持续取决于应用商店为永久性数据存储，但它们不是唯一可用的解决方案。 NoSQL 数据库喜欢[MongoDB](https://www.mongodb.com/what-is-mongodb)提供存储对象的不同方法。 而不是将对象映射到表和行，另一种方法是序列化整个对象图中，并将结果存储。 此方法的优点至少在开始，是简单和性能。 当然简单得比要分解成多个表关系对象的密钥存储的单个序列化的对象，并从数据库检索更新和自上一次对象可能已更改的行。 同样，提取和反序列化的基于密钥的存储区中的单个对象通常是更加快速、 轻松比复杂联接或完全撰写关系数据库中的相同对象所需的多个数据库查询。 缺少锁或事务或固定的架构也使得 NoSQL 数据库非常适用于许多机，支持大型数据集之间的伸缩。

另一方面，NoSQL 数据库 （如通常称为） 有其缺点。 关系数据库使用规范化来强制实施一致性并避免重复的数据。 这减少了数据库的总大小，并确保立即在整个数据库有对共享数据的更新。 在关系数据库中，地址表可能引用国家/地区表按 ID，这样，如果更改了国家/地区的名称，地址记录会带来好处更新而无需自己无需进行更新。 但是，在 NoSQL 数据库中，地址和其关联的国家/地区可能进行序列化多个存储对象的一部分。 国家/地区名称的更新需要将所有此类的对象，以更新，而不是单个行。 关系数据库还可通过强制执行规则如外键来确保关系的完整性。 NoSQL 数据库通常不提供此类约束对其数据。

另一个复杂性 NoSQL 数据库必须处理是版本控制。 当对象的属性更改时，它可能无法从存储的过去版本反序列化。 因此，必须更新已序列化的对象 （早期） 版本的所有现有对象，以符合其新的架构。 这不是从概念上讲不同于关系数据库，其中架构更改有时需要更新脚本或映射更新。 但是，必须修改的条目数通常是很多占用更多的 NoSQL 方法，因为没有数据的多个副本。

在 NoSQL 数据库来存储对象的多个版本中，也可以是固定的架构的关系数据库通常不支持。 但是，在这种情况下你的应用程序代码将需要帐户存在以前版本的对象，添加额外的复杂性。

NoSQL 数据库通常不会强制使用[ACID](http://en.wikipedia.org/wiki/ACID)，这意味着它们具有在关系数据库的性能和可扩展性优势。 它们非常适合极大型数据集并不是适合于规范化的表结构中的存储对象。 没有为什么单个应用程序不能充分利用这两者的关系和 NoSQL 数据库，使用每个最佳适合的理由。

## <a name="azure-documentdb"></a>Azure DocumentDB

Azure DocumentDB 是完全托管的 NoSQL 数据库服务提供基于云的无架构数据存储。 DocumentDB 为快速和可预测性能、 高可用性、 弹性缩放和全局通讯组生成。 尽管一种 NoSQL 数据库，开发人员可以使用 JSON 数据的丰富且熟悉 SQL 查询功能。 作为 JSON 文档存储在 DocumentDB 中的所有资源。 作为资源进行管理*项*，后者是包含元数据，文档和*馈送*，它们的项的集合。 图 8-2 显示不同的 DocumentDB 资源之间的关系。


![DocumentDB，NoSQL JSON 数据库中的资源之间的层次结构关系](./media/image8-2.png)

**图 8-2。** DocumentDB 资源组织。

DocumentDB 查询语言是用于查询 JSON 文档的简单但强大接口。 语言支持 ANSI SQL 语法的子集，并将添加的 JavaScript 对象、 数组、 对象构造和函数调用的深度集成。

**引用 – DocumentDB**

-   DocumentDB Introduction\
    <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a>其他持久性选项

在添加到关系和 NoSQL 存储选项中，ASP.NET Core 应用程序可以使用 Azure 存储空间将各种数据格式和文件存储在一种基于云的、 可缩放的方式。 Azure 存储是可大规模缩放，以便你可以启动出存储少量数据，并增加到存储数百或兆兆字节，如果你的应用程序需要它。 Azure 存储空间支持四种类型的数据：

-   非结构化的文本或二进制存储，也称为对象存储的 blob 存储。

-   结构化数据集，可通过行键访问的表存储。

-   可靠的基于队列的消息传送的队列存储。

-   Azure 虚拟机和本地应用程序之间共享的文件访问的文件存储。

**引用 – Azure 存储空间**

-   Azure 存储 Introduction\
    <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a>缓存

在 web 应用程序，应在尽可能最短时间内完成每个 web 请求。 一种方法来实现此目的是限制的服务器必须做出无法完成请求的外部调用数。 缓存与服务器上存储数据的副本 （或另一个数据存储，它是与数据源轻松查询的详细信息）。 Web 应用程序和特别是非 SPA 传统 web 应用程序，需要生成与每个请求的整个用户界面。 这通常涉及到进行很多相同数据库的查询从一个用户请求重复到下一步。 在大多数情况下，此数据很少更改使有很少需要不断地从数据库中请求它。 ASP.NET 核心支持响应缓存，用于缓存整个页面和数据缓存，支持更精细的缓存行为。

在实施缓存时，务必将保留在考虑分离问题。 避免在数据访问逻辑，或你的用户界面中实现缓存逻辑。 相反，封装在其自己的类中，缓存并使用配置来管理其行为。 这打开/关闭和单独责任原则，并将使你更轻松地管理你如何使用它随着你的应用程序中的缓存。

### <a name="aspnet-core-response-caching"></a>ASP.NET 核心响应缓存

ASP.NET 核心支持两个级别的响应缓存。 第一个级别不会在服务器上，任何内容进行缓存，但将指示客户端和代理服务器缓存响应的 HTTP 标头添加。 这是通过将 ResponseCache 属性添加到单个控制器或操作实现：

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

响应缓存中间件将自动缓存响应基于一组条件，可以自定义的条件。 默认情况下，通过 GET 或 HEAD 方法请求的仅 200 （正常） 响应进行缓存。 此外，请求必须具有与缓存控件的响应： 公共标头，并且不能包括授权或集 Cookie 标头。 请参阅[由缓存中间件的响应的缓存条件的完整列表](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching)。

### <a name="data-caching"></a>数据缓存

而不是 （或除了） 缓存完整的 web 响应，你可以缓存单个数据查询的结果。 为此，你可以使用在内存缓存中，在 web 服务器上，或使用[分布式的缓存](https://docs.microsoft.com/aspnet/core/performance/caching/distributed)。 本部分将演示如何实现在内存中缓存。

添加对内存的支持 （或分布式） 在缓存中 ConfigureServices:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

请务必添加 Microsoft.Extensions.Caching.Memory NuGet 包以及。

一旦你已添加该服务，你请求 IMemoryCache 通过依赖关系注入只要你需要访问缓存。 在此示例中，CachedCatalogService 使用代理服务器 （或修饰器） 设计模式中，通过提供 ICatalogService 用于控制对的访问 （或添加到行为） 的其他实现的基础 CatalogService 实现。

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

若要配置应用程序以使用缓存的版本的服务，但仍允许服务来获取的 CatalogService 它需要在其构造函数中的实例，则要 ConfigureServices 中添加以下：

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

与此就地，数据库调用提取目录数据，则只会发出一次每分钟，而不是对每个请求。 具体取决于发送到网站的流量，这会对数据库和当前依赖于此服务公开的查询的所有三个主页上的平均页面加载时间对执行的查询数的有非常显著的影响。

当缓存实现时，出现一个问题是*过时的数据*– 也就是说，在源但过期的版本已更改的数据保留在缓存。 若要缓解此问题，一种简单的方法是使用小缓存持续时间，因为对于繁忙的应用程序没有将扩展缓存数据的长度限制另一个好处。 例如，考虑一个页，使单次数据库查询，并每秒 10 倍的请求。 如果此页为一分钟缓存，则将导致每分钟进行从 600 降为 1，99.8%的减少的数据库查询数。 如果改为将缓存持续时间进行了一小时，全面降低将 99.997%，但现在的过时数据的可能性和潜在期限同时增加了更显著。

另一种方法是主动更新所包含的数据时删除缓存项。 如果知道其密钥，则可以删除任何单个条目。

```csharp
_cache.Remove(cacheKey);
```

如果你的应用程序公开更新其缓存的项的功能，则可以在执行更新代码中删除对应的缓存条目。 有时可能有许多依赖于一组特定的数据的不同项。 在这种情况下，它可用于创建缓存项，通过使用 CancellationChangeToken 之间的依赖关系。 与 CancellationChangeToken，可以通过取消令牌同时终止多个缓存条目。

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
[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)
