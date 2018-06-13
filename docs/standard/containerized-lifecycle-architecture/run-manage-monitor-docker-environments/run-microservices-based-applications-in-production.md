---
title: 在生产环境中运行由和基于微服务的应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 47685bfd8dca50c5e93be7574ea6ef30a49cbede
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568792"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="da403-103">在生产环境中运行由和基于微服务的应用程序</span><span class="sxs-lookup"><span data-stu-id="da403-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="da403-104">由多个微服务的应用程序需要将其部署到 orchestrator 群集为了简化部署的复杂性和使其从 IT 角度来看可行。</span><span class="sxs-lookup"><span data-stu-id="da403-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="da403-105">如果 orchestrator 群集中，没有它将是部署和向外扩展复杂微服务应用程序非常困难。</span><span class="sxs-lookup"><span data-stu-id="da403-105">Without an orchestrator cluster, it would be very difficult to deploy and scale-out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="da403-106">Orchestrators、 计划程序时和容器群集简介</span><span class="sxs-lookup"><span data-stu-id="da403-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="da403-107">前面的此电子书，我们引入了*群集*和*计划程序*上软件体系结构和开发的讨论的一部分。</span><span class="sxs-lookup"><span data-stu-id="da403-107">Earlier in this e-book, we introduced *clusters* and *schedulers* as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="da403-108">Docker 群集的示例包括 Docker Swarm 和 Mesosphere 的数据中心操作系统 (DC/OS)。</span><span class="sxs-lookup"><span data-stu-id="da403-108">Examples of Docker clusters are Docker Swarm and Mesosphere Datacenter Operating System (DC/OS).</span></span> <span data-ttu-id="da403-109">这两个可以作为 Microsoft Azure 容器服务提供的基础结构的一部分运行。</span><span class="sxs-lookup"><span data-stu-id="da403-109">Both of these can run as a part of the infrastructure provided by Microsoft Azure Container Service.</span></span>

<span data-ttu-id="da403-110">当应用程序是向外扩展的跨多个主机系统时，管理每个主机系统和抽象化基础平台的复杂性的能力变得极具吸引力。</span><span class="sxs-lookup"><span data-stu-id="da403-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="da403-111">这就确切地说是 orchestrators 和计划程序提供的内容。</span><span class="sxs-lookup"><span data-stu-id="da403-111">That is precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="da403-112">看看简要此处所示：</span><span class="sxs-lookup"><span data-stu-id="da403-112">Let's take a brief look at them here:</span></span>

-   <span data-ttu-id="da403-113">**计划程序 * * * *"计划"指的管理员可以将服务文件加载到建立如何运行特定容器的主机系统的能力。</span><span class="sxs-lookup"><span data-stu-id="da403-113">**Schedulers*** *"Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="da403-114">启动 Docker 群集中的容器往往会被称为计划。</span><span class="sxs-lookup"><span data-stu-id="da403-114">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="da403-115">虽然计划针对加载的更多常规的意义上中的服务定义的特定行为的是计划程序负责将挂钩到主机的 init 系统中任何所需的容量的服务进行管理。</span><span class="sxs-lookup"><span data-stu-id="da403-115">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

<span data-ttu-id="da403-116">一个群集计划程序有多个目标： 有效地使用群集的资源，使用用户提供的放置约束，计划应用程序快速不将它们保留在挂起状态，具有在一定程度"的公平性，"正在可靠的错误，并始终为可用。</span><span class="sxs-lookup"><span data-stu-id="da403-116">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

-   <span data-ttu-id="da403-117">**业务流程 * * * *平台扩展到部署在主机群集上的复杂、 multicontainer 工作负荷的生命周期管理功能。</span><span class="sxs-lookup"><span data-stu-id="da403-117">**Orchestration*** *Platforms extend life-cycle management capabilities to complex, multicontainer workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="da403-118">通过使宿主基础结构的抽象化，业务流程工具将向用户授予了如何将整个群集视为单个部署目标。</span><span class="sxs-lookup"><span data-stu-id="da403-118">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

<span data-ttu-id="da403-119">业务流程的过程包括工具和一个平台，它可以自动执行的应用程序管理从初始放置或每个容器; 的部署的所有方面将容器移动到不同的主机，具体取决于其主机的运行状况或性能;版本控制和滚动更新以及运行状况监视功能的支持缩放和故障转移;还有更多。</span><span class="sxs-lookup"><span data-stu-id="da403-119">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

<span data-ttu-id="da403-120">Orchestration 是广泛的术语，表示与容器计划、 群集管理和可能设置的其他主机。</span><span class="sxs-lookup"><span data-stu-id="da403-120">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="da403-121">提供 orchestrators 和计划程序的功能很非常复杂，开发并从从头开始创建，因此你通常想要使由供应商提供的业务流程解决方案使用。</span><span class="sxs-lookup"><span data-stu-id="da403-121">The capabilities provided by orchestrators and schedulers are very complex to develop and create from scratch, and therefore you usually would want to make use of orchestration solutions offered by vendors.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="da403-122">[以前] (index.md) [下一步] (管理-生产-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="da403-122">[Previous] (index.md) [Next] (manage-production-docker-environments.md)</span></span>
