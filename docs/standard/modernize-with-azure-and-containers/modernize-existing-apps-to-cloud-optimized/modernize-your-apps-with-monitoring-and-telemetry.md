---
title: 通过监视和遥测对应用进行现代化
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |通过监视和遥测对应用进行现代化
ms.date: 04/30/2018
ms.openlocfilehash: 5bffb336234f63dca150acc9ef31f9efa2e3937b
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758617"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="7b1b2-103">通过监视和遥测对应用进行现代化</span><span class="sxs-lookup"><span data-stu-id="7b1b2-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="7b1b2-104">在生产环境中运行应用程序时，很重要，必须了解你的应用程序的执行有关的见解。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="7b1b2-105">它执行在高级别？</span><span class="sxs-lookup"><span data-stu-id="7b1b2-105">Is it performing at a high level?</span></span> <span data-ttu-id="7b1b2-106">用户收到错误，或是稳定和可靠的应用程序？</span><span class="sxs-lookup"><span data-stu-id="7b1b2-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="7b1b2-107">需要丰富的性能监视、 功能强大警报和仪表板，帮助确保你的应用程序可用并且按预期执行。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="7b1b2-108">此外需要能够快速查看是否有问题，确定多少客户会受到影响，并执行根本原因分析，以查找并修复该问题。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="7b1b2-109">监视应用程序使用 Application Insights</span><span class="sxs-lookup"><span data-stu-id="7b1b2-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="7b1b2-110">Application Insights 是面向 web 开发人员可以在多个平台上的可扩展应用程序性能管理 (APM) 服务。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="7b1b2-111">使用它监视实时 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="7b1b2-112">Application Insights 会自动检测性能异常。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="7b1b2-113">它包括强大的分析工具来帮助你诊断问题，并帮助你了解用户实际使用你的应用。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="7b1b2-114">Application Insights 旨在帮助持续提高性能和可用性。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="7b1b2-115">它在各种平台，包括.NET、 Node.js 和 J2EE，是否适用于应用托管在本地或云中。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="7b1b2-116">Application Insights 集成，与您的 DevOps 流程，并具有与各种开发工具的连接点。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="7b1b2-117">图 4-10 演示了如何 Application Insights 监视你的应用程序和它如何到仪表板中显示这些见解的示例。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 监视仪表板](./media/image10.png)

> <span data-ttu-id="7b1b2-119">**图 4-10。**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-119">**Figure 4-10.**</span></span> <span data-ttu-id="7b1b2-120">Application Insights 监视仪表板</span><span class="sxs-lookup"><span data-stu-id="7b1b2-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="7b1b2-121">监视 Docker 基础结构与 Log Analytics 和其容器监视解决方案</span><span class="sxs-lookup"><span data-stu-id="7b1b2-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="7b1b2-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)属于[Microsoft Azure 总体监视解决方案](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="7b1b2-123">它也是服务[Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="7b1b2-124">Log Analytics 监视云并在本地环境 (在内部部署的 OMS) 可帮助维护可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="7b1b2-125">它可以收集资源和其他监视工具来跨多个源提供分析云和本地环境中生成的数据。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="7b1b2-126">相对于 Azure 基础结构日志，Log Analytics 作为 Azure 服务，引入日志和指标数据从其他 Azure 服务 (通过[Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor))，Azure Vm、 Docker 容器，并在本地或其他云基础结构。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="7b1b2-127">Log Analytics 提供灵活的日志搜索和现成的-分析此数据的基础。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="7b1b2-128">它提供了丰富的工具，可用于跨源分析数据，这样复杂的查询将针对所有日志，并可以主动发出警报根据指定的条件。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="7b1b2-129">甚至可以收集自定义数据中心 Log Analytics 存储库中，您可以在其中查询和可视化这些数据。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="7b1b2-130">您还可以充分利用 Log Analytics 内置解决方案，以立即深入了解安全性和基础结构的功能。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="7b1b2-131">可以通过 OMS 门户中或在任何浏览器中运行，在 Azure 门户访问 Log Analytics，并提供可以访问配置设置和多个工具来分析和处理收集的数据。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="7b1b2-132">[容器监视解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)中 Log Analytics 可帮助您查看和管理 Docker 和 Windows 容器主机在一个位置。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="7b1b2-133">此解决方案显示哪些容器正在运行，哪些容器映像运行它们，以及运行容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="7b1b2-134">可以查看详细的审核信息，包括与容器一起使用的命令。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="7b1b2-135">此外可以通过查看和搜索集中式的日志，而无需远程查看 Docker 或 Windows 的主机来排查容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="7b1b2-136">您可以找到可能会干扰并花费较长的主机上的过多资源的容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="7b1b2-137">此外，您可以查看集中式的 CPU、 内存、 存储和网络使用情况和性能信息，为容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="7b1b2-138">在运行 Windows 的计算机，您可以集中并比较日志从 Windows Server HYPER-V 和 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="7b1b2-139">该解决方案支持以下容器业务流程协调程序：</span><span class="sxs-lookup"><span data-stu-id="7b1b2-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="7b1b2-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="7b1b2-140">Docker Swarm</span></span>

- <span data-ttu-id="7b1b2-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="7b1b2-141">DC/OS</span></span>

- <span data-ttu-id="7b1b2-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7b1b2-142">Kubernetes</span></span>

- <span data-ttu-id="7b1b2-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="7b1b2-143">Red Hat OpenShift</span></span>

<span data-ttu-id="7b1b2-144">图 4-11 显示了各种容器主机和代理和 OMS 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics 容器监视解决方案](./media/image11.png)

> <span data-ttu-id="7b1b2-146">**图 4-11。**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-146">**Figure 4-11.**</span></span> <span data-ttu-id="7b1b2-147">Log Analytics 容器监视解决方案</span><span class="sxs-lookup"><span data-stu-id="7b1b2-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="7b1b2-148">可以使用的 Log Analytics 容器监视解决方案：</span><span class="sxs-lookup"><span data-stu-id="7b1b2-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="7b1b2-149">请参阅有关在单个位置所有容器主机的信息。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="7b1b2-150">知道哪些容器正在运行，哪些映像运行它们，并运行位置。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="7b1b2-151">请参阅在容器上的操作的审核线索。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="7b1b2-152">通过查看和搜索而无需远程登录到 Docker 主机的集中化的日志进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="7b1b2-153">查找可能是"噪声邻居，"并在消耗过多资源的主机上的容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="7b1b2-154">查看集中式的 CPU、 内存、 存储和网络使用情况和性能信息，为容器。</span><span class="sxs-lookup"><span data-stu-id="7b1b2-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b1b2-155">其他资源</span><span class="sxs-lookup"><span data-stu-id="7b1b2-155">Additional resources</span></span>

- <span data-ttu-id="7b1b2-156">**Microsoft Azure 中的监视概述**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="7b1b2-157">**什么是 Application Insights？**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="7b1b2-158">**什么是 Log Analytics？**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="7b1b2-159">**Azure Monitor 中的容器监视解决方案**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="7b1b2-160">**Azure Monitor 概述**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="7b1b2-161">**什么是 Operations Management Suite (OMS)？**</span><span class="sxs-lookup"><span data-stu-id="7b1b2-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="7b1b2-162">[上一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[下一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7b1b2-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
