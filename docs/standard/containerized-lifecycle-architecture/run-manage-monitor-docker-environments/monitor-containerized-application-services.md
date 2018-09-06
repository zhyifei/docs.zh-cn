---
title: 监视容器化应用程序服务
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4bdc4470624ce6e905ab858a2bd8b607c8d3d646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731308"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="c9391-103">监视容器化应用程序服务</span><span class="sxs-lookup"><span data-stu-id="c9391-103">Monitor containerized application services</span></span>

<span data-ttu-id="c9391-104">很重要的拆分为多个容器和微服务的应用程序具有一种方法来监视和分析应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="c9391-104">It is critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="c9391-105">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="c9391-105">Microsoft Application Insights</span></span>

<span data-ttu-id="c9391-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)是一项可扩展分析服务，用于监视实时应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9391-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="c9391-107">它可帮助你检测和诊断性能问题以及了解用户实际使用你的应用。</span><span class="sxs-lookup"><span data-stu-id="c9391-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="c9391-108">它专为开发人员的意图是为了帮助您不断提高的性能和可用性的服务或应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9391-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="c9391-109">Application Insights 适用于 web/服务和独立上各种不同的平台，如.NET、 Java、 Node.js 和许多其他平台，托管在本地或云中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9391-109">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="c9391-110">分析在 QA 环境中使用 Application Insights 的 Docker 应用</span><span class="sxs-lookup"><span data-stu-id="c9391-110">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="c9391-111">因为它涉及到 Docker，可以绘制生命周期事件和性能计数器从 Application Insights 上的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="c9391-111">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="c9391-112">只需运行[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)如的容器中你的主机，它将显示性能计数器的主机也与其他 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="c9391-112">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="c9391-113">此应用程序见解 Docker 映像 (图 6-1） 可帮助你通过将收集有关性能和活动的 Docker 主机 (即，在 Linux Vm)、 Docker 容器和运行的应用程序的遥测数据来监视容器化应用程序在其中。</span><span class="sxs-lookup"><span data-stu-id="c9391-113">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![示例](./media/image1.png)

<span data-ttu-id="c9391-115">图 6-1: Application Insights 监视 Docker 主机和容器</span><span class="sxs-lookup"><span data-stu-id="c9391-115">Figure 6-1: Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="c9391-116">在运行时[应用程序见解 Docker 映像](https://hub.docker.com/r/microsoft/applicationinsights/)Docker 主机上你利用以下：</span><span class="sxs-lookup"><span data-stu-id="c9391-116">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

-   <span data-ttu-id="c9391-117">有关在主机上运行的所有容器的遥测数据的生命周期-启动、 停止和其他操作。</span><span class="sxs-lookup"><span data-stu-id="c9391-117">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

-   <span data-ttu-id="c9391-118">所有容器的性能计数器： CPU、 内存、 网络使用情况和的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9391-118">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

-   <span data-ttu-id="c9391-119">如果还安装了[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)在容器中运行的应用，这些应用程序的所有遥测数据将具有识别容器和主机计算机的其他属性。</span><span class="sxs-lookup"><span data-stu-id="c9391-119">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="c9391-120">因此，例如，如果有多个主机中运行的应用的实例，您将轻松能够筛选由主机应用程序遥测数据。</span><span class="sxs-lookup"><span data-stu-id="c9391-120">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="c9391-121">设置 Application Insights 监视 Docker 应用程序和 Docker 主机</span><span class="sxs-lookup"><span data-stu-id="c9391-121">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="c9391-122">若要创建 Application Insights 资源时，请遵循后面的列表中显示的文章中的说明。</span><span class="sxs-lookup"><span data-stu-id="c9391-122">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="c9391-123">Azure 门户将为您创建所需的脚本。</span><span class="sxs-lookup"><span data-stu-id="c9391-123">Azure Portal will create the necessary script for you.</span></span>

-   <span data-ttu-id="c9391-124">**在 Application Insights 中监视 Docker 应用程序：**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span><span class="sxs-lookup"><span data-stu-id="c9391-124">**Monitor Docker applications in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span></span>

-   <span data-ttu-id="c9391-125">**在 Docker 中心和 Github 的应用程序见解 Docker 映像：**</span><span class="sxs-lookup"><span data-stu-id="c9391-125">**Application Insights Docker image at Docker Hub and Github:**</span></span>  
<span data-ttu-id="c9391-126">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) 和 <https://github.com/Microsoft/ApplicationInsights-Docker></span><span class="sxs-lookup"><span data-stu-id="c9391-126">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) and <https://github.com/Microsoft/ApplicationInsights-Docker></span></span>

-   <span data-ttu-id="c9391-127">**设置 ASP.NET 的 Application Insights:**</span><span class="sxs-lookup"><span data-stu-id="c9391-127">**Set up Application Insights for ASP.NET:**</span></span>  
[https://docs.microsoft.com/azure/application-insights/app-insights-asp-net](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   <span data-ttu-id="c9391-128">**适用于网页的 application Insights:**</span><span class="sxs-lookup"><span data-stu-id="c9391-128">**Application Insights for web pages:**</span></span>  
<https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="microsoft-operations-management-suite"></a><span data-ttu-id="c9391-129">Microsoft Operations Management Suite</span><span class="sxs-lookup"><span data-stu-id="c9391-129">Microsoft Operations Management Suite</span></span>

<span data-ttu-id="c9391-130">[Operations Management Suite](https://microsoft.com/oms)是简化的 IT 管理解决方案，提供了 log analytics、 自动化、 备份和站点恢复。</span><span class="sxs-lookup"><span data-stu-id="c9391-130">[Operations Management Suite](https://microsoft.com/oms) is a simplified IT management solution that provides log analytics, automation, backup, and site recovery.</span></span> <span data-ttu-id="c9391-131">基于[查询](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/)，可以将 Operations Management Suite[警报](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts)并设置通过修正[Azure 自动化](https://docs.microsoft.com/azure/automation/)。</span><span class="sxs-lookup"><span data-stu-id="c9391-131">Based on [queries](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, you can raise [alerts](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) and set remediation via [Azure Automation](https://docs.microsoft.com/azure/automation/).</span></span> <span data-ttu-id="c9391-132">它也可无缝集成和现有的管理解决方案提供单个窗格中的玻璃视图。</span><span class="sxs-lookup"><span data-stu-id="c9391-132">It also seamlessly integrates with your existing management solutions to provide a single pane-of-glass view.</span></span> <span data-ttu-id="c9391-133">Operations Management Suite 可帮助你管理和保护你的本地和云基础结构。</span><span class="sxs-lookup"><span data-stu-id="c9391-133">Operations Management Suite helps you to manage and protect your on-premises and cloud infrastructure.</span></span>

### <a name="operations-management-suitehttpsmicrosoftcomoms-container-solution-for-docker"></a><span data-ttu-id="c9391-134">[Operations Management Suite](https://microsoft.com/oms) Docker 的容器解决方案</span><span class="sxs-lookup"><span data-stu-id="c9391-134">[Operations Management Suite](https://microsoft.com/oms) Container Solution for Docker</span></span>

<span data-ttu-id="c9391-135">除了自身提供有价值的服务，Operations Management Suite 容器解决方案可以管理和监视 Docker 主机和容器显示容器和容器主机在哪里的相关信息哪些容器正在运行或发生故障，以及 Docker 守护程序和容器的日志发送到*stdout*并*stderr*。</span><span class="sxs-lookup"><span data-stu-id="c9391-135">In addition to providing valuable services on its own, the Operations Management Suite Container Solution can manage and monitor Docker hosts and containers by showing information about where your containers and container hosts are, which containers are running or failed, and Docker daemon and container logs sent to *stdout* and *stderr*.</span></span> <span data-ttu-id="c9391-136">它还显示容器和主机的性能指标，如 CPU、内存、网络和存储，帮助排除故障和找到具有干扰性的相邻容器。</span><span class="sxs-lookup"><span data-stu-id="c9391-136">It also shows performance metrics such as CPU, memory, network, and storage for the container and hosts to help you troubleshoot and find noisy neighbor containers.</span></span>

![](./media/image2.png)

<span data-ttu-id="c9391-137">有关通过 Operations Management Suite 所示的 Docker 容器的图 6-2： 信息</span><span class="sxs-lookup"><span data-stu-id="c9391-137">Figure 6-2: Information about Docker containers shown by Operations Management Suite</span></span>

<span data-ttu-id="c9391-138">Application Insights 和 Operations Management Suite 监视活动; 重点但是，Application Insights 更侧重监视应用本身得益于其在应用中运行的 SDK。</span><span class="sxs-lookup"><span data-stu-id="c9391-138">Application Insights and Operations Management Suite both focus on monitoring activities; however, Application Insights focuses more on monitoring the apps themselves thanks to its SDK running within the app.</span></span> <span data-ttu-id="c9391-139">但是，Operations Management Suite 更侧重于围绕这些主机，基础结构以及它提供一个非常灵活数据驱动搜索/查询系统时提供深度分析在规模较大的日志。</span><span class="sxs-lookup"><span data-stu-id="c9391-139">However, Operations Management Suite focuses much more on the infrastructure around the hosts, plus it offers deep analysis on logs at scale while providing a very flexible data-driven search/query system.</span></span>

<span data-ttu-id="c9391-140">Operations Management Suite 作为基于云的服务实现，因为你可以使其启动并运行投入基础结构服务中的最小投资。</span><span class="sxs-lookup"><span data-stu-id="c9391-140">Because Operations Management Suite is implemented as a cloud-based service, you can have it up and running quickly with minimal investment in infrastructure services.</span></span> <span data-ttu-id="c9391-141">新功能，将自动传递，从而节省持续维护和升级成本。</span><span class="sxs-lookup"><span data-stu-id="c9391-141">New features are delivered automatically, saving you from ongoing maintenance and upgrade costs.</span></span>

<span data-ttu-id="c9391-142">使用 Operations Management Suite 容器解决方案，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c9391-142">Using Operations Management Suite Container Solution, you can do the following:</span></span>

-   <span data-ttu-id="c9391-143">集中管理和关联数以百万计的大规模的 Docker 容器中的日志</span><span class="sxs-lookup"><span data-stu-id="c9391-143">Centralize and correlate millions of logs from Docker containers at scale</span></span>

-   <span data-ttu-id="c9391-144">请参阅有关在单个位置所有容器主机的信息</span><span class="sxs-lookup"><span data-stu-id="c9391-144">See information about all container hosts in a single location</span></span>

-   <span data-ttu-id="c9391-145">知道哪些容器正在运行，哪些映像运行它们，并运行位置</span><span class="sxs-lookup"><span data-stu-id="c9391-145">Know which containers are running, what image they're running, and where they're running</span></span>

-   <span data-ttu-id="c9391-146">快速诊断可能会导致问题容器主机的"干扰邻居"容器</span><span class="sxs-lookup"><span data-stu-id="c9391-146">Quickly diagnose "noisy neighbor" containers that can cause problems on container hosts</span></span>

-   <span data-ttu-id="c9391-147">有关容器，请参阅操作的审核线索</span><span class="sxs-lookup"><span data-stu-id="c9391-147">See an audit trail for actions on containers</span></span>

-   <span data-ttu-id="c9391-148">通过查看和搜索而无需远程处理与 Docker 主机的集中化的日志进行故障排除</span><span class="sxs-lookup"><span data-stu-id="c9391-148">Troubleshoot by viewing and searching centralized logs without remoting to the Docker hosts</span></span>

-   <span data-ttu-id="c9391-149">查找可能是"噪声邻居"和在主机上的使用过多资源的容器</span><span class="sxs-lookup"><span data-stu-id="c9391-149">Find containers that might be "noisy neighbors" and consuming excess resources on a host</span></span>

-   <span data-ttu-id="c9391-150">查看集中式的 CPU、 内存、 存储和用于容器的网络使用情况和性能信息</span><span class="sxs-lookup"><span data-stu-id="c9391-150">View centralized CPU, memory, storage, and network usage and performance information for containers</span></span>

-   <span data-ttu-id="c9391-151">生成 Docker 容器进行 Azure 自动化测试</span><span class="sxs-lookup"><span data-stu-id="c9391-151">Generate test Docker containers with Azure Automation</span></span>

<span data-ttu-id="c9391-152">您可以通过运行类似于类型的查询来查看性能信息 = 性能，在图 6-3 中所示。</span><span class="sxs-lookup"><span data-stu-id="c9391-152">You can see performance information by running queries like Type=Perf, as shown in Figure 6-3.</span></span>

![DockerPerfMetricsView](./media/image3.png)<span data-ttu-id="c9391-154">{width="5.78625in" height="3.25in"}</span><span class="sxs-lookup"><span data-stu-id="c9391-154">{width="5.78625in" height="3.25in"}</span></span>

<span data-ttu-id="c9391-155">图 6-3： 通过 Operations Management Suite 所示的 Docker 主机的性能指标</span><span class="sxs-lookup"><span data-stu-id="c9391-155">Figure 6-3: Performance metrics of Docker hosts shown by Operations Management Suite</span></span>

<span data-ttu-id="c9391-156">保存查询也是 Operations Management Suite 中的标准功能，可帮助你记录发现的有用和发现趋势在系统中的查询。</span><span class="sxs-lookup"><span data-stu-id="c9391-156">Saving queries is also a standard feature in Operations Management Suite and can help you keep queries you've found useful and discover trends in your system.</span></span>

<span data-ttu-id="c9391-157">**详细信息** 若要查找有关安装和配置 Docker 容器中的解决方案[Operations Management Suite](https://microsoft.com/oms)，转到<https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>。</span><span class="sxs-lookup"><span data-stu-id="c9391-157">**More info** To find information on installing and configuring the Docker container solution in [Operations Management Suite](https://microsoft.com/oms), go to <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c9391-158">[上一页](manage-production-docker-environments.md)
[下一页](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="c9391-158">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
