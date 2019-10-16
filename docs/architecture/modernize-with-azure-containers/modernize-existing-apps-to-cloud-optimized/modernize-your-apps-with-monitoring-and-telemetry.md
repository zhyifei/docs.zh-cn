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
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="b2861-103">通过监视和遥测对应用进行现代化</span><span class="sxs-lookup"><span data-stu-id="b2861-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="b2861-104">在生产环境中运行应用程序时，请务必了解应用程序的执行情况。</span><span class="sxs-lookup"><span data-stu-id="b2861-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="b2861-105">它是否在高级别执行？</span><span class="sxs-lookup"><span data-stu-id="b2861-105">Is it performing at a high level?</span></span> <span data-ttu-id="b2861-106">用户是否遇到了错误，或是应用程序是否稳定和可靠？</span><span class="sxs-lookup"><span data-stu-id="b2861-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="b2861-107">需要丰富的性能监视、功能强大的警报和仪表板，帮助确保你的应用程序可用并按预期方式执行。</span><span class="sxs-lookup"><span data-stu-id="b2861-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="b2861-108">还需要能够快速查看是否存在问题，确定受影响的客户数量，并执行根本原因分析来查找并解决问题。</span><span class="sxs-lookup"><span data-stu-id="b2861-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="b2861-109">监视应用程序的 Application Insights</span><span class="sxs-lookup"><span data-stu-id="b2861-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="b2861-110">Application Insights 是适用于在多个平台上工作的 web 开发人员的可扩展应用程序性能管理（APM）服务。</span><span class="sxs-lookup"><span data-stu-id="b2861-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="b2861-111">用于监视实时 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2861-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="b2861-112">Application Insights 会自动检测性能异常。</span><span class="sxs-lookup"><span data-stu-id="b2861-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="b2861-113">它包含强大的分析工具，可帮助你诊断问题，并帮助你了解用户对你的应用程序的实际操作。</span><span class="sxs-lookup"><span data-stu-id="b2861-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="b2861-114">Application Insights 旨在帮助你持续提高性能和可用性。</span><span class="sxs-lookup"><span data-stu-id="b2861-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="b2861-115">它适用于各种平台，包括 .NET、node.js 和 J2EE，无论是在本地还是在云中托管。</span><span class="sxs-lookup"><span data-stu-id="b2861-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="b2861-116">Application Insights 与 DevOps 过程集成，并具有各种开发工具的连接点。</span><span class="sxs-lookup"><span data-stu-id="b2861-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="b2861-117">图4-10 显示了一个示例，说明了 Application Insights 如何监视应用程序以及它如何将这些见解呈现给仪表板。</span><span class="sxs-lookup"><span data-stu-id="b2861-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 监视仪表板的屏幕截图。](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

<span data-ttu-id="b2861-119">**图4-10。**</span><span class="sxs-lookup"><span data-stu-id="b2861-119">**Figure 4-10.**</span></span> <span data-ttu-id="b2861-120">Application Insights 监视仪表板</span><span class="sxs-lookup"><span data-stu-id="b2861-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="b2861-121">利用 Log Analytics 及其容器监视解决方案监视 Docker 基础结构</span><span class="sxs-lookup"><span data-stu-id="b2861-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="b2861-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)是[Microsoft Azure 总体监视解决方案](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2861-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="b2861-123">它也是[Operations Management Suite （OMS）](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)中的一项服务。</span><span class="sxs-lookup"><span data-stu-id="b2861-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="b2861-124">Log Analytics 监视云和本地环境（适用于本地的 OMS），以帮助维护可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="b2861-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="b2861-125">它收集由云和本地环境中的资源生成的数据以及其他监视工具的数据，以便跨多个源提供分析。</span><span class="sxs-lookup"><span data-stu-id="b2861-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="b2861-126">与 Azure 基础结构日志相关，Log Analytics 为 Azure 服务，从其他 Azure 服务（通过[Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)）、Azure Vm、Docker 容器以及本地或其他云基础结构引入日志和指标数据。</span><span class="sxs-lookup"><span data-stu-id="b2861-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="b2861-127">Log Analytics 在此数据的基础上提供灵活的日志搜索和现成的分析。</span><span class="sxs-lookup"><span data-stu-id="b2861-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="b2861-128">它提供丰富的工具，可用于跨源分析数据，允许跨所有日志进行复杂的查询，并且可以根据指定的条件主动发出警报。</span><span class="sxs-lookup"><span data-stu-id="b2861-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="b2861-129">您甚至可以在中央 Log Analytics 存储库中收集自定义数据，您可以在该存储库中对其进行查询和可视化。</span><span class="sxs-lookup"><span data-stu-id="b2861-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="b2861-130">你还可以利用 Log Analytics 内置解决方案，立即深入了解基础结构的安全性和功能。</span><span class="sxs-lookup"><span data-stu-id="b2861-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="b2861-131">可以通过 OMS 门户或 Azure 门户（在任何浏览器中运行）访问 Log Analytics，并提供对配置设置和多个工具的访问权限，以便分析和处理收集的数据。</span><span class="sxs-lookup"><span data-stu-id="b2861-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="b2861-132">Log Analytics 中的[容器监视解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)可帮助你在一个位置查看和管理 Docker 和 Windows 容器主机。</span><span class="sxs-lookup"><span data-stu-id="b2861-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="b2861-133">解决方案显示哪些容器正在运行、正在运行的容器映像和容器运行的位置。</span><span class="sxs-lookup"><span data-stu-id="b2861-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="b2861-134">您可以查看详细的审核信息，包括与容器一起使用的命令。</span><span class="sxs-lookup"><span data-stu-id="b2861-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="b2861-135">你还可以通过查看和搜索集中式日志来排查容器问题，而无需远程查看 Docker 或 Windows 主机。</span><span class="sxs-lookup"><span data-stu-id="b2861-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="b2861-136">可以在主机上找到可能有干扰并消耗过多资源的容器。</span><span class="sxs-lookup"><span data-stu-id="b2861-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="b2861-137">此外，还可以查看容器的集中式 CPU、内存、存储和网络使用情况以及性能信息。</span><span class="sxs-lookup"><span data-stu-id="b2861-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="b2861-138">在运行 Windows 的计算机上，可以集中和比较 Windows Server、Hyper-v 和 Docker 容器中的日志。</span><span class="sxs-lookup"><span data-stu-id="b2861-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="b2861-139">此解决方案支持以下容器协调器：</span><span class="sxs-lookup"><span data-stu-id="b2861-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="b2861-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="b2861-140">Docker Swarm</span></span>

- <span data-ttu-id="b2861-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="b2861-141">DC/OS</span></span>

- <span data-ttu-id="b2861-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b2861-142">Kubernetes</span></span>

- <span data-ttu-id="b2861-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="b2861-143">Red Hat OpenShift</span></span>

<span data-ttu-id="b2861-144">图4-11 显示了各种容器主机与代理和 OMS 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="b2861-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics 容器监视解决方案的屏幕截图。](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

<span data-ttu-id="b2861-146">**图4-11。**</span><span class="sxs-lookup"><span data-stu-id="b2861-146">**Figure 4-11.**</span></span> <span data-ttu-id="b2861-147">Log Analytics 容器监视解决方案</span><span class="sxs-lookup"><span data-stu-id="b2861-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="b2861-148">你可以使用 Log Analytics 容器监视解决方案来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b2861-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="b2861-149">查看单个位置中有关所有容器主机的信息。</span><span class="sxs-lookup"><span data-stu-id="b2861-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="b2861-150">了解正在运行的容器、正在运行的映像以及运行的位置。</span><span class="sxs-lookup"><span data-stu-id="b2861-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="b2861-151">查看容器上操作的审核线索。</span><span class="sxs-lookup"><span data-stu-id="b2861-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="b2861-152">通过查看和搜索集中式日志进行故障排除，而无需远程登录到 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="b2861-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="b2861-153">查找可能 "干扰邻居" 的容器，并在主机上消耗过多的资源。</span><span class="sxs-lookup"><span data-stu-id="b2861-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="b2861-154">查看容器的集中式 CPU、内存、存储和网络使用情况以及性能信息。</span><span class="sxs-lookup"><span data-stu-id="b2861-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b2861-155">其他资源</span><span class="sxs-lookup"><span data-stu-id="b2861-155">Additional resources</span></span>

- <span data-ttu-id="b2861-156">**Microsoft Azure 中的监视概述**</span><span class="sxs-lookup"><span data-stu-id="b2861-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="b2861-157">**什么是 Application Insights？**</span><span class="sxs-lookup"><span data-stu-id="b2861-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="b2861-158">**什么是 Log Analytics？**</span><span class="sxs-lookup"><span data-stu-id="b2861-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="b2861-159">**Azure Monitor 中的容器监视解决方案**</span><span class="sxs-lookup"><span data-stu-id="b2861-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="b2861-160">**Azure Monitor 概述**</span><span class="sxs-lookup"><span data-stu-id="b2861-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="b2861-161">**什么是 Operations Management Suite （OMS）？**</span><span class="sxs-lookup"><span data-stu-id="b2861-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="b2861-162">[上一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[下一页](life-cycle-ci-cd-pipelines-devops-tools.md)</span><span class="sxs-lookup"><span data-stu-id="b2861-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](life-cycle-ci-cd-pipelines-devops-tools.md)</span></span>
