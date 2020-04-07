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
# <a name="azure-monitor"></a><span data-ttu-id="a1896-103">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="a1896-103">Azure Monitor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a1896-104">没有其他云提供商像 Azure 中那样成熟云应用程序监视解决方案。</span><span class="sxs-lookup"><span data-stu-id="a1896-104">No other cloud provider has as mature of a cloud application monitoring solution as that found in Azure.</span></span> <span data-ttu-id="a1896-105">Azure 监视器是一系列工具的一个总括名称，旨在提供对系统状态的可见性、对任何问题的见解以及应用程序的优化。</span><span class="sxs-lookup"><span data-stu-id="a1896-105">Azure Monitor is an umbrella name for a collection of tools designed to provide visibility into the state of your system, insights into any problems, and optimization of your application.</span></span>

<span data-ttu-id="a1896-106">![Azure 监视器，一个工具的集合，用于深入了解云原生应用程序的工作原理。](./media/azure-monitor.png)
**图7-12**。</span><span class="sxs-lookup"><span data-stu-id="a1896-106">![Azure Monitor, a collection to tools to provide insight into how a cloud-native application is functioning.](./media/azure-monitor.png)
**Figure 7-12**.</span></span> <span data-ttu-id="a1896-107">Azure 监视器，一个工具的集合，用于深入了解云原生应用程序的工作原理。</span><span class="sxs-lookup"><span data-stu-id="a1896-107">Azure Monitor, a collection to tools to provide insight into how a cloud-native application is functioning.</span></span>

## <a name="gathering-logs-and-metrics"></a><span data-ttu-id="a1896-108">收集日志和指标</span><span class="sxs-lookup"><span data-stu-id="a1896-108">Gathering logs and metrics</span></span>

<span data-ttu-id="a1896-109">任何监视解决方案的第一步是收集尽可能多的数据。</span><span class="sxs-lookup"><span data-stu-id="a1896-109">The first step in any monitoring solution is to gather as much data as possible.</span></span> <span data-ttu-id="a1896-110">可以收集的数据越多，获得的见解就越深。</span><span class="sxs-lookup"><span data-stu-id="a1896-110">The more data that can be gathered, the deeper the insights that can be obtained.</span></span> <span data-ttu-id="a1896-111">传统上，检测系统很困难。</span><span class="sxs-lookup"><span data-stu-id="a1896-111">Instrumenting systems has traditionally been difficult.</span></span> <span data-ttu-id="a1896-112">简单网络管理协议（SNMP）是收集机器级信息的黄金标准协议，但它需要大量的知识和配置。</span><span class="sxs-lookup"><span data-stu-id="a1896-112">Simple Network Management Protocol (SNMP) was the gold standard protocol for collecting machine level information but it required a great deal of knowledge and configuring.</span></span> <span data-ttu-id="a1896-113">幸运的是，由于 Azure 监视器会自动收集最常见的指标，因此许多辛勤工作已消除。</span><span class="sxs-lookup"><span data-stu-id="a1896-113">Fortunately, much of this hard work has been eliminated as the most common metrics are gathered automatically by Azure Monitor.</span></span>

<span data-ttu-id="a1896-114">应用程序级别指标和事件无法自动检测，因为它们特定于要部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1896-114">Application level metrics and events aren't possible to instrument automatically because they're specific to the application being deployed.</span></span> <span data-ttu-id="a1896-115">为了收集这些指标，可以使用[SDK 和 API](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics)直接报告此类信息，例如客户注册或完成订单时。</span><span class="sxs-lookup"><span data-stu-id="a1896-115">In order to gather these metrics, there are [SDKs and APIs available](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) to directly report such information, such as when a customer signs up or completes an order.</span></span> <span data-ttu-id="a1896-116">还可以捕获异常，并通过应用程序见解报告回 Azure 监视器。</span><span class="sxs-lookup"><span data-stu-id="a1896-116">Exceptions can also be captured and reported back into Azure Monitor via Application Insights.</span></span> <span data-ttu-id="a1896-117">SDK 支持云本机应用程序中找到的大多数语言，包括 Go、Python、JavaScript 和 .NET 语言。</span><span class="sxs-lookup"><span data-stu-id="a1896-117">The SDKs support most every language found in Cloud Native Applications including Go, Python, JavaScript, and the .NET languages.</span></span>

<span data-ttu-id="a1896-118">收集有关应用程序状态信息的最终目标是确保您的最终用户获得良好的体验。</span><span class="sxs-lookup"><span data-stu-id="a1896-118">The ultimate goal of gathering information about the state of your application is to ensure that your end users have a good experience.</span></span> <span data-ttu-id="a1896-119">还有什么比进行[外部 Web 测试](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)更好的方法来判断用户是否遇到问题？</span><span class="sxs-lookup"><span data-stu-id="a1896-119">What better way to tell if users are experiencing issues than doing [outside-in web tests](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)?</span></span> <span data-ttu-id="a1896-120">这些测试可以像从世界各地的位置 ping 网站一样简单，也可以像让代理登录到网站并模拟用户操作一样简单。</span><span class="sxs-lookup"><span data-stu-id="a1896-120">These tests can be as simple as pinging your website from locations around the world or as involved as having agents log into the site and simulate user actions.</span></span>

## <a name="reporting-data"></a><span data-ttu-id="a1896-121">报告数据</span><span class="sxs-lookup"><span data-stu-id="a1896-121">Reporting data</span></span>

<span data-ttu-id="a1896-122">收集数据后，可以对其进行操作、汇总和绘制成图表，从而允许用户在出现问题时立即查看。</span><span class="sxs-lookup"><span data-stu-id="a1896-122">Once the data is gathered, it can be manipulated, summarized, and plotted into charts, which allow users to instantly see when there are problems.</span></span> <span data-ttu-id="a1896-123">这些图表可以收集到仪表板或工作簿中，这是一个多页报告，旨在讲述有关系统某些方面的故事。</span><span class="sxs-lookup"><span data-stu-id="a1896-123">These charts can be gathered into dashboards or into Workbooks, a multi-page report designed to tell a story about some aspect of the system.</span></span>

<span data-ttu-id="a1896-124">没有人工智能或机器学习，任何现代应用都不完整。</span><span class="sxs-lookup"><span data-stu-id="a1896-124">No modern application would be complete without some artificial intelligence or machine learning.</span></span> <span data-ttu-id="a1896-125">为此，[可以将数据传递到](https://www.youtube.com/watch?v=Cuza-I1g9tw)Azure 中的各种机器学习工具，以允许您提取其他将隐藏的趋势和信息。</span><span class="sxs-lookup"><span data-stu-id="a1896-125">To this end, data [can be passed](https://www.youtube.com/watch?v=Cuza-I1g9tw) to the various machine learning tools in Azure to allow you to extract trends and information that would otherwise be hidden.</span></span>

<span data-ttu-id="a1896-126">应用程序见解提供了一种称为 Kusto 的强大查询语言，可用于查找记录、汇总记录甚至绘图图表。</span><span class="sxs-lookup"><span data-stu-id="a1896-126">Application Insights provides a powerful query language called Kusto that can be used to find records, summarize them, and even plot charts.</span></span> <span data-ttu-id="a1896-127">例如，此查询将查找 2007 年 11 月的所有记录，按状态对其进行分组，并将前 10 条打印为饼图。</span><span class="sxs-lookup"><span data-stu-id="a1896-127">For instance, this query will locate all the records for the month of November 2007, group them by state, and plot the top 10 as a pie chart.</span></span>

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

<span data-ttu-id="a1896-128">![应用程序见解查询](./media/azure-monitor.png)
**图图 7-13**的结果。</span><span class="sxs-lookup"><span data-stu-id="a1896-128">![The result of the Application Insights Query](./media/azure-monitor.png)
**Figure 7-13**.</span></span> <span data-ttu-id="a1896-129">应用程序见解查询的结果。</span><span class="sxs-lookup"><span data-stu-id="a1896-129">The result of the Application Insights Query.</span></span>

<span data-ttu-id="a1896-130">有一个[操场，尝试Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples)查询，这是一个梦幻般的地方，花一两个小时。</span><span class="sxs-lookup"><span data-stu-id="a1896-130">There is a [playground for experimenting with Kusto](https://dataexplorer.azure.com/clusters/help/databases/Samples) queries, which is a fantastic place to spend an hour or two.</span></span> <span data-ttu-id="a1896-131">阅读[示例查询](https://docs.microsoft.com/azure/kusto/query/samples)也可以具有指导意义。</span><span class="sxs-lookup"><span data-stu-id="a1896-131">Reading [sample queries](https://docs.microsoft.com/azure/kusto/query/samples) can also be instructive.</span></span>

## <a name="dashboards"></a><span data-ttu-id="a1896-132">仪表板</span><span class="sxs-lookup"><span data-stu-id="a1896-132">Dashboards</span></span>

<span data-ttu-id="a1896-133">有几种不同的仪表板技术可用于显示 Azure 监视器中的信息。</span><span class="sxs-lookup"><span data-stu-id="a1896-133">There are several different dashboard technologies that may be used to surface the information from Azure Monitor.</span></span> <span data-ttu-id="a1896-134">也许最简单的方法是在应用程序见解中运行查询[，并将数据绘制到图表中](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)。</span><span class="sxs-lookup"><span data-stu-id="a1896-134">Perhaps the simplest is to just run queries in Application Insights and [plot the data into a chart](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards).</span></span>

<span data-ttu-id="a1896-135">![嵌入在主 Azure 仪表板](./media/azure-monitor.png)
**图 7-14**中的应用程序见解图表的示例。</span><span class="sxs-lookup"><span data-stu-id="a1896-135">![An example of Application Insights charts embedded in the main Azure Dashboard](./media/azure-monitor.png)
**Figure 7-14**.</span></span> <span data-ttu-id="a1896-136">嵌入在主 Azure 仪表板中的应用程序见解图表的示例。</span><span class="sxs-lookup"><span data-stu-id="a1896-136">An example of Application Insights charts embedded in the main Azure Dashboard.</span></span>

<span data-ttu-id="a1896-137">然后，这些图表可以通过使用仪表板功能适当地嵌入 Azure 门户中。</span><span class="sxs-lookup"><span data-stu-id="a1896-137">These charts can then be embedded in the Azure portal proper through use of the dashboard feature.</span></span> <span data-ttu-id="a1896-138">对于具有更严格要求（如能够向下钻取到多个数据层）的用户[，Azure](https://powerbi.microsoft.com/)监视器数据可用于 Power BI 。</span><span class="sxs-lookup"><span data-stu-id="a1896-138">For users with more exacting requirements, such as being able to drill down into several tiers of data, Azure Monitor data is available to [Power BI](https://powerbi.microsoft.com/).</span></span> <span data-ttu-id="a1896-139">Power BI 是一种行业领先的企业级商业智能工具，可以聚合来自许多不同的数据源的数据。</span><span class="sxs-lookup"><span data-stu-id="a1896-139">Power BI is an industry-leading, enterprise class, business intelligence tool that can aggregate data from many different data sources.</span></span>

<span data-ttu-id="a1896-140">![例如 Power BI](./media/azure-monitor.png)
仪表板**图 7-15**。</span><span class="sxs-lookup"><span data-stu-id="a1896-140">![An example Power BI dashboard](./media/azure-monitor.png)
**Figure 7-15**.</span></span> <span data-ttu-id="a1896-141">例如 Power BI 仪表板。</span><span class="sxs-lookup"><span data-stu-id="a1896-141">An example Power BI dashboard.</span></span>

## <a name="alerts"></a><span data-ttu-id="a1896-142">警报</span><span class="sxs-lookup"><span data-stu-id="a1896-142">Alerts</span></span>

<span data-ttu-id="a1896-143">有时，数据仪表板不足。</span><span class="sxs-lookup"><span data-stu-id="a1896-143">Sometimes, having data dashboards is insufficient.</span></span> <span data-ttu-id="a1896-144">如果没有人醒着观看仪表板，则问题处理甚至检测到仍可能需要数小时。</span><span class="sxs-lookup"><span data-stu-id="a1896-144">If nobody is awake to watch the dashboards, then it can still be many hours before a problem is addressed, or even detected.</span></span> <span data-ttu-id="a1896-145">为此，Azure 监视器还提供一流的[警报解决方案](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)。</span><span class="sxs-lookup"><span data-stu-id="a1896-145">To this end, Azure Monitor also provides a top notch [alerting solution](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview).</span></span> <span data-ttu-id="a1896-146">警报可以由多种条件触发，包括：</span><span class="sxs-lookup"><span data-stu-id="a1896-146">Alerts can be triggered by a wide range of conditions including:</span></span>

- <span data-ttu-id="a1896-147">指标值</span><span class="sxs-lookup"><span data-stu-id="a1896-147">Metric values</span></span>
- <span data-ttu-id="a1896-148">日志搜索查询</span><span class="sxs-lookup"><span data-stu-id="a1896-148">Log search queries</span></span>
- <span data-ttu-id="a1896-149">活动日志事件</span><span class="sxs-lookup"><span data-stu-id="a1896-149">Activity Log events</span></span>
- <span data-ttu-id="a1896-150">基础 Azure 平台的运行状况</span><span class="sxs-lookup"><span data-stu-id="a1896-150">Health of the underlying Azure platform</span></span>
- <span data-ttu-id="a1896-151">网址可用性测试</span><span class="sxs-lookup"><span data-stu-id="a1896-151">Tests for web site availability</span></span>

<span data-ttu-id="a1896-152">触发时，警报可以执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="a1896-152">When triggered, the alerts can perform a wide variety of tasks.</span></span> <span data-ttu-id="a1896-153">简单一方面，警报可能只是向邮件列表发送电子邮件通知或向个人发送短信。</span><span class="sxs-lookup"><span data-stu-id="a1896-153">On the simple side, the alerts may just send an e-mail notification to a mailing list or a text message to an individual.</span></span> <span data-ttu-id="a1896-154">涉及的警报越多，可能会触发 PagerDuty 等工具中的工作流，因为 PagerDuty 知道谁正在呼叫特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="a1896-154">More involved alerts might trigger a workflow in a tool such as PagerDuty, which is aware of who is on call for a particular application.</span></span> <span data-ttu-id="a1896-155">警报可以在[Microsoft Flow](https://flow.microsoft.com/)中触发操作，从而在工作流中释放几乎无限的可能性。</span><span class="sxs-lookup"><span data-stu-id="a1896-155">Alerts can trigger actions in [Microsoft Flow](https://flow.microsoft.com/) unlocking near limitless possibilities for workflows.</span></span>

<span data-ttu-id="a1896-156">当识别警报的常见原因时，可以通过有关警报的常见原因以及解决这些问题的步骤的详细信息来增强警报。</span><span class="sxs-lookup"><span data-stu-id="a1896-156">As common causes of alerts are identified, the alerts can be enhanced with details about the common causes of the alerts and the steps to take to resolve them.</span></span> <span data-ttu-id="a1896-157">高度成熟的云原生应用程序部署可能会选择启动自我修复任务，这些任务执行操作，例如从缩放集中删除故障节点或触发自动缩放活动。</span><span class="sxs-lookup"><span data-stu-id="a1896-157">Highly mature cloud-native application deployments may opt to kick off self-healing tasks, which perform actions such as removing failing nodes from a scale set or triggering an autoscaling activity.</span></span> <span data-ttu-id="a1896-158">最终，可能不再需要在凌晨 2 点叫醒待命人员来解决现场问题，因为系统将能够调整自身以补偿或至少跛行，直到第二天早上有人到达工作岗位。</span><span class="sxs-lookup"><span data-stu-id="a1896-158">Eventually it may no longer be necessary to wake up on-call personnel at 2AM to resolve a live-site issue as the system will be able to adjust itself to compensate or at least limp along until somebody arrives at work the next morning.</span></span>

<span data-ttu-id="a1896-159">Azure 监视器自动利用机器学习来了解已部署应用程序的正常操作参数。</span><span class="sxs-lookup"><span data-stu-id="a1896-159">Azure Monitor automatically leverages machine learning to understand the normal operating parameters of deployed applications.</span></span> <span data-ttu-id="a1896-160">这使它能够检测在其正常参数之外运行的服务。</span><span class="sxs-lookup"><span data-stu-id="a1896-160">This enables it to detect services that are operating outside of their normal parameters.</span></span> <span data-ttu-id="a1896-161">例如，站点上典型的工作日流量可能是每分钟 10，000 个请求。</span><span class="sxs-lookup"><span data-stu-id="a1896-161">For instance, the typical weekday traffic on the site might be 10,000 requests per minute.</span></span> <span data-ttu-id="a1896-162">然后，在给定的一周内，请求数量突然达到每分钟非常不寻常的 20，000 个请求。</span><span class="sxs-lookup"><span data-stu-id="a1896-162">And then, on a given week, suddenly the number of requests hits a highly unusual 20,000 requests per minute.</span></span> <span data-ttu-id="a1896-163">[智能检测](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics)将注意到这种偏离规范并触发警报。</span><span class="sxs-lookup"><span data-stu-id="a1896-163">[Smart Detection](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) will notice this deviation from the norm and trigger an alert.</span></span> <span data-ttu-id="a1896-164">同时，趋势分析足够聪明，以避免在流量负载预期时触发误报。</span><span class="sxs-lookup"><span data-stu-id="a1896-164">At the same time, the trend analysis is smart enough to avoid firing false positives when the traffic load is expected.</span></span>

## <a name="references"></a><span data-ttu-id="a1896-165">参考</span><span class="sxs-lookup"><span data-stu-id="a1896-165">References</span></span>

- [<span data-ttu-id="a1896-166">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="a1896-166">Azure Monitor</span></span>](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
><span data-ttu-id="a1896-167">[上一页](monitoring-azure-kubernetes.md)
>[下一页](identity.md)</span><span class="sxs-lookup"><span data-stu-id="a1896-167">[Previous](monitoring-azure-kubernetes.md)
[Next](identity.md)</span></span>
