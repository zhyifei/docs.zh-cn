---
title: "微服务体系结构"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |微服务体系结构"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a><span data-ttu-id="55e60-104">微服务体系结构</span><span class="sxs-lookup"><span data-stu-id="55e60-104">Microservices architecture</span></span>

<span data-ttu-id="55e60-105">顾名思义，微服务体系结构将是一种方法生成服务器应用程序为小型服务的一组。</span><span class="sxs-lookup"><span data-stu-id="55e60-105">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="55e60-106">每个服务在其自己的进程中运行，并与其他进程使用 （如 HTTP/HTTPS)，Websocket 协议通信或[AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)。</span><span class="sxs-lookup"><span data-stu-id="55e60-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="55e60-107">每个微服务实现的特定的端到端域或在某些上下文边界内的业务功能和每个必须自主开发和进行可部署独立的。</span><span class="sxs-lookup"><span data-stu-id="55e60-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="55e60-108">最后，每个微服务应拥有其相关的域数据模型和基于不同的数据存储技术 （SQL、 NoSQL） 和编程语言不同的域逻辑 （自主性和分散的数据管理）。</span><span class="sxs-lookup"><span data-stu-id="55e60-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="55e60-109">Microservice 应该是什么大小？</span><span class="sxs-lookup"><span data-stu-id="55e60-109">What size should a microservice be?</span></span> <span data-ttu-id="55e60-110">在开发时 microservice，大小不应是重要的一点。</span><span class="sxs-lookup"><span data-stu-id="55e60-110">When developing a microservice, size should not be the important point.</span></span> <span data-ttu-id="55e60-111">相反，重要的一点应创建松散耦合服务以便您具有自主性的开发、 部署和缩放，每个服务。</span><span class="sxs-lookup"><span data-stu-id="55e60-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="55e60-112">当然，标识和设计时微服务，你应尝试使它们尽可能小，只要你没有与其他微服务直接依赖项太多。</span><span class="sxs-lookup"><span data-stu-id="55e60-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you do not have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="55e60-113">不是微服务构成的大小是内部的内聚它必须具有和其独立于其他服务更重要。</span><span class="sxs-lookup"><span data-stu-id="55e60-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="55e60-114">为什么微服务体系结构？</span><span class="sxs-lookup"><span data-stu-id="55e60-114">Why a microservices architecture?</span></span> <span data-ttu-id="55e60-115">简单地说，它提供了长期的灵活性。</span><span class="sxs-lookup"><span data-stu-id="55e60-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="55e60-116">微服务启用更好的可维护性复杂、 大，且高度可伸缩的系统中通过让你创建基于许多，每个包含粒度和自治生命周期的独立可部署服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55e60-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="55e60-117">作为一项额外权益，微服务可以向外扩展独立。</span><span class="sxs-lookup"><span data-stu-id="55e60-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="55e60-118">而不是让你必须向外扩展作为一个单元的单个整体应用程序，你可以改为向外扩展特定微服务。</span><span class="sxs-lookup"><span data-stu-id="55e60-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="55e60-119">这样一来，你可以扩展只需要更多的处理能力或网络带宽，以支持请求，而不是向外扩展的应用程序不需要进行扩展的其他区域的功能的区域。</span><span class="sxs-lookup"><span data-stu-id="55e60-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that do not need to be scaled.</span></span> <span data-ttu-id="55e60-120">这意味着节省成本，因为需要更少的硬件。</span><span class="sxs-lookup"><span data-stu-id="55e60-120">That means cost savings because you need less hardware.</span></span>

![](./media/image6.png)

<span data-ttu-id="55e60-121">**图 4-6**。</span><span class="sxs-lookup"><span data-stu-id="55e60-121">**Figure 4-6**.</span></span> <span data-ttu-id="55e60-122">与微服务方法的整体部署</span><span class="sxs-lookup"><span data-stu-id="55e60-122">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="55e60-123">如图 4-6 所示，微服务方法就会允许敏捷更改和快速迭代的每个微服务，因为您可以更改的复杂、 大，且可缩放的应用程序特定的小区域。</span><span class="sxs-lookup"><span data-stu-id="55e60-123">As Figure 4-6 shows, the microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="55e60-124">构建细化基于微服务的应用程序启用持续集成和持续交付做法。</span><span class="sxs-lookup"><span data-stu-id="55e60-124">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="55e60-125">它还提高了新的函数传递到应用程序。</span><span class="sxs-lookup"><span data-stu-id="55e60-125">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="55e60-126">细化组成应用程序还允许你运行和测试微服务的隔离，并同时保持它们之间的清除协定自主发展。</span><span class="sxs-lookup"><span data-stu-id="55e60-126">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="55e60-127">只要不更改接口或协定，可以更改任何微服务构成的内部实现，或添加新功能，而不会断开其他微服务。</span><span class="sxs-lookup"><span data-stu-id="55e60-127">As long as you do not change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="55e60-128">以下是重要的方面以便在转到生产环境且基于微服务的系统的成功：</span><span class="sxs-lookup"><span data-stu-id="55e60-128">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

-   <span data-ttu-id="55e60-129">监视和运行状况检查的服务和基础结构。</span><span class="sxs-lookup"><span data-stu-id="55e60-129">Monitoring and health checks of the services and infrastructure.</span></span>

-   <span data-ttu-id="55e60-130">服务 （即，云和 orchestrators） 的可伸缩基础结构。</span><span class="sxs-lookup"><span data-stu-id="55e60-130">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

-   <span data-ttu-id="55e60-131">安全设计和实现多个级别： 身份验证、 授权、 机密管理、 安全通信，等等。</span><span class="sxs-lookup"><span data-stu-id="55e60-131">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

-   <span data-ttu-id="55e60-132">通常使用不同的团队将重点放在不同的微服务上的快速应用程序交付。</span><span class="sxs-lookup"><span data-stu-id="55e60-132">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

-   <span data-ttu-id="55e60-133">DevOps 和 CI/CD 实践和基础结构。</span><span class="sxs-lookup"><span data-stu-id="55e60-133">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="55e60-134">其中，仅第一个由三个涵盖或在本指南中引入的。</span><span class="sxs-lookup"><span data-stu-id="55e60-134">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="55e60-135">最后两个点，与应用程序生命周期相关，介绍其他[容器 Docker 应用生命周期内使用 Microsoft 平台和工具](https://aka.ms/dockerlifecycleebook)电子书。</span><span class="sxs-lookup"><span data-stu-id="55e60-135">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55e60-136">其他资源</span><span class="sxs-lookup"><span data-stu-id="55e60-136">Additional resources</span></span>

-   <span data-ttu-id="55e60-137">**Mark Russinovich。微服务： 由云应用程序 revolution**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span><span class="sxs-lookup"><span data-stu-id="55e60-137">**Mark Russinovich. Microservices: An application revolution powered by the cloud**
[*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)</span></span>

-   <span data-ttu-id="55e60-138">**Martin Fowler。微服务**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span><span class="sxs-lookup"><span data-stu-id="55e60-138">**Martin Fowler. Microservices**
[*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)</span></span>

-   <span data-ttu-id="55e60-139">**Martin Fowler。Microservice 先决条件**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span><span class="sxs-lookup"><span data-stu-id="55e60-139">**Martin Fowler. Microservice Prerequisites**
[*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)</span></span>

-   <span data-ttu-id="55e60-140">**Jimmy Nilsson。块区云计算**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span><span class="sxs-lookup"><span data-stu-id="55e60-140">**Jimmy Nilsson. Chunk Cloud Computing**
[*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)</span></span>

-   <span data-ttu-id="55e60-141">**Cesar de la Torre。容器 Docker 应用生命周期内使用 Microsoft 平台和工具**（可下载电子图书） [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span><span class="sxs-lookup"><span data-stu-id="55e60-141">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="55e60-142">[以前](服务-面向-architecture.md) [下一步] (数据-自主性-每个-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="55e60-142">[Previous] (service-oriented-architecture.md) [Next] (data-sovereignty-per-microservice.md)</span></span>
