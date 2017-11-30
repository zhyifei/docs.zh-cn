---
title: "复原和微服务中的高可用性"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |复原和微服务中的高可用性"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 149e28ac7bd7383e4e960ed8a226943e2b9bdaa1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="resiliency-and-high-availability-in-microservices"></a>复原和微服务中的高可用性

若要解决，尤其是在分布式系统的困难问题之一处理意外故障。 许多开发人员编写的代码涉及处理异常、，这也是按测试所用时间最多其中。 问题是更多地涉及不仅仅编写代码来处理故障。 当运行微服务的计算机出现故障时，会发生什么情况？ 不仅需要检测此微服务失败 （上其自己的硬问题），而且你还必须采取措施来重新启动你的 microservice。

Microservice 需要为能够弹性应对故障和要能够重新启动的可用性的另一台计算机的次数。 此复原还涉及到微服务可以恢复此状态，以及是否微服务可以成功地重新启动代表 microservice，已保存的状态。 换而言之，需要有 （进程可以随时重新启动） 的计算功能中的复原能力以及状态或数据 （无数据丢失和数据保持一致） 中的恢复能力。

而在其他情况下，例如升级应用程序期间出现故障的时期间加剧的复原的问题。 Microservice，使用部署系统中，需要用来确定是否它可以继续向前移动到较新版本，或改为回滚到以前的版本保持一致的状态。 例如足够多的计算机是否可用，以使移动转发以及如何恢复以前版本的微服务的问题需要考虑。 这要求 microservice 发出运行状况信息，以便总体应用程序和 orchestrator 可以使这些决策。

此外，相关复原到基于云的系统必须表现得。 如前文所述，基于云的系统必须采用失败，必须尝试从它们中自动恢复。 例如，在发生网络或容器的故障，客户端应用程序或客户端服务必须具有重试发送消息或重试请求，因为在许多情况下在云中的故障是部分的策略。 [实现灵活的应用程序](#implementing_resilient_apps)本指南中的部分介绍如何处理部分失败。 它通过使用类似的库来描述技术重试使用指数退让或.NET 核心中的断路器模式[Polly](https://github.com/App-vNext/Polly)，它提供大量不同的策略来处理此主题。

## <a name="health-management-and-diagnostics-in-microservices"></a>运行状况管理和诊断中微服务

似乎很明显，并经常被忽略，但 microservice 必须报告其运行状况和诊断。 否则，为很少的见解，从操作的角度。 跨一组独立的服务关联的诊断事件和处理机时钟歪斜以有意义的事件是顺序的一个挑战。 在相同的方式，通过一致的协议和数据格式与微服务交互，没有如何运行状况和诊断最终用于查询和查看事件存储中的事件日志中的标准化的需要。 在微服务方法中，它是密钥不同团队达成单个日志记录格式。 需要有一种在应用程序中查看诊断事件的一致性方法。

### <a name="health-checks"></a>运行状况检查

运行状况是不同的诊断。 有关报告其当前状态以采取相应的措施微服务运行状况。 一个很好示例使用升级和部署机制，以保持可用性。 虽然服务当前可能处于不正常状态因进程故障或计算机重新启动，但服务仍可能操作。 你需要的最后一步是通过使其更糟执行升级。 最佳方法是先执行操作调查或留出时间让微服务恢复。 从微服务的运行状况事件帮助我们做出明智的决策，并在起作用，帮助您创建自我修复服务。

在实现运行状况检查 ASP.NET 核心服务部分中的本指南中，我们介绍如何使用你微服务中的新 ASP.NET HealthChecks 库，因此它们可以报告其状态到监视的服务以采取相应的措施。

### <a name="using-diagnostics-and-logs-event-streams"></a>使用诊断和日志事件流

日志提供有关如何应用程序或服务正在运行，包括异常、 警告和简单的信息性消息的信息。 通常，尽管异常通常还显示堆栈跟踪跨多行，通过每个事件，一行以文本格式将为每个日志。

在整体基于服务器的应用程序，可以只需将日志写入磁盘 （日志文件） 上的文件，然后对其使用任何工具进行分析。 因为应用程序执行仅限于固定的服务器或 VM，因此通常不太复杂，无法分析的事件流。 但是，在分布式应用程序在 orchestrator 群集中的很多节点中在其中执行多个服务，能够关联分布式的事件是一个难题。

基于微服务构成的应用程序应尝试通过本身，存储的事件或日志文件的输出流，甚至不尝试管理到一个中心位置的事件的路由。 它应该是透明的这意味着每个进程只应写入其事件流到下，将在其中运行的执行环境基础结构收集标准输出。 这些事件流路由器的一个示例是[Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow)，其中从多个来源收集事件流，并将其输出系统发布。 这些错误可能包括简单的标准输出开发环境或云系统，例如[Application Insights](https://azure.microsoft.com/services/application-insights/)， [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) （对于本地应用程序），和[Azure 诊断](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). 也有很好的第三方日志分析平台和工具，可以搜索警报，报表，和监视器日志，即使在实时，如[Splunk](http://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA)。

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Orchestrators 管理运行状况和诊断信息

在创建基于微服务构成的应用程序时，你需要处理的复杂性。 当然，单个 microservice 很容易处理，但几十或数百个类型和数千种微服务的实例是一个复杂的问题。 它仅仅是涉及不会生成你的 microservice 体系结构，你还需要高可用性、 可寻址性、 复原能力、 运行状况和诊断如果你想要有一个稳定且提供一致性的系统。

![](./media/image22.png)

**图 4-22**。 微服务平台是必不可少的应用程序的运行状况管理

显示在图 4-22 中的复杂问题是很难通过自行解决。 开发团队应集中精力解决业务问题并生成与 microservice 基于方法的自定义应用程序。 它们应不专注于解决复杂的基础结构问题;如果已更改，则任何基于微服务构成的应用程序的成本会很大。 因此，有 microservice 面向的平台，称为 orchestrators 或 microservice 群集，尝试解决的问题硬的生成和运行服务并有效地使用基础结构资源。 这将减少生成的应用程序使用微服务方法的复杂性。

不同 orchestrators 听起来类似，但诊断和运行状况检查提供的每个区别在于功能和状态的成熟度，有时根据操作系统平台，如在下一部分中所述。

## <a name="additional-resources"></a>其他资源

-   **十二个因素应用中。XI。日志： 将日志事件流视为**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Microsoft 诊断 EventFlow 库。** GitHub 存储库。

    [*https://github.com/Azure/diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **Azure 诊断是什么**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **将 Windows 计算机连接到 Azure 中的日志分析服务**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **日志记录你平均值： 使用语义的日志记录应用程序块**
    [*https://msdn.microsoft.com/library/dn440729 (v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk。** 官方网站。
    [*http://www.splunk.com*](http://www.splunk.com)

-   **EventSource 类**。 事件跟踪 Windows (ETW) 的 API [ *https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource)




>[!div class="step-by-step"]
[以前](microservice-based-composite-ui-shape-layout.md) [下一步] (scalable-available-multi-container-microservice-applications.md)
