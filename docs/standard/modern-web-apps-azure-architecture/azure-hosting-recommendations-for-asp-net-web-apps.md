---
title: 关于 ASP.NET Core Web 应用的 Azure 托管建议
description: 使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 关于 ASP.NET Web 应用的 Azure 托管建议
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: d328f92ef5e64ee5d92b71472a5e32e2f5d007fd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063231"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a><span data-ttu-id="6f909-103">关于 ASP.NET Core Web 应用的 Azure 托管建议</span><span class="sxs-lookup"><span data-stu-id="6f909-103">Azure hosting recommendations for ASP.NET Core web apps</span></span>

> <span data-ttu-id="6f909-104">“全球各地的业务线领导绕过 IT 部门，从云获取应用程序（又称 SaaS）并支付使用费用，就像订阅杂志一样。</span><span class="sxs-lookup"><span data-stu-id="6f909-104">"Line-of-business leaders everywhere are bypassing IT departments to get applications from the cloud (aka SaaS) and paying for them like they would a magazine subscription.</span></span> <span data-ttu-id="6f909-105">不再需要服务时，他们可取消订阅，不会出现设备闲置的情况。”</span><span class="sxs-lookup"><span data-stu-id="6f909-105">And when the service is no longer required, they can cancel the subscription with no equipment left unused in the corner."</span></span>  
> <span data-ttu-id="6f909-106">\-Gartner 分析师 Daryl Plummer</span><span class="sxs-lookup"><span data-stu-id="6f909-106">_\- Daryl Plummer, Gartner analyst_</span></span>

<span data-ttu-id="6f909-107">无论面对何种应用程序需要和体系结构，Microsoft Azure 均可提供支持。</span><span class="sxs-lookup"><span data-stu-id="6f909-107">Whatever your application's needs and architecture, Windows Azure can support it.</span></span> <span data-ttu-id="6f909-108">托管需求可以非常简单（例如静态网站），也可以非常复杂（例如由多个服务组成的复杂的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="6f909-108">Your hosting needs can be as simple as a static website to a sophisticated application made up of dozens of services.</span></span> <span data-ttu-id="6f909-109">对于 ASP.NET Core 整体 Web 应用程序和支持服务，推荐以下几种常见配置。</span><span class="sxs-lookup"><span data-stu-id="6f909-109">For ASP.NET Core monolithic web applications and supporting services, there are several well-known configurations that are recommended.</span></span> <span data-ttu-id="6f909-110">无论是完整应用程序、单个进程或数据，本文中的建议配置均按待托管资源的类型分组。</span><span class="sxs-lookup"><span data-stu-id="6f909-110">The recommendations on this article are grouped based on the kind of resource to be hosted, whether full applications, individual processes, or data.</span></span>

## <a name="web-applications"></a><span data-ttu-id="6f909-111">Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="6f909-111">Web applications</span></span>

<span data-ttu-id="6f909-112">可通过以下方式托管 Web 应用程序：</span><span class="sxs-lookup"><span data-stu-id="6f909-112">Web applications can be hosted with:</span></span>

- <span data-ttu-id="6f909-113">应用服务 Web 应用</span><span class="sxs-lookup"><span data-stu-id="6f909-113">App Service Web Apps</span></span>

- <span data-ttu-id="6f909-114">容器</span><span class="sxs-lookup"><span data-stu-id="6f909-114">Containers</span></span>

- <span data-ttu-id="6f909-115">虚拟机 (VM)</span><span class="sxs-lookup"><span data-stu-id="6f909-115">Virtual Machines (VMs)</span></span>

<span data-ttu-id="6f909-116">其中，对于大多数方案，推荐使用应用服务 Web 应用方法。</span><span class="sxs-lookup"><span data-stu-id="6f909-116">Of these, App Service Web Apps is the recommended approach for most scenarios.</span></span> <span data-ttu-id="6f909-117">对于微服务体系结构，请考虑使用基于容器的方法。</span><span class="sxs-lookup"><span data-stu-id="6f909-117">For microservice architectures, consider a container-based approach.</span></span> <span data-ttu-id="6f909-118">如果需要更好地控制运行应用程序的计算机，请考虑使用 Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="6f909-118">If you need more control over the machines running your application, consider Azure Virtual Machines.</span></span>

### <a name="app-service-web-apps"></a><span data-ttu-id="6f909-119">应用服务 Web 应用</span><span class="sxs-lookup"><span data-stu-id="6f909-119">App Service Web Apps</span></span>

<span data-ttu-id="6f909-120">应用服务 Web 应用提供的完全托管平台针对托管 Web 应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="6f909-120">App Service Web Apps offers a fully managed platform optimized for hosting web applications.</span></span> <span data-ttu-id="6f909-121">它是一种平台即服务 (PaaS) 产品/服务，可使你专注于业务逻辑，而由 Azure 负责维护应用运行和缩放所需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-121">It's a platform as a service (PaaS) offering that lets you focus on your business logic, while Azure takes care of the infrastructure needed to run and scale the app.</span></span> <span data-ttu-id="6f909-122">应用服务 Web 应用的一些关键功能：</span><span class="sxs-lookup"><span data-stu-id="6f909-122">Some key features of App Service Web Apps:</span></span>

- <span data-ttu-id="6f909-123">DevOps 优化（持续集成和交付、多环境、A/B 测试和脚本支持）。</span><span class="sxs-lookup"><span data-stu-id="6f909-123">DevOps optimization (continuous integration and delivery, multiple environments, A/B testing, scripting support).</span></span>

- <span data-ttu-id="6f909-124">全球缩放和高可用性。</span><span class="sxs-lookup"><span data-stu-id="6f909-124">Global scale and high availability.</span></span>

- <span data-ttu-id="6f909-125">可连接至 SaaS 平台和本地数据。</span><span class="sxs-lookup"><span data-stu-id="6f909-125">Connections to SaaS platforms and your on-premises data.</span></span>

- <span data-ttu-id="6f909-126">安全性和符合性。</span><span class="sxs-lookup"><span data-stu-id="6f909-126">Security and compliance.</span></span>

- <span data-ttu-id="6f909-127">Visual Studio 集成。</span><span class="sxs-lookup"><span data-stu-id="6f909-127">Visual Studio integration.</span></span>

- <span data-ttu-id="6f909-128">通过[用于容器的 Web 应用](https://azure.microsoft.com/en-us/services/app-service/containers/)支持 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="6f909-128">Support for Linux and Windows containers via [Web App for Containers](https://azure.microsoft.com/en-us/services/app-service/containers/).</span></span>

<span data-ttu-id="6f909-129">Azure 应用服务是适合大多数 Web 应用的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="6f909-129">Azure App Service is the best choice for most web apps.</span></span> <span data-ttu-id="6f909-130">该平台集成部署与管理，站点可快速缩放以处理高流量负载，内置负载均衡和流量管理器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="6f909-130">Deployment and management are integrated into the platform, sites can scale quickly to handle high traffic loads, and the built-in load balancing and traffic manager provide high availability.</span></span> <span data-ttu-id="6f909-131">可通过在线迁移工具将现有站点轻松移动到 Azure 应用服务、使用 Web 应用程序库中的开源应用或使用框架和你选择的工具创建新的站点。</span><span class="sxs-lookup"><span data-stu-id="6f909-131">You can move existing sites to Azure App Service easily with an online migration tool, use an open-source app from the Web Application Gallery, or create a new site using the framework and tools of your choice.</span></span> <span data-ttu-id="6f909-132">通过 WebJobs 功能可将后台作业处理轻松添加到应用服务 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="6f909-132">The WebJobs feature makes it easy to add background job processing to your App Service web app.</span></span>

### <a name="azure-kubernetes-service"></a><span data-ttu-id="6f909-133">Azure Kubernetes 服务</span><span class="sxs-lookup"><span data-stu-id="6f909-133">Azure Kubernetes Service</span></span>

<span data-ttu-id="6f909-134">Azure Kubernetes 服务 (AKS) 管理托管的 Kubernetes 环境，即使没有容器业务流程专业知识，也可快速轻松地部署和管理容器化应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f909-134">Azure Kubernetes Service (AKS) manages your hosted Kubernetes environment, making it quick and easy to deploy and manage containerized applications without container orchestration expertise.</span></span> <span data-ttu-id="6f909-135">此外，它还通过预配、升级和按需缩放资源，消除了持续操作和维护的负担，而无需应用程序脱机。</span><span class="sxs-lookup"><span data-stu-id="6f909-135">It also eliminates the burden of ongoing operations and maintenance by provisioning, upgrading, and scaling resources on demand, without taking your applications offline.</span></span>

<span data-ttu-id="6f909-136">通过将大量责任转移至 Azure，AKS 降低了管理 Kubernetes 群集的复杂性和运营开销。</span><span class="sxs-lookup"><span data-stu-id="6f909-136">AKS reduces the complexity and operational overhead of managing a Kubernetes cluster by offloading much of that responsibility to Azure.</span></span> <span data-ttu-id="6f909-137">作为一项托管的 Kubernetes 服务，Azure 将为你处理运行状况监视和维护等关键任务。</span><span class="sxs-lookup"><span data-stu-id="6f909-137">As a hosted Kubernetes service, Azure handles critical tasks like health monitoring and maintenance for you.</span></span> <span data-ttu-id="6f909-138">并且，你仅需支付群集中的代理节点，而无需支付主节点。</span><span class="sxs-lookup"><span data-stu-id="6f909-138">Also, you pay only for the agent nodes within your clusters, not for the masters.</span></span> <span data-ttu-id="6f909-139">作为一项托管的 Kubernetes 服务，AKS 提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="6f909-139">As a managed Kubernetes service, AKS provides:</span></span>

- <span data-ttu-id="6f909-140">自动化的 Kubernetes 版本升级和修补。</span><span class="sxs-lookup"><span data-stu-id="6f909-140">Automated Kubernetes version upgrades and patching.</span></span>
- <span data-ttu-id="6f909-141">轻松的群集缩放。</span><span class="sxs-lookup"><span data-stu-id="6f909-141">Easy cluster scaling.</span></span>
- <span data-ttu-id="6f909-142">自我修复型托管控制平面（主节点）。</span><span class="sxs-lookup"><span data-stu-id="6f909-142">Self-healing hosted control plane (masters).</span></span>
- <span data-ttu-id="6f909-143">节省成本：仅支付运行的代理池节点。</span><span class="sxs-lookup"><span data-stu-id="6f909-143">Cost savings - pay only for running agent pool nodes.</span></span>

<span data-ttu-id="6f909-144">由于 Azure 会负责管理 AKS 群集中的节点，因此，很多任务（例如群集升级）不再需要手动执行。</span><span class="sxs-lookup"><span data-stu-id="6f909-144">With Azure handling the management of the nodes in your AKS cluster, you no longer need to perform many tasks manually, like cluster upgrades.</span></span> <span data-ttu-id="6f909-145">由于 Azure 会处理这些关键维护任务，因此，AKS 不提供对群集的直接访问（例如使用 SSH）。</span><span class="sxs-lookup"><span data-stu-id="6f909-145">Because Azure handles these critical maintenance tasks for you, AKS doesn't provide direct access (such as with SSH) to the cluster.</span></span>

### <a name="azure-virtual-machines"></a><span data-ttu-id="6f909-146">Azure 虚拟机</span><span class="sxs-lookup"><span data-stu-id="6f909-146">Azure Virtual Machines</span></span>

<span data-ttu-id="6f909-147">如果现有应用程序需要经过大量修改才可在应用服务中运行，为简化迁移到云的操作，可选择虚拟机。</span><span class="sxs-lookup"><span data-stu-id="6f909-147">If you have an existing application that would require substantial modifications to run in App Service, you could choose Virtual Machines in order to simplify migrating to the cloud.</span></span> <span data-ttu-id="6f909-148">然而，与 Azure 应用服务相比，正确配置、保护和维护 VM 需要更多时间和 IT 专业知识。</span><span class="sxs-lookup"><span data-stu-id="6f909-148">However, correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to Azure App Service.</span></span> <span data-ttu-id="6f909-149">如要使用 Azure 虚拟机，请务必考虑到 VM 环境的修补、更新和管理所需的持续性维护工作。</span><span class="sxs-lookup"><span data-stu-id="6f909-149">If you're considering Azure Virtual Machines, make sure you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="6f909-150">Azure 虚拟机属于基础结构即服务 (IaaS)，而应用服务属于 PaaS。</span><span class="sxs-lookup"><span data-stu-id="6f909-150">Azure Virtual Machines is infrastructure as a service (IaaS), while App Service is PaaS.</span></span> <span data-ttu-id="6f909-151">还应考虑将应用作为 Windows 容器部署到用于容器的 Web 应用是否可能成为方案的可行选项。</span><span class="sxs-lookup"><span data-stu-id="6f909-151">You should also consider whether deploying your app as a Windows Container to Web App for Containers might be a viable option for your scenario.</span></span>

## <a name="logical-processes"></a><span data-ttu-id="6f909-152">逻辑进程</span><span class="sxs-lookup"><span data-stu-id="6f909-152">Logical processes</span></span>

<span data-ttu-id="6f909-153">对于可从应用程序的剩余部分分离的单独逻辑进程，可以“无服务器”方式将其独立部署到 Azure Functions。</span><span class="sxs-lookup"><span data-stu-id="6f909-153">Individual logical processes that can be decoupled from the rest of the application may be deployed independently to Azure Functions in a "serverless" manner.</span></span> <span data-ttu-id="6f909-154">通过 Azure Functions 可编写解决特定问题所需的代码，无需担心运行它的应用程序或基础结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-154">Azure Functions lets you just write the code you need for a given problem, without worrying about the application or infrastructure to run it.</span></span> <span data-ttu-id="6f909-155">可选择各种编程语言，包括 C\#、F\#、Node.js、Python 和 PHP，以便你选择一种最高效语言来处理手头任务。</span><span class="sxs-lookup"><span data-stu-id="6f909-155">You can choose from a variety of programming languages, including C\#, F\#, Node.js, Python, and PHP, allowing you to pick the most productive language for the task at hand.</span></span> <span data-ttu-id="6f909-156">与多数基于云的解决方案一样，仅需为使用的时间量支付费用，而且 Azure Functions 按需扩展非常可靠。</span><span class="sxs-lookup"><span data-stu-id="6f909-156">Like most cloud-based solutions, you pay only for the amount of time your use, and you can trust Azure Functions to scale up as needed.</span></span>

## <a name="data"></a><span data-ttu-id="6f909-157">数据</span><span class="sxs-lookup"><span data-stu-id="6f909-157">Data</span></span>

<span data-ttu-id="6f909-158">Azure 提供多种数据存储选择，以便应用程序可使用恰当的数据提供程序处理相关数据。</span><span class="sxs-lookup"><span data-stu-id="6f909-158">Azure offers a wide variety of data storage options, so that your application can use the appropriate data provider for the data in question.</span></span>

<span data-ttu-id="6f909-159">对于事务和关系数据，Azure SQL 数据库是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="6f909-159">For transactional, relational data, Azure SQL Databases are the best option.</span></span> <span data-ttu-id="6f909-160">对于以读取为主的高性能数据，受 Azure SQL 数据库支持的 Redis 缓存是一个不错的解决方案。</span><span class="sxs-lookup"><span data-stu-id="6f909-160">For high performance read-mostly data, a Redis cache backed by an Azure SQL Database is a good solution.</span></span>

<span data-ttu-id="6f909-161">可使用多种方式存储非结构化 JSON 数据，包括 SQL 数据库列、Blob、Azure 存储中的表以及 Cosmos DB。</span><span class="sxs-lookup"><span data-stu-id="6f909-161">Unstructured JSON data can be stored in a variety of ways, from SQL Database columns to Blobs or Tables in Azure Storage, to DocumentDB.</span></span> <span data-ttu-id="6f909-162">其中，Cosmos DB 提供最佳查询功能，建议用于必须支持查询的大量基于 JSON 的文档。</span><span class="sxs-lookup"><span data-stu-id="6f909-162">Of these, DocumentDB offers the best querying functionality, and is the recommended option for large numbers of JSON-based documents that must support querying.</span></span>

<span data-ttu-id="6f909-163">暂时命令或者用于安排应用程序行为的基于事件的数据可使用 Azure 服务总线或 Azure 存储队列。</span><span class="sxs-lookup"><span data-stu-id="6f909-163">Transient command- or event-based data used to orchestrate application behavior can use Azure Service Bus or Azure Storage Queues.</span></span> <span data-ttu-id="6f909-164">Azure 存储总线具有更强的灵活性，建议将该服务用于处理应用程序内和应用程序间的非普通消息传递。</span><span class="sxs-lookup"><span data-stu-id="6f909-164">Azure Storage Bus offers more flexibility and is the recommended service for non-trivial messaging within and between applications.</span></span>

## <a name="architecture-recommendations"></a><span data-ttu-id="6f909-165">体系结构建议</span><span class="sxs-lookup"><span data-stu-id="6f909-165">Architecture recommendations</span></span>

<span data-ttu-id="6f909-166">应用程序要求应决定其体系结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-166">Your application's requirements should dictate its architecture.</span></span> <span data-ttu-id="6f909-167">有多种不同的 Azure 服务可供使用。</span><span class="sxs-lookup"><span data-stu-id="6f909-167">There are many different Azure services available.</span></span> <span data-ttu-id="6f909-168">选择正确的服务是一项重要决定。</span><span class="sxs-lookup"><span data-stu-id="6f909-168">Choosing the right one is an important decision.</span></span> <span data-ttu-id="6f909-169">Microsoft 提供一系列参考体系结构，帮助用户确定针对常见方案优化的典型体系结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-169">Microsoft offers a gallery of reference architectures to help identify typical architectures optimized for common scenarios.</span></span> <span data-ttu-id="6f909-170">可找到一个与应用程序要求高度契合或至少提供一个出发点的参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-170">You may find a reference architecture that maps closely to your application's requirements, or at least offers a starting point.</span></span>

<span data-ttu-id="6f909-171">图 11-2 显示了一个示例参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-171">Figure 11-2 shows an example reference architecture.</span></span> <span data-ttu-id="6f909-172">该图介绍了一个建议用于为市场营销而优化的 Sitecore 内容管理系统网站的体系结构方式。</span><span class="sxs-lookup"><span data-stu-id="6f909-172">This diagram describes a recommended architecture approach for a Sitecore content management system website optimized for marketing.</span></span>

![](./media/image11-2.png)

<span data-ttu-id="6f909-173">**Figure 11-1**。</span><span class="sxs-lookup"><span data-stu-id="6f909-173">**Figure 11-1.**</span></span> <span data-ttu-id="6f909-174">Sitecore 市场营销网站参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="6f909-174">Sitecore marketing website reference architecture.</span></span>

<span data-ttu-id="6f909-175">**参考：Azure 托管建议**</span><span class="sxs-lookup"><span data-stu-id="6f909-175">**References – Azure hosting recommendations**</span></span>

- <span data-ttu-id="6f909-176">Azure解决方案体系结构\\</span><span class="sxs-lookup"><span data-stu-id="6f909-176">Azure Solution Architectures\\</span></span>
  <https://azure.microsoft.com/solutions/architecture/>

- <span data-ttu-id="6f909-177">Azure 开发人员指南\\</span><span class="sxs-lookup"><span data-stu-id="6f909-177">Azure Developer Guide\\</span></span>
  <https://azure.microsoft.com/campaigns/developer-guide/>

- <span data-ttu-id="6f909-178">Web 应用概述\\</span><span class="sxs-lookup"><span data-stu-id="6f909-178">Web Apps overview\\</span></span>
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- <span data-ttu-id="6f909-179">用于容器的 Web 应用\\</span><span class="sxs-lookup"><span data-stu-id="6f909-179">Web App for Containers\\</span></span>
  <https://azure.microsoft.com/en-us/services/app-service/containers/>

- <span data-ttu-id="6f909-180">Azure Kubernetes 服务 (AKS) 简介\\</span><span class="sxs-lookup"><span data-stu-id="6f909-180">Introduction to Azure Kubernetes Service (AKS)\\</span></span>
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[<span data-ttu-id="6f909-181">上一篇</span><span class="sxs-lookup"><span data-stu-id="6f909-181">Previous</span></span>](development-process-for-azure.md)
