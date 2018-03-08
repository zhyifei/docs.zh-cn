---
title: "处理部分失败的策略"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 处理部分失败的策略"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0b5fdb03e4b0d0c2d4e8aa8a897fd46d56707f11
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="strategies-for-handling-partial-failure"></a><span data-ttu-id="730e2-104">处理部分失败的策略</span><span class="sxs-lookup"><span data-stu-id="730e2-104">Strategies for handling partial failure</span></span>

<span data-ttu-id="730e2-105">处理部分失败的策略如下。</span><span class="sxs-lookup"><span data-stu-id="730e2-105">Strategies for dealing with partial failures include the following.</span></span>

<span data-ttu-id="730e2-106">**在内部微服务中使用异步通信（例如，基于消息的通信）**。</span><span class="sxs-lookup"><span data-stu-id="730e2-106">**Use asynchronous communication (for example, message-based communication) across internal microservices**.</span></span> <span data-ttu-id="730e2-107">强烈建议不要跨内部微服务创建长链同步 HTTP 调用，因为此错误设计会最终成为中断的主要原因。</span><span class="sxs-lookup"><span data-stu-id="730e2-107">It is highly advisable not to create long chains of synchronous HTTP calls across the internal microservices because that incorrect design will eventually become the main cause of bad outages.</span></span> <span data-ttu-id="730e2-108">与此相反，建议跨内部微服务情况下，仅在经过初始请求/响应周期后，使用异步（基于消息）通信，但客户端应用程序和第一级微服务或细化 API 网关之间的前端通信除外。</span><span class="sxs-lookup"><span data-stu-id="730e2-108">On the contrary, except for the front-end communications between the client applications and the first level of microservices or fine-grained API Gateways, it is recommended to use only asynchronous (message-based) communication once past the initial request/response cycle, across the internal microservices.</span></span> <span data-ttu-id="730e2-109">最终一致性和事件驱动的体系结构有助于尽可能减少连锁反应。</span><span class="sxs-lookup"><span data-stu-id="730e2-109">Eventual consistency and event-driven architectures will help to minimize ripple effects.</span></span> <span data-ttu-id="730e2-110">这些方法强制执行较高级别的微服务自治，从而防止此处提到的问题发生。</span><span class="sxs-lookup"><span data-stu-id="730e2-110">These approaches enforce a higher level of microservice autonomy and therefore prevent against the problem noted here.</span></span>

<span data-ttu-id="730e2-111">**采用使用指数回退算法的重试**。</span><span class="sxs-lookup"><span data-stu-id="730e2-111">**Use retries with exponential backoff**.</span></span> <span data-ttu-id="730e2-112">这种技术有助于通过执行特定次数的调用重试避免短时间的间歇性故障，以防仅短时间内服务不可用。</span><span class="sxs-lookup"><span data-stu-id="730e2-112">This technique helps to avoid short and intermittent failures by performing call retries a certain number of times, in case the service was not available only for a short time.</span></span> <span data-ttu-id="730e2-113">此问题可能是因为间歇性网络问题或微服务/容器移动到群集中的不同节点造成的。</span><span class="sxs-lookup"><span data-stu-id="730e2-113">This might occur due to intermittent network issues or when a microservice/container is moved to a different node in a cluster.</span></span> <span data-ttu-id="730e2-114">但是，如果这些重试没有针对断路器恰当设计，可能加剧连锁反应，最终导致[拒绝服务 (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)。</span><span class="sxs-lookup"><span data-stu-id="730e2-114">However, if these retries are not designed properly with circuit breakers, it can aggravate the ripple effects, ultimately even causing a [Denial of Service (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).</span></span>

<span data-ttu-id="730e2-115">**暂时避开网络超时**。</span><span class="sxs-lookup"><span data-stu-id="730e2-115">**Work around network timeouts**.</span></span> <span data-ttu-id="730e2-116">通常情况下，客户端应设计为不会无限期阻止，且应在等待响应时使用超时。</span><span class="sxs-lookup"><span data-stu-id="730e2-116">In general, clients should be designed not to block indefinitely and to always use timeouts when waiting for a response.</span></span> <span data-ttu-id="730e2-117">使用超时可确保永远不会无限期地占用资源。</span><span class="sxs-lookup"><span data-stu-id="730e2-117">Using timeouts ensures that resources are never tied up indefinitely.</span></span>

<span data-ttu-id="730e2-118">**使用断路器模式**。</span><span class="sxs-lookup"><span data-stu-id="730e2-118">**Use the Circuit Breaker pattern**.</span></span> <span data-ttu-id="730e2-119">在此方法中，客户端进程跟踪失败请求数。</span><span class="sxs-lookup"><span data-stu-id="730e2-119">In this approach, the client process tracks the number of failed requests.</span></span> <span data-ttu-id="730e2-120">如果错误率超出配置的限制，“断路器”跳变，使进一步尝试立即失败。</span><span class="sxs-lookup"><span data-stu-id="730e2-120">If the error rate exceeds a configured limit, a “circuit breaker” trips so that further attempts fail immediately.</span></span> <span data-ttu-id="730e2-121">（如果大量请求失败，则表明服务不可用，发送请求无意义。）超时期限过后，客户端应重试，如果新的请求成功，关闭断路器。</span><span class="sxs-lookup"><span data-stu-id="730e2-121">(If a large number of requests are failing, that suggests the service is unavailable and that sending requests is pointless.) After a timeout period, the client should try again and, if the new requests are successful, close the circuit breaker.</span></span>

<span data-ttu-id="730e2-122">**提供回退**。</span><span class="sxs-lookup"><span data-stu-id="730e2-122">**Provide fallbacks**.</span></span> <span data-ttu-id="730e2-123">在此方法中，客户端进程在请求失败时执行回退逻辑，如返回缓存数据或默认值。</span><span class="sxs-lookup"><span data-stu-id="730e2-123">In this approach, the client process performs fallback logic when a request fails, such as returning cached data or a default value.</span></span> <span data-ttu-id="730e2-124">这是适用于查询的一种方法，对于更新或命令较复杂。</span><span class="sxs-lookup"><span data-stu-id="730e2-124">This is an approach suitable for queries, and is more complex for updates or commands.</span></span>

<span data-ttu-id="730e2-125">**限制排队请求数**。</span><span class="sxs-lookup"><span data-stu-id="730e2-125">**Limit the number of queued requests**.</span></span> <span data-ttu-id="730e2-126">客户端还应对客户端微服务可发送到特定服务的未完成请求的数量设置上限。</span><span class="sxs-lookup"><span data-stu-id="730e2-126">Clients should also impose an upper bound on the number of outstanding requests that a client microservice can send to a particular service.</span></span> <span data-ttu-id="730e2-127">如果已达到限制，发出其他请求可能无意义，这些尝试应立即失败。</span><span class="sxs-lookup"><span data-stu-id="730e2-127">If the limit has been reached, it is probably pointless to make additional requests, and those attempts should fail immediately.</span></span> <span data-ttu-id="730e2-128">对于实现，Polly [Bulkhead 隔离](https://github.com/App-vNext/Polly/wiki/Bulkhead)策略可以用于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="730e2-128">In terms of implementation, the Polly [Bulkhead Isolation](https://github.com/App-vNext/Polly/wiki/Bulkhead) policy can be used to fulfil this requirement.</span></span> <span data-ttu-id="730e2-129">这种方法实质上是将 <xref:System.Threading.SemaphoreSlim> 作为实现的平行化限制。</span><span class="sxs-lookup"><span data-stu-id="730e2-129">This approach is essentially a parallelization throttle with <xref:System.Threading.SemaphoreSlim> as the implementation.</span></span> <span data-ttu-id="730e2-130">它也允许 bulkhead 外的“队列”。</span><span class="sxs-lookup"><span data-stu-id="730e2-130">It also permits a "queue" outside the bulkhead.</span></span> <span data-ttu-id="730e2-131">可在执行前主动舍弃额外的负载（例如，由于容量被视为已满）。</span><span class="sxs-lookup"><span data-stu-id="730e2-131">You can proactively shed excess load even before execution (for example, because capacity is deemed full).</span></span> <span data-ttu-id="730e2-132">这样一来，其对某些失败情景的响应速度比断路器要快，因为断路器会等待失败。</span><span class="sxs-lookup"><span data-stu-id="730e2-132">This makes its response to certain failure scenarios faster than a circuit breaker would be, since the circuit breaker waits for the failures.</span></span> <span data-ttu-id="730e2-133">Polly 中的 BulkheadPolicy 对象公开 bulkhead 和队列的已满程度，且提供有关溢出的事件，因此也可用于驱动自动水平缩放。</span><span class="sxs-lookup"><span data-stu-id="730e2-133">The BulkheadPolicy object in Polly exposes how full the bulkhead and queue are, and offers events on overflow so can also be used to drive automated horizontal scaling.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="730e2-134">其他资源</span><span class="sxs-lookup"><span data-stu-id="730e2-134">Additional resources</span></span>

-   <span data-ttu-id="730e2-135">恢复模式
    [https://docs.microsoft.com/azure/architecture/patterns/category/resiliency](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="730e2-135">**Resiliency patterns**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="730e2-136">添加恢复和优化性能
    [https://msdn.microsoft.com/library/jj591574.aspx](https://msdn.microsoft.com/library/jj591574.aspx)</span><span class="sxs-lookup"><span data-stu-id="730e2-136">**Adding Resilience and Optimizing Performance**
[*https://msdn.microsoft.com/library/jj591574.aspx*](https://msdn.microsoft.com/library/jj591574.aspx)</span></span>

-   <span data-ttu-id="730e2-137">**Bulkhead。**</span><span class="sxs-lookup"><span data-stu-id="730e2-137">**Bulkhead.**</span></span> <span data-ttu-id="730e2-138">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="730e2-138">GitHub repo.</span></span> <span data-ttu-id="730e2-139">使用 Polly 策略的实现。\\</span><span class="sxs-lookup"><span data-stu-id="730e2-139">Implementation with Polly policy.\\</span></span>
    [<span data-ttu-id="730e2-140">https://github.com/App-vNext/Polly/wiki/Bulkhead</span><span class="sxs-lookup"><span data-stu-id="730e2-140">*https://github.com/App-vNext/Polly/wiki/Bulkhead*</span></span>](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   <span data-ttu-id="730e2-141">为 Azure 设计可恢复的应用程序
    [https://docs.microsoft.com/azure/architecture/resiliency/](https://docs.microsoft.com/azure/architecture/resiliency/)</span><span class="sxs-lookup"><span data-stu-id="730e2-141">**Designing resilient applications for Azure**
[*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)</span></span>

-   <span data-ttu-id="730e2-142">**瞬时故障处理**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span><span class="sxs-lookup"><span data-stu-id="730e2-142">**Transient fault handling**
<https://docs.microsoft.com/azure/architecture/best-practices/transient-faults></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="730e2-143">[Previous] (handle-partial-failure.md) [Next] (implement-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="730e2-143">[Previous] (handle-partial-failure.md) [Next] (implement-retries-exponential-backoff.md)</span></span>
