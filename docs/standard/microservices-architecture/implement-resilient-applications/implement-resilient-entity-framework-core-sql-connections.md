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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>实现弹性 Entity Framework 核心 SQL 连接

对于 Azure SQL DB，实体框架核心已经提供了内部数据库连接复原和重试逻辑。 但需要启用每个 DbContext 连接的实体框架执行策略，如果你想要[可恢复的 EF 核心连接](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)。

例如，下面的代码位于 EF 核心连接级别启用可恢复将重试，如果连接失败的 SQL 连接。

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>执行策略和使用 BeginTransaction 和多个 Dbcontext 的显式事务

当在 EF 核心连接中启用了重试时，使用 EF 核心执行每个操作将成为其自己的可重试操作。 每个查询和 SaveChanges 每次调用将重试作为一个单元如果发生暂时性故障。

但是，如果你的代码启动事务使用 BeginTransaction，你要定义你自己的一组操作需要被视为一个单元 — 发生故障时，已回滚事务内的所有内容。 如果你尝试执行该事务时使用 EF 执行策略 （重试策略） 并将从多个 Dbcontext 的多个 SaveChanges 调用包含在事务中，你将看到如下所示的异常。

> System.InvalidOperationException： 配置的执行策略 SqlServerRetryingExecutionStrategy 不支持用户启动事务。 使用 DbContext.Database.CreateExecutionStrategy() 返回的执行策略在作为可重试单元事务中执行所有操作。

解决方案是使用委托表示的所有内容，需要执行手动调用 EF 执行策略。 如果发生暂时性故障，则执行策略将再次调用委托。 例如，下面的代码显示如何在使用两个 eShopOnContainers 中实现多个 Dbcontext (\_catalogContext 和 IntegrationEventLogContext) 更新的产品，然后保存时ProductPriceChangedIntegrationEvent 对象，需要使用不同的 DbContext。

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

第一个 DbContext 是\_DbContext catalogContext，第二位于\_integrationEventLogService 对象。 跨多个 Dbcontext 使用 EF 执行策略执行提交操作。

## <a name="additional-resources"></a>其他资源

-   **连接复原和与实体框架的命令截获**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre。使用弹性实体框架核心 Sql 连接和事务**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[以前](实现-重试-指数-backoff.md) [下一步] (implement-custom-http-call-retries-exponential-backoff.md)
