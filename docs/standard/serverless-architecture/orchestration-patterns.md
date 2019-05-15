---
title: 业务流程模式-无服务器应用
description: Azure Durable functions 拉取请求
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 18e13c5355490ef4a019ceda459114bdb6bfd539
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638810"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="65a4b-103">业务流程模式</span><span class="sxs-lookup"><span data-stu-id="65a4b-103">Orchestration patterns</span></span>

<span data-ttu-id="65a4b-104">Durable Functions，可以更轻松地创建有状态工作流的无服务器环境中的离散、 长时间运行的活动组成。</span><span class="sxs-lookup"><span data-stu-id="65a4b-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="65a4b-105">Durable Functions 可以跟踪的工作流和定期检查点的进度的执行历史记录，因为它有助于实现一些有趣的模式。</span><span class="sxs-lookup"><span data-stu-id="65a4b-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="65a4b-106">函数链</span><span class="sxs-lookup"><span data-stu-id="65a4b-106">Function chaining</span></span>

<span data-ttu-id="65a4b-107">在典型的顺序过程中，需要执行一个接一个按特定顺序活动。</span><span class="sxs-lookup"><span data-stu-id="65a4b-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="65a4b-108">（可选） 接下来的活动可能需要一些来自上一个函数。</span><span class="sxs-lookup"><span data-stu-id="65a4b-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="65a4b-109">此依赖项上的活动顺序创建执行的函数链。</span><span class="sxs-lookup"><span data-stu-id="65a4b-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="65a4b-110">使用 Durable Functions 来实现此工作流模式的优点来自于其能够执行检查点。</span><span class="sxs-lookup"><span data-stu-id="65a4b-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="65a4b-111">如果服务器发生故障，网络超时或出现一些其他问题，Durable functions 可以从最后一个已知状态恢复并继续运行工作流，即使它位于另一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="65a4b-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="65a4b-112">在前面的代码示例中，`CallActivityAsync`函数负责数据中心中的虚拟机上运行给定的活动。</span><span class="sxs-lookup"><span data-stu-id="65a4b-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="65a4b-113">Await 返回，并且基础任务完成后，执行将记录到历史记录表中。</span><span class="sxs-lookup"><span data-stu-id="65a4b-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="65a4b-114">使业务流程协调程序函数中的代码可以使用所有熟悉的构造的任务并行库和 async/await 关键字。</span><span class="sxs-lookup"><span data-stu-id="65a4b-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="65a4b-115">下面的代码是什么的简化的示例`ProcessPayment`方法可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="65a4b-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="65a4b-116">异步 HTTP Api</span><span class="sxs-lookup"><span data-stu-id="65a4b-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="65a4b-117">在某些情况下，工作流可能包含需要相当长一段时间才能完成的活动。</span><span class="sxs-lookup"><span data-stu-id="65a4b-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="65a4b-118">假设进程中用于启动媒体的备份到 blob 存储的文件。</span><span class="sxs-lookup"><span data-stu-id="65a4b-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="65a4b-119">根据大小和数量的媒体文件，此备份过程可能需要数小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="65a4b-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="65a4b-120">在此方案中，`DurableOrchestrationClient`的能够检查正在运行的工作流的状态将会很有用。</span><span class="sxs-lookup"><span data-stu-id="65a4b-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="65a4b-121">使用时`HttpTrigger`以启动工作流`CreateCheckStatusResponse`方法可用于返回的一个实例`HttpResponseMessage`。</span><span class="sxs-lookup"><span data-stu-id="65a4b-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="65a4b-122">可用于检查正在运行的进程的状态的有效负载中的 URI 为客户端提供此响应。</span><span class="sxs-lookup"><span data-stu-id="65a4b-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="65a4b-123">下面的示例结果显示了响应有效负载的结构。</span><span class="sxs-lookup"><span data-stu-id="65a4b-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="65a4b-124">使用您首选的 HTTP 客户端，GET 请求可以对 statusQueryGetUri 中的 URI 来检查正在运行的工作流的状态。</span><span class="sxs-lookup"><span data-stu-id="65a4b-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="65a4b-125">返回的状态响应应类似于下面的代码。</span><span class="sxs-lookup"><span data-stu-id="65a4b-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="65a4b-126">此过程将继续，因为状态响应将更改为**失败**或**Completed**。</span><span class="sxs-lookup"><span data-stu-id="65a4b-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="65a4b-127">成功完成后，**输出**有效负载中的属性将包含任何返回的数据。</span><span class="sxs-lookup"><span data-stu-id="65a4b-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="65a4b-128">监视</span><span class="sxs-lookup"><span data-stu-id="65a4b-128">Monitoring</span></span>

<span data-ttu-id="65a4b-129">Azure Functions 提供的简单定期任务`TimerTrigger`可以基于 CRON 表达式计划的。</span><span class="sxs-lookup"><span data-stu-id="65a4b-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="65a4b-130">计时器非常适用于简单的生存期较短的任务，但可能需要更灵活的计划的位置的方案。</span><span class="sxs-lookup"><span data-stu-id="65a4b-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="65a4b-131">当监视模式和 Durable Functions 可帮助时，此方案。</span><span class="sxs-lookup"><span data-stu-id="65a4b-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="65a4b-132">Durable Functions，灵活的计划间隔、 生存期管理和创建从单个业务流程函数的多个监视器进程。</span><span class="sxs-lookup"><span data-stu-id="65a4b-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="65a4b-133">此功能的一个用例可能创建满足特定的阈值，完成的股票价格更改的观察程序。</span><span class="sxs-lookup"><span data-stu-id="65a4b-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="65a4b-134">`DurableOrchestrationContext``CreateTimer`方法设置的计划循环的下一个调用以检查股票价格更改。</span><span class="sxs-lookup"><span data-stu-id="65a4b-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="65a4b-135">`DurableOrchestrationContext` 此外具有`CurrentUtcDateTime`属性在 UTC 中获取当前日期时间值。</span><span class="sxs-lookup"><span data-stu-id="65a4b-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="65a4b-136">最好使用此属性，而不是`DateTime.UtcNow`因为它采用不易模拟用于测试。</span><span class="sxs-lookup"><span data-stu-id="65a4b-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="65a4b-137">推荐的资源</span><span class="sxs-lookup"><span data-stu-id="65a4b-137">Recommended resources</span></span>

* [<span data-ttu-id="65a4b-138">Azure Durable 函数</span><span class="sxs-lookup"><span data-stu-id="65a4b-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="65a4b-139">.NET Core 和 .NET Standard 中的单元测试</span><span class="sxs-lookup"><span data-stu-id="65a4b-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="65a4b-140">[上一页](durable-azure-functions.md)
>[下一页](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="65a4b-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
