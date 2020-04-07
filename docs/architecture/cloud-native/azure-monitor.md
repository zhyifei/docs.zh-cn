---
title: Azure Monitor
description: 使用 Azure 监视器来查看系统正在运行。
ms.date: 02/05/2020
ms.openlocfilehash: 4e5ddba6c1c13dc65662a7748d4ae3a58a6a6f68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805634"
---
# <a name="azure-monitor"></a>Azure Monitor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

没有其他云提供商像 Azure 中那样成熟云应用程序监视解决方案。 Azure 监视器是一系列工具的一个总括名称，旨在提供对系统状态的可见性、对任何问题的见解以及应用程序的优化。

![Azure 监视器，一个工具的集合，用于深入了解云原生应用程序的工作原理。](./media/azure-monitor.png)
**图7-12**。 Azure 监视器，一个工具的集合，用于深入了解云原生应用程序的工作原理。

## <a name="gathering-logs-and-metrics"></a>收集日志和指标

任何监视解决方案的第一步是收集尽可能多的数据。 可以收集的数据越多，获得的见解就越深。 传统上，检测系统很困难。 简单网络管理协议（SNMP）是收集机器级信息的黄金标准协议，但它需要大量的知识和配置。 幸运的是，由于 Azure 监视器会自动收集最常见的指标，因此许多辛勤工作已消除。

应用程序级别指标和事件无法自动检测，因为它们特定于要部署的应用程序。 为了收集这些指标，可以使用[SDK 和 API](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics)直接报告此类信息，例如客户注册或完成订单时。 还可以捕获异常，并通过应用程序见解报告回 Azure 监视器。 SDK 支持云本机应用程序中找到的大多数语言，包括 Go、Python、JavaScript 和 .NET 语言。

收集有关应用程序状态信息的最终目标是确保您的最终用户获得良好的体验。 还有什么比进行[外部 Web 测试](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)更好的方法来判断用户是否遇到问题？ 这些测试可以像从世界各地的位置 ping 网站一样简单，也可以像让代理登录到网站并模拟用户操作一样简单。

## <a name="reporting-data"></a>报告数据

收集数据后，可以对其进行操作、汇总和绘制成图表，从而允许用户在出现问题时立即查看。 这些图表可以收集到仪表板或工作簿中，这是一个多页报告，旨在讲述有关系统某些方面的故事。

没有人工智能或机器学习，任何现代应用都不完整。 为此，[可以将数据传递到](https://www.youtube.com/watch?v=Cuza-I1g9tw)Azure 中的各种机器学习工具，以允许您提取其他将隐藏的趋势和信息。

应用程序见解提供了一种称为 Kusto 的强大查询语言，可用于查找记录、汇总记录甚至绘图图表。 例如，此查询将查找 2007 年 11 月的所有记录，按状态对其进行分组，并将前 10 条打印为饼图。

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![应用程序见解查询](./media/azure-monitor.png)
**图图 7-13**的结果。 应用程序见解查询的结果。

有一个[操场，尝试Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples)查询，这是一个梦幻般的地方，花一两个小时。 阅读[示例查询](https://docs.microsoft.com/azure/kusto/query/samples)也可以具有指导意义。

## <a name="dashboards"></a>仪表板

有几种不同的仪表板技术可用于显示 Azure 监视器中的信息。 也许最简单的方法是在应用程序见解中运行查询[，并将数据绘制到图表中](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)。

![嵌入在主 Azure 仪表板](./media/azure-monitor.png)
**图 7-14**中的应用程序见解图表的示例。 嵌入在主 Azure 仪表板中的应用程序见解图表的示例。

然后，这些图表可以通过使用仪表板功能适当地嵌入 Azure 门户中。 对于具有更严格要求（如能够向下钻取到多个数据层）的用户[，Azure](https://powerbi.microsoft.com/)监视器数据可用于 Power BI 。 Power BI 是一种行业领先的企业级商业智能工具，可以聚合来自许多不同的数据源的数据。

![例如 Power BI](./media/azure-monitor.png)
仪表板**图 7-15**。 例如 Power BI 仪表板。

## <a name="alerts"></a>警报

有时，数据仪表板不足。 如果没有人醒着观看仪表板，则问题处理甚至检测到仍可能需要数小时。 为此，Azure 监视器还提供一流的[警报解决方案](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)。 警报可以由多种条件触发，包括：

- 指标值
- 日志搜索查询
- 活动日志事件
- 基础 Azure 平台的运行状况
- 网址可用性测试

触发时，警报可以执行各种任务。 简单一方面，警报可能只是向邮件列表发送电子邮件通知或向个人发送短信。 涉及的警报越多，可能会触发 PagerDuty 等工具中的工作流，因为 PagerDuty 知道谁正在呼叫特定应用程序。 警报可以在[Microsoft Flow](https://flow.microsoft.com/)中触发操作，从而在工作流中释放几乎无限的可能性。

当识别警报的常见原因时，可以通过有关警报的常见原因以及解决这些问题的步骤的详细信息来增强警报。 高度成熟的云原生应用程序部署可能会选择启动自我修复任务，这些任务执行操作，例如从缩放集中删除故障节点或触发自动缩放活动。 最终，可能不再需要在凌晨 2 点叫醒待命人员来解决现场问题，因为系统将能够调整自身以补偿或至少跛行，直到第二天早上有人到达工作岗位。

Azure 监视器自动利用机器学习来了解已部署应用程序的正常操作参数。 这使它能够检测在其正常参数之外运行的服务。 例如，站点上典型的工作日流量可能是每分钟 10，000 个请求。 然后，在给定的一周内，请求数量突然达到每分钟非常不寻常的 20，000 个请求。 [智能检测](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics)将注意到这种偏离规范并触发警报。 同时，趋势分析足够聪明，以避免在流量负载预期时触发误报。

## <a name="references"></a>参考

- [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[上一页](monitoring-azure-kubernetes.md)
>[下一页](identity.md)
