---
title: "协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ff524c6d61c6ce51a1a3e831cd666a3b61ac849e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a><span data-ttu-id="9091d-104">协调安排微服务和多容器应用程序，实现高可伸缩性和高可用性</span><span class="sxs-lookup"><span data-stu-id="9091d-104">Orchestrating microservices and multi-container applications for high scalability and availability</span></span>

<span data-ttu-id="9091d-105">如果应用程序基于微服务或只是跨多个容器拆分，则必须使用适用于生产就绪应用程序的业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-105">Using orchestrators for production-ready applications is essential if your application is based on microservices or simply split across multiple containers.</span></span> <span data-ttu-id="9091d-106">如前所述，在基于微服务的方法中，每个微服务均拥有其模型和数据，如此从开发和部署的角度来看，它便是具有自主性。</span><span class="sxs-lookup"><span data-stu-id="9091d-106">As introduced previously, in a microservice-based approach, each microservice owns its model and data so that it will be autonomous from a development and deployment point of view.</span></span> <span data-ttu-id="9091d-107">但即使拥有由多个服务组成的更传统的应用程序（如 SOA），也将拥有多个容器或服务，这些容器或服务中包含需要作为分布式系统部署的单个业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-107">But even if you have a more traditional application that is composed of multiple services (like SOA), you will also have multiple containers or services comprising a single business application that need to be deployed as a distributed system.</span></span> <span data-ttu-id="9091d-108">这类系统的扩展和管理非常复杂；因此，如果想要拥有生产就绪且可缩放的多容器应用程序，则必须使用业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-108">These kinds of systems are complex to scale out and manage; therefore, you absolutely need an orchestrator if you want to have a production-ready and scalable multi-container application.</span></span>

<span data-ttu-id="9091d-109">图 4-23 介绍如何部署到由多个微服务（容器）组成的应用程序群集。</span><span class="sxs-lookup"><span data-stu-id="9091d-109">Figure 4-23 illustrates deployment into a cluster of an application composed of multiple microservices (containers).</span></span>

![](./media/image23.PNG)

<span data-ttu-id="9091d-110">图 4-23。</span><span class="sxs-lookup"><span data-stu-id="9091d-110">**Figure 4-23**.</span></span> <span data-ttu-id="9091d-111">容器群集</span><span class="sxs-lookup"><span data-stu-id="9091d-111">A cluster of containers</span></span>

<span data-ttu-id="9091d-112">它看上去类似于逻辑方法。</span><span class="sxs-lookup"><span data-stu-id="9091d-112">It looks like a logical approach.</span></span> <span data-ttu-id="9091d-113">但是如何处理负载均衡、路由以及如何协调安排这些组合式应用程序呢？</span><span class="sxs-lookup"><span data-stu-id="9091d-113">But how are you handling load-balancing, routing, and orchestrating these composed applications?</span></span>

<span data-ttu-id="9091d-114">单个 Docker 主机中的普通 Docker 引擎能够满足在一台主机上管理单映像实例的需求，但若要管理针对更复杂的分布式应用程序而部署在多个主机上的多个容器，则无法满足需求。</span><span class="sxs-lookup"><span data-stu-id="9091d-114">The plain Docker Engine in single Docker hosts meets the needs of managing single image instances on one host, but it falls short when it comes to managing multiple containers deployed on multiple hosts for more complex distributed applications.</span></span> <span data-ttu-id="9091d-115">大多数情况下，需要一个管理平台，该平台能自动启动容器、扩展容器（每个映像具有多个实例）、必要时暂停或关闭，并且在理想情况下还能控制资源（如网络和数据存储）访问方式。</span><span class="sxs-lookup"><span data-stu-id="9091d-115">In most cases, you need a management platform that will automatically start containers, scale-out containers with multiple instances per image, suspend them or shut them down when needed, and ideally also control how they access resources like the network and data storage.</span></span>

<span data-ttu-id="9091d-116">如果不仅要管理个别容器或非常简单的组合式应用，还要进一步管理使用微服务的较大型企业应用程序，则必须转向业务流程和群集平台。</span><span class="sxs-lookup"><span data-stu-id="9091d-116">To go beyond the management of individual containers or very simple composed apps and move toward larger enterprise applications with microservices, you must turn to orchestration and clustering platforms.</span></span>

<span data-ttu-id="9091d-117">从体系结构和开发的角度来看，如果要生成由基于微服务的应用程序组成的大型企业应用程序，则务必了解清楚下面列出的支持高级方案的平台和产品：</span><span class="sxs-lookup"><span data-stu-id="9091d-117">From an architecture and development point of view, if you are building large enterprise composed of microservices-based applications, it is important to understand the following platforms and products that support advanced scenarios:</span></span>

<span data-ttu-id="9091d-118">**群集和业务流程协调程序**。</span><span class="sxs-lookup"><span data-stu-id="9091d-118">**Clusters and orchestrators**.</span></span> <span data-ttu-id="9091d-119">如果需要跨多个 Docker 主机扩展应用程序例如生成基于微服务的大型应用程序时，能够通过抽象化基础平台的复杂性来将所有主机作为单个群集管理是至关重要的。</span><span class="sxs-lookup"><span data-stu-id="9091d-119">When you need to scale out applications across many Docker hosts, as when a large microservice-based application, it is critical to be able to manage all those hosts as a single cluster by abstracting the complexity of the underlying platform.</span></span> <span data-ttu-id="9091d-120">这就是容器群集和业务流程协调程序所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="9091d-120">That is what the container clusters and orchestrators provide.</span></span> <span data-ttu-id="9091d-121">业务流程协调程序示例包括 Azure Service Fabric、Kubernetes、Docker Swarm 和 Mesosphere DC/OS。</span><span class="sxs-lookup"><span data-stu-id="9091d-121">Examples of orchestrators are Azure Service Fabric, Kubernetes, Docker Swarm and Mesosphere DC/OS.</span></span> <span data-ttu-id="9091d-122">通过 Azure 容器服务，可在 Azure 中获取最后三个开源业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-122">The last three open-source orchestrators are available in Azure through Azure Container Service.</span></span>

<span data-ttu-id="9091d-123">**计划程序**。</span><span class="sxs-lookup"><span data-stu-id="9091d-123">**Schedulers**.</span></span> <span data-ttu-id="9091d-124">计划意味着管理员能够在群集中启动容器，如此这些容器也可提供 UI。</span><span class="sxs-lookup"><span data-stu-id="9091d-124">*Scheduling* means to have the capability for an administrator to launch containers in a cluster so they also provide a UI.</span></span> <span data-ttu-id="9091d-125">群集计划程序具有多个职责：高效使用群集资源、设置用户提供的约束、有效负载均衡节点或主机间的容器，以及在提供高可用性的同时强力解决错误。</span><span class="sxs-lookup"><span data-stu-id="9091d-125">A cluster scheduler has several responsibilities: to use the cluster’s resources efficiently, to set the constraints provided by the user, to efficiently load-balance containers across nodes or hosts, and to be robust against errors while providing high availability.</span></span>

<span data-ttu-id="9091d-126">群集和计划程序的概念密切相关，因此不同供应商提供的产品通常具有这两套功能。</span><span class="sxs-lookup"><span data-stu-id="9091d-126">The concepts of a cluster and a scheduler are closely related, so the products provided by different vendors often provide both sets of capabilities.</span></span> <span data-ttu-id="9091d-127">下表显示了适用于群集和计划程序的最重要的平台和软件选项。</span><span class="sxs-lookup"><span data-stu-id="9091d-127">The following list shows the most important platform and software choices you have for clusters and schedulers.</span></span> <span data-ttu-id="9091d-128">通常在公有云（如 Azure）中提供这些业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-128">These orchestrators are generally offered in public clouds like Azure.</span></span>

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a><span data-ttu-id="9091d-129">适用于容器群集、业务流程和计划的软件平台</span><span class="sxs-lookup"><span data-stu-id="9091d-129">Software platforms for container clustering, orchestration, and scheduling</span></span>

<span data-ttu-id="9091d-130">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9091d-130">Kubernetes</span></span>

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> <span data-ttu-id="9091d-132">Kubernetes 是一款开源产品，提供各种功能，从群集基础结构和容器计划到安排功能均涵盖在内。</span><span class="sxs-lookup"><span data-stu-id="9091d-132">Kubernetes is an open-source product that provides functionality that ranges from cluster infrastructure and container scheduling to orchestrating capabilities.</span></span> <span data-ttu-id="9091d-133">它能实现跨主机群集自动部署、缩放以及执行各种应用程序容器操作。</span><span class="sxs-lookup"><span data-stu-id="9091d-133">It lets you automate deployment, scaling, and operations of application containers across clusters of hosts.</span></span>
>
> <span data-ttu-id="9091d-134">Kubernetes 提供以容器为中心的基础结构，将应用程序容器分组为逻辑单元，以便管理和发现。</span><span class="sxs-lookup"><span data-stu-id="9091d-134">Kubernetes provides a container-centric infrastructure that groups application containers into logical units for easy management and discovery.</span></span>
>
> <span data-ttu-id="9091d-135">Kubernetes 在 Linux 中的运用已发展成熟，但在 Windows 中相对较弱。</span><span class="sxs-lookup"><span data-stu-id="9091d-135">Kubernetes is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="9091d-136">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="9091d-136">Docker Swarm</span></span>

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> <span data-ttu-id="9091d-138">Docker Swarm 能够对 Docker 容器进行聚类分析和计划。</span><span class="sxs-lookup"><span data-stu-id="9091d-138">Docker Swarm lets you cluster and schedule Docker containers.</span></span> <span data-ttu-id="9091d-139">通过使用 Swarm，可以将多个 Docker 主机转换味单个虚拟 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="9091d-139">By using Swarm, you can turn a pool of Docker hosts into a single, virtual Docker host.</span></span> <span data-ttu-id="9091d-140">客户端可以向 Swarm 发出 API 请求（方法同其向主机发出请求），这意味着 Swarm 可以使应用程序轻松地扩展到多个主机。</span><span class="sxs-lookup"><span data-stu-id="9091d-140">Clients can make API requests to Swarm the same way they do to hosts, meaning that Swarm makes it easy for applications to scale to multiple hosts.</span></span>
>
> <span data-ttu-id="9091d-141">Docker Swarm 是来自 Docker 公司 的产品。</span><span class="sxs-lookup"><span data-stu-id="9091d-141">Docker Swarm is a product from Docker, the company.</span></span>
>
> <span data-ttu-id="9091d-142">Docker v1.12 或更高版本可以运行本机内置 Swarm 模式。</span><span class="sxs-lookup"><span data-stu-id="9091d-142">Docker v1.12 or later can run native and built-in Swarm Mode.</span></span>

<span data-ttu-id="9091d-143">Mesosphere DC/OS</span><span class="sxs-lookup"><span data-stu-id="9091d-143">Mesosphere DC/OS</span></span>

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> <span data-ttu-id="9091d-145">Mesosphere Enterprise DC/OS（基于 Apache Mesos）是用于运行容器和分布式应用程序的生产就绪平台。</span><span class="sxs-lookup"><span data-stu-id="9091d-145">Mesosphere Enterprise DC/OS (based on Apache Mesos) is a production-ready platform for running containers and distributed applications.</span></span>
>
> <span data-ttu-id="9091d-146">DC/OS 的工作方式是提取群集中的可用资源集合，并使这些资源可用于在其上构建的组件。</span><span class="sxs-lookup"><span data-stu-id="9091d-146">DC/OS works by abstracting a collection of the resources available in the cluster and making those resources available to components built on top of it.</span></span> <span data-ttu-id="9091d-147">Marathon 通常用作与 DC/OS 集成的计划程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-147">Marathon is usually used as a scheduler integrated with DC/OS.</span></span>
>
> <span data-ttu-id="9091d-148">DC/OS 在 Linux 中的运用已发展成熟，但在 Windows 中相对较弱。</span><span class="sxs-lookup"><span data-stu-id="9091d-148">DC/OS is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="9091d-149">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="9091d-149">Azure Service Fabric</span></span>

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> <span data-ttu-id="9091d-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) 是用于生成应用程序的 Microsoft 微服务平台。</span><span class="sxs-lookup"><span data-stu-id="9091d-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) is a Microsoft microservices platform for building applications.</span></span> <span data-ttu-id="9091d-152">它是服务的[业务流程协调程序](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)，可创建计算机群集。</span><span class="sxs-lookup"><span data-stu-id="9091d-152">It is an [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) of services and creates clusters of machines.</span></span> <span data-ttu-id="9091d-153">Service Fabric 可将服务作为容器或纯进程进行部署。</span><span class="sxs-lookup"><span data-stu-id="9091d-153">Service Fabric can deploy services as containers or as plain processes.</span></span> <span data-ttu-id="9091d-154">它甚至可以在同一应用程序和群集中将进程中的服务与容器中的服务进行组合。</span><span class="sxs-lookup"><span data-stu-id="9091d-154">It can even mix services in processes with services in containers within the same application and cluster.</span></span>
>
> <span data-ttu-id="9091d-155">Service Fabric 提供其他可选的规定 [Service Fabric 编程模型](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)（如[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)和 [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)）。</span><span class="sxs-lookup"><span data-stu-id="9091d-155">Service Fabric provides additional and optional prescriptive [Service Fabric programming models ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) like [stateful services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) and [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).</span></span>
>
> <span data-ttu-id="9091d-156">Service Fabric 在 Windows 中的运用已经成熟（已在 Windows 中发展多年），但在 Linux 中相对较弱。</span><span class="sxs-lookup"><span data-stu-id="9091d-156">Service Fabric is mature in Windows (years evolving in Windows), less mature in Linux.</span></span> 
> <span data-ttu-id="9091d-157">自 2017 年以来，Service Fabric 同时支持 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9091d-157">Both Linux and Windows containers are supported in Service Fabric since 2017.</span></span>

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a><span data-ttu-id="9091d-158">在 Microsoft Azure 中使用基于容器的业务流程协调程序</span><span class="sxs-lookup"><span data-stu-id="9091d-158">Using container-based orchestrators in Microsoft Azure</span></span>

<span data-ttu-id="9091d-159">多家云供应商提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Microsoft Azure、Amazon EC2 容器服务和 Google 容器引擎。</span><span class="sxs-lookup"><span data-stu-id="9091d-159">Several cloud vendors offer Docker containers support plus Docker clusters and orchestration support, including Microsoft Azure, Amazon EC2 Container Service, and Google Container Engine.</span></span> <span data-ttu-id="9091d-160">Microsoft Azure 通过 Azure 容器服务 (ACS) 提供 Docker 群集和业务流程协调程序支持，下一节中将详细说明。</span><span class="sxs-lookup"><span data-stu-id="9091d-160">Microsoft Azure provides Docker cluster and orchestrator support through Azure Container Service (ACS), as explained in the next section.</span></span>

<span data-ttu-id="9091d-161">另一个选项是使用 Microsoft Azure Service Fabric（微服务平台），它也支持基于 Linux 和 Windows 容器的 Docker。</span><span class="sxs-lookup"><span data-stu-id="9091d-161">Another choice is to use Microsoft Azure Service Fabric (a microservices platform), which also supports Docker based on Linux and Windows Containers.</span></span> <span data-ttu-id="9091d-162">Service Fabric 可在 Azure 或其他云上运行，也可在[本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)运行。</span><span class="sxs-lookup"><span data-stu-id="9091d-162">Service Fabric runs on Azure or any other cloud, and also runs [on-premises](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).</span></span>

## <a name="using-azure-container-service"></a><span data-ttu-id="9091d-163">使用 Azure 容器服务</span><span class="sxs-lookup"><span data-stu-id="9091d-163">Using Azure Container Service</span></span>

<span data-ttu-id="9091d-164">Docker 群集汇集多个 Docker 主机，并将它们作为单个虚拟 Docker 主机公开，因此可以将多个容器部署到群集。</span><span class="sxs-lookup"><span data-stu-id="9091d-164">A Docker cluster pools multiple Docker hosts and exposes them as a single virtual Docker host, so you can deploy multiple containers into the cluster.</span></span> <span data-ttu-id="9091d-165">该群集将处理可伸缩性、运行状况等所有复杂的管理任务。</span><span class="sxs-lookup"><span data-stu-id="9091d-165">The cluster will handle all the complex management plumbing, like scalability, health, and so forth.</span></span> <span data-ttu-id="9091d-166">图 4-24 显示组合式应用程序的 Docker 群集如何映射到 Azure 容器服务 (ACS)。</span><span class="sxs-lookup"><span data-stu-id="9091d-166">Figure 4-24 represents how a Docker cluster for composed applications maps to Azure Container Service (ACS).</span></span>

<span data-ttu-id="9091d-167">ACS 提供了一种方法，可简化虚拟机（预配置为运行容器化应用程序）群集的创建、配置和管理。</span><span class="sxs-lookup"><span data-stu-id="9091d-167">ACS provides a way to simplify the creation, configuration, and management of a cluster of virtual machines that are preconfigured to run containerized applications.</span></span> <span data-ttu-id="9091d-168">通过使用常用开源计划和业务流程工具的优化配置，ACS 能够利用现有技能或大量不断增长的社区专业知识，在 Microsoft Azure 上部署和管理基于容器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-168">Using an optimized configuration of popular open-source scheduling and orchestration tools, ACS enables you to use your existing skills or draw on a large and growing body of community expertise to deploy and manage container-based applications on Microsoft Azure.</span></span>

<span data-ttu-id="9091d-169">Azure 容器服务优化了专门针对 Azure 的常用 Docker 群集开源和技术的配置。</span><span class="sxs-lookup"><span data-stu-id="9091d-169">Azure Container Service optimizes the configuration of popular Docker clustering open source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="9091d-170">可以获得一个开放的解决方案，该解决方案为容器和应用程序配置提供可移植性。</span><span class="sxs-lookup"><span data-stu-id="9091d-170">You get an open solution that offers portability for both your containers and your application configuration.</span></span> <span data-ttu-id="9091d-171">用户选择主机的大小和数量以及业务流程协调程序工具，然后容器服务可处理其他操作。</span><span class="sxs-lookup"><span data-stu-id="9091d-171">You select the size, the number of hosts, and the orchestrator tools, and Container Service handles everything else.</span></span>

![](./media/image28.png)

<span data-ttu-id="9091d-172">图 4-24。</span><span class="sxs-lookup"><span data-stu-id="9091d-172">**Figure 4-24**.</span></span> <span data-ttu-id="9091d-173">Azure 容器服务中的群集选项</span><span class="sxs-lookup"><span data-stu-id="9091d-173">Clustering choices in Azure Container Service</span></span>

<span data-ttu-id="9091d-174">ACS 利用 Docker 映像来确保应用程序容器是完全可移植的。</span><span class="sxs-lookup"><span data-stu-id="9091d-174">ACS leverages Docker images to ensure that your application containers are fully portable.</span></span> <span data-ttu-id="9091d-175">它支持选择开源业务流程平台，如 DC/OS （由 Apache Mesos 提供支持）、Kubernetes（最初由 Google 创建）和 Docker Swarm，确保这些应用程序可以扩展到数千或甚至数万个容器。</span><span class="sxs-lookup"><span data-stu-id="9091d-175">It supports your choice of open-source orchestration platforms like DC/OS (powered by Apache Mesos), Kubernetes (originally created by Google), and Docker Swarm, to ensure that these applications can be scaled to thousands or even tens of thousands of containers.</span></span>

<span data-ttu-id="9091d-176">Azure 容器服务能够利用 Azure 的企业级功能，同时仍然保持应用程序的可移植性，包括业务流程层的可移植性。</span><span class="sxs-lookup"><span data-stu-id="9091d-176">The Azure Container service enables you to take advantage of the enterprise-grade features of Azure while still maintaining application portability, including at the orchestration layers.</span></span>

![](./media/image29.png)

<span data-ttu-id="9091d-177">图 4-25。</span><span class="sxs-lookup"><span data-stu-id="9091d-177">**Figure 4-25**.</span></span> <span data-ttu-id="9091d-178">ACS 中的业务流程协调程序</span><span class="sxs-lookup"><span data-stu-id="9091d-178">Orchestrators in ACS</span></span>

<span data-ttu-id="9091d-179">如图 4-25 所示，Azure 容器服务只是 Azure 提供的基础结构，以便部署 DC/OS、Kubernetes 或 Docker Swarm，但 ACS 不实现任何其他业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9091d-179">As shown in Figure 4-25, Azure Container Service is simply the infrastructure provided by Azure in order to deploy DC/OS, Kubernetes or Docker Swarm, but ACS does not implement any additional orchestrator.</span></span> <span data-ttu-id="9091d-180">因此，ACS 本身并不是这种业务流程协调程序，只是利用容器的现有开源业务流程协调程序的基础结构。</span><span class="sxs-lookup"><span data-stu-id="9091d-180">Therefore, ACS is not an orchestrator as such, only an infrastructure that leverages existing open-source orchestrators for containers.</span></span>

<span data-ttu-id="9091d-181">从使用情况来看，Azure 容器服务的目标是通过使用常用的开源工具和技术提供容器的托管环境。</span><span class="sxs-lookup"><span data-stu-id="9091d-181">From a usage perspective, the goal of Azure Container Service is to provide a container hosting environment by using popular open-source tools and technologies.</span></span> <span data-ttu-id="9091d-182">为此，它为选择的业务流程协调程序公开标准 API 终结点。</span><span class="sxs-lookup"><span data-stu-id="9091d-182">To this end, it exposes the standard API endpoints for your chosen orchestrator.</span></span> <span data-ttu-id="9091d-183">通过使用这些终结点，可以利用能与这些终结点通信的任何软件。</span><span class="sxs-lookup"><span data-stu-id="9091d-183">By using these endpoints, you can leverage any software that can talk to those endpoints.</span></span> <span data-ttu-id="9091d-184">例如，对于 Docker Swarm 终结点，可选择使用 Docker 命令行接口 (CLI)。</span><span class="sxs-lookup"><span data-stu-id="9091d-184">For example, in the case of the Docker Swarm endpoint, you might choose to use the Docker command-line interface (CLI).</span></span> <span data-ttu-id="9091d-185">对于 DC/OS，可选择使用 DC/OS CLI。</span><span class="sxs-lookup"><span data-stu-id="9091d-185">For DC/OS, you might choose to use the DC/OS CLI.</span></span>

### <a name="getting-started-with-azure-container-service"></a><span data-ttu-id="9091d-186">Azure 容器服务入门</span><span class="sxs-lookup"><span data-stu-id="9091d-186">Getting started with Azure Container Service</span></span> 

<span data-ttu-id="9091d-187">若要开始使用 Azure 容器服务，请使用 Azure 资源管理器模板或 [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli) 从 Azure 门户部署 Azure 容器服务群集。</span><span class="sxs-lookup"><span data-stu-id="9091d-187">To begin using Azure Container Service, you deploy an Azure Container Service cluster from the Azure portal by using an Azure Resource Manager template or the [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli).</span></span> <span data-ttu-id="9091d-188">可用模板包括 [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)、[Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) 和 [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。</span><span class="sxs-lookup"><span data-stu-id="9091d-188">Available templates include [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), and [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos).</span></span> <span data-ttu-id="9091d-189">快速入门模板可以修改为包括其他或高级 Azure 配置。</span><span class="sxs-lookup"><span data-stu-id="9091d-189">The quickstart templates can be modified to include additional or advanced Azure configuration.</span></span> <span data-ttu-id="9091d-190">有关部署 Azure 容器服务群集的详细信息，请参阅 Azure 网站上的[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/container-service-deployment)。</span><span class="sxs-lookup"><span data-stu-id="9091d-190">For more information on deploying an Azure Container Service cluster, see [Deploy an Azure Container Service cluster](https://docs.microsoft.com/azure/container-service/container-service-deployment) on the Azure website.</span></span>

<span data-ttu-id="9091d-191">作为 ACS 的一部分，默认安装的任何软件都不收费。</span><span class="sxs-lookup"><span data-stu-id="9091d-191">There are no fees for any of the software installed by default as part of ACS.</span></span> <span data-ttu-id="9091d-192">所有默认选项都通过开源软件实现。</span><span class="sxs-lookup"><span data-stu-id="9091d-192">All default options are implemented with open-source software.</span></span>

<span data-ttu-id="9091d-193">ACS 当前可用于 Azure 中的标准 A、D、DS、G 和 GS 系列 Linux 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="9091d-193">ACS is currently available for Standard A, D, DS, G, and GS series Linux virtual machines in Azure.</span></span> <span data-ttu-id="9091d-194">仅针对所选的计算实例以及使用的其他基础结构资源（如存储和网络）收取费用。</span><span class="sxs-lookup"><span data-stu-id="9091d-194">You are charged only for the compute instances you choose, as well as the other underlying infrastructure resources consumed, such as storage and networking.</span></span> <span data-ttu-id="9091d-195">ACS 本身不会以增量方式收费。</span><span class="sxs-lookup"><span data-stu-id="9091d-195">There are no incremental charges for ACS itself.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9091d-196">其他资源</span><span class="sxs-lookup"><span data-stu-id="9091d-196">Additional resources</span></span>

-   <span data-ttu-id="9091d-197">**使用 Azure 容器服务的 Docker 容器托管解决方案见解**
    [https://docs.microsoft.com/azure/container-service/container-service-intro](https://docs.microsoft.com/azure/container-service/container-service-intro)</span><span class="sxs-lookup"><span data-stu-id="9091d-197">**Introduction to Docker container hosting solutions with Azure Container Service**
[*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)</span></span>

-   <span data-ttu-id="9091d-198">**Docker Swarm overview**
    （Docker Swarm 概述）[https://docs.docker.com/swarm/overview/](https://docs.docker.com/swarm/overview/)</span><span class="sxs-lookup"><span data-stu-id="9091d-198">**Docker Swarm overview**
[*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)</span></span>

-   <span data-ttu-id="9091d-199">**Swarm mode overview**
    (Swarm 模式概述)[https://docs.docker.com/engine/swarm/](https://docs.docker.com/engine/swarm/)</span><span class="sxs-lookup"><span data-stu-id="9091d-199">**Swarm mode overview**
[*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)</span></span>

-   <span data-ttu-id="9091d-200">**Mesosphere DC/OS Overview**
    （Mesosphere DC/OS 概述）[https://docs.mesosphere.com/1.7/overview/](https://docs.mesosphere.com/1.7/overview/)</span><span class="sxs-lookup"><span data-stu-id="9091d-200">**Mesosphere DC/OS Overview**
[*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)</span></span>

-   <span data-ttu-id="9091d-201">**Kubernetes。**</span><span class="sxs-lookup"><span data-stu-id="9091d-201">**Kubernetes.**</span></span> <span data-ttu-id="9091d-202">官方网站。</span><span class="sxs-lookup"><span data-stu-id="9091d-202">The official site.\\</span></span>
    [<span data-ttu-id="9091d-203">http://kubernetes.io/</span><span class="sxs-lookup"><span data-stu-id="9091d-203">*http://kubernetes.io/*</span></span>](http://kubernetes.io/)


>[!div class="step-by-step"]
<span data-ttu-id="9091d-204">[上一页] (resilient-high-availability-microservices.md) [下一页] (using-azure-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="9091d-204">[Previous] (resilient-high-availability-microservices.md) [Next] (using-azure-service-fabric.md)</span></span>
