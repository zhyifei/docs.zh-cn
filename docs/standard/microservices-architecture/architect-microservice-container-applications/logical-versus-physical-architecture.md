---
title: 逻辑体系结构与物理体系结构
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 逻辑体系结构与物理体系结构
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: bb5f0daf0bcf824d72bb104914de03532bd3f9f7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213337"
---
# <a name="logical-architecture-versus-physical-architecture"></a><span data-ttu-id="458d4-103">逻辑体系结构与物理体系结构</span><span class="sxs-lookup"><span data-stu-id="458d4-103">Logical architecture versus physical architecture</span></span>

<span data-ttu-id="458d4-104">此时若停止并讨论逻辑体系结构和物理体系结构之间的区别，以及将其用于设计基于微服务的应用程序的方式，会很有用。</span><span class="sxs-lookup"><span data-stu-id="458d4-104">It is useful at this point to stop and discuss the distinction between logical architecture and physical architecture, and how this applies to the design of microservice-based applications.</span></span>

<span data-ttu-id="458d4-105">首先，生成微服务不需要使用特殊技术。</span><span class="sxs-lookup"><span data-stu-id="458d4-105">To begin, building microservices does not require the use of any specific technology.</span></span> <span data-ttu-id="458d4-106">例如，创建基于微服务的体系结构对 Docker 容器并没有强制性要求。</span><span class="sxs-lookup"><span data-stu-id="458d4-106">For instance, Docker containers are not mandatory in order to create a microservice-based architecture.</span></span> <span data-ttu-id="458d4-107">这些微服务也可以像普通进程那样运行。</span><span class="sxs-lookup"><span data-stu-id="458d4-107">Those microservices could also be run as plain processes.</span></span> <span data-ttu-id="458d4-108">微服务是一种逻辑体系结构。</span><span class="sxs-lookup"><span data-stu-id="458d4-108">Microservices is a logical architecture.</span></span>

<span data-ttu-id="458d4-109">此外，即使微服务能够作为单一服务、进程或容器进行物理实现（为简化起见，此方法是 [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) 原始版本采取的做法），生成由数十个甚至数百个服务组成的大型复杂应用程序时，并不需要商业微服务和物理服务或容器之间的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="458d4-109">Moreover, even when a microservice could be physically implemented as a single service, process, or container (for simplicity’s sake, that is the approach taken in the initial version of [eShopOnContainers](https://aka.ms/MicroservicesArchitecture)), this parity between business microservice and physical service or container is not necessarily required in all cases when you build a large and complex application composed of many dozens or even hundreds of services.</span></span>

<span data-ttu-id="458d4-110">这就是应用程序的逻辑体系结构和物理体系结构之间存在的差异。</span><span class="sxs-lookup"><span data-stu-id="458d4-110">This is where there is a difference between an application’s logical architecture and physical architecture.</span></span> <span data-ttu-id="458d4-111">系统的逻辑体系结构和逻辑边界不一定要与物理或部署体系结构一对一映射。</span><span class="sxs-lookup"><span data-stu-id="458d4-111">The logical architecture and logical boundaries of a system do not necessarily map one-to-one to the physical or deployment architecture.</span></span> <span data-ttu-id="458d4-112">这种情况可能会发生，但不会经常发生。</span><span class="sxs-lookup"><span data-stu-id="458d4-112">It can happen, but it often does not.</span></span>

<span data-ttu-id="458d4-113">尽管已确定某些商业微服务或界定上下文，但这并不意味着实现它们的最佳方式总是为每个商业微服务创建单一服务（如 ASP.NET Web API）或者单一 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="458d4-113">Although you might have identified certain business microservices or Bounded Contexts, it does not mean that the best way to implement them is always by creating a single service (such as an ASP.NET Web API) or single Docker container for each business microservice.</span></span> <span data-ttu-id="458d4-114">必须使用单一服务或容器实现每个商业微服务的这一规则过于严苛。</span><span class="sxs-lookup"><span data-stu-id="458d4-114">Having a rule saying each business microservice has to be implemented using a single service or container is too rigid.</span></span>

<span data-ttu-id="458d4-115">因此，商业微服务或界定上下文是可能（或不可能）与物理体系结构一致的逻辑体系结构。</span><span class="sxs-lookup"><span data-stu-id="458d4-115">Therefore, a business microservice or Bounded Context is a logical architecture that might coincide (or not) with physical architecture.</span></span> <span data-ttu-id="458d4-116">必须通过使代码和状态可独立、可进行版本控制、部署和缩放，让商业微服务或界定上下文能够自治，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="458d4-116">The important point is that a business microservice or Bounded Context must be autonomous by allowing code and state to be independently versioned, deployed, and scaled.</span></span>

<span data-ttu-id="458d4-117">如图 4-8 所示，目录商业微服务可由几个服务或进程组成。</span><span class="sxs-lookup"><span data-stu-id="458d4-117">As Figure 4-8 shows, the catalog business microservice could be composed of several services or processes.</span></span> <span data-ttu-id="458d4-118">这些服务可以是多个 ASP.NET Web API 服务，也可以是使用 HTTP 或其他任何协议的其他任何服务。</span><span class="sxs-lookup"><span data-stu-id="458d4-118">These could be multiple ASP.NET Web API services or any other kind of services using HTTP or any other protocol.</span></span> <span data-ttu-id="458d4-119">更重要的是，这些服务只要对于相同业务领域具有内聚性，便能共享相同数据。</span><span class="sxs-lookup"><span data-stu-id="458d4-119">More importantly, the services could share the same data, as long as these services are cohesive with respect to the same business domain.</span></span>

![](./media/image8.png)

<span data-ttu-id="458d4-120">**图 4-8**。</span><span class="sxs-lookup"><span data-stu-id="458d4-120">**Figure 4-8**.</span></span> <span data-ttu-id="458d4-121">使用多个物理服务的商业微服务</span><span class="sxs-lookup"><span data-stu-id="458d4-121">Business microservice with several physical services</span></span>

<span data-ttu-id="458d4-122">示例中的服务共享相同的数据模型，因为 Web API 服务针对的是与搜索服务相同的数据。</span><span class="sxs-lookup"><span data-stu-id="458d4-122">The services in the example share the same data model because the Web API service targets the same data as the Search service.</span></span> <span data-ttu-id="458d4-123">因此，在商业微服务的物理实现中，拆分该功能便可根据需要纵向扩展或横向扩展这些内部服务中的每一个。</span><span class="sxs-lookup"><span data-stu-id="458d4-123">So, in the physical implementation of the business microservice, you are splitting that functionality so you can scale each of those internal services up or down as needed.</span></span> <span data-ttu-id="458d4-124">Web API 服务通常比搜索服务需要更多的实例，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="458d4-124">Maybe the Web API service usually needs more instances than the Search service, or vice versa.</span></span>

<span data-ttu-id="458d4-125">简而言之，微服务的逻辑体系结构并不总是与物理部署体系结构一致。</span><span class="sxs-lookup"><span data-stu-id="458d4-125">In short, the logical architecture of microservices does not always have to coincide with the physical deployment architecture.</span></span> <span data-ttu-id="458d4-126">在本指南中，我们所提到的微服务是可以映射到一个或多个服务的商业微服务或逻辑微服务。</span><span class="sxs-lookup"><span data-stu-id="458d4-126">In this guide, whenever we mention a microservice, we mean a business or logical microservice that could map to one or more services.</span></span> <span data-ttu-id="458d4-127">大多数情况下，可以映射到单个服务，但也有可能映射到多个服务。</span><span class="sxs-lookup"><span data-stu-id="458d4-127">In most cases, this will be a single service, but it might be more.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="458d4-128">[上一页](data-sovereignty-per-microservice.md)
[下一页](distributed-data-management.md)</span><span class="sxs-lookup"><span data-stu-id="458d4-128">[Previous](data-sovereignty-per-microservice.md)
[Next](distributed-data-management.md)</span></span>
