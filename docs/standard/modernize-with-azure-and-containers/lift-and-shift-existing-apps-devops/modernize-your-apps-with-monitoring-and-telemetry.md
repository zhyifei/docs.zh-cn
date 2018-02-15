---
title: "更新你的应用的监视和遥测"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |更新你的应用的监视和遥测"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1535951eb648deab17cf8c2fe64db6ddf7df4cb5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="5ae8e-103">更新你的应用的监视和遥测</span><span class="sxs-lookup"><span data-stu-id="5ae8e-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="5ae8e-104">在生产环境中运行应用程序时，很重要，具有有关如何执行你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="5ae8e-105">它正在执行在高级别？</span><span class="sxs-lookup"><span data-stu-id="5ae8e-105">Is it performing at a high level?</span></span> <span data-ttu-id="5ae8e-106">用户收到错误，或是稳定且可靠的应用程序？</span><span class="sxs-lookup"><span data-stu-id="5ae8e-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="5ae8e-107">你需要丰富的性能监视、 功能强大警报和仪表板，以帮助确保你的应用程序可用并按预期执行。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="5ae8e-108">你还需要能够快速查看是否有问题，确定有多少客户受到影响，并执行根本原因分析，以查找并修复该问题。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="5ae8e-109">监视你的应用程序使用 Application Insights</span><span class="sxs-lookup"><span data-stu-id="5ae8e-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="5ae8e-110">Application Insights 是一个可扩展的应用程序性能管理 (APM) 服务的 web 开发人员在多个平台上工作。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="5ae8e-111">使用它监视实时 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="5ae8e-112">Application Insights 自动检测性能异常。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="5ae8e-113">它包括强大的分析工具来帮助你诊断问题，并帮助你了解用户实际执行的操作与你的应用。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="5ae8e-114">Application Insights 旨在帮助你持续改进性能和可用性。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="5ae8e-115">它在各种平台，包括.NET、 Node.js 和 J2EE，是否适用于应用程序托管在本地或云中。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="5ae8e-116">Application Insights 与您的 DevOps 流程，集成，具有到不同的开发工具的连接点。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="5ae8e-117">图 4-10 显示如何 Application Insights 监视你的应用程序和它如何到仪表板中显示这些 insights 的示例。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 监视仪表板](./media/image10.png)

> <span data-ttu-id="5ae8e-119">**图 4-10。**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-119">**Figure 4-10.**</span></span> <span data-ttu-id="5ae8e-120">Application Insights 监视仪表板</span><span class="sxs-lookup"><span data-stu-id="5ae8e-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="5ae8e-121">监视使用日志分析和其容器监视解决方案 Docker 基础结构</span><span class="sxs-lookup"><span data-stu-id="5ae8e-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="5ae8e-122">[Azure 日志分析](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)属于[总体监视解决方案的 Microsoft Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="5ae8e-123">它也是一服务[Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="5ae8e-124">日志分析监视云，并且本地环境 (对于本地 OMS) 可帮助维护可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="5ae8e-125">它收集生成的资源在云和本地环境中和从其他监视工具，以跨多个源提供的分析数据。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="5ae8e-126">与 Azure 基础结构日志，有关日志分析，作为一项 Azure 服务，引入来自其他 Azure 服务的日志和度量值数据 (通过[Azure 监视器](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor))，Azure 虚拟机、 Docker 容器和在本地或其他云基础结构。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="5ae8e-127">日志分析提供灵活的日志搜索和扩展的框分析基于此数据。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="5ae8e-128">它提供了丰富的工具，你可以使用跨源分析数据，它允许在所有日志之间的复杂的查询而可以主动警报基于指定的条件。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="5ae8e-129">你甚至可以收集中央日志分析存储库中，可以在此查询，并可视化这些数据的自定义数据。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="5ae8e-130">你还可以考虑利用日志分析内置解决方案，以立即深入了解安全和基础结构的功能。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="5ae8e-131">你可以访问日志分析通过 OMS 门户或 Azure 门户中，在任何浏览器中运行，并提供了你有权访问配置设置和多个工具来分析和处理收集的数据。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="5ae8e-132">[容器监视解决方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)中日志分析可帮助你查看和管理 Docker 和 Windows 容器主机在单个位置。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="5ae8e-133">解决方案显示哪些容器运行，哪些容器映像它们正在运行，请和其中运行容器。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="5ae8e-134">你可以查看详细的审核信息，包括与容器正在使用的命令。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="5ae8e-135">此外可以通过查看和搜索而无需远程查看 Docker 或 Windows 主机的集中式的日志来排除容器。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="5ae8e-136">你可以找到可能的主机上的干扰和使用过多资源的容器。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="5ae8e-137">此外，你可以查看集中式的 CPU、 内存、 存储和网络使用情况和的容器的性能信息。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="5ae8e-138">在运行 Windows 的计算机，可以集中并比较日志从 Windows Server HYPER-V 和 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="5ae8e-139">解决方案支持以下容器 orchestrators:</span><span class="sxs-lookup"><span data-stu-id="5ae8e-139">The solution supports the following container orchestrators:</span></span>

-   <span data-ttu-id="5ae8e-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="5ae8e-140">Docker Swarm</span></span>

-   <span data-ttu-id="5ae8e-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="5ae8e-141">DC/OS</span></span>

-   <span data-ttu-id="5ae8e-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5ae8e-142">Kubernetes</span></span>

-   <span data-ttu-id="5ae8e-143">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5ae8e-143">Service Fabric</span></span>

-   <span data-ttu-id="5ae8e-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="5ae8e-144">Red Hat OpenShift</span></span>

<span data-ttu-id="5ae8e-145">图 4-11 显示各种容器主机和代理和 OMS 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![日志分析容器监视解决方案](./media/image11.png)

> <span data-ttu-id="5ae8e-147">**图 4-11。**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-147">**Figure 4-11.**</span></span> <span data-ttu-id="5ae8e-148">日志分析容器监视解决方案</span><span class="sxs-lookup"><span data-stu-id="5ae8e-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="5ae8e-149">你可以使用的日志分析容器监视解决方案：</span><span class="sxs-lookup"><span data-stu-id="5ae8e-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

-   <span data-ttu-id="5ae8e-150">请参阅有关在单个位置的所有容器主机的信息。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-150">See information about all container hosts in a single location.</span></span>

-   <span data-ttu-id="5ae8e-151">了解哪些容器是运行，哪些映像它们正在运行，请和其中运行它们。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-151">Know which containers are running, what image they're running, and where they're running.</span></span>

-   <span data-ttu-id="5ae8e-152">请参阅在容器上的操作的审核痕迹。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-152">See an audit trail for actions on containers.</span></span>

-   <span data-ttu-id="5ae8e-153">通过查看和搜索没有远程登录到 Docker 主机的集中式的日志排查问题。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

-   <span data-ttu-id="5ae8e-154">查找容器可能是"干扰性邻居，"并使用主机上的过多资源。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

-   <span data-ttu-id="5ae8e-155">查看集中式的 CPU、 内存、 存储和网络使用情况和的容器的性能信息。</span><span class="sxs-lookup"><span data-stu-id="5ae8e-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5ae8e-156">其他资源</span><span class="sxs-lookup"><span data-stu-id="5ae8e-156">Additional resources</span></span>

-   <span data-ttu-id="5ae8e-157">**在 Microsoft Azure 中监视概述**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-157">**Overview of monitoring in Microsoft Azure**</span></span>

[<span data-ttu-id="5ae8e-158">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview</span><span class="sxs-lookup"><span data-stu-id="5ae8e-158">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview</span></span>](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   <span data-ttu-id="5ae8e-159">**Application Insights 是什么？**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-159">**What is Application Insights?**</span></span>

[<span data-ttu-id="5ae8e-160">https://docs.microsoft.com/azure/application-insights/app-insights-overview</span><span class="sxs-lookup"><span data-stu-id="5ae8e-160">https://docs.microsoft.com/azure/application-insights/app-insights-overview</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   <span data-ttu-id="5ae8e-161">**日志分析是什么？**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-161">**What is Log Analytics?**</span></span>

[<span data-ttu-id="5ae8e-162">https://docs.microsoft.com/azure/log-analytics/log-analytics-overview</span><span class="sxs-lookup"><span data-stu-id="5ae8e-162">https://docs.microsoft.com/azure/log-analytics/log-analytics-overview</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   <span data-ttu-id="5ae8e-163">**容器监视解决方案中日志分析**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-163">**Container Monitoring solution in Log Analytics**</span></span>

[<span data-ttu-id="5ae8e-164">https://docs.microsoft.com/azure/log-analytics/log-analytics-containers</span><span class="sxs-lookup"><span data-stu-id="5ae8e-164">https://docs.microsoft.com/azure/log-analytics/log-analytics-containers</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   <span data-ttu-id="5ae8e-165">Azure 监视器概述</span><span class="sxs-lookup"><span data-stu-id="5ae8e-165">**Overview of Azure Monitor**</span></span>

[<span data-ttu-id="5ae8e-166">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor</span><span class="sxs-lookup"><span data-stu-id="5ae8e-166">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor</span></span>](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   <span data-ttu-id="5ae8e-167">**Operations Management Suite (OMS) 是什么？**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-167">**What is Operations Management Suite (OMS)?**</span></span>

[<span data-ttu-id="5ae8e-168">https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview</span><span class="sxs-lookup"><span data-stu-id="5ae8e-168">https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview</span></span>](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   <span data-ttu-id="5ae8e-169">**监视与 OMS 配合使用的 Service Fabric 中的 Windows Server 容器**</span><span class="sxs-lookup"><span data-stu-id="5ae8e-169">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

[<span data-ttu-id="5ae8e-170">https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver</span><span class="sxs-lookup"><span data-stu-id="5ae8e-170">https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
<span data-ttu-id="5ae8e-171">[上一页](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[下一页](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="5ae8e-171">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
