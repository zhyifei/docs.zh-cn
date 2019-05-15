---
title: 持久的 Azure 函数-无服务器应用
description: 持久的 Azure 函数来扩展 Azure Functions 运行时，若要启用在代码中的有状态工作流。
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: f7ee74926d6658042120113b49dc763383881423
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643406"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="417be-103">持久 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="417be-103">Durable Azure functions</span></span>

<span data-ttu-id="417be-104">当使用 Azure Functions 创建无服务器应用程序，您的操作将通常设计为无状态方式运行。</span><span class="sxs-lookup"><span data-stu-id="417be-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="417be-105">选择此设计的原因是因为作为平台的刻度，则很难知道哪些服务器运行代码。</span><span class="sxs-lookup"><span data-stu-id="417be-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="417be-106">它还就会难以确定多少个实例处于活动状态，在任意给定时间。</span><span class="sxs-lookup"><span data-stu-id="417be-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="417be-107">但是，有需要为已知的进程的当前状态的应用程序的类。</span><span class="sxs-lookup"><span data-stu-id="417be-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="417be-108">请考虑提交到在线商店订单的过程。</span><span class="sxs-lookup"><span data-stu-id="417be-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="417be-109">签出操作可能是由多个操作，需要了解该过程的状态的工作流。</span><span class="sxs-lookup"><span data-stu-id="417be-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="417be-110">此类信息可能包括产品库存中，如果客户具有自己的帐户，以及处理信用卡的结果的任何信用额度。</span><span class="sxs-lookup"><span data-stu-id="417be-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="417be-111">这些操作轻松可能是其自己的内部工作流或甚至从第三方系统服务。</span><span class="sxs-lookup"><span data-stu-id="417be-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="417be-112">各种模式目前存在该帮助进行协调的内部和外部系统之间的应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="417be-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="417be-113">它是通常会遇到依赖于集中式队列系统、 分布式的键-值存储或共享的数据库来管理该状态的解决方案。</span><span class="sxs-lookup"><span data-stu-id="417be-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="417be-114">但是，它们现在需要进行预配和管理的所有其他资源。</span><span class="sxs-lookup"><span data-stu-id="417be-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="417be-115">在无服务器环境中，你的代码会非常麻烦尝试手动协调这些资源。</span><span class="sxs-lookup"><span data-stu-id="417be-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="417be-116">Azure Functions 提供了用于创建调用 Durable Functions 的有状态函数的替代。</span><span class="sxs-lookup"><span data-stu-id="417be-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="417be-117">Durable Functions 是 Azure Functions 运行时，使您能够在代码中的有状态工作流定义的扩展。</span><span class="sxs-lookup"><span data-stu-id="417be-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="417be-118">通过将分解到活动的工作流，Durable Functions 扩展可管理状态、 创建进度检查点和跨服务器处理的函数调用的分布。</span><span class="sxs-lookup"><span data-stu-id="417be-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="417be-119">在后台，它使的 Azure 存储帐户中用于保存执行历史记录、 计划活动函数和检索响应。</span><span class="sxs-lookup"><span data-stu-id="417be-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="417be-120">在无服务器代码应永远不会与保持在该存储帐户中的信息和交互并通常不是开发人员需要与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="417be-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="417be-121">触发有状态工作流</span><span class="sxs-lookup"><span data-stu-id="417be-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="417be-122">Durable Functions 中的有状态工作流可以分解为两个内部组件;业务流程和活动触发器。</span><span class="sxs-lookup"><span data-stu-id="417be-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="417be-123">触发器和绑定是使用 Azure functions，使无服务器函数开始，接收输入，并返回结果时要通知的核心组件。</span><span class="sxs-lookup"><span data-stu-id="417be-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="417be-124">使用业务流程客户端</span><span class="sxs-lookup"><span data-stu-id="417be-124">Working with the Orchestration client</span></span>

<span data-ttu-id="417be-125">业务流程是在 Azure Functions 中触发操作的其他样式进行比较时唯一的。</span><span class="sxs-lookup"><span data-stu-id="417be-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="417be-126">Durable Functions 可实现函数可能需要数小时甚至数天才能完成的执行。</span><span class="sxs-lookup"><span data-stu-id="417be-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="417be-127">与需要的应用，可以检查正在运行的业务流程的状态，提前终止，或者将外部事件的通知发送对提供该类型的行为。</span><span class="sxs-lookup"><span data-stu-id="417be-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="417be-128">对于这种情况下，Durable Functions 扩展提供了`DurableOrchestrationClient`，可与之交互的类对函数进行安排。</span><span class="sxs-lookup"><span data-stu-id="417be-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="417be-129">通过获取对业务流程客户端访问`OrchestrationClientAttribute`绑定。</span><span class="sxs-lookup"><span data-stu-id="417be-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="417be-130">通常情况下，应包括此属性与另一种触发器类型，如`HttpTrigger`或`ServiceBusTrigger`。</span><span class="sxs-lookup"><span data-stu-id="417be-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="417be-131">一旦源函数已被触发，业务流程客户端可以用于启动业务流程协调程序函数。</span><span class="sxs-lookup"><span data-stu-id="417be-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a><span data-ttu-id="417be-132">业务流程协调程序函数</span><span class="sxs-lookup"><span data-stu-id="417be-132">The orchestrator function</span></span>

<span data-ttu-id="417be-133">作为业务流程协调程序函数批注与 Azure Functions 将 OrchestrationTriggerAttribute 函数的函数。</span><span class="sxs-lookup"><span data-stu-id="417be-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="417be-134">它负责管理构成了在有状态工作流的各种活动。</span><span class="sxs-lookup"><span data-stu-id="417be-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="417be-135">业务流程协调程序函数不能使 OrchestrationTriggerAttribute 以外的绑定的使用。</span><span class="sxs-lookup"><span data-stu-id="417be-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="417be-136">此属性仅用于 DurableOrchestrationContext 的参数类型。</span><span class="sxs-lookup"><span data-stu-id="417be-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="417be-137">可以不使用任何其他输入，因为反序列化在函数签名中的输入不受支持。</span><span class="sxs-lookup"><span data-stu-id="417be-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="417be-138">若要获取有关提供的业务流程客户端，GetInput\<T\>必须使用方法。</span><span class="sxs-lookup"><span data-stu-id="417be-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="417be-139">此外，业务流程函数的返回类型必须为 void、 Task 或 JSON 可序列化值。</span><span class="sxs-lookup"><span data-stu-id="417be-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="417be-140">*为简便起见，已被错误处理代码省略，*</span><span class="sxs-lookup"><span data-stu-id="417be-140">*Error handling code has been left out for brevity*</span></span>

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

<span data-ttu-id="417be-141">业务流程的多个实例可以在同一时间是启动并正在运行。</span><span class="sxs-lookup"><span data-stu-id="417be-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="417be-142">调用`StartNewAsync`方法`DurableOrchestrationClient`启动业务流程的新实例。</span><span class="sxs-lookup"><span data-stu-id="417be-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="417be-143">该方法将返回`Task<string>`完成业务流程已启动时将完成。</span><span class="sxs-lookup"><span data-stu-id="417be-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="417be-144">类型的异常`TimeoutException`获取如果在 30 秒内启动该业务流程尚未引发。</span><span class="sxs-lookup"><span data-stu-id="417be-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="417be-145">已完成`Task<string>`从`StartNewAsync`应包含业务流程实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="417be-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="417be-146">可以使用此实例 ID 来调用该特定业务流程上的操作。</span><span class="sxs-lookup"><span data-stu-id="417be-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="417be-147">业务流程可查询状态或发送事件通知。</span><span class="sxs-lookup"><span data-stu-id="417be-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="417be-148">活动函数</span><span class="sxs-lookup"><span data-stu-id="417be-148">The activity functions</span></span>

<span data-ttu-id="417be-149">活动函数无非是获取组合在一起的业务流程函数来创建工作流中的离散操作。</span><span class="sxs-lookup"><span data-stu-id="417be-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="417be-150">下面是会执行大部分实际工作。</span><span class="sxs-lookup"><span data-stu-id="417be-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="417be-151">它们表示业务逻辑，长时间运行的进程和到更大的解决方案的填数游戏块。</span><span class="sxs-lookup"><span data-stu-id="417be-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="417be-152">`ActivityTriggerAttribute`用于进行批注类型的函数参数`DurableActivityContext`。</span><span class="sxs-lookup"><span data-stu-id="417be-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="417be-153">使用批注通知运行时函数旨在用作活动函数。</span><span class="sxs-lookup"><span data-stu-id="417be-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="417be-154">使用检索到活动函数的输入的值`GetInput<T>`方法的`DurableActivityContext`参数。</span><span class="sxs-lookup"><span data-stu-id="417be-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="417be-155">与业务流程函数相似，活动函数的返回类型必须为 void、 Task 或 JSON 可序列化值。</span><span class="sxs-lookup"><span data-stu-id="417be-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="417be-156">获取活动函数中引发的任何未处理的异常会获取向上发送到调用的业务流程协调程序函数，其中显示为`TaskFailedException`。</span><span class="sxs-lookup"><span data-stu-id="417be-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="417be-157">此时，可以捕获和记录在业务流程协调程序，该错误，该活动可以重试。</span><span class="sxs-lookup"><span data-stu-id="417be-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="417be-158">推荐的资源</span><span class="sxs-lookup"><span data-stu-id="417be-158">Recommended resources</span></span>

* [<span data-ttu-id="417be-159">Durable Functions</span><span class="sxs-lookup"><span data-stu-id="417be-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="417be-160">Durable Functions 的绑定</span><span class="sxs-lookup"><span data-stu-id="417be-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [<span data-ttu-id="417be-161">在 Durable Functions 中管理实例</span><span class="sxs-lookup"><span data-stu-id="417be-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="417be-162">[上一页](event-grid.md)
>[下一页](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="417be-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
