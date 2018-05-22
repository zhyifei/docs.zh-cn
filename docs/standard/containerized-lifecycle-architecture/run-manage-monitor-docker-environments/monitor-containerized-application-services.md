---
title: 监视容器化应用程序服务
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3877767117d8292644782fc07df6667931688be2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="monitor-containerized-application-services"></a>监视容器化应用程序服务

这非常重要将拆分为多个容器和微服务的应用程序可以有一种方式监视和分析应用程序的行为。

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是一种可扩展的分析服务监控你实时应用程序。 它可帮助你可以检测和诊断性能问题，可以了解用户实际执行的操作与你的应用。 它旨在为开发人员，目的是为了帮助您持续改进性能和可用性的服务或应用程序。 Application Insights 适用于 web/服务和独立上了多种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用。

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>使用 Application Insights QA 环境中的分析 Docker 应用

有关 Docker，你可以图表生命周期事件和 Application Insights 上的 Docker 容器的性能计数器。 你只需运行[应用程序 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)由于中你的主机，和它的容器将与其他 Docker 映像，以及主机中显示性能计数器。 此应用程序 Insights Docker 映像 (图 6-1） 可帮助你通过收集关于性能和活动的 Docker 主机 (即，Linux Vm)、 Docker 容器和运行的应用程序的遥测监视容器化应用程序在其中。

![示例](./media/image1.png)

图 6-1: Application Insights 监视 Docker 主机和容器

当你运行[应用程序 Insights Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)你的 Docker 主机，您受益于以下：

-   生命周期有关主机上运行的所有容器的遥测-启动、 停止和等。

-   所有容器的性能计数器： CPU、 内存、 网络使用情况，和的详细信息。

-   如果还安装[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中运行的应用，这些应用程序的所有遥测将都包含标识的容器和主机计算机的附加属性。 因此，例如，如果你有多个主机中运行的应用程序的实例，你将轻松能够筛选由主机应用遥测。

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>设置 Application Insights 监视 Docker 应用程序和 Docker 主机

若要创建 Application Insights 资源时，请执行后面的列表中显示的文章中的说明。 Azure 门户将为你创建所需的脚本。

-   **在 Application Insights 监视 Docker 应用程序：**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **在 Docker Hub 和 Github 的应用程序 Insights Docker 映像：**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) 和 <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **为 ASP.NET 配置 Application Insights 设置：**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **网页的应用程序 Insights:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](http://microsoft.com/oms)是简化的 IT 管理解决方案，提供日志分析、 自动化、 备份和站点恢复。 基于[查询](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/)中 Operations Management Suite，可以引发[警报](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts)并设置修正通过[Azure 自动化](https://docs.microsoft.com/azure/automation/)。 它还无缝集成与你现有的管理解决方案，以提供单一的窗格中的半透明视图。 Operations Management Suite 可帮助你管理和保护本地和云基础结构。

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](http://microsoft.com/oms) for Docker 容器解决方案

除了在其自身提供有价值的服务，操作管理套件容器解决方案可以管理和监视通过显示有关你的容器和容器主机在哪里，信息的 Docker 主机和容器容器正在运行或未通过，以及 Docker 守护程序和容器的日志发送到*stdout*和*stderr*。 它还显示容器和主机的性能指标，如 CPU、内存、网络和存储，帮助排除故障和找到具有干扰性的相邻容器。

![](./media/image2.png)

有关 Docker 容器的 Operations Management Suite 所示的图 6-2： 信息

Application Insights 和 Operations Management Suite 专注于监视活动;但是，Application Insights 更侧重于监视应用本身由于其 SDK 在应用内运行。 但是，Operations Management Suite 得多重点解决主机，基础结构以及它提供的同时，提供一个十分灵活，数据驱动搜索/查询系统在规模较大的日志的深入分析。

由于 Operations Management Suite 作为一项基于云的服务实现的你可以使其启动并正在运行快速基础结构服务中的最小投资。 新增功能，将自动传递，从而使您正在进行维护和升级的成本。

使用 Operations Management Suite 容器解决方案时，可以执行以下操作：

-   集中并关联数以百万计的大规模的 Docker 容器中的日志

-   请参阅有关在单个位置的所有容器主机的信息

-   了解哪些容器是运行，哪些映像它们正在运行，请和其中运行它们

-   快速诊断"干扰邻居"容器，可以在容器主机上会出现问题

-   请参阅在容器上的操作的审核跟踪

-   通过查看和搜索没有远程处理与 Docker 主机的集中式的日志疑难解答

-   查找可能是"干扰性邻居"，在主机上的使用过多资源的容器

-   查看集中式的 CPU、 内存、 存储和容器的网络使用情况和性能信息

-   生成测试与 Azure 自动化的 Docker 容器

你可以通过运行类似类型的查询来查看性能信息 = 性能，在图 6-3 中所示。

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

图 6-3： 性能度量值的 Operations Management Suite 所示的 Docker 主机

保存查询也是中 Operations Management Suite 的标准功能，可帮助你保持查询已发现非常有用，并在你的系统中发现趋势。

**详细信息** 若要查找有关安装和配置 Docker 容器中的解决方案[Operations Management Suite](http://microsoft.com/oms)，请转到<https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>。

>[!div class="step-by-step"]
[以前] (manage-production-docker-environments.md) [下一步] (.../key-takeaways/index.md)
