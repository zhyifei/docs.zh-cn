---
title: 监视容器化应用程序服务
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4bdc4470624ce6e905ab858a2bd8b607c8d3d646
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326460"
---
# <a name="monitor-containerized-application-services"></a>监视容器化应用程序服务

很重要的拆分为多个容器和微服务的应用程序具有一种方法来监视和分析应用程序的行为。

## <a name="microsoft-application-insights"></a>Microsoft Application Insights

[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是一项可扩展分析服务，用于监视实时应用程序。 它可帮助你检测和诊断性能问题以及了解用户实际使用你的应用。 它专为开发人员的意图是为了帮助您不断提高的性能和可用性的服务或应用程序。 Application Insights 适用于 web/服务和独立上各种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用程序。

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a>分析在 QA 环境中使用 Application Insights 的 Docker 应用

因为它涉及到 Docker，可以绘制生命周期事件和性能计数器从 Application Insights 上的 Docker 容器。 只需运行[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)如的容器中你的主机，它将显示性能计数器的主机也与其他 Docker 映像。 此应用程序见解 Docker 映像 (图 6-1） 可帮助你通过将收集有关性能和活动的 Docker 主机 (即，在 Linux Vm)、 Docker 容器和运行的应用程序的遥测数据来监视容器化应用程序在其中。

![示例](./media/image1.png)

图 6-1: Application Insights 监视 Docker 主机和容器

在运行时[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)Docker 主机上你利用以下：

-   有关在主机上运行的所有容器的遥测数据的生命周期-启动、 停止和其他操作。

-   所有容器的性能计数器： CPU、 内存、 网络使用情况和的详细信息。

-   如果还安装了[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中运行的应用，这些应用程序的所有遥测数据将具有识别容器和主机计算机的其他属性。 因此，例如，如果有多个主机中运行的应用的实例，您将轻松能够筛选由主机应用程序遥测数据。

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a>设置 Application Insights 监视 Docker 应用程序和 Docker 主机

若要创建 Application Insights 资源时，请遵循后面的列表中显示的文章中的说明。 Azure 门户将为您创建所需的脚本。

-   **在 Application Insights 中监视 Docker 应用程序：**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)

-   **在 Docker 中心和 Github 的应用程序见解 Docker 映像：**  
[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) 和 <https://github.com/Microsoft/ApplicationInsights-Docker>

-   **设置 ASP.NET 的 Application Insights:**  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   **适用于网页的 application Insights:**  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a>Microsoft Operations Management Suite

[Operations Management Suite](https://microsoft.com/oms)是简化的 IT 管理解决方案，提供了 log analytics、 自动化、 备份和站点恢复。 基于[查询](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/)，可以将 Operations Management Suite[警报](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts)并设置通过修正[Azure 自动化](https://docs.microsoft.com/azure/automation/)。 它也可无缝集成和现有的管理解决方案提供单个窗格中的玻璃视图。 Operations Management Suite 可帮助你管理和保护你的本地和云基础结构。

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a>[Operations Management Suite](https://microsoft.com/oms) Docker 的容器解决方案

除了自身提供有价值的服务，Operations Management Suite 容器解决方案可以管理和监视 Docker 主机和容器显示容器和容器主机在哪里的相关信息哪些容器正在运行或发生故障，以及 Docker 守护程序和容器的日志发送到*stdout*并*stderr*。 它还显示容器和主机的性能指标，如 CPU、内存、网络和存储，帮助排除故障和找到具有干扰性的相邻容器。

![](./media/image2.png)

有关通过 Operations Management Suite 所示的 Docker 容器的图 6-2： 信息

Application Insights 和 Operations Management Suite 监视活动; 重点但是，Application Insights 更侧重监视应用本身得益于其在应用中运行的 SDK。 但是，Operations Management Suite 更侧重于围绕这些主机，基础结构以及它提供一个非常灵活数据驱动搜索/查询系统时提供深度分析在规模较大的日志。

Operations Management Suite 作为基于云的服务实现，因为你可以使其启动并运行投入基础结构服务中的最小投资。 新功能，将自动传递，从而节省持续维护和升级成本。

使用 Operations Management Suite 容器解决方案，可以执行以下操作：

-   集中管理和关联数以百万计的大规模的 Docker 容器中的日志

-   请参阅有关在单个位置所有容器主机的信息

-   知道哪些容器正在运行，哪些映像运行它们，并运行位置

-   快速诊断可能会导致问题容器主机的"干扰邻居"容器

-   有关容器，请参阅操作的审核线索

-   通过查看和搜索而无需远程处理与 Docker 主机的集中化的日志进行故障排除

-   查找可能是"噪声邻居"和在主机上的使用过多资源的容器

-   查看集中式的 CPU、 内存、 存储和用于容器的网络使用情况和性能信息

-   生成 Docker 容器进行 Azure 自动化测试

您可以通过运行类似于类型的查询来查看性能信息 = 性能，在图 6-3 中所示。

![DockerPerfMetricsView](./media/image3.png){width="5.78625in" height="3.25in"}

图 6-3： 通过 Operations Management Suite 所示的 Docker 主机的性能指标

保存查询也是 Operations Management Suite 中的标准功能，可帮助你记录发现的有用和发现趋势在系统中的查询。

**详细信息** 若要查找有关安装和配置 Docker 容器中的解决方案[Operations Management Suite](https://microsoft.com/oms)，转到<https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>。

>[!div class="step-by-step"]
[上一页](manage-production-docker-environments.md)
[下一页](../key-takeaways/index.md)
