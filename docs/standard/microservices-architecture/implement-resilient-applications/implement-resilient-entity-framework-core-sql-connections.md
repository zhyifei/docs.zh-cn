---
title: "实现弹性 Entity Framework 核心 SQL 连接"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现弹性 Entity Framework 核心 SQL 连接"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="532ab-104">实现弹性 Entity Framework 核心 SQL 连接</span><span class="sxs-lookup"><span data-stu-id="532ab-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="532ab-105">对于 Azure SQL DB，实体框架核心已经提供了内部数据库连接复原和重试逻辑。</span><span class="sxs-lookup"><span data-stu-id="532ab-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="532ab-106">但需要启用每个 DbContext 连接的实体框架执行策略，如果你想要[可恢复的 EF 核心连接](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)。</span><span class="sxs-lookup"><span data-stu-id="532ab-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="532ab-107">例如，下面的代码位于 EF 核心连接级别启用可恢复将重试，如果连接失败的 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="532ab-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
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
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="532ab-108">执行策略和使用 BeginTransaction 和多个 Dbcontext 的显式事务</span><span class="sxs-lookup"><span data-stu-id="532ab-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="532ab-109">当在 EF 核心连接中启用了重试时，使用 EF 核心执行每个操作将成为其自己的可重试操作。</span><span class="sxs-lookup"><span data-stu-id="532ab-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="532ab-110">每个查询和 SaveChanges 每次调用将重试作为一个单元如果发生暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="532ab-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="532ab-111">但是，如果你的代码启动事务使用 BeginTransaction，你要定义你自己的一组操作需要被视为一个单元 — 发生故障时，已回滚事务内的所有内容。</span><span class="sxs-lookup"><span data-stu-id="532ab-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="532ab-112">如果你尝试执行该事务时使用 EF 执行策略 （重试策略） 并将从多个 Dbcontext 的多个 SaveChanges 调用包含在事务中，你将看到如下所示的异常。</span><span class="sxs-lookup"><span data-stu-id="532ab-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="532ab-113">System.InvalidOperationException： 配置的执行策略 SqlServerRetryingExecutionStrategy 不支持用户启动事务。</span><span class="sxs-lookup"><span data-stu-id="532ab-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="532ab-114">使用 DbContext.Database.CreateExecutionStrategy() 返回的执行策略在作为可重试单元事务中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="532ab-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="532ab-115">解决方案是使用委托表示的所有内容，需要执行手动调用 EF 执行策略。</span><span class="sxs-lookup"><span data-stu-id="532ab-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="532ab-116">如果发生暂时性故障，则执行策略将再次调用委托。</span><span class="sxs-lookup"><span data-stu-id="532ab-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="532ab-117">例如，下面的代码显示如何在使用两个 eShopOnContainers 中实现多个 Dbcontext (\_catalogContext 和 IntegrationEventLogContext) 更新的产品，然后保存时ProductPriceChangedIntegrationEvent 对象，需要使用不同的 DbContext。</span><span class="sxs-lookup"><span data-stu-id="532ab-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

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
}
```

<span data-ttu-id="532ab-118">第一个 DbContext 是\_DbContext catalogContext，第二位于\_integrationEventLogService 对象。</span><span class="sxs-lookup"><span data-stu-id="532ab-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="532ab-119">跨多个 Dbcontext 使用 EF 执行策略执行提交操作。</span><span class="sxs-lookup"><span data-stu-id="532ab-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="532ab-120">其他资源</span><span class="sxs-lookup"><span data-stu-id="532ab-120">Additional resources</span></span>

-   <span data-ttu-id="532ab-121">**连接复原和与实体框架的命令截获**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="532ab-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="532ab-122">**Cesar de la Torre。使用弹性实体框架核心 Sql 连接和事务**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="532ab-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="532ab-123">[以前](实现-重试-指数-backoff.md) [下一步] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="532ab-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
