---
title: 业务流程模式-无服务器应用
description: Azure 持久性函数 pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522632"
---
# <a name="orchestration-patterns"></a>业务流程模式

Durable Functions 使你可以更轻松地创建由无服务器环境中的离散的、长时间运行的活动组成的有状态工作流。 由于 Durable Functions 可以跟踪工作流的进度并定期检查执行历史记录，因此它的作用就在于实现一些有趣的模式。

## <a name="function-chaining"></a>函数链接

在典型的顺序过程中，活动需要按特定顺序逐个执行。 或者，即将发生的活动可能需要以前函数的一些输出。 此依赖项对活动排序创建了一个执行函数链。

使用 Durable Functions 实现此工作流模式的好处在于它可以执行检查点操作。 如果服务器崩溃、网络超时或发生其他问题，则持久性函数可以从上一已知状态恢复，并继续运行工作流，即使它在另一台服务器上也是如此。

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

在上面的代码示例中，@no__t 0 函数负责在数据中心中的虚拟机上运行给定的活动。 当 await 返回并且基础任务完成时，执行将记录到历史记录表。 业务流程协调程序函数中的代码可以使用任何熟悉的任务并行库构造和 async/await 关键字。

下面的代码简单举例介绍了 `ProcessPayment` 方法：

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>异步 HTTP Api

在某些情况下，工作流可能包含需要较长时间才能完成的活动。 假设有一个进程，该进程将媒体文件备份到 blob 存储中。 根据媒体文件的大小和数量，此备份过程可能需要数小时才能完成。

在这种情况下，@no__t 0 的功能可以检查正在运行的工作流的状态，这会很有用。 使用 `HttpTrigger` 来启动工作流时，可以使用 @no__t 1 方法返回 @no__t 的实例。 此响应为客户端提供有效负载中的 URI，可用于检查正在运行的进程的状态。

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

下面的示例结果显示了响应负载的结构。

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

使用你的首选 HTTP 客户端，可以对 statusQueryGetUri 中的 URI 发出 GET 请求，以检查正在运行的工作流的状态。 返回的状态响应应类似于以下代码。

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

进程继续时，状态响应将更改为 "已**失败**" 或 "**已完成**"。 成功完成后，负载中的**输出**属性将包含任何返回的数据。

## <a name="monitoring"></a>监视

对于简单的定期任务，Azure Functions 提供可基于 CRON 表达式计划的 `TimerTrigger`。 计时器适用于简单、生存期较短的任务，但可能存在需要更灵活的计划的情况。 这种情况是监视模式和 Durable Functions 可帮助。

Durable Functions 允许灵活计划间隔、生存期管理和从单个业务流程函数创建多个监视器进程。 此功能的一个用例是为在满足特定阈值后完成的股票价格变化创建观察程序。

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

`DurableOrchestrationContext` `CreateTimer` 方法设置用于检查股票价格变化的下一次调用的计划。 @no__t，还具有 @no__t 1 属性，用于获取 UTC 格式的当前日期时间值。 最好使用此属性（而不是 `DateTime.UtcNow`），因为它很容易模拟进行测试。

## <a name="recommended-resources"></a>推荐的资源

- [Azure Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [.NET Core 和 .NET Standard 中的单元测试](../../core/testing/index.md)

>[!div class="step-by-step"]
>[上一页](durable-azure-functions.md)
>[下一页](serverless-business-scenarios.md)
