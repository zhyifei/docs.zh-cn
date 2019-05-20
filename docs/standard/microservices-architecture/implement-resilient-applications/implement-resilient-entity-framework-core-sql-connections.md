---
title: 实现复原 Entity Framework Core SQL 连接
description: 了解如何实现复原 Entity Framework Core SQL 连接。 在云中使用 Azure SQL 数据库时，此技术尤为重要。
ms.date: 10/16/2018
ms.openlocfilehash: 3bf5c1827cee1da69aeccdc9f15573c301fc9363
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639897"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="768be-104">实现复原 Entity Framework Core SQL 连接</span><span class="sxs-lookup"><span data-stu-id="768be-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="768be-105">对于 Azure SQL DB，Entity Framework Core (EF) 早已提供了内部数据库连接复原和重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="768be-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="768be-106">但如果想要[复原 EF Core 连接](/ef/core/miscellaneous/connection-resiliency)，则需要为每个 <xref:Microsoft.EntityFrameworkCore.DbContext> 连接启用 Entity Framework 执行策略。</span><span class="sxs-lookup"><span data-stu-id="768be-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="768be-107">例如，EF Core 连接级别的下列代码可启用复原 SQL 连接，此连接在连接失败时会重试。</span><span class="sxs-lookup"><span data-stu-id="768be-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="768be-108">使用 BeginTransaction 和多个 DbContext 的执行策略和显式事务</span><span class="sxs-lookup"><span data-stu-id="768be-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="768be-109">在 EF Core 连接中启用重试时，使用 EF Core 执行的每项操作都会成为其自己的可重试操作。</span><span class="sxs-lookup"><span data-stu-id="768be-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="768be-110">如果发生暂时性故障，每个查询和 `SaveChanges` 的每次调用都会作为一个单元进行重试。</span><span class="sxs-lookup"><span data-stu-id="768be-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="768be-111">但是，如果你的代码使用 `BeginTransaction` 启动事务，则自行定义一组需要作为一个单元来处理的操作。</span><span class="sxs-lookup"><span data-stu-id="768be-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="768be-112">如果发生故障，则必须回滚事务中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="768be-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="768be-113">如果在使用 EF 执行策略（重试策略）时尝试执行该事务，并从多个 DbContext 调用 `SaveChanges`，则会收到与下列情况类似的异常：</span><span class="sxs-lookup"><span data-stu-id="768be-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="768be-114">System.InvalidOperationException：已配置的执行策略“SqlServerRetryingExecutionStrategy”不支持用户启动的事务。</span><span class="sxs-lookup"><span data-stu-id="768be-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="768be-115">使用由“DbContext.Database.CreateExecutionStrategy()”返回的执行策略执行事务（作为一个可回溯单元）中的所有操作。</span><span class="sxs-lookup"><span data-stu-id="768be-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="768be-116">该解决方案通过代表所有需要执行的委托来手动调用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="768be-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="768be-117">如果发生暂时性故障，执行策略会再次调用委托。</span><span class="sxs-lookup"><span data-stu-id="768be-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="768be-118">例如，以下代码演示了在更新产品时，如何使用两个 DbContext（\_ catalogContext 和 IntegrationEventLogContext）在 eShopOnContainers 中实现该操作，然后保存需要使用不同 DbContext 的 ProductPriceChangedIntegrationEvent 对象。</span><span class="sxs-lookup"><span data-stu-id="768be-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

<span data-ttu-id="768be-119">第一个 <xref:Microsoft.EntityFrameworkCore.DbContext> 是 `_catalogContext`，第二个 `DbContext` 在 `_integrationEventLogService` 对象中。</span><span class="sxs-lookup"><span data-stu-id="768be-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_integrationEventLogService` object.</span></span> <span data-ttu-id="768be-120">通过使用 EF 执行策略在所有 `DbContext` 对象之间执行“提交”操作。</span><span class="sxs-lookup"><span data-stu-id="768be-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="768be-121">若要实现此多个 `DbContext` 提交，`SaveEventAndCatalogContextChangesAsync` 要使用 `ResilientTransaction` 类，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="768be-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database 
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

<span data-ttu-id="768be-122">基本上，`ResilientTransaction.ExecuteAsync` 方法从传递的 `DbContext` (`_catalogContext`) 开始一个事务，然后让 `EventLogService` 使用该事务保存来自 `IntegrationEventLogContext` 的更改，然后提交整个事务。</span><span class="sxs-lookup"><span data-stu-id="768be-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts 
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="768be-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="768be-123">Additional resources</span></span>

- <span data-ttu-id="768be-124">**ASP.NET MVC 应用程序中的 EF 的连接复原和命令截获** \\</span><span class="sxs-lookup"><span data-stu-id="768be-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** \\</span></span>
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="768be-125">**Cesar de la Torre。使用复原 Entity Framework Core SQL 连接和事务** \\</span><span class="sxs-lookup"><span data-stu-id="768be-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** \\</span></span>
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="768be-126">[上一页](implement-retries-exponential-backoff.md)
>[下一页](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="768be-126">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>
