---
title: 实现复原 Entity Framework Core SQL 连接
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现复原 Entity Framework Core SQL 连接
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 79f115a2d897463c213eda6f4d6951ff0cbeb3ca
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105470"
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>实现复原 Entity Framework Core SQL 连接

对于 Azure SQL DB，Entity Framework Core 早已提供了内部数据库连接复原和重试逻辑。 但如果想要[复原 EF Core 连接](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)，则需要为每个 DbContext 连接启用 Entity Framework 执行策略。

例如，EF Core 连接级别的下列代码可启用复原 SQL 连接，此连接在连接失败时会重试。

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>使用 BeginTransaction 和多个 DbContext 的执行策略和显式事务

在 EF Core 连接中启用重试时，使用 EF Core 执行的每项操作都会成为其自己的可重试操作。 如果发生暂时性故障，每个查询和 SaveChanges 的每次调用都会作为一个单元进行重试。

但是，如果代码使用 BeginTransaction 启动事务，这表示在定义一组自己的操作，这些操作需要被视为一个单元 - 如果发生故障，事务内的所有内容都会回退。 如果在使用 EF 执行策略（重试策略）时尝试执行该事务，并且事务中包含一些来自多个 DbContext 的 SaveChanges 调用，则会看到与下列情况类似的异常。

> System.InvalidOperationException：已配置的执行策略“SqlServerRetryingExecutionStrategy”不支持用户启动的事务。 使用由“DbContext.Database.CreateExecutionStrategy()”返回的执行策略执行事务（作为一个可回溯单元）中的所有操作。

该解决方案通过代表所有需要执行的委托来手动调用 EF 执行策略。 如果发生暂时性故障，执行策略会再次调用委托。 例如，以下代码演示了在更新产品时，如何使用两个 DbContext (\_ catalogContext 和 IntegrationEventLogContext) 在 eShopOnContainers 中实现该操作，然后保存需要使用不同 DbContext 的 ProductPriceChangedIntegrationEvent 对象。

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

第一个 DbContext 是 \_catalogContext，第二个 DbContext 位于 \_ integrationEventLogService 对象内。 通过使用 EF 执行策略在多个 DbContext 之间执行“提交”操作。

## <a name="additional-resources"></a>其他资源

-   **通过 Entity Framework 连接复原和命令截获**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre。使用复原 Entity Framework Core SQL 连接和事务**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[上一页](implement-retries-exponential-backoff.md)
[下一页](implement-custom-http-call-retries-exponential-backoff.md)
