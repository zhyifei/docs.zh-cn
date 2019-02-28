---
title: 监视容器化应用程序服务
description: 了解监视容器体系结构的一些重要层面
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975740"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="723e7-103">监视容器化应用程序服务</span><span class="sxs-lookup"><span data-stu-id="723e7-103">Monitor containerized application services</span></span>

<span data-ttu-id="723e7-104">很重要的拆分为多个容器和微服务的应用程序具有一种方法来监视和分析整个应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="723e7-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="723e7-105">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="723e7-105">Microsoft Application Insights</span></span>

<span data-ttu-id="723e7-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是一项可扩展分析服务，用于监视实时应用程序。</span><span class="sxs-lookup"><span data-stu-id="723e7-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="723e7-107">它可帮助你检测和诊断性能问题以及了解用户实际使用你的应用。</span><span class="sxs-lookup"><span data-stu-id="723e7-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="723e7-108">它专为开发人员的意图是为了帮助您不断提高的性能和可用性的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="723e7-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="723e7-109">Application Insights 适用于 web/服务和独立上各种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="723e7-109">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="723e7-110">分析在 QA 环境中使用 Application Insights 的 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="723e7-110">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="723e7-111">因为它涉及到 Docker，可以绘制生命周期事件和性能计数器从 Application Insights 上的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="723e7-111">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="723e7-112">只需运行[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)如的容器中你的主机，它将显示性能计数器的主机也与其他 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="723e7-112">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="723e7-113">此应用程序见解 Docker 映像 (图 6-1） 可帮助你通过将收集有关性能和活动的 Docker 主机 (即，在 Linux Vm)、 Docker 容器和运行的应用程序的遥测数据来监视容器化应用程序在其中。</span><span class="sxs-lookup"><span data-stu-id="723e7-113">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![示例](./media/image1.png)

<span data-ttu-id="723e7-115">**图 6-1**.</span><span class="sxs-lookup"><span data-stu-id="723e7-115">**Figure 6-1**.</span></span> <span data-ttu-id="723e7-116">Application Insights 监视 Docker 主机和容器</span><span class="sxs-lookup"><span data-stu-id="723e7-116">Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="723e7-117">在运行时[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)Docker 主机上你利用以下：</span><span class="sxs-lookup"><span data-stu-id="723e7-117">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

- <span data-ttu-id="723e7-118">有关在主机上运行的所有容器的遥测数据的生命周期-启动、 停止和其他操作。</span><span class="sxs-lookup"><span data-stu-id="723e7-118">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

- <span data-ttu-id="723e7-119">所有容器的性能计数器：CPU、 内存、 网络使用情况和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="723e7-119">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

- <span data-ttu-id="723e7-120">如果还安装了[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中运行的应用，这些应用程序的所有遥测数据将具有识别容器和主机计算机的其他属性。</span><span class="sxs-lookup"><span data-stu-id="723e7-120">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="723e7-121">因此，例如，如果有多个主机中运行的应用的实例，您将轻松能够筛选由主机应用程序遥测数据。</span><span class="sxs-lookup"><span data-stu-id="723e7-121">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="723e7-122">设置 Application Insights 监视 Docker 应用程序和 Docker 主机</span><span class="sxs-lookup"><span data-stu-id="723e7-122">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="723e7-123">若要创建 Application Insights 资源时，请遵循后面的列表中显示的文章中的说明。</span><span class="sxs-lookup"><span data-stu-id="723e7-123">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="723e7-124">Azure 门户将为您创建所需的脚本。</span><span class="sxs-lookup"><span data-stu-id="723e7-124">Azure portal will create the necessary script for you.</span></span>

- <span data-ttu-id="723e7-125">**在 Application Insights 中监视 Docker 应用程序：** \\</span><span class="sxs-lookup"><span data-stu-id="723e7-125">**Monitor Docker applications in Application Insights:** \\</span></span>
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- <span data-ttu-id="723e7-126">**在 Docker 中心和 GitHub 的应用程序见解 Docker 映像：** \\</span><span class="sxs-lookup"><span data-stu-id="723e7-126">**Application Insights Docker image at Docker Hub and GitHub:** \\</span></span>
  <span data-ttu-id="723e7-127"><https://hub.docker.com/r/microsoft/applicationinsights/> 和 \\</span><span class="sxs-lookup"><span data-stu-id="723e7-127"><https://hub.docker.com/r/microsoft/applicationinsights/> and \\</span></span>
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- <span data-ttu-id="723e7-128">**为 ASP.NET web 应用和 ASP.NET Core 设置 Application Insights:** \\</span><span class="sxs-lookup"><span data-stu-id="723e7-128">**Set up Application Insights for ASP.NET web apps and ASP.NET Core:** \\</span></span>
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- <span data-ttu-id="723e7-129">**适用于网页的 application Insights:**</span><span class="sxs-lookup"><span data-stu-id="723e7-129">**Application Insights for web pages:**</span></span>  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a><span data-ttu-id="723e7-130">安全、 备份和监视服务</span><span class="sxs-lookup"><span data-stu-id="723e7-130">Security, backup, and monitoring services</span></span>

<span data-ttu-id="723e7-131">有许多支持零碎工作具有大量你需要处理以确保你的应用程序和基础结构中前陷波条件，以支持业务需求的详细信息，这种情况变得更加复杂的微服务领域，因此您需要一种方法当您需要采取措施时具有高级别和详细视图。</span><span class="sxs-lookup"><span data-stu-id="723e7-131">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="723e7-132">Azure 提供的工具来管理并提供在云中和本地资源的四个关键方面的统一的视图：</span><span class="sxs-lookup"><span data-stu-id="723e7-132">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="723e7-133">**安全**。</span><span class="sxs-lookup"><span data-stu-id="723e7-133">**Security**.</span></span> <span data-ttu-id="723e7-134">与[Azure 安全中心](https://azure.microsoft.com/services/security-center/)。</span><span class="sxs-lookup"><span data-stu-id="723e7-134">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="723e7-135">获取完整的可见性和控制虚拟机、 应用和工作负荷的安全性。</span><span class="sxs-lookup"><span data-stu-id="723e7-135">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="723e7-136">集中你的安全策略的管理，并集成现有流程和工具。</span><span class="sxs-lookup"><span data-stu-id="723e7-136">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="723e7-137">检测到使用高级分析真正的威胁。</span><span class="sxs-lookup"><span data-stu-id="723e7-137">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="723e7-138">**备份**。</span><span class="sxs-lookup"><span data-stu-id="723e7-138">**Backup**.</span></span> <span data-ttu-id="723e7-139">与[Azure 备份](https://azure.microsoft.com/services/backup/)。</span><span class="sxs-lookup"><span data-stu-id="723e7-139">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="723e7-140">避免成本高昂的业务中断，满足符合性目标，并保护数据免受勒索软件和人为错误。</span><span class="sxs-lookup"><span data-stu-id="723e7-140">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="723e7-141">保留备份数据在传输过程中和静止加密。</span><span class="sxs-lookup"><span data-stu-id="723e7-141">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="723e7-142">请确保访问基于多重身份验证，以防止未经授权的使用。</span><span class="sxs-lookup"><span data-stu-id="723e7-142">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="723e7-143">**监视**。</span><span class="sxs-lookup"><span data-stu-id="723e7-143">**Monitoring**.</span></span> <span data-ttu-id="723e7-144">与[Azure 监视](https://azure.microsoft.com/solutions/monitoring/)， [Log Analytics](https://azure.microsoft.com/services/log-analytics/)，并[Application Insights](https://azure.microsoft.com/services/application-insights/)。</span><span class="sxs-lookup"><span data-stu-id="723e7-144">With [Azure monitoring](https://azure.microsoft.com/solutions/monitoring/), [Log Analytics](https://azure.microsoft.com/services/log-analytics/), and [Application Insights](https://azure.microsoft.com/services/application-insights/).</span></span>
  - <span data-ttu-id="723e7-145">获取完整的可见性的运行状况和性能的 Azure 工作负荷、 应用和基础结构。</span><span class="sxs-lookup"><span data-stu-id="723e7-145">Get full visibility into the health and performance of your Azure workloads, apps, and infrastructure.</span></span>
  - <span data-ttu-id="723e7-146">从任何源收集数据，获取丰富见解的虚拟机、 容器和应用程序。</span><span class="sxs-lookup"><span data-stu-id="723e7-146">Collect data from any source and get rich insights into your virtual machines, containers, and applications.</span></span>
  - <span data-ttu-id="723e7-147">查找您需要使用交互式查询和全文搜索的信息。</span><span class="sxs-lookup"><span data-stu-id="723e7-147">Find the information you need using interactive queries and full-text search.</span></span> 
  - <span data-ttu-id="723e7-148">执行根本原因分析使用高级分析，包括机器学习算法。</span><span class="sxs-lookup"><span data-stu-id="723e7-148">Perform root-cause analysis with advanced analytics, including machine learning algorithms.</span></span>

- <span data-ttu-id="723e7-149">**本地资源**。</span><span class="sxs-lookup"><span data-stu-id="723e7-149">**On-premises resources**.</span></span> <span data-ttu-id="723e7-150">与[真正一致的混合云](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)。</span><span class="sxs-lookup"><span data-stu-id="723e7-150">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="723e7-151">[上一页](manage-production-docker-environments.md)
>[下一页](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="723e7-151">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
