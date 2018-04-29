---
title: 微服务体系结构
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 微服务体系结构
keywords: Docker, 微服务, ASP.NET, 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 78d3903e7ed4abf27e78812de87ccbcb9f733663
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="microservices-architecture"></a><span data-ttu-id="38e1d-104">微服务体系结构</span><span class="sxs-lookup"><span data-stu-id="38e1d-104">Microservices architecture</span></span>

<span data-ttu-id="38e1d-105">顾名思义，微服务体系结构是一种将服务器应用程序生成为一组小型服务的方法。</span><span class="sxs-lookup"><span data-stu-id="38e1d-105">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="38e1d-106">每个服务都在自己的进程中运行，并使用 HTTP/HTTPS、WebSocket 或 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) 等协议与其他进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="38e1d-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="38e1d-107">每个微服务在特定的上下文边界内实现特定的端到端域或业务功能，每个微服务都必须自主开发，并且可以独立部署。</span><span class="sxs-lookup"><span data-stu-id="38e1d-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="38e1d-108">最后，每个微服务都应拥有其基于不同数据存储技术（SQL、NoSQL）和不同编程语言的相关域数据模型和域逻辑（主权和分散式数据管理）。</span><span class="sxs-lookup"><span data-stu-id="38e1d-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="38e1d-109">微服务应该有多大？</span><span class="sxs-lookup"><span data-stu-id="38e1d-109">What size should a microservice be?</span></span> <span data-ttu-id="38e1d-110">在开发微服务时，大小不应该是重点。</span><span class="sxs-lookup"><span data-stu-id="38e1d-110">When developing a microservice, size should not be the important point.</span></span> <span data-ttu-id="38e1d-111">相反，重点应该是创建松散耦合的服务以便自主地为每个服务进行开发、部署和缩放。</span><span class="sxs-lookup"><span data-stu-id="38e1d-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="38e1d-112">当然，在标识和设计微服务时，只要与其他微服务不存在太多直接依赖关系，应尝试使它们尽可能小。</span><span class="sxs-lookup"><span data-stu-id="38e1d-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you do not have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="38e1d-113">比微服务的大小更重要的是，它必须具有内部内聚，并且独立于其他服务。</span><span class="sxs-lookup"><span data-stu-id="38e1d-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="38e1d-114">为何选择微服务体系结构？</span><span class="sxs-lookup"><span data-stu-id="38e1d-114">Why a microservices architecture?</span></span> <span data-ttu-id="38e1d-115">简而言之，它提供了长期的灵活性。</span><span class="sxs-lookup"><span data-stu-id="38e1d-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="38e1d-116">通过允许基于许多独立的可部署服务（每个服务都具有粒度和自主生命周期）创建应用程序，微服务在复杂、大型和高度可缩放的系统中支持更好的可维护性。</span><span class="sxs-lookup"><span data-stu-id="38e1d-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="38e1d-117">微服务的另外一大优势是，可以独立横向扩展。</span><span class="sxs-lookup"><span data-stu-id="38e1d-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="38e1d-118">可以横向扩展特定的微服务，而无需将单个整体应用程序作为一个单位扩展。</span><span class="sxs-lookup"><span data-stu-id="38e1d-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="38e1d-119">这样做便可单独扩展需要更多处理能力或网络带宽以支撑需求的功能区域，而不用横向扩展应用程序中不需要扩展的其他区域。</span><span class="sxs-lookup"><span data-stu-id="38e1d-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that do not need to be scaled.</span></span> <span data-ttu-id="38e1d-120">这意味着节省成本，因为所需硬件更少。</span><span class="sxs-lookup"><span data-stu-id="38e1d-120">That means cost savings because you need less hardware.</span></span>

![](./media/image6.png)

<span data-ttu-id="38e1d-121">**图 4-6**。</span><span class="sxs-lookup"><span data-stu-id="38e1d-121">**Figure 4-6**.</span></span> <span data-ttu-id="38e1d-122">整体部署与微服务方法</span><span class="sxs-lookup"><span data-stu-id="38e1d-122">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="38e1d-123">如图 4-6 所示，微服务方法允许对每个微服务进行灵活更改和快速迭代，因为可以更改复杂、大型和可缩放的应用程序特定的小区域。</span><span class="sxs-lookup"><span data-stu-id="38e1d-123">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="38e1d-124">构建基于微服务的细粒度应用程序使持续集成和持续交付实践可行。</span><span class="sxs-lookup"><span data-stu-id="38e1d-124">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="38e1d-125">它还加快了应用程序中新功能的交付。</span><span class="sxs-lookup"><span data-stu-id="38e1d-125">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="38e1d-126">应用程序的细粒度组合还支持以隔离方式运行和测试微服务，并在维护它们之间的清除协定的同时进行自主升级。</span><span class="sxs-lookup"><span data-stu-id="38e1d-126">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="38e1d-127">只要不更改接口或协定，就可以更改任何微服务的内部实现或添加新功能，而不会中断其他微服务。</span><span class="sxs-lookup"><span data-stu-id="38e1d-127">As long as you do not change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="38e1d-128">以下是使用基于微服务的系统成功投入生产的重要方面：</span><span class="sxs-lookup"><span data-stu-id="38e1d-128">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

-   <span data-ttu-id="38e1d-129">对服务和基础结构的监视和运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="38e1d-129">Monitoring and health checks of the services and infrastructure.</span></span>

-   <span data-ttu-id="38e1d-130">服务（即云和业务流程协调程序）的可缩放基础结构。</span><span class="sxs-lookup"><span data-stu-id="38e1d-130">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

-   <span data-ttu-id="38e1d-131">多个级别的安全设计和实现：身份验证、授权、机密管理、安全通信等。</span><span class="sxs-lookup"><span data-stu-id="38e1d-131">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

-   <span data-ttu-id="38e1d-132">快速应用程序交付，通常不同的团队重点负责不同的微服务。</span><span class="sxs-lookup"><span data-stu-id="38e1d-132">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

-   <span data-ttu-id="38e1d-133">DevOps 和 CI/CD 实践和基础结构。</span><span class="sxs-lookup"><span data-stu-id="38e1d-133">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="38e1d-134">其中，本指南只涵盖或介绍了前三项内容。</span><span class="sxs-lookup"><span data-stu-id="38e1d-134">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="38e1d-135">最后两项与应用程序生命周期相关，在附加的[《使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期》](https://aka.ms/dockerlifecycleebook)电子书中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="38e1d-135">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38e1d-136">其他资源</span><span class="sxs-lookup"><span data-stu-id="38e1d-136">Additional resources</span></span>

-   <span data-ttu-id="38e1d-137">**Mark Russinovich。Microservices: An application revolution powered by the cloud**（微服务：云推动的应用程序革命）
    [https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span><span class="sxs-lookup"><span data-stu-id="38e1d-137">**Mark Russinovich. Microservices: An application revolution powered by the cloud**
[*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span></span>

-   <span data-ttu-id="38e1d-138">**Martin Fowler。Microservices**（微服务）
    [https://www.martinfowler.com/articles/microservices.html](https://www.martinfowler.com/articles/microservices.html)</span><span class="sxs-lookup"><span data-stu-id="38e1d-138">**Martin Fowler. Microservices**
[*https://www.martinfowler.com/articles/microservices.html*](https://www.martinfowler.com/articles/microservices.html)</span></span>

-   <span data-ttu-id="38e1d-139">**Martin Fowler。Microservice Prerequisites**（微服务先决条件）
    [https://martinfowler.com/bliki/MicroservicePrerequisites.html](https://martinfowler.com/bliki/MicroservicePrerequisites.html)</span><span class="sxs-lookup"><span data-stu-id="38e1d-139">**Martin Fowler. Microservice Prerequisites**
[*https://martinfowler.com/bliki/MicroservicePrerequisites.html*](https://martinfowler.com/bliki/MicroservicePrerequisites.html)</span></span>

-   <span data-ttu-id="38e1d-140">**Jimmy Nilsson。Chunk Cloud Computing**（区块云计算）
    [https://www.infoq.com/articles/CCC-Jimmy-Nilsson](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span><span class="sxs-lookup"><span data-stu-id="38e1d-140">**Jimmy Nilsson. Chunk Cloud Computing**
[*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span></span>

-   <span data-ttu-id="38e1d-141">**Cesar de la Torre。Containerized Docker Application Lifecycle with Microsoft Platform and Tools**（使用 Microsoft 平台和工具容器化 Docker 应用程序生命周期）（可下载电子书）[https://aka.ms/dockerlifecycleebook](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="38e1d-141">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="38e1d-142">[上一篇] (service-oriented-architecture.md) [下一篇] (data-sovereignty-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="38e1d-142">[Previous] (service-oriented-architecture.md) [Next] (data-sovereignty-per-microservice.md)</span></span>
