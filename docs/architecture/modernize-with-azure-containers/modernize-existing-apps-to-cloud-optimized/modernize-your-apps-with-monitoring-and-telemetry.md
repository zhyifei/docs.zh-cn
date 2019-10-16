---
title: 通过监视和遥测对应用进行现代化
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |通过监视和遥测实现应用现代化
ms.date: 04/30/2018
ms.openlocfilehash: 3d629e89a73c870d4b6396c6b1d0ecbe95b79ead
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393854"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a>通过监视和遥测对应用进行现代化

在生产环境中运行应用程序时，请务必了解应用程序的执行情况。 它是否在高级别执行？ 用户是否遇到了错误，或是应用程序是否稳定和可靠？ 需要丰富的性能监视、功能强大的警报和仪表板，帮助确保你的应用程序可用并按预期方式执行。 还需要能够快速查看是否存在问题，确定受影响的客户数量，并执行根本原因分析来查找并解决问题。

## <a name="monitor-your-application-with-application-insights"></a>监视应用程序的 Application Insights

Application Insights 是适用于在多个平台上工作的 web 开发人员的可扩展应用程序性能管理（APM）服务。 用于监视实时 web 应用程序。 Application Insights 会自动检测性能异常。 它包含强大的分析工具，可帮助你诊断问题，并帮助你了解用户对你的应用程序的实际操作。 Application Insights 旨在帮助你持续提高性能和可用性。 它适用于各种平台，包括 .NET、node.js 和 J2EE，无论是在本地还是在云中托管。 Application Insights 与 DevOps 过程集成，并具有各种开发工具的连接点。

图4-10 显示了一个示例，说明了 Application Insights 如何监视应用程序以及它如何将这些见解呈现给仪表板。

![Application Insights 监视仪表板的屏幕截图。](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

**图4-10。** Application Insights 监视仪表板

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a>利用 Log Analytics 及其容器监视解决方案监视 Docker 基础结构

[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)是[Microsoft Azure 总体监视解决方案](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)的一部分。 它也是[Operations Management Suite （OMS）](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)中的一项服务。 Log Analytics 监视云和本地环境（适用于本地的 OMS），以帮助维护可用性和性能。 它收集由云和本地环境中的资源生成的数据以及其他监视工具的数据，以便跨多个源提供分析。

与 Azure 基础结构日志相关，Log Analytics 为 Azure 服务，从其他 Azure 服务（通过[Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)）、Azure Vm、Docker 容器以及本地或其他云基础结构引入日志和指标数据。 Log Analytics 在此数据的基础上提供灵活的日志搜索和现成的分析。 它提供丰富的工具，可用于跨源分析数据，允许跨所有日志进行复杂的查询，并且可以根据指定的条件主动发出警报。 您甚至可以在中央 Log Analytics 存储库中收集自定义数据，您可以在该存储库中对其进行查询和可视化。 你还可以利用 Log Analytics 内置解决方案，立即深入了解基础结构的安全性和功能。

可以通过 OMS 门户或 Azure 门户（在任何浏览器中运行）访问 Log Analytics，并提供对配置设置和多个工具的访问权限，以便分析和处理收集的数据。

Log Analytics 中的[容器监视解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)可帮助你在一个位置查看和管理 Docker 和 Windows 容器主机。 解决方案显示哪些容器正在运行、正在运行的容器映像和容器运行的位置。 您可以查看详细的审核信息，包括与容器一起使用的命令。 你还可以通过查看和搜索集中式日志来排查容器问题，而无需远程查看 Docker 或 Windows 主机。 可以在主机上找到可能有干扰并消耗过多资源的容器。 此外，还可以查看容器的集中式 CPU、内存、存储和网络使用情况以及性能信息。 在运行 Windows 的计算机上，可以集中和比较 Windows Server、Hyper-v 和 Docker 容器中的日志。 此解决方案支持以下容器协调器：

- Docker Swarm

- DC/OS

- Kubernetes

- Red Hat OpenShift

图4-11 显示了各种容器主机与代理和 OMS 之间的关系。

![Log Analytics 容器监视解决方案的屏幕截图。](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

**图4-11。** Log Analytics 容器监视解决方案

你可以使用 Log Analytics 容器监视解决方案来执行以下操作：

- 查看单个位置中有关所有容器主机的信息。

- 了解正在运行的容器、正在运行的映像以及运行的位置。

- 查看容器上操作的审核线索。

- 通过查看和搜索集中式日志进行故障排除，而无需远程登录到 Docker 主机。

- 查找可能 "干扰邻居" 的容器，并在主机上消耗过多的资源。

- 查看容器的集中式 CPU、内存、存储和网络使用情况以及性能信息。

### <a name="additional-resources"></a>其他资源

- **Microsoft Azure 中的监视概述**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **什么是 Application Insights？**

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- **什么是 Log Analytics？**

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- **Azure Monitor 中的容器监视解决方案**

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- **Azure Monitor 概述**

<https://docs.microsoft.com/azure/azure-monitor/overview>

- **什么是 Operations Management Suite （OMS）？**

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
>[上一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[下一页](life-cycle-ci-cd-pipelines-devops-tools.md)
