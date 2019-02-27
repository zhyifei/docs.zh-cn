---
title: 在生产环境中运行组合和基于微服务的应用程序
description: 了解在生产环境中运行基于容器的应用程序的关键组件
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835208"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="07877-103">在生产环境中运行组合和基于微服务的应用程序</span><span class="sxs-lookup"><span data-stu-id="07877-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="07877-104">由多个微服务构成的应用程序需要将部署到业务流程协调程序群集为了简化部署的复杂性和使其可行从 IT 角度来看。</span><span class="sxs-lookup"><span data-stu-id="07877-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="07877-105">而无需与业务流程协调程序的群集，很难部署和横向扩展的复杂微服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="07877-105">Without an orchestrator cluster, it would be difficult to deploy and scale out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="07877-106">业务流程协调程序、 计划程序，以及容器群集简介</span><span class="sxs-lookup"><span data-stu-id="07877-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="07877-107">这本电子书，前面*群集*并*计划程序*讨论有关软件体系结构和开发的一部分引入。</span><span class="sxs-lookup"><span data-stu-id="07877-107">Earlier in this e-book, *clusters* and *schedulers* were introduced as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="07877-108">Kubernetes 和 Service Fabric 是 Docker 群集的示例。</span><span class="sxs-lookup"><span data-stu-id="07877-108">Kubernetes and Service Fabric are examples of Docker clusters.</span></span> <span data-ttu-id="07877-109">这两个这些业务流程协调程序可以运行提供 Microsoft Azure Kubernetes 服务的基础结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="07877-109">Both of these orchestrators can run as a part of the infrastructure provided by Microsoft Azure Kubernetes Service.</span></span>

<span data-ttu-id="07877-110">当应用程序是向外扩展跨多个主机系统时，管理每个主机系统和抽象出底层平台的复杂性的能力变得极具吸引力。</span><span class="sxs-lookup"><span data-stu-id="07877-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="07877-111">这就准确地说是业务流程协调程序和计划程序提供的内容。</span><span class="sxs-lookup"><span data-stu-id="07877-111">That's precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="07877-112">看看简要此处所示：</span><span class="sxs-lookup"><span data-stu-id="07877-112">Let's take a brief look at them here:</span></span>

- <span data-ttu-id="07877-113">**计划程序**。</span><span class="sxs-lookup"><span data-stu-id="07877-113">**Schedulers**.</span></span><span data-ttu-id="07877-114"> "计划"是指管理员能够加载到建立如何运行特定容器的主机系统上的服务文件的功能。</span><span class="sxs-lookup"><span data-stu-id="07877-114"> "Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="07877-115">启动 Docker 群集中的容器通常被称为计划。</span><span class="sxs-lookup"><span data-stu-id="07877-115">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="07877-116">尽管计划是指特定操作的加载服务定义中的，在更多常规意义上，计划程序负责挂接到主机的 init 系统中任何所需的容量管理服务。</span><span class="sxs-lookup"><span data-stu-id="07877-116">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

   <span data-ttu-id="07877-117">群集计划程序具有多个目标： 高效使用群集的资源中，使用用户提供的放置约束，计划具有的应用程序快速以不将它们保留在挂起状态，在一定程度"的公平性，"正在可靠的错误，并始终为可用。</span><span class="sxs-lookup"><span data-stu-id="07877-117">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

- <span data-ttu-id="07877-118">**业务流程协调程序**。</span><span class="sxs-lookup"><span data-stu-id="07877-118">**Orchestrators**.</span></span><span data-ttu-id="07877-119"> 平台扩展到的主机群集中部署复杂的多容器工作负荷的生命周期管理功能。</span><span class="sxs-lookup"><span data-stu-id="07877-119"> Platforms extend life-cycle management capabilities to complex, multi-container workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="07877-120">通过将抽象化的主机基础结构，业务流程工具为用户提供了一种方法将整个群集视为单个部署目标。</span><span class="sxs-lookup"><span data-stu-id="07877-120">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

   <span data-ttu-id="07877-121">业务流程的过程包括工具和一个平台，可以自动从初始放置或部署每个容器; 应用程序管理的所有方面将容器移动到不同的主机，具体取决于其主机的运行状况或性能;版本控制和滚动更新和运行状况监视功能的支持缩放和故障转移;及更多。</span><span class="sxs-lookup"><span data-stu-id="07877-121">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

   <span data-ttu-id="07877-122">业务流程是一个泛指的术语，指容器计划、 群集管理和可能的预配其他主机。</span><span class="sxs-lookup"><span data-stu-id="07877-122">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="07877-123">提供的业务流程协调程序和计划程序的功能比较复杂开发并从头开始创建，因此你通常想要使用由供应商提供的业务流程解决方案。</span><span class="sxs-lookup"><span data-stu-id="07877-123">The capabilities provided by orchestrators and schedulers are complex to develop and create from scratch, therefore you usually would want to use orchestration solutions offered by vendors.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="07877-124">[上一页](index.md)
>[下一页](manage-production-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="07877-124">[Previous](index.md)
[Next](manage-production-docker-environments.md)</span></span>
