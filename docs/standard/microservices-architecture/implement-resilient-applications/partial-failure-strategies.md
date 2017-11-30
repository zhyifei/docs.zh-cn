---
title: "用于处理部分失败的策略"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |用于处理部分失败的策略"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ff3bed530b13a9b1822c7cccf5a4d47df6fc6239
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="strategies-for-handling-partial-failure"></a><span data-ttu-id="6c6d5-104">用于处理部分失败的策略</span><span class="sxs-lookup"><span data-stu-id="6c6d5-104">Strategies for handling partial failure</span></span>

<span data-ttu-id="6c6d5-105">用于处理部分失败的策略包括以下内容。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-105">Strategies for dealing with partial failures include the following.</span></span>

<span data-ttu-id="6c6d5-106">**在内部微服务使用异步通信 （例如，基于消息的通信）**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-106">**Use asynchronous communication (for example, message-based communication) across internal microservices**.</span></span> <span data-ttu-id="6c6d5-107">高，最好是不跨内部微服务创建的同步的 HTTP 调用的长链，因为该正确设计最终将变得不正确的服务中断的主要原因。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-107">It is highly advisable not to create long chains of synchronous HTTP calls across the internal microservices because that incorrect design will eventually become the main cause of bad outages.</span></span> <span data-ttu-id="6c6d5-108">相反，除客户端应用程序和微服务或细化 API 网关的第一个级别之间的前端通信，建议使用仅异步 （基于消息的） 通信一次之后的初始请求 /响应周期，跨内部微服务。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-108">On the contrary, except for the front-end communications between the client applications and the first level of microservices or fine-grained API Gateways, it is recommended to use only asynchronous (message-based) communication once past the initial request/response cycle, across the internal microservices.</span></span> <span data-ttu-id="6c6d5-109">最终一致性和事件驱动的体系结构将有助于最大程度减少 ripple 效果。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-109">Eventual consistency and event-driven architectures will help to minimize ripple effects.</span></span> <span data-ttu-id="6c6d5-110">这些方法强制 microservice 自治的更高级别，并因此防止在此记录的问题。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-110">These approaches enforce a higher level of microservice autonomy and therefore prevent against the problem noted here.</span></span>

<span data-ttu-id="6c6d5-111">**重试使用指数退让**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-111">**Use retries with exponential backoff**.</span></span> <span data-ttu-id="6c6d5-112">这种技术有助于避免短并会通过执行调用出现间歇性故障重试一定次数的以防该服务未仅可用于在短时间。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-112">This technique helps to avoid short and intermittent failures by performing call retries a certain number of times, in case the service was not available only for a short time.</span></span> <span data-ttu-id="6c6d5-113">这可能是由于间歇性网络问题或在 microservice/容器移动到群集中的不同节点时。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-113">This might occur due to intermittent network issues or when a microservice/container is moved to a different node in a cluster.</span></span> <span data-ttu-id="6c6d5-114">但是，如果这些重试不正确设计使用断路器，它可以担负 ripple 影响，甚至最终导致[拒绝服务 (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-114">However, if these retries are not designed properly with circuit breakers, it can aggravate the ripple effects, ultimately even causing a [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).</span></span>

<span data-ttu-id="6c6d5-115">**解决网络超时**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-115">**Work around network timeouts**.</span></span> <span data-ttu-id="6c6d5-116">通常情况下，不无限期阻止并等待响应时始终使用超时，则应设计客户端。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-116">In general, clients should be designed not to block indefinitely and to always use timeouts when waiting for a response.</span></span> <span data-ttu-id="6c6d5-117">使用超时可确保永远不会无限期地占用资源。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-117">Using timeouts ensures that resources are never tied up indefinitely.</span></span>

<span data-ttu-id="6c6d5-118">**使用断路器模式**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-118">**Use the Circuit Breaker pattern**.</span></span> <span data-ttu-id="6c6d5-119">在此方法中，客户端进程跟踪失败请求数。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-119">In this approach, the client process tracks the number of failed requests.</span></span> <span data-ttu-id="6c6d5-120">如果错误率超出配置的限制，"断路器"行程，以便进一步尝试立即失败。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-120">If the error rate exceeds a configured limit, a “circuit breaker” trips so that further attempts fail immediately.</span></span> <span data-ttu-id="6c6d5-121">（如果大量的请求失败，则表明服务不可用，发送请求将毫无意义。）超时期限过后，客户端应重试，并在新的请求已成功，关闭断路器。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-121">(If a large number of requests are failing, that suggests the service is unavailable and that sending requests is pointless.) After a timeout period, the client should try again and, if the new requests are successful, close the circuit breaker.</span></span>

<span data-ttu-id="6c6d5-122">**提供回退**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-122">**Provide fallbacks**.</span></span> <span data-ttu-id="6c6d5-123">在此方法中，客户端进程执行回退的逻辑，当请求失败，如返回缓存的数据或默认值。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-123">In this approach, the client process performs fallback logic when a request fails, such as returning cached data or a default value.</span></span> <span data-ttu-id="6c6d5-124">这是适用于查询，一种方法，更新或命令变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-124">This is an approach suitable for queries, and is more complex for updates or commands.</span></span>

<span data-ttu-id="6c6d5-125">**限制的排队请求数**。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-125">**Limit the number of queued requests**.</span></span> <span data-ttu-id="6c6d5-126">客户端还应施加的未完成客户端微服务可以将发送到特定服务的请求数上限。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-126">Clients should also impose an upper bound on the number of outstanding requests that a client microservice can send to a particular service.</span></span> <span data-ttu-id="6c6d5-127">如果已达到限制，它也可能毫无意义发出其他请求，且这些尝试应立即失败。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-127">If the limit has been reached, it is probably pointless to make additional requests, and those attempts should fail immediately.</span></span> <span data-ttu-id="6c6d5-128">在实现中，Polly 方面[Bulkhead 隔离](https://github.com/App-vNext/Polly/wiki/Bulkhead)策略可以用于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-128">In terms of implementation, the Polly [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) policy can be used to fulfil this requirement.</span></span> <span data-ttu-id="6c6d5-129">这种方法是实质上是并行化限制与[SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1)作为实现。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-129">This approach is essentially a parallelization throttle with [SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1) as the implementation.</span></span> <span data-ttu-id="6c6d5-130">它也允许外部 bulkhead"队列"。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-130">It also permits a "queue" outside the bulkhead.</span></span> <span data-ttu-id="6c6d5-131">（例如，由于容量都视为完整），可以主动舍弃之前执行的额外负载。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-131">You can proactively shed excess load even before execution (for example, because capacity is deemed full).</span></span> <span data-ttu-id="6c6d5-132">这样，某些故障情况下它的响应速度之快超乎断路器将因为断路器等待失败。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-132">This makes its response to certain failure scenarios faster than a circuit breaker would be, since the circuit breaker waits for the failures.</span></span> <span data-ttu-id="6c6d5-133">中 Polly BulkheadPolicy 对象公开程度 bulkhead 和队列，并提供事件在溢出因此还可用来驱动器自动水平缩放。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-133">The BulkheadPolicy object in Polly exposes how full the bulkhead and queue are, and offers events on overflow so can also be used to drive automated horizontal scaling.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6c6d5-134">其他资源</span><span class="sxs-lookup"><span data-stu-id="6c6d5-134">Additional resources</span></span>

-   <span data-ttu-id="6c6d5-135">**复原模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="6c6d5-135">**Resiliency patterns**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="6c6d5-136">**添加恢复能力和优化性能**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)</span><span class="sxs-lookup"><span data-stu-id="6c6d5-136">**Adding Resilience and Optimizing Performance**
[*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)</span></span>

-   <span data-ttu-id="6c6d5-137">**Bulkhead。**</span><span class="sxs-lookup"><span data-stu-id="6c6d5-137">**Bulkhead.**</span></span> <span data-ttu-id="6c6d5-138">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="6c6d5-138">GitHub repo.</span></span> <span data-ttu-id="6c6d5-139">与 Polly 策略的实现。 \\</span><span class="sxs-lookup"><span data-stu-id="6c6d5-139">Implementation with Polly policy.\\</span></span>
    [<span data-ttu-id="6c6d5-140">*https://github.com/App-vNext/Polly/wiki/Bulkhead*</span><span class="sxs-lookup"><span data-stu-id="6c6d5-140">*https://github.com/App-vNext/Polly/wiki/Bulkhead*</span></span>](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   <span data-ttu-id="6c6d5-141">**设计灵活的应用程序，azure**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)</span><span class="sxs-lookup"><span data-stu-id="6c6d5-141">**Designing resilient applications for Azure**
[*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)</span></span>

-   <span data-ttu-id="6c6d5-142">**暂时性故障处理**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span><span class="sxs-lookup"><span data-stu-id="6c6d5-142">**Transient fault handling**
<https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6c6d5-143">[以前](句柄的部分-failure.md) [下一步] (实现-重试-指数-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="6c6d5-143">[Previous] (handle-partial-failure.md) [Next] (implement-retries-exponential-backoff.md)</span></span>
