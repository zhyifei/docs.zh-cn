---
title: 为云构建复原服务就绪。 在云中处理暂时性故障
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |为云构建复原服务就绪。 在云中处理暂时性故障
ms.date: 04/30/2018
ms.openlocfilehash: e6fae8140b55cb0308dca9f4b77e961501b41f8f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739390"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>为云构建复原服务就绪：在云中接纳暂时性故障

恢复能力是指从故障中恢复并继续工作的能力。 复原并不是要避免故障，而是接受会发生故障的事实，然后以避免停机或数据丢失的方式对其进行响应。 恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。

当你的应用程序至少实现了基于软件的复原模式（而不是基于硬件的模型）时，你的应用程序即可为云做好准备。 你的云应用程序必须采用将会出现的部分故障。 设计或部分重构您的应用程序，以通过预期的部分故障实现复原。 它应该用于应对部分故障，例如暂时性的网络中断和节点，或者 Vm 在云中崩溃。 即使将容器移至 orchestrator 群集内的其他节点，也可能导致应用程序中出现间歇性的短故障。

## <a name="handling-partial-failure"></a>处理部分失败错误

在基于云的应用程序中，存在部分故障的现有风险。 例如，单个网站实例或容器可能会失败，或者可能是短时间不可用或没有响应。 或者，单个 VM 或服务器可能会崩溃。

由于客户端和服务是独立的进程，因此服务可能无法及时响应客户端的请求。 此服务可能已过载，响应速度慢，或者由于网络问题而无法在短时间访问该服务。

例如，假设有一个在 Azure SQL 数据库中访问数据库的单一 .NET 应用程序。 如果 Azure SQL 数据库或任何其他第三方服务没有短暂的响应时间（Azure SQL 数据库可能会移动到不同的节点或服务器，并且在几秒钟内无响应），则当用户尝试执行任何操作时，应用程序可能会崩溃并完成 show 此时引发异常。

使用 HTTP 服务的应用可能会出现类似的情况。 在出现短暂的暂时性故障时，网络或服务本身可能无法在云中使用。

如图4-9 中所示的弹性应用程序应该实现 "使用指数回退重试" 之类的技术，使应用程序有机会处理资源的暂时性故障。 你还应在应用程序中使用 "断路程序"。 当某个应用程序实际上是长期故障时，断路器会阻止该应用程序尝试访问该资源。 通过使用断路器，应用程序可避免造成自身的拒绝服务。

![使用指数回退处理的重试的部分失败关系图。](./media/build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud/retry-partial-failures.png)

**图4-9。** 使用指数回退处理重试的部分失败

可以在 HTTP 资源和数据库资源中使用这些技术。 在图4-9 中，应用程序基于3层体系结构，因此，你需要在服务级别（HTTP）和数据层级（TCP）上使用这些方法。 在仅使用单个应用层和数据库（无其他服务或微服务）的单一应用程序层中，处理数据库连接级别的暂时性故障可能就足够了。 在这种情况下，只需要数据库连接的特定配置。

实现访问数据库的可恢复性通信时，根据所使用的 .NET 版本，它可能很简单（例如，[使用实体框架6或更高](/ef/ef6/fundamentals/connection-resiliency/retry-logic)版本）。 只需配置数据库连接即可）。 或者，你可能需要使用其他库，如[暂时性故障处理应用程序块](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50))（适用于早期版本的 .net），甚至实现你自己的库。

实现 HTTP 重试和断路时，适用于 .NET 的建议使用[Polly](https://github.com/App-vNext/Polly)库，该库面向 .NET Framework 4.0、.NET Framework 4.5 和 .NET Standard 1.1，其中包括 .net Core 支持。

若要了解如何实现用于处理云中部分故障的策略，请参阅以下参考。

### <a name="additional-resources"></a>其他资源

- **实现可恢复性通信以处理部分故障**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **实体框架连接复原和重试逻辑（版本6及更高版本）**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **暂时性故障处理应用程序块**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **用于复原 HTTP 通信的 Polly 库**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[下一页](modernize-your-apps-with-monitoring-and-telemetry.md)
