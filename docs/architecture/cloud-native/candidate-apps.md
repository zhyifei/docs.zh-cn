---
title: 云本机的候选应用
description: 了解哪些类型的应用程序受益于云原生方法
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805609"
---
# <a name="candidate-apps-for-cloud-native"></a><span data-ttu-id="bf148-103">云本机的候选应用</span><span class="sxs-lookup"><span data-stu-id="bf148-103">Candidate apps for cloud native</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bf148-104">查看产品组合中的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf148-104">Look at the apps in your portfolio.</span></span> <span data-ttu-id="bf148-105">其中有多少人有资格获得云原生架构？</span><span class="sxs-lookup"><span data-stu-id="bf148-105">How many of them qualify for a cloud-native architecture?</span></span> <span data-ttu-id="bf148-106">它们全部？</span><span class="sxs-lookup"><span data-stu-id="bf148-106">All of them?</span></span> <span data-ttu-id="bf148-107">也许有些？</span><span class="sxs-lookup"><span data-stu-id="bf148-107">Perhaps some?</span></span>

<span data-ttu-id="bf148-108">应用成本/收益分析，大多数人很可能不支持云原生所需的高昂价格标签。</span><span class="sxs-lookup"><span data-stu-id="bf148-108">Applying a cost/benefit analysis, there's a good chance that most wouldn't support the hefty price tag required to be cloud native.</span></span> <span data-ttu-id="bf148-109">云原生成本将远远超过应用程序的业务价值。</span><span class="sxs-lookup"><span data-stu-id="bf148-109">The cost of being cloud native would far exceed the business value of the application.</span></span>

<span data-ttu-id="bf148-110">哪种应用程序可能是云本机的候选类型？</span><span class="sxs-lookup"><span data-stu-id="bf148-110">What type of application might be a candidate for cloud native?</span></span>

- <span data-ttu-id="bf148-111">需要不断发展业务能力/功能的大型战略企业系统</span><span class="sxs-lookup"><span data-stu-id="bf148-111">A large, strategic enterprise system that needs to constantly evolve business capabilities/features</span></span>

- <span data-ttu-id="bf148-112">需要高释放速度的应用程序 - 高度置信度</span><span class="sxs-lookup"><span data-stu-id="bf148-112">An application that requires a high release velocity - with high confidence</span></span>

- <span data-ttu-id="bf148-113">具有单个功能且无需完全重新部署整个系统*即可发布的系统*</span><span class="sxs-lookup"><span data-stu-id="bf148-113">A system with where individual features must release *without* a full redeployment of the entire system</span></span>

- <span data-ttu-id="bf148-114">由具有不同技术堆栈专业知识的团队开发的应用程序</span><span class="sxs-lookup"><span data-stu-id="bf148-114">An application developed by teams with expertise in different technology stacks</span></span>

- <span data-ttu-id="bf148-115">具有必须独立扩展的组件的应用程序</span><span class="sxs-lookup"><span data-stu-id="bf148-115">An application with components that must scale independently</span></span>

<span data-ttu-id="bf148-116">然后是遗留系统。</span><span class="sxs-lookup"><span data-stu-id="bf148-116">Then there are legacy systems.</span></span> <span data-ttu-id="bf148-117">虽然我们都希望构建新的应用程序，但我们通常负责实现对业务至关重要的遗留工作负载的现代化。</span><span class="sxs-lookup"><span data-stu-id="bf148-117">While we'd all like to build new applications, we're often responsible for modernizing legacy workloads that are critical to the business.</span></span> <span data-ttu-id="bf148-118">随着时间的推移，旧应用程序可以分解为微服务，容器化，并最终"重新平台"到云本机体系结构。</span><span class="sxs-lookup"><span data-stu-id="bf148-118">Over time, a legacy application could be decomposed into microservices, containerized, and ultimately "replatformed" into a cloud-native architecture.</span></span>

### <a name="modernizing-legacy-apps"></a><span data-ttu-id="bf148-119">现代化传统应用</span><span class="sxs-lookup"><span data-stu-id="bf148-119">Modernizing legacy apps</span></span>

<span data-ttu-id="bf148-120">免费的 Microsoft 电子书[使用 Azure 云和 Windows 容器对现有 .NET 应用程序进行现代化改造](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)，为将本地工作负载迁移到云提供了指南。</span><span class="sxs-lookup"><span data-stu-id="bf148-120">The free Microsoft e-book [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) provides guidance for migrating on-premises workloads into cloud.</span></span> <span data-ttu-id="bf148-121">图 1-10 显示了没有一种单一、一刀切的策略来实现旧应用程序的现代化。</span><span class="sxs-lookup"><span data-stu-id="bf148-121">Figure 1-10 shows that there isn't a single, one-size-fits-all strategy for modernizing legacy applications.</span></span>

![迁移旧工作负载的策略](./media/strategies-for-migrating-legacy-workloads.png)

<span data-ttu-id="bf148-123">**图 1-10**.</span><span class="sxs-lookup"><span data-stu-id="bf148-123">**Figure 1-10**.</span></span> <span data-ttu-id="bf148-124">迁移旧工作负载的策略</span><span class="sxs-lookup"><span data-stu-id="bf148-124">Strategies for migrating legacy workloads</span></span>

<span data-ttu-id="bf148-125">非关键应用主要受益于快速提升和移动 （[云基础架构就绪](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)） 迁移。</span><span class="sxs-lookup"><span data-stu-id="bf148-125">Monolithic apps that are non-critical largely benefit from a quick lift-and-shift ([Cloud Infrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) migration.</span></span> <span data-ttu-id="bf148-126">在这里，本地工作负载将重新托管到基于云的 VM，无需更改。</span><span class="sxs-lookup"><span data-stu-id="bf148-126">Here, the on-premises workload is rehosted to a cloud-based VM, without changes.</span></span> <span data-ttu-id="bf148-127">此方法使用[IaaS（基础设施即服务）模型](https://azure.microsoft.com/overview/what-is-iaas/)。</span><span class="sxs-lookup"><span data-stu-id="bf148-127">This approach uses the [IaaS (Infrastructure as a Service) model](https://azure.microsoft.com/overview/what-is-iaas/).</span></span> <span data-ttu-id="bf148-128">Azure 包括多个工具，如[Azure 迁移](https://azure.microsoft.com/services/azure-migrate/)[、Azure 站点恢复](https://azure.microsoft.com/services/site-recovery/)和[Azure 数据库迁移服务](https://azure.microsoft.com/campaigns/database-migration/)，以便更轻松地移动。</span><span class="sxs-lookup"><span data-stu-id="bf148-128">Azure includes several tools such as [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/), and [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) to make such a move easier.</span></span> <span data-ttu-id="bf148-129">虽然这种策略可以节省一些成本，但此类应用程序通常不是为解锁和利用云计算的优势而构建的。</span><span class="sxs-lookup"><span data-stu-id="bf148-129">While this strategy can yield some cost savings, such applications typically weren't architected to unlock and leverage the benefits of cloud computing.</span></span>

<span data-ttu-id="bf148-130">对业务至关重要的单一应用通常受益于增强的提升和移位 （*云优化*） 迁移。</span><span class="sxs-lookup"><span data-stu-id="bf148-130">Monolithic apps that are critical to the business oftentimes benefit from an enhanced lift-and-shift (*Cloud Optimized*) migration.</span></span> <span data-ttu-id="bf148-131">此方法包括启用关键云服务的部署优化 ， 而无需更改应用程序的核心体系结构。</span><span class="sxs-lookup"><span data-stu-id="bf148-131">This approach includes deployment optimizations that enable key cloud services - without changing the core architecture of the application.</span></span> <span data-ttu-id="bf148-132">例如，您可以将应用程序[容器化](https://docs.microsoft.com/virtualization/windowscontainers/about/)，并将其部署到容器协调器，如本书后面讨论的[Azure Kubernetes 服务](https://azure.microsoft.com/services/kubernetes-service/)。</span><span class="sxs-lookup"><span data-stu-id="bf148-132">For example, you might [containerize](https://docs.microsoft.com/virtualization/windowscontainers/about/) the application and deploy it to a container orchestrator, like [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), discussed later in this book.</span></span> <span data-ttu-id="bf148-133">进入云后，应用程序可能会使用其他云服务，如数据库、消息队列、监视和分布式缓存。</span><span class="sxs-lookup"><span data-stu-id="bf148-133">Once in the cloud, the application could consume other cloud services such as databases, message queues, monitoring, and distributed caching.</span></span>

<span data-ttu-id="bf148-134">最后，执行战略企业功能的单一应用可能最好受益于*云原生*方法，这是本书的主题。</span><span class="sxs-lookup"><span data-stu-id="bf148-134">Finally, monolithic apps that perform strategic enterprise functions might best benefit from a *Cloud-Native* approach, the subject of this book.</span></span> <span data-ttu-id="bf148-135">此方法提供敏捷性和速度。</span><span class="sxs-lookup"><span data-stu-id="bf148-135">This approach provides agility and velocity.</span></span> <span data-ttu-id="bf148-136">但是，它的代价是重新平台、重新构建和重写代码。</span><span class="sxs-lookup"><span data-stu-id="bf148-136">But, it comes at a cost of replatforming, rearchitecting, and rewriting code.</span></span>

<span data-ttu-id="bf148-137">如果您和您的团队认为云原生方法是适当的，则您应该与组织一起使决策合理化。</span><span class="sxs-lookup"><span data-stu-id="bf148-137">If you and your team believe a cloud-native approach is appropriate, it behooves you to rationalize the decision with your organization.</span></span> <span data-ttu-id="bf148-138">云原生方法将解决的业务问题究竟是什么？</span><span class="sxs-lookup"><span data-stu-id="bf148-138">What exactly is the business problem that a cloud-native approach will solve?</span></span> <span data-ttu-id="bf148-139">它如何与业务需求保持一致？</span><span class="sxs-lookup"><span data-stu-id="bf148-139">How would it align with business needs?</span></span>

- <span data-ttu-id="bf148-140">快速发布功能，增强信心？</span><span class="sxs-lookup"><span data-stu-id="bf148-140">Rapid releases of features with increased confidence?</span></span>

- <span data-ttu-id="bf148-141">细粒度可扩展性 - 更有效地使用资源？</span><span class="sxs-lookup"><span data-stu-id="bf148-141">Fine-grained scalability - more efficient usage of resources?</span></span>

- <span data-ttu-id="bf148-142">提高系统弹性？</span><span class="sxs-lookup"><span data-stu-id="bf148-142">Improved system resiliency?</span></span>

- <span data-ttu-id="bf148-143">提高系统性能？</span><span class="sxs-lookup"><span data-stu-id="bf148-143">Improved system performance?</span></span>

- <span data-ttu-id="bf148-144">对操作的更多可见性？</span><span class="sxs-lookup"><span data-stu-id="bf148-144">More visibility into operations?</span></span>

- <span data-ttu-id="bf148-145">混合开发平台和数据存储，以找到最适合作业的工具？</span><span class="sxs-lookup"><span data-stu-id="bf148-145">Blend development platforms and data stores to arrive at the best tool for the job?</span></span>

- <span data-ttu-id="bf148-146">面向未来的应用投资？</span><span class="sxs-lookup"><span data-stu-id="bf148-146">Future-proof application investment?</span></span>

<span data-ttu-id="bf148-147">正确的迁移策略取决于组织优先级和您所针对的系统。</span><span class="sxs-lookup"><span data-stu-id="bf148-147">The right migration strategy depends on organizational priorities and the systems you're targeting.</span></span> <span data-ttu-id="bf148-148">对许多人来说，云优化单片应用程序或向 N-Tier 应用添加粗粒度服务可能更具成本效益。</span><span class="sxs-lookup"><span data-stu-id="bf148-148">For many, it may be more cost effective to cloud-optimize a monolithic application or add coarse-grained services to an N-Tier app.</span></span> <span data-ttu-id="bf148-149">在这些情况下，您仍然可以充分利用云 PaaS 功能，如 Azure 应用服务提供的功能。</span><span class="sxs-lookup"><span data-stu-id="bf148-149">In these cases, you can still make full use of cloud PaaS capabilities like the ones offered by Azure App Service.</span></span>

## <a name="summary"></a><span data-ttu-id="bf148-150">总结</span><span class="sxs-lookup"><span data-stu-id="bf148-150">Summary</span></span>

<span data-ttu-id="bf148-151">在本章中，我们介绍了云原生计算。</span><span class="sxs-lookup"><span data-stu-id="bf148-151">In this chapter, we introduced cloud-native computing.</span></span> <span data-ttu-id="bf148-152">我们提供了一个定义以及驱动云本机应用程序的关键功能。</span><span class="sxs-lookup"><span data-stu-id="bf148-152">We provided a definition along with the key capabilities that drive a cloud-native application.</span></span> <span data-ttu-id="bf148-153">我们研究了可能证明这种投资和努力合理的应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="bf148-153">We looked at the types of applications that might justify this investment and effort.</span></span>

<span data-ttu-id="bf148-154">在介绍之后，我们现在将深入探讨云原生。</span><span class="sxs-lookup"><span data-stu-id="bf148-154">With the introduction behind, we now dive into a much more detailed look at cloud native.</span></span>

### <a name="references"></a><span data-ttu-id="bf148-155">参考</span><span class="sxs-lookup"><span data-stu-id="bf148-155">References</span></span>

- [<span data-ttu-id="bf148-156">云原生计算基金会</span><span class="sxs-lookup"><span data-stu-id="bf148-156">Cloud Native Computing Foundation</span></span>](https://www.cncf.io/)

- [<span data-ttu-id="bf148-157">.NET 微服务：容器化 .NET 应用程序的体系结构</span><span class="sxs-lookup"><span data-stu-id="bf148-157">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="bf148-158">使用 Azure 云和 Windows 容器对现有 .NET 应用程序进行现代化</span><span class="sxs-lookup"><span data-stu-id="bf148-158">Modernize existing .NET applications with Azure cloud and Windows Containers</span></span>](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [<span data-ttu-id="bf148-159">科妮莉亚·戴维斯的云原生模式</span><span class="sxs-lookup"><span data-stu-id="bf148-159">Cloud Native Patterns by Cornelia Davis</span></span>](https://www.manning.com/books/cloud-native-patterns)

- [<span data-ttu-id="bf148-160">超越十二因素应用</span><span class="sxs-lookup"><span data-stu-id="bf148-160">Beyond the Twelve-Factor Application</span></span>](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [<span data-ttu-id="bf148-161">什么是基础架构作为代码</span><span class="sxs-lookup"><span data-stu-id="bf148-161">What is Infrastructure as Code</span></span>](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [<span data-ttu-id="bf148-162">优步工程的微观部署：自信地每天部署</span><span class="sxs-lookup"><span data-stu-id="bf148-162">Uber Engineering's Micro Deploy: Deploying Daily with Confidence</span></span>](https://eng.uber.com/micro-deploy/)

- [<span data-ttu-id="bf148-163">Netflix 如何部署代码</span><span class="sxs-lookup"><span data-stu-id="bf148-163">How Netflix Deploys Code</span></span>](https://www.infoq.com/news/2013/06/netflix/)

- [<span data-ttu-id="bf148-164">用于扩展微信微服务的过载控制</span><span class="sxs-lookup"><span data-stu-id="bf148-164">Overload Control for Scaling WeChat Microservices</span></span>](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
><span data-ttu-id="bf148-165">[上一页](definition.md)
>[下一页](introduce-eshoponcontainers-reference-app.md)</span><span class="sxs-lookup"><span data-stu-id="bf148-165">[Previous](definition.md)
[Next](introduce-eshoponcontainers-reference-app.md)</span></span>
