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
# <a name="strategies-for-handling-partial-failure"></a>用于处理部分失败的策略

用于处理部分失败的策略包括以下内容。

**在内部微服务使用异步通信 （例如，基于消息的通信）**。 高，最好是不跨内部微服务创建的同步的 HTTP 调用的长链，因为该正确设计最终将变得不正确的服务中断的主要原因。 相反，除客户端应用程序和微服务或细化 API 网关的第一个级别之间的前端通信，建议使用仅异步 （基于消息的） 通信一次之后的初始请求 /响应周期，跨内部微服务。 最终一致性和事件驱动的体系结构将有助于最大程度减少 ripple 效果。 这些方法强制 microservice 自治的更高级别，并因此防止在此记录的问题。

**重试使用指数退让**。 这种技术有助于避免短并会通过执行调用出现间歇性故障重试一定次数的以防该服务未仅可用于在短时间。 这可能是由于间歇性网络问题或在 microservice/容器移动到群集中的不同节点时。 但是，如果这些重试不正确设计使用断路器，它可以担负 ripple 影响，甚至最终导致[拒绝服务 (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)。

**解决网络超时**。 通常情况下，不无限期阻止并等待响应时始终使用超时，则应设计客户端。 使用超时可确保永远不会无限期地占用资源。

**使用断路器模式**。 在此方法中，客户端进程跟踪失败请求数。 如果错误率超出配置的限制，"断路器"行程，以便进一步尝试立即失败。 （如果大量的请求失败，则表明服务不可用，发送请求将毫无意义。）超时期限过后，客户端应重试，并在新的请求已成功，关闭断路器。

**提供回退**。 在此方法中，客户端进程执行回退的逻辑，当请求失败，如返回缓存的数据或默认值。 这是适用于查询，一种方法，更新或命令变得更加复杂。

**限制的排队请求数**。 客户端还应施加的未完成客户端微服务可以将发送到特定服务的请求数上限。 如果已达到限制，它也可能毫无意义发出其他请求，且这些尝试应立即失败。 在实现中，Polly 方面[Bulkhead 隔离](https://github.com/App-vNext/Polly/wiki/Bulkhead)策略可以用于满足此要求。 这种方法是实质上是并行化限制与[SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1)作为实现。 它也允许外部 bulkhead"队列"。 （例如，由于容量都视为完整），可以主动舍弃之前执行的额外负载。 这样，某些故障情况下它的响应速度之快超乎断路器将因为断路器等待失败。 中 Polly BulkheadPolicy 对象公开程度 bulkhead 和队列，并提供事件在溢出因此还可用来驱动器自动水平缩放。

## <a name="additional-resources"></a>其他资源

-   **复原模式**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **添加恢复能力和优化性能**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)

-   **Bulkhead。** GitHub 存储库。 与 Polly 策略的实现。 \
    [*https://github.com/App-vNext/Polly/wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **设计灵活的应用程序，azure**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **暂时性故障处理**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[以前](句柄的部分-failure.md) [下一步] (实现-重试-指数-backoff.md)
