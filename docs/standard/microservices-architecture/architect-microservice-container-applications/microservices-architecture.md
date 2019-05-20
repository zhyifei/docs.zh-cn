---
title: 微服务体系结构
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 微服务体系结构的 30,000 英尺视图。
ms.date: 09/20/2018
ms.openlocfilehash: 3cf2a94140042d3cf76b5b63fe4e98638c56dbfe
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644856"
---
# <a name="microservices-architecture"></a><span data-ttu-id="89b3b-103">微服务体系结构</span><span class="sxs-lookup"><span data-stu-id="89b3b-103">Microservices architecture</span></span>

<span data-ttu-id="89b3b-104">顾名思义，微服务体系结构是一种将服务器应用程序生成为一组小型服务的方法。</span><span class="sxs-lookup"><span data-stu-id="89b3b-104">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="89b3b-105">这意味着微服务体系结构主要面向后端，虽然该方法也会用于前端。</span><span class="sxs-lookup"><span data-stu-id="89b3b-105">That means a microservices architecture is mainly oriented to the back-end, although the approach is also being used for the front end.</span></span> <span data-ttu-id="89b3b-106">每个服务都在自己的进程中运行，并使用 HTTP/HTTPS、WebSocket 或 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) 等协议与其他进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="89b3b-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="89b3b-107">每个微服务在特定的上下文边界内实现特定的端到端域或业务功能，每个微服务都必须自主开发，并且可以独立部署。</span><span class="sxs-lookup"><span data-stu-id="89b3b-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="89b3b-108">最后，每个微服务都应拥有其自己的相关域数据模型和域逻辑（主权和分散式数据管理），并且可以基于不同的数据存储技术（SQL、NoSQL）和不同的编程语言。</span><span class="sxs-lookup"><span data-stu-id="89b3b-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) and could be based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="89b3b-109">微服务应该有多大？</span><span class="sxs-lookup"><span data-stu-id="89b3b-109">What size should a microservice be?</span></span> <span data-ttu-id="89b3b-110">在开发微服务时，大小不应成为重点。</span><span class="sxs-lookup"><span data-stu-id="89b3b-110">When developing a microservice, size shouldn't be the important point.</span></span> <span data-ttu-id="89b3b-111">相反，重点应该是创建松散耦合的服务以便自主地为每个服务进行开发、部署和缩放。</span><span class="sxs-lookup"><span data-stu-id="89b3b-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="89b3b-112">当然，在标识和设计微服务时，只要与其他微服务不存在过多的直接依赖项，就应尝试让它们尽可能地小。</span><span class="sxs-lookup"><span data-stu-id="89b3b-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you don't have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="89b3b-113">比微服务的大小更重要的是，它必须具有内部内聚，并且独立于其他服务。</span><span class="sxs-lookup"><span data-stu-id="89b3b-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="89b3b-114">为何选择微服务体系结构？</span><span class="sxs-lookup"><span data-stu-id="89b3b-114">Why a microservices architecture?</span></span> <span data-ttu-id="89b3b-115">简而言之，它提供了长期的灵活性。</span><span class="sxs-lookup"><span data-stu-id="89b3b-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="89b3b-116">通过允许基于许多独立的可部署服务（每个服务都具有粒度和自主生命周期）创建应用程序，微服务在复杂、大型和高度可缩放的系统中支持更好的可维护性。</span><span class="sxs-lookup"><span data-stu-id="89b3b-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="89b3b-117">微服务的另外一大优势是，可以独立横向扩展。</span><span class="sxs-lookup"><span data-stu-id="89b3b-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="89b3b-118">可以横向扩展特定的微服务，而无需将单个整体应用程序作为一个单位扩展。</span><span class="sxs-lookup"><span data-stu-id="89b3b-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="89b3b-119">这样便可单独缩放需要更多处理能力或网络带宽以支撑需求的功能区域，而不用横向扩展应用程序中不需要缩放的其他区域。</span><span class="sxs-lookup"><span data-stu-id="89b3b-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that don't need to be scaled.</span></span> <span data-ttu-id="89b3b-120">这意味着节省成本，因为所需硬件更少。</span><span class="sxs-lookup"><span data-stu-id="89b3b-120">That means cost savings because you need less hardware.</span></span>

![在传统的整体方法中，应用程序会通过在多个服务器/VM 中克隆整个应用程序进行缩放。](./media/image6.png)

<span data-ttu-id="89b3b-123">**图 4-6**。</span><span class="sxs-lookup"><span data-stu-id="89b3b-123">**Figure 4-6**.</span></span> <span data-ttu-id="89b3b-124">整体部署与微服务方法</span><span class="sxs-lookup"><span data-stu-id="89b3b-124">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="89b3b-125">如图 4-6 所示，微服务方法允许对每个微服务进行灵活更改和快速迭代，因为可以更改复杂、大型和可缩放的应用程序特定的小区域。</span><span class="sxs-lookup"><span data-stu-id="89b3b-125">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="89b3b-126">构建基于微服务的细粒度应用程序使持续集成和持续交付实践可行。</span><span class="sxs-lookup"><span data-stu-id="89b3b-126">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="89b3b-127">它还加快了应用程序中新功能的交付。</span><span class="sxs-lookup"><span data-stu-id="89b3b-127">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="89b3b-128">应用程序的细粒度组合还支持以隔离方式运行和测试微服务，并在维护它们之间的清除协定的同时进行自主升级。</span><span class="sxs-lookup"><span data-stu-id="89b3b-128">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="89b3b-129">只要不更改接口或协定，就可以更改任何微服务的内部实现或添加新功能，而不会中断其他微服务。</span><span class="sxs-lookup"><span data-stu-id="89b3b-129">As long as you don't change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="89b3b-130">以下是使用基于微服务的系统成功投入生产的重要方面：</span><span class="sxs-lookup"><span data-stu-id="89b3b-130">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

- <span data-ttu-id="89b3b-131">对服务和基础结构的监视和运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="89b3b-131">Monitoring and health checks of the services and infrastructure.</span></span>

- <span data-ttu-id="89b3b-132">服务（即云和业务流程协调程序）的可缩放基础结构。</span><span class="sxs-lookup"><span data-stu-id="89b3b-132">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

- <span data-ttu-id="89b3b-133">多个级别的安全设计和实现：身份验证、授权、机密管理、安全通信等。</span><span class="sxs-lookup"><span data-stu-id="89b3b-133">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

- <span data-ttu-id="89b3b-134">快速应用程序交付，通常不同的团队重点负责不同的微服务。</span><span class="sxs-lookup"><span data-stu-id="89b3b-134">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

- <span data-ttu-id="89b3b-135">DevOps 和 CI/CD 实践和基础结构。</span><span class="sxs-lookup"><span data-stu-id="89b3b-135">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="89b3b-136">其中，本指南只涵盖或介绍了前三项内容。</span><span class="sxs-lookup"><span data-stu-id="89b3b-136">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="89b3b-137">最后两项与应用程序生命周期相关，在附加的[《使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期》](https://aka.ms/dockerlifecycleebook)电子书中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="89b3b-137">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89b3b-138">其他资源</span><span class="sxs-lookup"><span data-stu-id="89b3b-138">Additional resources</span></span>

- <span data-ttu-id="89b3b-139">\**Mark Russinovich。微服务：云推动的应用程序革命 \**</span><span class="sxs-lookup"><span data-stu-id="89b3b-139">**Mark Russinovich. Microservices: An application revolution powered by the cloud** \\</span></span>
  <https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/>

- <span data-ttu-id="89b3b-140">**Martin Fowler。Microservices** \（微服务）</span><span class="sxs-lookup"><span data-stu-id="89b3b-140">**Martin Fowler. Microservices** \\</span></span>
  <https://www.martinfowler.com/articles/microservices.html>

- <span data-ttu-id="89b3b-141">**Martin Fowler。Microservice Prerequisites** \（微服务先决条件）</span><span class="sxs-lookup"><span data-stu-id="89b3b-141">**Martin Fowler. Microservice Prerequisites** \\</span></span>
  <https://martinfowler.com/bliki/MicroservicePrerequisites.html>

- <span data-ttu-id="89b3b-142">**Jimmy Nilsson。Chunk Cloud Computing** \（区块云计算）</span><span class="sxs-lookup"><span data-stu-id="89b3b-142">**Jimmy Nilsson. Chunk Cloud Computing** \\</span></span>
  <https://www.infoq.com/articles/CCC-Jimmy-Nilsson>

- <span data-ttu-id="89b3b-143">**Cesar de la Torre。Containerized Docker Application Lifecycle with Microsoft Platform and Tools**（使用 Microsoft 平台和工具的容器化 Docker 应用程序生命周期）（可下载的电子书）\\</span><span class="sxs-lookup"><span data-stu-id="89b3b-143">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) \\</span></span>
  <https://aka.ms/dockerlifecycleebook>

>[!div class="step-by-step"]
><span data-ttu-id="89b3b-144">[上一页](service-oriented-architecture.md)
>[下一页](data-sovereignty-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="89b3b-144">[Previous](service-oriented-architecture.md)
[Next](data-sovereignty-per-microservice.md)</span></span>
