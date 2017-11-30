---
title: "更新你的应用的监视和遥测"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |更新你的应用的监视和遥测"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 03a6f2be9dc6c020cfe93a2597d1288943e527c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>更新你的应用的监视和遥测

在生产环境中运行应用程序时，很重要，具有有关如何执行你的应用程序。 它正在执行在高级别？ 用户收到错误，或是稳定且可靠的应用程序？ 你需要丰富的性能监视、 功能强大警报和仪表板，以帮助确保你的应用程序可用并按预期执行。 你还需要能够快速查看是否有问题，确定有多少客户受到影响，并执行根本原因分析，以查找并修复该问题。

## <a name="monitor-your-application-with-application-insights"></a>监视你的应用程序使用 Application Insights

Application Insights 是一个可扩展的应用程序性能管理 (APM) 服务的 web 开发人员在多个平台上工作。 使用它监视实时 web 应用程序。 Application Insights 自动检测性能异常。 它包括强大的分析工具来帮助你诊断问题，并帮助你了解用户实际执行的操作与你的应用。 Application Insights 旨在帮助你持续改进性能和可用性。 它在各种平台，包括.NET、 Node.js 和 J2EE，是否适用于应用程序托管在本地或云中。 Application Insights 与您的 DevOps 流程，集成，具有到不同的开发工具的连接点。

图 4-10 显示如何 Application Insights 监视你的应用程序和它如何到仪表板中显示这些 insights 的示例。

![Application Insights 监视仪表板](./media/image10.png)

> **图 4-10。** Application Insights 监视仪表板

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>监视使用日志分析和其容器监视解决方案 Docker 基础结构

[Azure 日志分析](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)属于[总体监视解决方案的 Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)。 它也是一服务[Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。 日志分析监视云，并且本地环境 (对于本地 OMS) 可帮助维护可用性和性能。 它收集生成的资源在云和本地环境中和从其他监视工具，以跨多个源提供的分析数据。

与 Azure 基础结构日志，有关日志分析，作为一项 Azure 服务，引入来自其他 Azure 服务的日志和度量值数据 (通过[Azure 监视器](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor))，Azure 虚拟机、 Docker 容器和在本地或其他云基础结构。 日志分析提供灵活的日志搜索和扩展的框分析基于此数据。 它提供了丰富的工具，你可以使用跨源分析数据，它允许在所有日志之间的复杂的查询而可以主动警报基于指定的条件。 你甚至可以收集中央日志分析存储库中，可以在此查询，并可视化这些数据的自定义数据。 你还可以考虑利用日志分析内置解决方案，以立即深入了解安全和基础结构的功能。

你可以访问日志分析通过 OMS 门户或 Azure 门户中，在任何浏览器中运行，并提供了你有权访问配置设置和多个工具来分析和处理收集的数据。

[容器监视解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)中日志分析可帮助你查看和管理 Docker 和 Windows 容器主机在单个位置。 解决方案显示哪些容器运行，哪些容器映像它们正在运行，请和其中运行容器。 你可以查看详细的审核信息，包括与容器正在使用的命令。 此外可以通过查看和搜索而无需远程查看 Docker 或 Windows 主机的集中式的日志来排除容器。 你可以找到可能的主机上的干扰和使用过多资源的容器。 此外，你可以查看集中式的 CPU、 内存、 存储和网络使用情况和的容器的性能信息。 在运行 Windows 的计算机，可以集中并比较日志从 Windows Server HYPER-V 和 Docker 容器。 解决方案支持以下容器 orchestrators:

-   Docker Swarm

-   DC/OS

-   Kubernetes

-   Service Fabric

-   Red Hat OpenShift

图 4-11 显示各种容器主机和代理和 OMS 之间的关系。

![日志分析容器监视解决方案](./media/image11.png)

> **图 4-11。** 日志分析容器监视解决方案

你可以使用的日志分析容器监视解决方案：

-   请参阅有关在单个位置的所有容器主机的信息。

-   了解哪些容器是运行，哪些映像它们正在运行，请和其中运行它们。

-   请参阅在容器上的操作的审核痕迹。

-   通过查看和搜索没有远程登录到 Docker 主机的集中式的日志排查问题。

-   查找容器可能是"干扰性邻居，"并使用主机上的过多资源。

-   查看集中式的 CPU、 内存、 存储和网络使用情况和的容器的性能信息。

### <a name="additional-resources"></a>其他资源

-   **在 Microsoft Azure 中监视概述**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   **Application Insights 是什么？**

[https://docs.microsoft.com/azure/application-insights/app-insights-overview](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   **日志分析是什么？**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-overview](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   **容器监视解决方案中日志分析**

[https://docs.microsoft.com/azure/log-analytics/log-analytics-containers](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   **Azure 监视器概述**

[https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   **Operations Management Suite (OMS) 是什么？**

[https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   **监视与 OMS 配合使用的 Service Fabric 中的 Windows Server 容器**

[https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
[上一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[下一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
