---
title: "EShopOnContainers DDD 微服务中的应用 CQRS 和 CQS 方法"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |EShopOnContainers DDD 微服务中的应用 CQRS 和 CQS 方法"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a><span data-ttu-id="81465-104">EShopOnContainers DDD 微服务中的应用 CQRS 和 CQS 方法</span><span class="sxs-lookup"><span data-stu-id="81465-104">Applying CQRS and CQS approaches in a DDD microservice in eShopOnContainers</span></span>

<span data-ttu-id="81465-105">在 eShopOnContainers 引用应用程序排序微服务构成的设计基于 CQRS 原则。</span><span class="sxs-lookup"><span data-stu-id="81465-105">The design of the ordering microservice at the eShopOnContainers reference application is based on CQRS principles.</span></span> <span data-ttu-id="81465-106">但是，它使用的最简单的方法，只需将查询与命令分离并使用相同的数据进行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="81465-106">However, it uses the simplest approach, which is just separating the queries from the commands and using the same database for both actions.</span></span>

<span data-ttu-id="81465-107">这些模式，并在这里，重要的一点的本质就是，查询也是幂等的： 无论多少次查询一个系统，该系统的状态将不会更改，你甚至可以使用不同的"读取"比"写入"的事务逻辑数据模型域模型，尽管排序微服务正在使用相同的数据库。</span><span class="sxs-lookup"><span data-stu-id="81465-107">The essence of those patterns, and the important point here, is that queries are idempotent: no matter how many times you query a system, the state of that system will not change You could even use a different “reads” data model than the transactional logic “writes” domain model, although the ordering microservices is using the same database.</span></span> <span data-ttu-id="81465-108">因此，这是简化的 CQRS 方法。</span><span class="sxs-lookup"><span data-stu-id="81465-108">Hence this is a simplified CQRS approach.</span></span>

<span data-ttu-id="81465-109">另一方面，命令，触发事务和数据更新，在系统中更改状态。</span><span class="sxs-lookup"><span data-stu-id="81465-109">On the other hand, commands, which trigger transactions and data updates, change state in the system.</span></span> <span data-ttu-id="81465-110">你需要使用命令，请注意与复杂性和不断变化的业务规则。</span><span class="sxs-lookup"><span data-stu-id="81465-110">With commands, you need to be careful when dealing with complexity and ever-changing business rules.</span></span> <span data-ttu-id="81465-111">这就是你想要应用 DDD 技术能够更好地建模的系统。</span><span class="sxs-lookup"><span data-stu-id="81465-111">This is the where you want to apply DDD techniques to have a better modeled system.</span></span>

<span data-ttu-id="81465-112">本指南中讲述的 DDD 模式应不会全局应用。</span><span class="sxs-lookup"><span data-stu-id="81465-112">The DDD patterns presented in this guide should not be applied universally.</span></span> <span data-ttu-id="81465-113">它们引入你的设计的约束。</span><span class="sxs-lookup"><span data-stu-id="81465-113">They introduce constraints on your design.</span></span> <span data-ttu-id="81465-114">这些约束随着时间推移，特别是在命令和其他修改系统状态的代码提供的好处，例如更高的质量。</span><span class="sxs-lookup"><span data-stu-id="81465-114">Those constraints provide benefits such as higher quality over time, especially in commands and other code that modifies system state.</span></span> <span data-ttu-id="81465-115">但是，这些约束添加较少的优势，用于读取和查询数据的复杂性。</span><span class="sxs-lookup"><span data-stu-id="81465-115">However, those constraints add complexity with fewer benefits for reading and querying data.</span></span>

<span data-ttu-id="81465-116">这种模式之一是聚合模式，我们在后面几节中更检查。</span><span class="sxs-lookup"><span data-stu-id="81465-116">One such pattern is the Aggregate pattern, which we examine more in later sections.</span></span> <span data-ttu-id="81465-117">简要，在聚合模式中，你将多个域对象作为单个单元由于在域中的关系。</span><span class="sxs-lookup"><span data-stu-id="81465-117">Briefly, in the Aggregate pattern, you treat many domain objects as a single unit as a result of their relationship in the domain.</span></span> <span data-ttu-id="81465-118">你可能不始终获得从查询; 在此模式的优点它可以增加查询逻辑的复杂性。</span><span class="sxs-lookup"><span data-stu-id="81465-118">You might not always gain advantages from this pattern in queries; it can increase the complexity of query logic.</span></span> <span data-ttu-id="81465-119">对于只读查询，未得到的将多个对象视为单个聚合的优势。</span><span class="sxs-lookup"><span data-stu-id="81465-119">For read-only queries, you do not get the advantages of treating multiple objects as a single Aggregate.</span></span> <span data-ttu-id="81465-120">你只能获取复杂性。</span><span class="sxs-lookup"><span data-stu-id="81465-120">You only get the complexity.</span></span>

<span data-ttu-id="81465-121">如所示图 9-2，本指南建议仅在你的 microservice 事务性/更新区域中使用 DDD 模式 （即，因为命令由触发）。</span><span class="sxs-lookup"><span data-stu-id="81465-121">As shown in Figure 9-2, this guide suggests using DDD patterns only in the transactional/updates area of your microservice (that is, as triggered by commands).</span></span> <span data-ttu-id="81465-122">查询可以遵循更简单的方法，并应分开后面 CQRS 方法的命令。</span><span class="sxs-lookup"><span data-stu-id="81465-122">Queries can follow a simpler approach and should be separated from commands, following a CQRS approach.</span></span>

<span data-ttu-id="81465-123">用于实现"查询端"，你可以选择多种方法，从你全面 ORM EF 核心、 AutoMapper 投影、 存储的过程、 视图、 具体化的视图或微型 ORM 等。</span><span class="sxs-lookup"><span data-stu-id="81465-123">For implementing the “queries side”, you can choose between many approaches, from your full-blown ORM like EF Core, AutoMapper projections, stored procedures, views, materialized views or a micro ORM.</span></span>

<span data-ttu-id="81465-124">本指南中和在 eShopOnContainers （专门排序微服务），我们选择实现直接查询使用 micro ORM 如[Dapper](https://github.com/StackExchange/dapper-dot-net)。</span><span class="sxs-lookup"><span data-stu-id="81465-124">In this guide and in eShopOnContainers (specifically the ordering microservice) we chose to implement straight queries using a micro ORM like [Dapper](https://github.com/StackExchange/dapper-dot-net).</span></span> <span data-ttu-id="81465-125">这样可以实现基于 SQL 语句，以获取最佳性能，使用极小的开销浅色 framework 感谢任何查询。</span><span class="sxs-lookup"><span data-stu-id="81465-125">This lets you implement any query based on SQL statements to get the best performance, thanks to a light framework with very little overhead.</span></span>

<span data-ttu-id="81465-126">请注意，当你使用此方法时，与你的模型影响如何将实体保存到 SQL 数据库的任何更新也需要 to SQL 查询使用 Dapper 或查询到的任何其他单独的 (非 EF) 方法的单独更新。</span><span class="sxs-lookup"><span data-stu-id="81465-126">Note that when you use this approach, any updates to your model that impact how entities are persisted to a SQL database also need separate updates to SQL queries used by Dapper or any other separate (non-EF) approaches to querying.</span></span>

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a><span data-ttu-id="81465-127">CQRS 和 DDD 模式不是顶级体系结构</span><span class="sxs-lookup"><span data-stu-id="81465-127">CQRS and DDD patterns are not top-level architectures</span></span>

<span data-ttu-id="81465-128">你必须知道该 CQRS 和 （如 DDD 层或具有聚合的域模型） 的大多数 DDD 模式不是体系结构风格，而是仅体系结构模式。</span><span class="sxs-lookup"><span data-stu-id="81465-128">It important to understand that CQRS and most DDD patterns (like DDD layers or a domain model with aggregates) are not architectural styles, but only architecture patterns.</span></span> <span data-ttu-id="81465-129">微服务、 SOA 和事件驱动体系结构 (EDA) 是体系结构风格的示例。</span><span class="sxs-lookup"><span data-stu-id="81465-129">Microservices, SOA, and event-driven architecture (EDA) are examples of architectural styles.</span></span> <span data-ttu-id="81465-130">许多组件，如许多微服务将系统描述它们。</span><span class="sxs-lookup"><span data-stu-id="81465-130">They describe a system of many components, such as many microservices.</span></span> <span data-ttu-id="81465-131">在单个系统或组件; 内的 CQRS 和 DDD 模式描述的内容在此情况下，内容在微服务。</span><span class="sxs-lookup"><span data-stu-id="81465-131">CQRS and DDD patterns describe something inside a single system or component; in this case, something inside a microservice.</span></span>

<span data-ttu-id="81465-132">不同的绑定上下文 (BCs) 将采用不同的模式。</span><span class="sxs-lookup"><span data-stu-id="81465-132">Different Bounded Contexts (BCs) will employ different patterns.</span></span> <span data-ttu-id="81465-133">它们都有不同的责任，并且这产生了不同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="81465-133">They have different responsibilities, and that leads to different solutions.</span></span> <span data-ttu-id="81465-134">值得重视的强制 everywhere 会导致失败的相同模式。</span><span class="sxs-lookup"><span data-stu-id="81465-134">It is worth emphasizing that forcing the same pattern everywhere leads to failure.</span></span> <span data-ttu-id="81465-135">无处不在不使用 CQRS 和 DDD 模式。</span><span class="sxs-lookup"><span data-stu-id="81465-135">Do not use CQRS and DDD patterns everywhere.</span></span> <span data-ttu-id="81465-136">许多子系统、 BCs 或微服务选项要更为简单，并可以更轻松地使用简单 CRUD 服务或使用另一种方法实现。</span><span class="sxs-lookup"><span data-stu-id="81465-136">Many subsystems, BCs, or microservices are simpler and can be implemented more easily using simple CRUD services or using another approach.</span></span>

<span data-ttu-id="81465-137">没有只有一个应用程序体系结构： 你设计 （例如微服务体系结构） 的系统或端到端应用程序的体系结构。</span><span class="sxs-lookup"><span data-stu-id="81465-137">There is only one application architecture: the architecture of the system or end-to-end application you are designing (for example, the microservices architecture).</span></span> <span data-ttu-id="81465-138">但是，每个绑定的上下文或该应用程序中的微服务的设计反映其自己的折衷方案和体系结构模式级别的内部设计决策。</span><span class="sxs-lookup"><span data-stu-id="81465-138">However, the design of each Bounded Context or microservice within that application reflects its own tradeoffs and internal design decisions at an architecture patterns level.</span></span> <span data-ttu-id="81465-139">不要尝试将相同的体系结构模式如 CQRS 或 DDD 无处不在。</span><span class="sxs-lookup"><span data-stu-id="81465-139">Do not try to apply the same architectural patterns like CQRS or DDD everywhere.</span></span>

####  <a name="additional-resources"></a><span data-ttu-id="81465-140">其他资源</span><span class="sxs-lookup"><span data-stu-id="81465-140">Additional resources</span></span>

-   <span data-ttu-id="81465-141">**Martin Fowler。CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span><span class="sxs-lookup"><span data-stu-id="81465-141">**Martin Fowler. CQRS**
[*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)</span></span>

-   <span data-ttu-id="81465-142">**Greg Young。CQS vs。CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span><span class="sxs-lookup"><span data-stu-id="81465-142">**Greg Young. CQS vs. CQRS**
[*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)</span></span>

-   <span data-ttu-id="81465-143">**Greg Young。CQRS 文档**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span><span class="sxs-lookup"><span data-stu-id="81465-143">**Greg Young. CQRS Documents**
[*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)</span></span>

-   <span data-ttu-id="81465-144">**Greg Young。CQRS，任务基于的 Ui 和事件来源**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span><span class="sxs-lookup"><span data-stu-id="81465-144">**Greg Young. CQRS, Task Based UIs and Event Sourcing**
[*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)</span></span>

-   <span data-ttu-id="81465-145">**Udi Dahan。阐明了 CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="81465-145">**Udi Dahan. Clarified CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="81465-146">**CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span><span class="sxs-lookup"><span data-stu-id="81465-146">**CQRS**
[*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)</span></span>

-   <span data-ttu-id="81465-147">**事件来源 (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span><span class="sxs-lookup"><span data-stu-id="81465-147">**Event-Sourcing (ES)**
[*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="81465-148">[以前](apply-simplified-microservice-cqrs-ddd-patterns.md) [下一步] (cqrs microservice reads.md)</span><span class="sxs-lookup"><span data-stu-id="81465-148">[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)</span></span>
