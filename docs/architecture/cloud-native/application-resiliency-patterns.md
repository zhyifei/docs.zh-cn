---
title: 应用程序复原能力模式
description: 构建适用于 Azure 的云本机 .NET 应用 |应用程序复原模式
ms.date: 06/30/2019
ms.openlocfilehash: 13811efaa88e0bd2824add1c8712b78b18d46375
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841887"
---
# <a name="application-resiliency-patterns"></a>应用程序复原能力模式

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

第一道防线是支持软件的应用程序复原能力。

虽然您可以投入大量时间来编写自己的复原框架，此类产品已经存在。 例如， [Polly](http://www.thepollyproject.org/)是一个全面的 .net 复原和暂时性故障处理库，使开发人员能够以流畅且线程安全的方式表达复原策略。 Polly 面向用完整 .NET Framework 或 .NET Core 构建的应用程序。 图6-2 显示了可从 Polly 库获取的复原策略（即功能）。 这些策略可单独应用或组合在一起应用。

![Polly 框架](./media/polly-resiliency-framework.png)

**图 6-2**. Polly 复原框架功能

请注意上图中的如何将复原策略应用于请求消息，不管是来自外部客户端还是来自其他后端服务。 目标是对可能暂时不可用的服务的请求进行补偿。 通常，这些短暂的中断会表现在图6-3 中所示的 HTTP 状态代码。

![要重试的 HTTP 状态代码](./media/http-status-codes.png)

**图 6-3**。 要重试的 HTTP 状态代码

问：是否要重试 HTTP 状态代码 403-禁止访问？ No。 此时，系统将正常运行，但通知调用方他们无权执行所请求的操作。 必须注意仅重试由失败导致的操作。

如第1章所述，构建云本机应用程序的 Microsoft 开发人员应面向 .NET Core。 版本2.1 引入了[HTTPClientFactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore)库，用于创建用于与基于 URL 的资源交互的 HTTP 客户端实例。 工厂类取代了原始 HTTPClient 类，它支持许多增强功能，其中一个功能与 Polly 复原库[紧密集成](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)。 利用它，你可以轻松地在应用程序启动类中定义复原策略来处理部分故障和连接问题。

接下来，让我们展开重试和断路器模式。

### <a name="retry-pattern"></a>重试模式

在分布式云本机环境中，对服务和云资源的调用可能会失败，因为暂时（短暂）故障，这通常会在短时间内自行更正。 实现重试策略可帮助云本机服务处理这些方案。

[重试模式](https://docs.microsoft.com/azure/architecture/patterns/retry)使服务能够用呈指数增加的等待时间重试失败的请求操作（可配置）。 图6-4 显示了一个重试操作。

![操作中的重试模式](./media/retry-pattern.png)

图 6-4。 操作中的重试模式

在上图中，已为请求操作实现重试模式。 它已配置为允许最多四次重试，而不能从两秒开始的回退时间间隔（等待时间）开始，每次后续尝试都呈指数级增长。

- 第一次调用失败并返回 HTTP 状态代码500。 应用程序等待两秒钟，然后重试呼叫。
- 第二次调用也失败，并返回 HTTP 状态代码500。 现在，应用程序将回退间隔加倍到4秒，然后重试该调用。
- 最后，第三次调用成功。
- 在此方案中，重试操作最多尝试四次重试，同时在调用失败之前将回退持续时间加倍。

在重试调用以允许服务时间自动更正之前，请务必增加回退时间。 最佳做法是实现以指数方式递增的回退（每次重试时加倍一次），以允许足够的更正时间。

## <a name="circuit-breaker-pattern"></a>断路器模式

尽管重试模式可以在部分失败时帮助抢救请求放大，但在某些情况下，可能会由于意外的事件需要更长的时间来解决，导致失败。 这些故障轻则导致部分连接中断，重则导致服务完全瘫痪。 在这些情况下，应用程序不必再重试不太可能成功的操作。

要使任务更糟，对非响应式服务执行连续重试操作可以将你转到自行投入使用的拒绝服务方案，在此方案中，你可以通过连续调用耗尽资源（如内存、线程和数据库连接，导致系统中使用相同资源的无关部分出现故障。

在这种情况下，操作会立即失败并仅在有可能成功的情况下尝试调用服务，这是最好的做法。

[断路器模式](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)可以防止应用程序重复尝试执行很可能失败的操作。 它还使用定期试验调用来监视应用程序，以确定是否已解决错误。 图6-5 显示了操作中的断路器模式。

![操作中的断路器模式](./media/circuit-breaker-pattern.png)

图 6-5。 操作中的断路器模式

在上图中，已将断路器模式添加到原始重试模式。 请注意，请求10个失败后，断路会打开，不再允许对服务的调用。 CheckCircuit 值设置为30秒，指定库允许一个请求继续到服务的频率。 如果该调用成功，线路将关闭，并且服务再次可用于通信。

请记住，断路器模式的目的*不同*于重试模式。 重试模式使应用程序能够在预期成功的情况下重试操作。 断路器模式可以防止应用程序执行可能会失败的操作。 通常，应用程序将通过使用重试模式来通过断路器调用操作来*合并*这两种模式。 但是，重试逻辑应对断路器返回的任何异常敏感，并在断路器指示故障不是暂时性时放弃重试尝试。

应用程序复原能力是处理请求的操作时必须执行的操作。 但这只是故事的一半。 接下来，我们介绍 Azure 云中提供的复原功能。

>[!div class="step-by-step"]
>[上一页](resiliency.md)
>[下一页](infrastructure-resiliency-azure.md)
