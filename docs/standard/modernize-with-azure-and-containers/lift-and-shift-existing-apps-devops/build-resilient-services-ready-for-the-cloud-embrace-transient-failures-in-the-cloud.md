---
title: 构建可复原的服务供云。 采用在云中的暂时性故障
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |构建可复原的服务供云。 采用在云中的暂时性故障
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0ac1d67a5b5b9a19f47c1d20eeb446977466510f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>构建可复原的服务供云： 采用在云中的暂时性故障

恢复能力是指从故障中恢复并继续工作的能力。 复原能力不是有关避免失败，但接受这一事实，将出现故障，并可避免停机时间或数据丢失的方式然后对它们的响应。 恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。

至少，实施基于软件的模型的复原能力，而不是基于硬件的模型时，你的应用程序可供云。 云应用程序必须采用肯定会发生部分故障。 你需要设计或部分重构你的应用程序，如果您想要获得预期的部分故障中恢复。 它应设计为处理部分故障，如暂时性网络中断和节点或在云中发生故障的 Vm。 正在移到不同 orchestrator 群集内节点的甚至容器可能会导致应用程序中的间歇性短失败。

## <a name="handling-partial-failure"></a>处理部分失败错误

在基于云的应用程序，没有部分的失败的受始终存在风险。 例如，单个网站实例或容器可能会失败，或者它可能不可用或没有响应。 在短时间。 或者，单个 VM 或服务器可能会崩溃。

因为客户端和服务都是单独的进程，服务可能无法及时响应客户端的请求。 服务可能被重载并响应速度极慢的请求，或它可能只是无法访问在短时间由于网络问题。

例如，考虑的整体的.NET 应用程序访问 Azure SQL 数据库中的数据库。 如果 Azure SQL 数据库或任何其他第三方服务的一条简短停止响应时间 （Azure SQL 数据库可能被移动到另一个节点或服务器，并可能在几秒内没有响应），当用户尝试执行任何操作，该应用程序可能崩溃和显示w 异常完全相同的时间。

类似的方案可能会出现在应用程序使用 HTTP 服务。 网络或服务本身可能不能在云中出现较短的暂时性故障。

显示在图 4-9 中所示弹性应用程序应实现"重试使用指数退让"技术以便应用程序有机会处理在资源中的暂时性故障。 此外应在应用程序中使用"断路器"。 断路器将停止应用程序尝试访问资源时实际长期故障。 通过使用断路器，该应用程序可避免引发拒绝到其自身的服务。

![由具有指数回退重试处理部分故障](./media/image9.png)

> **图 4-9。** 由具有指数回退重试处理部分故障

在 HTTP 资源和数据库资源，你可以使用这些技术。 在图 4-9、 应用程序基于 3 层体系结构，因此需要在服务级别 (HTTP) 和数据层级别 (TCP) 这些技术。 在使用单个应用程序层将数据库 （没有其他服务或微服务） 以及一个整体应用程序，处理数据库连接级别的暂时性故障可能是足够。 在该方案中，通常只是数据库连接的特定配置是必需的。

实现访问数据库时，具体取决于你使用的，.NET 版本的弹性通信时它可以是非常简单 (例如， [Entity Framework 6 或更高版本](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)，它是只需配置数据库连接）。 或者，你可能需要使用类似的其他库[暂时性故障处理应用程序块](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)（对于早期版本的.NET），或甚至实现你自己的库。

实现 HTTP 重试次数和断路器时，.NET 的推荐方法是使用[Polly](https://github.com/App-vNext/Polly)库，后者面向.NET 4.0、.NET 4.5 和.NET 标准 1.1，包括.NET 核心的支持。

若要了解如何实现用于处理部分故障在云中的策略，请参阅以下引用。

### <a name="additional-resources"></a>其他资源

-   **实现弹性通信来处理部分失败**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   **实体框架连接复原和重试逻辑 （6 和更高版本）**

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   **暂时性故障处理应用程序块**

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   **弹性 HTTP 通信的 Polly 库**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[下一页](modernize-your-apps-with-monitoring-and-telemetry.md)
