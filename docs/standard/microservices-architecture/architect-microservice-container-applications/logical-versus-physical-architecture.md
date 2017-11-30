---
title: "与物理体系结构的逻辑体系结构"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |与物理体系结构的逻辑体系结构"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 635774a8fcd0cf1c0ede6a73c604071f538a37fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a><span data-ttu-id="7913c-104">与物理体系结构的逻辑体系结构</span><span class="sxs-lookup"><span data-stu-id="7913c-104">Logical architecture versus physical architecture</span></span>

<span data-ttu-id="7913c-105">很有用，此时若要停止并讨论逻辑体系结构和物理体系结构和如何这适用于基于微服务构成的应用程序的设计之间的区别。</span><span class="sxs-lookup"><span data-stu-id="7913c-105">It is useful at this point to stop and discuss the distinction between logical architecture and physical architecture, and how this applies to the design of microservice-based applications.</span></span>

<span data-ttu-id="7913c-106">若要开始，生成微服务不需要任何特定的技术的使用。</span><span class="sxs-lookup"><span data-stu-id="7913c-106">To begin, building microservices does not require the use of any specific technology.</span></span> <span data-ttu-id="7913c-107">例如，Docker 容器并不是强制才能创建基于微服务的体系结构。</span><span class="sxs-lookup"><span data-stu-id="7913c-107">For instance, Docker containers are not mandatory in order to create a microservice-based architecture.</span></span> <span data-ttu-id="7913c-108">此外可以作为纯进程运行这些微服务。</span><span class="sxs-lookup"><span data-stu-id="7913c-108">Those microservices could also be run as plain processes.</span></span> <span data-ttu-id="7913c-109">微服务是一个逻辑体系结构。</span><span class="sxs-lookup"><span data-stu-id="7913c-109">Microservices is a logical architecture.</span></span>

<span data-ttu-id="7913c-110">此外，即使 microservice 无法物理实现为单个服务、 进程或容器 (即为简单起见，在初始版本而采取的做法[eShopOnContainers](http://aka.ms/MicroservicesArchitecture))，此之间的奇偶校验业务微服务和物理服务或容器不一定需要在所有情况下生成的许多几十或甚至数百个服务组成的大型和复杂应用程序时。</span><span class="sxs-lookup"><span data-stu-id="7913c-110">Moreover, even when a microservice could be physically implemented as a single service, process, or container (for simplicity’s sake, that is the approach taken in the initial version of [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), this parity between business microservice and physical service or container is not necessarily required in all cases when you build a large and complex application composed of many dozens or even hundreds of services.</span></span>

<span data-ttu-id="7913c-111">这就是应用程序的逻辑体系结构和物理体系结构之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="7913c-111">This is where there is a difference between an application’s logical architecture and physical architecture.</span></span> <span data-ttu-id="7913c-112">逻辑体系结构和系统的逻辑边界并不一定一对一映射到物理计算机或部署体系结构。</span><span class="sxs-lookup"><span data-stu-id="7913c-112">The logical architecture and logical boundaries of a system do not necessarily map one-to-one to the physical or deployment architecture.</span></span> <span data-ttu-id="7913c-113">这个问题会发生，但通常不能。</span><span class="sxs-lookup"><span data-stu-id="7913c-113">It can happen, but it often does not.</span></span>

<span data-ttu-id="7913c-114">尽管某些业务微服务或限定上下文，你可能具有确定，但它并不意味着实现它们的最佳方法是始终通过创建单一服务 （如 ASP.NET Web API) 或每个业务微服务构成的单个 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="7913c-114">Although you might have identified certain business microservices or Bounded Contexts, it does not mean that the best way to implement them is always by creating a single service (such as an ASP.NET Web API) or single Docker container for each business microservice.</span></span> <span data-ttu-id="7913c-115">具有指示每个业务微服务构成的规则必须使用单个服务实现或容器是过于严格。</span><span class="sxs-lookup"><span data-stu-id="7913c-115">Having a rule saying each business microservice has to be implemented using a single service or container is too rigid.</span></span>

<span data-ttu-id="7913c-116">因此，业务 microservice 或绑定上下文是不可能同时发生的逻辑体系结构与物理体系结构。</span><span class="sxs-lookup"><span data-stu-id="7913c-116">Therefore, a business microservice or Bounded Context is a logical architecture that might coincide (or not) with physical architecture.</span></span> <span data-ttu-id="7913c-117">重要的一点是，业务 microservice 或绑定上下文必须自治通过允许代码和状态以进行独立版本控制、 部署，并且扩展。</span><span class="sxs-lookup"><span data-stu-id="7913c-117">The important point is that a business microservice or Bounded Context must be autonomous by allowing code and state to be independently versioned, deployed, and scaled.</span></span>

<span data-ttu-id="7913c-118">如图 4-8 所示，目录业务 microservice 无法撰写的多个服务或进程。</span><span class="sxs-lookup"><span data-stu-id="7913c-118">As Figure 4-8 shows, the catalog business microservice could be composed of several services or processes.</span></span> <span data-ttu-id="7913c-119">这些可以是多个 ASP.NET Web API 服务或任何其他类型的使用 HTTP 或任何其他协议的服务。</span><span class="sxs-lookup"><span data-stu-id="7913c-119">These could be multiple ASP.NET Web API services or any other kind of services using HTTP or any other protocol.</span></span> <span data-ttu-id="7913c-120">更重要的是，服务可以共享相同的数据，只要这些服务与相同的业务领域提供一致性。</span><span class="sxs-lookup"><span data-stu-id="7913c-120">More importantly, the services could share the same data, as long as these services are cohesive with respect to the same business domain.</span></span>

![](./media/image8.png)

<span data-ttu-id="7913c-121">**图 4-8**。</span><span class="sxs-lookup"><span data-stu-id="7913c-121">**Figure 4-8**.</span></span> <span data-ttu-id="7913c-122">使用多个物理服务业务微服务</span><span class="sxs-lookup"><span data-stu-id="7913c-122">Business microservice with several physical services</span></span>

<span data-ttu-id="7913c-123">在示例中的服务共享相同的数据模型，因为 Web API 服务的目标与搜索服务相同的数据。</span><span class="sxs-lookup"><span data-stu-id="7913c-123">The services in the example share the same data model because the Web API service targets the same data as the Search service.</span></span> <span data-ttu-id="7913c-124">因此，在业务微服务构成的物理实现，你拆分该功能使你可以每个这些内部服务向上或向下根据需要扩展。</span><span class="sxs-lookup"><span data-stu-id="7913c-124">So, in the physical implementation of the business microservice, you are splitting that functionality so you can scale each of those internal services up or down as needed.</span></span> <span data-ttu-id="7913c-125">可能 Web API 服务通常需要更多实例比搜索服务中，反之亦然。）</span><span class="sxs-lookup"><span data-stu-id="7913c-125">Maybe the Web API service usually needs more instances than the Search service, or vice versa.)</span></span>

<span data-ttu-id="7913c-126">简单地说，微服务的逻辑体系结构始终没有与物理部署体系结构保持一致。</span><span class="sxs-lookup"><span data-stu-id="7913c-126">In short, the logical architecture of microservices does not always have to coincide with the physical deployment architecture.</span></span> <span data-ttu-id="7913c-127">在本指南中，我们提到微服务，只要我们意味着在业务或无法映射到一个或多个服务的逻辑微服务。</span><span class="sxs-lookup"><span data-stu-id="7913c-127">In this guide, whenever we mention a microservice, we mean a business or logical microservice that could map to one or more services.</span></span> <span data-ttu-id="7913c-128">在大多数情况下，这将是单个服务，但它可能是更多。</span><span class="sxs-lookup"><span data-stu-id="7913c-128">In most cases, this will be a single service, but it might be more.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7913c-129">[以前](数据-自主性-每个-microservice.md) [下一步] (分布式的数据-management.md)</span><span class="sxs-lookup"><span data-stu-id="7913c-129">[Previous] (data-sovereignty-per-microservice.md) [Next] (distributed-data-management.md)</span></span>
