---
title: "协调微服务和多容器应用程序的高可伸缩性和可用性"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |协调微服务和多容器应用程序的高可伸缩性和可用性"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a><span data-ttu-id="8b9e8-104">协调微服务和多容器应用程序的高可伸缩性和可用性</span><span class="sxs-lookup"><span data-stu-id="8b9e8-104">Orchestrating microservices and multi-container applications for high scalability and availability</span></span>

<span data-ttu-id="8b9e8-105">如果你的应用程序是基于微服务或只需将拆分到多个容器，对生产就绪应用程序使用 orchestrators 就至关重要。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-105">Using orchestrators for production-ready applications is essential if your application is based on microservices or simply split across multiple containers.</span></span> <span data-ttu-id="8b9e8-106">因为以前，在基于微服务构成的方法中，引入了每个微服务拥有的模型和数据，以便将成为自治的开发和部署的角度。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-106">As introduced previously, in a microservice-based approach, each microservice owns its model and data so that it will be autonomous from a development and deployment point of view.</span></span> <span data-ttu-id="8b9e8-107">但即使你有了更传统的应用程序，其中包含多个服务 （如 SOA)，你还将具有多个容器或服务组成的单个业务应用程序需要作为分布式系统进行部署。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-107">But even if you have a more traditional application that is composed of multiple services (like SOA), you will also have multiple containers or services comprising a single business application that need to be deployed as a distributed system.</span></span> <span data-ttu-id="8b9e8-108">这些类型的系统很复杂，来向外扩展和管理;因此，如果你想要有一个生产就绪且可伸缩的多容器应用程序绝对需要编排器。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-108">These kinds of systems are complex to scale out and manage; therefore, you absolutely need an orchestrator if you want to have a production-ready and scalable multi-container application.</span></span>

<span data-ttu-id="8b9e8-109">图 4-23 阐释了部署到多个微服务 （容器） 组成的应用程序的群集。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-109">Figure 4-23 illustrates deployment into a cluster of an application composed of multiple microservices (containers).</span></span>

![](./media/image23.PNG)

<span data-ttu-id="8b9e8-110">**图 4-23**。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-110">**Figure 4-23**.</span></span> <span data-ttu-id="8b9e8-111">有个容器的群集</span><span class="sxs-lookup"><span data-stu-id="8b9e8-111">A cluster of containers</span></span>

<span data-ttu-id="8b9e8-112">它看上去像逻辑的方法。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-112">It looks like a logical approach.</span></span> <span data-ttu-id="8b9e8-113">但是，如何为你处理负载平衡、 路由和协调这些组成应用程序？</span><span class="sxs-lookup"><span data-stu-id="8b9e8-113">But how are you handling load-balancing, routing, and orchestrating these composed applications?</span></span>

<span data-ttu-id="8b9e8-114">单个 Docker 主机中的纯 Docker 引擎满足需要的管理一个主机上的单个映像实例，但管理更复杂的分布式应用程序的多个主机上部署的多个容器时，这个过程很短。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-114">The plain Docker Engine in single Docker hosts meets the needs of managing single image instances on one host, but it falls short when it comes to managing multiple containers deployed on multiple hosts for more complex distributed applications.</span></span> <span data-ttu-id="8b9e8-115">在大多数情况下，你需要一个管理平台，将自动启动容器，使用每个图像的多个实例的横向扩展容器挂起它们或在需要时关闭它们，理想情况下还控制访问资源，如网络和数据的方式存储。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-115">In most cases, you need a management platform that will automatically start containers, scale-out containers with multiple instances per image, suspend them or shut them down when needed, and ideally also control how they access resources like the network and data storage.</span></span>

<span data-ttu-id="8b9e8-116">以超出单个容器或非常简单的由应用程序和更接近微服务使用的大型企业应用程序的管理，你必须启用业务流程和群集平台。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-116">To go beyond the management of individual containers or very simple composed apps and move toward larger enterprise applications with microservices, you must turn to orchestration and clustering platforms.</span></span>

<span data-ttu-id="8b9e8-117">从体系结构和开发角度来看，如果你正在构建的基于微服务应用程序，组成的大型企业务必了解以下平台和产品的支持高级的方案：</span><span class="sxs-lookup"><span data-stu-id="8b9e8-117">From an architecture and development point of view, if you are building large enterprise composed of microservices-based applications, it is important to understand the following platforms and products that support advanced scenarios:</span></span>

<span data-ttu-id="8b9e8-118">**群集和 orchestrators**。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-118">**Clusters and orchestrators**.</span></span> <span data-ttu-id="8b9e8-119">当你需要横向扩展应用程序跨多个 Docker 主机，因为当大型基于微服务构成的应用程序，它是关键能够通过抽取基础平台的复杂性作为一个群集管理所有这些主机。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-119">When you need to scale out applications across many Docker hosts, as when a large microservice-based application, it is critical to be able to manage all those hosts as a single cluster by abstracting the complexity of the underlying platform.</span></span> <span data-ttu-id="8b9e8-120">这就是容器群集和 orchestrators 的提供。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-120">That is what the container clusters and orchestrators provide.</span></span> <span data-ttu-id="8b9e8-121">Orchestrators 的示例包括 Azure Service Fabric、 Kubernetes、 Docker Swarm 和 Mesosphere DC/OS。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-121">Examples of orchestrators are Azure Service Fabric, Kubernetes, Docker Swarm and Mesosphere DC/OS.</span></span> <span data-ttu-id="8b9e8-122">最后三个开放源代码 orchestrators 是通过 Azure 容器服务的 Azure 中提供。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-122">The last three open-source orchestrators are available in Azure through Azure Container Service.</span></span>

<span data-ttu-id="8b9e8-123">**计划程序**。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-123">**Schedulers**.</span></span> <span data-ttu-id="8b9e8-124">*计划*意味着能够使用的管理员才能启动群集中的容器，因此它们还提供 UI 的功能。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-124">*Scheduling* means to have the capability for an administrator to launch containers in a cluster so they also provide a UI.</span></span> <span data-ttu-id="8b9e8-125">一个群集计划程序有多个职责： 以有效地使用群集的资源、 设置用户，有效地跨节点或主机的负载平衡容器提供的约束以及要同时提供高可靠针对错误可用性。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-125">A cluster scheduler has several responsibilities: to use the cluster’s resources efficiently, to set the constraints provided by the user, to efficiently load-balance containers across nodes or hosts, and to be robust against errors while providing high availability.</span></span>

<span data-ttu-id="8b9e8-126">密切相关的群集，计划程序的概念，因此通常由不同供应商提供的产品提供的功能的两个集。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-126">The concepts of a cluster and a scheduler are closely related, so the products provided by different vendors often provide both sets of capabilities.</span></span> <span data-ttu-id="8b9e8-127">以下列表显示的最重要的平台和你有针对群集和计划程序的软件选择。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-127">The following list shows the most important platform and software choices you have for clusters and schedulers.</span></span> <span data-ttu-id="8b9e8-128">这些 orchestrators 通常是按如 Azure 公有云提供的。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-128">These orchestrators are generally offered in public clouds like Azure.</span></span>

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a><span data-ttu-id="8b9e8-129">对群集的容器、 编排和计划的软件平台</span><span class="sxs-lookup"><span data-stu-id="8b9e8-129">Software platforms for container clustering, orchestration, and scheduling</span></span>

<span data-ttu-id="8b9e8-130">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="8b9e8-130">Kubernetes</span></span>

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> <span data-ttu-id="8b9e8-132">Kubernetes 是一种开放源代码产品，它提供功能，范围为群集基础结构和容器协调功能计划。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-132">Kubernetes is an open-source product that provides functionality that ranges from cluster infrastructure and container scheduling to orchestrating capabilities.</span></span> <span data-ttu-id="8b9e8-133">它使你能够自动部署、 缩放和操作的应用程序容器跨主机群集。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-133">It lets you automate deployment, scaling, and operations of application containers across clusters of hosts.</span></span>
>
> <span data-ttu-id="8b9e8-134">Kubernetes 提供分组为逻辑单元轻松管理和发现的应用程序容器的容器以中心基础结构。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-134">Kubernetes provides a container-centric infrastructure that groups application containers into logical units for easy management and discovery.</span></span>
>
> <span data-ttu-id="8b9e8-135">在 Linux 中，Windows 中不太成熟成熟 Kubernetes。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-135">Kubernetes is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="8b9e8-136">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="8b9e8-136">Docker Swarm</span></span>

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> <span data-ttu-id="8b9e8-138">Docker Swarm 允许群集和计划 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-138">Docker Swarm lets you cluster and schedule Docker containers.</span></span> <span data-ttu-id="8b9e8-139">通过使用 Swarm，便可以将转换单个、 虚拟的 Docker 主机的 Docker 主机的池。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-139">By using Swarm, you can turn a pool of Docker hosts into a single, virtual Docker host.</span></span> <span data-ttu-id="8b9e8-140">客户端可以发出 API 请求以 Swarm 相同的方式一样主机，这意味着，Swarm 轻松地让应用程序扩展到多个主机。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-140">Clients can make API requests to Swarm the same way they do to hosts, meaning that Swarm makes it easy for applications to scale to multiple hosts.</span></span>
>
> <span data-ttu-id="8b9e8-141">Docker Swarm 是从 Docker，公司的产品。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-141">Docker Swarm is a product from Docker, the company.</span></span>
>
> <span data-ttu-id="8b9e8-142">Docker v1.12 或更高版本可以运行本机和内置 Swarm 模式。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-142">Docker v1.12 or later can run native and built-in Swarm Mode.</span></span>

<span data-ttu-id="8b9e8-143">Mesosphere DC/OS</span><span class="sxs-lookup"><span data-stu-id="8b9e8-143">Mesosphere DC/OS</span></span>

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> <span data-ttu-id="8b9e8-145">Mesosphere 企业 DC/OS （基于 Apache Mesos） 是一个用于运行容器和分布式应用程序的生产就绪平台。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-145">Mesosphere Enterprise DC/OS (based on Apache Mesos) is a production-ready platform for running containers and distributed applications.</span></span>
>
> <span data-ttu-id="8b9e8-146">DC/OS 工作方式： 它的群集中可用的资源集合，并使这些资源可用于上构建的组件。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-146">DC/OS works by abstracting a collection of the resources available in the cluster and making those resources available to components built on top of it.</span></span> <span data-ttu-id="8b9e8-147">Marathon 通常用作与 DC/OS 集成在一起的计划。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-147">Marathon is usually used as a scheduler integrated with DC/OS.</span></span>
>
> <span data-ttu-id="8b9e8-148">DC/OS 是在 Linux 中，Windows 中不太成熟成熟。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-148">DC/OS is mature in Linux, less mature in Windows.</span></span>

<span data-ttu-id="8b9e8-149">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="8b9e8-149">Azure Service Fabric</span></span>

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> <span data-ttu-id="8b9e8-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview)是 Microsoft 微服务平台，用于生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-151">[Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) is a Microsoft microservices platform for building applications.</span></span> <span data-ttu-id="8b9e8-152">它是[orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction)的服务，并创建群集的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-152">It is an [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) of services and creates clusters of machines.</span></span> <span data-ttu-id="8b9e8-153">为容器或纯进程，Service Fabric 可以将服务部署。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-153">Service Fabric can deploy services as containers or as plain processes.</span></span> <span data-ttu-id="8b9e8-154">它可以甚至组合进程中的服务容器中的相同应用程序和群集中的服务。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-154">It can even mix services in processes with services in containers within the same application and cluster.</span></span>
>
> <span data-ttu-id="8b9e8-155">Service Fabric 提供了附加的和可选说明性[编程模型的 Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework)如[有状态服务](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction)和[Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-155">Service Fabric provides additional and optional prescriptive [Service Fabric programming models ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) like [stateful services](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) and [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).</span></span>
>
> <span data-ttu-id="8b9e8-156">在 Windows 中 （数年时间发展 Windows 中），较成熟在 Linux 中，Service Fabric 是成熟。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-156">Service Fabric is mature in Windows (years evolving in Windows), less mature in Linux.</span></span> 
> <span data-ttu-id="8b9e8-157">自 2017 年以来，在 Service Fabric 支持 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-157">Both Linux and Windows containers are supported in Service Fabric since 2017.</span></span>

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a><span data-ttu-id="8b9e8-158">在 Microsoft Azure 中使用容器基于 orchestrators</span><span class="sxs-lookup"><span data-stu-id="8b9e8-158">Using container-based orchestrators in Microsoft Azure</span></span>

<span data-ttu-id="8b9e8-159">多个云供应商都提供 Docker 容器支持以及 Docker 群集和业务流程支持，包括 Microsoft Azure、 Amazon EC2 容器服务和 Google 容器引擎。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-159">Several cloud vendors offer Docker containers support plus Docker clusters and orchestration support, including Microsoft Azure, Amazon EC2 Container Service, and Google Container Engine.</span></span> <span data-ttu-id="8b9e8-160">在下一部分中所述，Microsoft Azure 将提供 Docker 群集和 orchestrator 支持通过 Azure 容器服务 (ACS)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-160">Microsoft Azure provides Docker cluster and orchestrator support through Azure Container Service (ACS), as explained in the next section.</span></span>

<span data-ttu-id="8b9e8-161">另一个选项是使用 Microsoft Azure Service Fabric （微服务平台），它还支持基于 Linux 和 Windows 容器的 Docker。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-161">Another choice is to use Microsoft Azure Service Fabric (a microservices platform), which also supports Docker based on Linux and Windows Containers.</span></span> <span data-ttu-id="8b9e8-162">Service Fabric 在 Azure 或任何其他云上运行，并且还运行[本地](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-162">Service Fabric runs on Azure or any other cloud, and also runs [on-premises](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).</span></span>

## <a name="using-azure-container-service"></a><span data-ttu-id="8b9e8-163">使用 Azure 容器服务</span><span class="sxs-lookup"><span data-stu-id="8b9e8-163">Using Azure Container Service</span></span>

<span data-ttu-id="8b9e8-164">Docker 群集池多个 Docker 主机，并将它们作为单个虚拟 Docker 主机时，公开，以便你可以将多个容器部署到群集。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-164">A Docker cluster pools multiple Docker hosts and exposes them as a single virtual Docker host, so you can deploy multiple containers into the cluster.</span></span> <span data-ttu-id="8b9e8-165">群集将处理可伸缩性、 运行状况，等的所有复杂的管理管道。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-165">The cluster will handle all the complex management plumbing, like scalability, health, and so forth.</span></span> <span data-ttu-id="8b9e8-166">图 4-24 表示由应用程序的 Docker 群集如何映射到 Azure 容器服务 (ACS)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-166">Figure 4-24 represents how a Docker cluster for composed applications maps to Azure Container Service (ACS).</span></span>

<span data-ttu-id="8b9e8-167">ACS 提供的方法来简化创建、 配置和管理已预先配置为运行容器化应用程序的虚拟机的群集。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-167">ACS provides a way to simplify the creation, configuration, and management of a cluster of virtual machines that are preconfigured to run containerized applications.</span></span> <span data-ttu-id="8b9e8-168">使用的优化的配置的受欢迎的开源计划和协调工具，ACS，可运用现有技能，使用或在不断增长的社区专业技术来部署和管理容器基于 Microsoft Azure 上的应用程序正文上绘制.</span><span class="sxs-lookup"><span data-stu-id="8b9e8-168">Using an optimized configuration of popular open-source scheduling and orchestration tools, ACS enables you to use your existing skills or draw on a large and growing body of community expertise to deploy and manage container-based applications on Microsoft Azure.</span></span>

<span data-ttu-id="8b9e8-169">Azure 容器服务优化了针对 Azure 的常用 Docker 聚类分析的开放源代码工具和技术配置。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-169">Azure Container Service optimizes the configuration of popular Docker clustering open source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="8b9e8-170">获取一个打开的解决方案，它提供你的容器和应用程序配置的可移植性。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-170">You get an open solution that offers portability for both your containers and your application configuration.</span></span> <span data-ttu-id="8b9e8-171">选择大小、 的主机，数量和 orchestrator 工具，并且容器服务处理其他所有内容。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-171">You select the size, the number of hosts, and the orchestrator tools, and Container Service handles everything else.</span></span>

![](./media/image28.png)

<span data-ttu-id="8b9e8-172">**图 4-24**。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-172">**Figure 4-24**.</span></span> <span data-ttu-id="8b9e8-173">Azure 容器服务中的聚类分析选项</span><span class="sxs-lookup"><span data-stu-id="8b9e8-173">Clustering choices in Azure Container Service</span></span>

<span data-ttu-id="8b9e8-174">ACS 利用以确保你的应用程序容器是完全可移植的 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-174">ACS leverages Docker images to ensure that your application containers are fully portable.</span></span> <span data-ttu-id="8b9e8-175">它支持你选择的开放源代码 orchestration 平台，如 DC/OS （电源已通过 Apache Mesos）、 Kubernetes （最初由 Google 创建），和 Docker Swarm，以确保这些应用程序可以将扩展到数千或甚至数万个容器。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-175">It supports your choice of open-source orchestration platforms like DC/OS (powered by Apache Mesos), Kubernetes (originally created by Google), and Docker Swarm, to ensure that these applications can be scaled to thousands or even tens of thousands of containers.</span></span>

<span data-ttu-id="8b9e8-176">Azure 容器服务使您能够同时，仍保持应用程序可移植性，包括在业务流程层充分利用 Azure 的企业级功能。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-176">The Azure Container service enables you to take advantage of the enterprise-grade features of Azure while still maintaining application portability, including at the orchestration layers.</span></span>

![](./media/image29.png)

<span data-ttu-id="8b9e8-177">**图 4-25**。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-177">**Figure 4-25**.</span></span> <span data-ttu-id="8b9e8-178">在 ACS 中的 orchestrators</span><span class="sxs-lookup"><span data-stu-id="8b9e8-178">Orchestrators in ACS</span></span>

<span data-ttu-id="8b9e8-179">所示图 4-25，Azure 容器服务都只是为了部署 DC/OS、 Kubernetes 或 Docker Swarm，提供 Azure 的基础结构，但 ACS 不实现任何其他 orchestrator。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-179">As shown in Figure 4-25, Azure Container Service is simply the infrastructure provided by Azure in order to deploy DC/OS, Kubernetes or Docker Swarm, but ACS does not implement any additional orchestrator.</span></span> <span data-ttu-id="8b9e8-180">因此，ACS 不 orchestrator 在这种情况下，利用现有的开源 orchestrators 的容器的基础结构。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-180">Therefore, ACS is not an orchestrator as such, only an infrastructure that leverages existing open-source orchestrators for containers.</span></span>

<span data-ttu-id="8b9e8-181">从使用情况的角度，Azure 容器服务的目标是通过使用常用的开源工具和技术提供容器的宿主环境。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-181">From a usage perspective, the goal of Azure Container Service is to provide a container hosting environment by using popular open-source tools and technologies.</span></span> <span data-ttu-id="8b9e8-182">为此，它你选 orchestrator 公开的标准的 API 终结点。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-182">To this end, it exposes the standard API endpoints for your chosen orchestrator.</span></span> <span data-ttu-id="8b9e8-183">通过使用这些终结点，你可以利用可与这些终结点的任何软件。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-183">By using these endpoints, you can leverage any software that can talk to those endpoints.</span></span> <span data-ttu-id="8b9e8-184">例如，对于 Docker Swarm 终结点，你可以选择使用 Docker 命令行界面 (CLI)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-184">For example, in the case of the Docker Swarm endpoint, you might choose to use the Docker command-line interface (CLI).</span></span> <span data-ttu-id="8b9e8-185">对于 DC/OS，你可能选择使用 DC/OS CLI。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-185">For DC/OS, you might choose to use the DC/OS CLI.</span></span>

### <a name="getting-started-with-azure-container-service"></a><span data-ttu-id="8b9e8-186">开始使用 Azure 容器服务</span><span class="sxs-lookup"><span data-stu-id="8b9e8-186">Getting started with Azure Container Service</span></span> 

<span data-ttu-id="8b9e8-187">若要开始使用 Azure 容器服务，你部署 Azure 容器服务群集在 Azure 门户中使用 Azure 资源管理器模板或[CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-187">To begin using Azure Container Service, you deploy an Azure Container Service cluster from the Azure portal by using an Azure Resource Manager template or the [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli).</span></span> <span data-ttu-id="8b9e8-188">可用模板包括[Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm)， [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes)，和[DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos)。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-188">Available templates include [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), and [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos).</span></span> <span data-ttu-id="8b9e8-189">快速入门模板可以修改为包括其他或高级 Azure 配置。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-189">The quickstart templates can be modified to include additional or advanced Azure configuration.</span></span> <span data-ttu-id="8b9e8-190">部署 Azure 容器服务群集的详细信息，请参阅[部署 Azure 容器服务群集](https://docs.microsoft.com/azure/container-service/container-service-deployment)Azure 网站上。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-190">For more information on deploying an Azure Container Service cluster, see [Deploy an Azure Container Service cluster](https://docs.microsoft.com/azure/container-service/container-service-deployment) on the Azure website.</span></span>

<span data-ttu-id="8b9e8-191">没有任何默认情况下作为 ACS 的一部分安装的软件的费用。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-191">There are no fees for any of the software installed by default as part of ACS.</span></span> <span data-ttu-id="8b9e8-192">所有默认选项是使用开放源代码软件都实现的。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-192">All default options are implemented with open-source software.</span></span>

<span data-ttu-id="8b9e8-193">ACS 是当前可用于标准 A、 D、 DS、 G 和 GS 系列 Azure 中的 Linux 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-193">ACS is currently available for Standard A, D, DS, G, and GS series Linux virtual machines in Azure.</span></span> <span data-ttu-id="8b9e8-194">你要只为你选择的计算实例，以及其他基础基础结构占用的资源，例如存储和网络付费。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-194">You are charged only for the compute instances you choose, as well as the other underlying infrastructure resources consumed, such as storage and networking.</span></span> <span data-ttu-id="8b9e8-195">有 ACS 本身没有增量费用。</span><span class="sxs-lookup"><span data-stu-id="8b9e8-195">There are no incremental charges for ACS itself.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b9e8-196">其他资源</span><span class="sxs-lookup"><span data-stu-id="8b9e8-196">Additional resources</span></span>

-   <span data-ttu-id="8b9e8-197">**托管 Azure 容器服务使用的解决方案的 Docker 容器简介**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)</span><span class="sxs-lookup"><span data-stu-id="8b9e8-197">**Introduction to Docker container hosting solutions with Azure Container Service**
[*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)</span></span>

-   <span data-ttu-id="8b9e8-198">**Docker Swarm 概述**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)</span><span class="sxs-lookup"><span data-stu-id="8b9e8-198">**Docker Swarm overview**
[*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)</span></span>

-   <span data-ttu-id="8b9e8-199">**Swarm 模式概述**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)</span><span class="sxs-lookup"><span data-stu-id="8b9e8-199">**Swarm mode overview**
[*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)</span></span>

-   <span data-ttu-id="8b9e8-200">**Mesosphere DC/OS 概述**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)</span><span class="sxs-lookup"><span data-stu-id="8b9e8-200">**Mesosphere DC/OS Overview**
[*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)</span></span>

-   <span data-ttu-id="8b9e8-201">**Kubernetes。**</span><span class="sxs-lookup"><span data-stu-id="8b9e8-201">**Kubernetes.**</span></span> <span data-ttu-id="8b9e8-202">官方网站。 \\</span><span class="sxs-lookup"><span data-stu-id="8b9e8-202">The official site.\\</span></span>
    [<span data-ttu-id="8b9e8-203">*http://kubernetes.io/*</span><span class="sxs-lookup"><span data-stu-id="8b9e8-203">*http://kubernetes.io/*</span></span>](http://kubernetes.io/)


>[!div class="step-by-step"]
<span data-ttu-id="8b9e8-204">[以前](弹性-高的可用性-microservices.md) [下一步] (使用-azure-服务-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="8b9e8-204">[Previous] (resilient-high-availability-microservices.md) [Next] (using-azure-service-fabric.md)</span></span>
