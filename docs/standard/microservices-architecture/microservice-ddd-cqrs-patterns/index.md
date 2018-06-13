---
title: 使用 DDD 和 CQRS 模式降低微服务中的业务复杂性
description: 容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 DDD 和 CQRS 模式降低微服务中的业务复杂性
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ef8e0b08c7ba4ddb78144df54d407998cd40fc55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577184"
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="8b460-103">使用 DDD 和 CQRS 模式降低微服务中的业务复杂性</span><span class="sxs-lookup"><span data-stu-id="8b460-103">Tackling Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="8b460-104">为每个微服务或反映对业务域理解的绑定上下文设计域模型。</span><span class="sxs-lookup"><span data-stu-id="8b460-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="8b460-105">本节重点介绍在需要降低子系统复杂性时实现的更高级的微服务，或按不断变化的业务规则派生自域专家知识的微服务。</span><span class="sxs-lookup"><span data-stu-id="8b460-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="8b460-106">本节中使用的体系结构模式基于域驱动的设计 (DDD) 以及命令和查询责任分离 (CQRS) 方法，如图 9-1 中所示。</span><span class="sxs-lookup"><span data-stu-id="8b460-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 9-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="8b460-107">**图 9-1**。</span><span class="sxs-lookup"><span data-stu-id="8b460-107">**Figure 9-1**.</span></span> <span data-ttu-id="8b460-108">外部微服务体系结构与每个微服务的内部体系结构模式</span><span class="sxs-lookup"><span data-stu-id="8b460-108">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="8b460-109">但是，大部分用于数据驱动微服务的技术（例如如何实现 ASP.NET Core Web API 服务或如何公开具有 Swashbuckle 的 Swagger 元数据）同样适用于使用 DDD 模式在内部实现的更高级的微服务。</span><span class="sxs-lookup"><span data-stu-id="8b460-109">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="8b460-110">本节是前几节内容的扩展，因为之前所述的大部分做法也适用于此处或任何类型的微服务。</span><span class="sxs-lookup"><span data-stu-id="8b460-110">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="8b460-111">本节首先提供有关用于 eShopOnContainers 引用应用程序的简化 CQRS 模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b460-111">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="8b460-112">之后，将概述 DDD 技术，使你能够找到可在应用程序中重用的常见模式。</span><span class="sxs-lookup"><span data-stu-id="8b460-112">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="8b460-113">DDD 是一个大主题，具有一套丰富的学习资源。</span><span class="sxs-lookup"><span data-stu-id="8b460-113">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="8b460-114">开始时可以阅读 Eric Evans 撰写的[《域驱动设计》](https://domainlanguage.com/ddd/)等此类书籍，以及 Vaughn Vernon、Jimmy Nilsson、Greg Young、Udi Dahan、Jimmy Bogard 和许多其他 DDD/CQRS 专家撰写的其他资料。</span><span class="sxs-lookup"><span data-stu-id="8b460-114">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="8b460-115">但最重要的是需要尝试了解如何与具体业务域中的专家配合，从对话、白板和域建模会话应用 DDD 技术。</span><span class="sxs-lookup"><span data-stu-id="8b460-115">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="8b460-116">其他资源</span><span class="sxs-lookup"><span data-stu-id="8b460-116">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="8b460-117">DDD（域驱动设计）</span><span class="sxs-lookup"><span data-stu-id="8b460-117">DDD (Domain-Driven Design)</span></span>

-   <span data-ttu-id="8b460-118">**Eric Evans。Domain Language**
    [https://domainlanguage.com/](https://domainlanguage.com/)（域语言）</span><span class="sxs-lookup"><span data-stu-id="8b460-118">**Eric Evans. Domain Language**
[*https://domainlanguage.com/*](https://domainlanguage.com/)</span></span>

-   <span data-ttu-id="8b460-119">**Martin Fowler。Domain-Driven Design**
    [https://martinfowler.com/tags/domain%20driven%20design.html](https://martinfowler.com/tags/domain%20driven%20design.html)（域驱动设计）</span><span class="sxs-lookup"><span data-stu-id="8b460-119">**Martin Fowler. Domain-Driven Design**
[*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)</span></span>

-   <span data-ttu-id="8b460-120">**Jimmy Bogard。Strengthening your domain: a primer**
    [https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)（强化域：入门）</span><span class="sxs-lookup"><span data-stu-id="8b460-120">**Jimmy Bogard. Strengthening your domain: a primer**
[*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span></span>

##### <a name="ddd-books"></a><span data-ttu-id="8b460-121">DDD 丛书</span><span class="sxs-lookup"><span data-stu-id="8b460-121">DDD books</span></span>

-   <span data-ttu-id="8b460-122">**Eric Evans。Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)（域驱动设计：软件核心复杂性应对之道）</span><span class="sxs-lookup"><span data-stu-id="8b460-122">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
[*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="8b460-123">**Eric Evans。Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)（域驱动设计参考：定义和模式摘要）</span><span class="sxs-lookup"><span data-stu-id="8b460-123">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
[*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span></span>

-   <span data-ttu-id="8b460-124">**Vaughn Vernon。Implementing Domain-Driven Design**
    [https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)（实现域驱动设计）</span><span class="sxs-lookup"><span data-stu-id="8b460-124">**Vaughn Vernon. Implementing Domain-Driven Design**
[*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="8b460-125">**Vaughn Vernon。Domain-Driven Design Distilled**
    [https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)（域驱动设计核心理念）</span><span class="sxs-lookup"><span data-stu-id="8b460-125">**Vaughn Vernon. Domain-Driven Design Distilled**
[*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span></span>

-   <span data-ttu-id="8b460-126">**Jimmy Nilsson。Applying Domain-Driven Design and Patterns**
    [https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)（应用域驱动设计和模式）</span><span class="sxs-lookup"><span data-stu-id="8b460-126">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
[*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span></span>

-   <span data-ttu-id="8b460-127">**Cesar de la Torre。N-Layered Domain-Oriented Architecture Guide with .NET**
    [https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)（使用 .NET 的 N 层域导向体系结构指南）</span><span class="sxs-lookup"><span data-stu-id="8b460-127">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
[*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span></span>

-   <span data-ttu-id="8b460-128">**Abel Avram 与 Floyd Marinescu。Domain-Driven Design Quickly**
    [https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)（快速完成域驱动设计）</span><span class="sxs-lookup"><span data-stu-id="8b460-128">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
[*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span></span>

<span data-ttu-id="8b460-129">DDD 培训</span><span class="sxs-lookup"><span data-stu-id="8b460-129">DDD training</span></span>

-   <span data-ttu-id="8b460-130">**Julie Lerman 与 Steve Smith。Domain-Driven Design Fundamentals**
    [http://bit.ly/PS-DDD](http://bit.ly/PS-DDD)（域驱动设计基础知识）</span><span class="sxs-lookup"><span data-stu-id="8b460-130">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
[*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8b460-131">[上一页] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [下一页] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="8b460-131">[Previous] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [Next] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
