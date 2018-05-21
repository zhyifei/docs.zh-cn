---
title: 在 eShopOnContainers 的 DDD 微服务中应用 CQRS 和 CQS 方法
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在 eShopOnContainers 的 DDD 微服务中应用 CQRS 和 CQS 方法
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6be8b52f42e3e37ff03e561af45c46f4dd283d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="99371-103">在 eShopOnContainers 的 DDD 微服务中应用 CQRS 和 CQS 方法</span><span class="sxs-lookup"><span data-stu-id="99371-103">Applying CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="99371-104">eShopOnContainers 引用应用程序处的订单微服务设计基于 CQRS 原则。</span><span class="sxs-lookup"><span data-stu-id="99371-104">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="99371-105">但是，它使用最简单的方法：只需将查询与命令分离，且执行这两种操作时使用相同的数据库。</span><span class="sxs-lookup"><span data-stu-id="99371-105">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="99371-106">这些模式的本质，同时也是很重要的一点，即查询是幂等的：无论对一个系统查询多少次，该系统的状态不会更改，甚至可以使用不同于事务逻辑“写入”域模型的“读取”数据模型，尽管订单微服务使用相同的数据库。</span><span class="sxs-lookup"><span data-stu-id="99371-106">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system will not change You could even use a different “reads” data model than the transactional logic “writes” domain model, although the ordering microservices is using the same database.</span></span> <span data-ttu-id="99371-107">因此这是简化的 CQRS 方法。</span><span class="sxs-lookup"><span data-stu-id="99371-107">Hence this is a simplified CQRS approach.</span></span>

<span data-ttu-id="99371-108">另一方面，用于触发事务和数据更新的命令在系统中会更改状态。</span><span class="sxs-lookup"><span data-stu-id="99371-108">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="99371-109">在处理复杂问题和不断变化的业务规则的过程中，使用命令时需小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="99371-109">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="99371-110">这正是应用 DDD 技术的时候，可以获取更好的模型化系统。</span><span class="sxs-lookup"><span data-stu-id="99371-110">This is the where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="99371-111">本指南中介绍的 DDD 模式并不是普遍适用的。</span><span class="sxs-lookup"><span data-stu-id="99371-111">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="99371-112">它们会在设计中引入约束。</span><span class="sxs-lookup"><span data-stu-id="99371-112">They introduce constraints on your design.</span></span> <span data-ttu-id="99371-113">这些约束具有一些优点，比如可随时间推移不断提升质量，特别是命令和用于修改系统状态的其他代码的质量。</span><span class="sxs-lookup"><span data-stu-id="99371-113">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="99371-114">但是这些约束在数据读取和查询方面的没有太多用处，反而会增加复杂性。</span><span class="sxs-lookup"><span data-stu-id="99371-114">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="99371-115">这种模式中的一种是聚合模式，会在后面几部分中进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="99371-115">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="99371-116">简单来说，在聚合模式中，因多个域对象在域中的关系，会将这些域对象作为一个单位来对待。</span><span class="sxs-lookup"><span data-stu-id="99371-116">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="99371-117">在查询中，此模式也可能产生不便，它可能会增加查询逻辑的复杂性。</span><span class="sxs-lookup"><span data-stu-id="99371-117">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="99371-118">对于只读查询，无法获得将多个对象视为单个聚合的优势。</span><span class="sxs-lookup"><span data-stu-id="99371-118">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="99371-119">而只会增加复杂性。</span><span class="sxs-lookup"><span data-stu-id="99371-119">You only get the complexity.</span></span>

<span data-ttu-id="99371-120">如图 9-2 所示，本指南建议仅在微服务的事务性/更新区域中使用 DDD 模式（也即由命令触发时）。</span><span class="sxs-lookup"><span data-stu-id="99371-120">As shown in Figure 9-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="99371-121">查询可以遵循更简单的方法，如果遵循 CQRS 方法，应将查询与命令分离开来。</span><span class="sxs-lookup"><span data-stu-id="99371-121">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="99371-122">要实现“查询端”，成熟的 ORM 中有许多方法可供选择：EF Core、AutoMapper 投影、存储过程、视图、具体化视图或微型 ORM。</span><span class="sxs-lookup"><span data-stu-id="99371-122">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="99371-123">在本指南和 eShopOnContainers （尤其是订单微服务）中，使用 [Dapper](https://github.com/StackExchange/dapper-dot-net) 等微型 ORM 实现直接查询。</span><span class="sxs-lookup"><span data-stu-id="99371-123">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="99371-124">这样可基于 SQL 语句实现任何查询并获取最佳性能，这得益于成本低廉的轻量级框架。</span><span class="sxs-lookup"><span data-stu-id="99371-124">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="99371-125">请注意，使用此方法时，如果对模型进行任何更新，且该更新会影响实体持久保存到 SQL 数据库的方式，那么同时需要 对 Dapper 使用的或任何其他单独的查询方法（非 EF）使用的 SQL 查询进行单独更新。</span><span class="sxs-lookup"><span data-stu-id="99371-125">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="99371-126">CQRS 和 DDD 模式不是顶层体系结构</span><span class="sxs-lookup"><span data-stu-id="99371-126">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="99371-127">须知 CQRS 和大多数 DDD 模式（如 DDD 层或带有聚合的域模型）不是体系结构样式，而只是体系结构模式。</span><span class="sxs-lookup"><span data-stu-id="99371-127">It important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="99371-128">体系结构样式的例子包括微服务、SOA 和事件驱动的体系结构 (EDA)。</span><span class="sxs-lookup"><span data-stu-id="99371-128">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="99371-129">它们描述由许多组件（如许多微服务）构成的系统。</span><span class="sxs-lookup"><span data-stu-id="99371-129">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="99371-130">而 CQRS 和 DDD 模式描述单个系统或组件内的某项内容，在本例中，也即微服务内的某项内容。</span><span class="sxs-lookup"><span data-stu-id="99371-130">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="99371-131">不同的界定上下文 (BC) 采用不同的模式。</span><span class="sxs-lookup"><span data-stu-id="99371-131">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="99371-132">它们具有不同的功能，会形成不同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="99371-132">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="99371-133">这里需强调的是，在任何情况下都使用相同模式会导致失败。</span><span class="sxs-lookup"><span data-stu-id="99371-133">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="99371-134">请勿滥用 CQRS 和 DDD 模式。</span><span class="sxs-lookup"><span data-stu-id="99371-134">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="99371-135">有许多更简单的子系统、BC 或微服务，可使用简单的 CRUD 服务或其他方法更轻松地实现。</span><span class="sxs-lookup"><span data-stu-id="99371-135">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="99371-136">只有一个应用程序体系结构：你设计的系统或端到端应用程序的体系结构（如微服务体系结构）。</span><span class="sxs-lookup"><span data-stu-id="99371-136">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="99371-137">但该应用程序中的每个界定的上下文或微服务的设计反映有关其自身的折衷方案和体系结构模式级别的内部设计决策。</span><span class="sxs-lookup"><span data-stu-id="99371-137">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="99371-138">请勿尝试将相同的体系结构模式（如 CQRS 或 DDD）用于所有情况。</span><span class="sxs-lookup"><span data-stu-id="99371-138">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

####  <a name="additional-resources"></a><span data-ttu-id="99371-139">其他资源</span><span class="sxs-lookup"><span data-stu-id="99371-139">Additional resources</span></span>

-   <span data-ttu-id="99371-140">**Martin Fowler。CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span><span class="sxs-lookup"><span data-stu-id="99371-140">**Martin Fowler. CQRS**
[*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span></span>

-   <span data-ttu-id="99371-141">**Greg Young.CQS 与CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span><span class="sxs-lookup"><span data-stu-id="99371-141">**Greg Young. CQS vs. CQRS**
[*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span></span>

-   <span data-ttu-id="99371-142">**Greg Young.CQRS 文档**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span><span class="sxs-lookup"><span data-stu-id="99371-142">**Greg Young. CQRS Documents**
[*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span></span>

-   <span data-ttu-id="99371-143">**Greg Young.CQRS、基于任务的 UI 和事件源**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span><span class="sxs-lookup"><span data-stu-id="99371-143">**Greg Young. CQRS, Task Based UIs and Event Sourcing**
[*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span></span>

-   <span data-ttu-id="99371-144">**Udi Dahan.Clarified CQRS**（明确的 CQRS）
    [http://udidahan.com/2009/12/09/clarified-cqrs/](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="99371-144">**Udi Dahan. Clarified CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="99371-145">**CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="99371-145">**CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="99371-146">**事件源 (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span><span class="sxs-lookup"><span data-stu-id="99371-146">**Event-Sourcing (ES)**
[*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="99371-147">[上一项] (apply-simplified-microservice-cqrs-ddd-patterns.md) [下一项] (cqrs microservice reads.md)</span><span class="sxs-lookup"><span data-stu-id="99371-147">[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)</span></span>
