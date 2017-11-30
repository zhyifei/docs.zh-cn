---
title: "分布式的数据管理挑战和解决方案"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |分布式的数据管理挑战和解决方案"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f961475b40c74bf448cff1aeae04ae4866360e52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="challenges-and-solutions-for-distributed-data-management"></a>分布式的数据管理挑战和解决方案

## <a name="challenge-1-how-to-define-the-boundaries-of-each-microservice"></a>质询\#1： 如何定义每个微服务构成的边界

定义 microservice 边界可能是任何人都遇到第一次质询。 每个微服务必须是一种你的应用程序，并且每个微服务应该自治与所有的优点和它具有的挑战。 但是，你如何标识这些边界？

首先，你需要专注于应用程序的逻辑域模型和相关的数据。 你必须尝试确定的数据和同一个应用程序中的不同上下文分离的岛。 每个上下文可能具有不同业务语言 （不同的业务术语表示）。 应定义和独立管理上下文。 条款和在这些不同的上下文中使用的实体可能听起来类似，但你可能会发现，在特定上下文中，一个业务概念适用于在另一个上下文中，不同的用途并甚至可能具有不同的名称。 例如，用户可以称为客户，则在 CRM 上下文中，为在未排序的上下文中购买者的标识或成员资格的上下文中的用户身份，等等。

为每个上下文完全是可以识别每个业务微服务和其相关的边界的方式标识具有不同的域的多个应用程序上下文之间的边界的方式域模型和数据。 你始终尝试最大程度减少这些微服务之间的耦合。 本指南将进入此部分中的标识和域的模型设计的更多详情[标识每个微服务的域模型边界](#identifying-domain-model-boundaries-for-each-microservice)更高版本。

## <a name="challenge-2-how-to-create-queries-that-retrieve-data-from-several-microservices"></a>质询\#2： 如何创建从多个微服务中检索数据的查询

第二个挑战是如何实现从多个微服务中检索数据，同时可避免聊天式通信到微服务从远程客户端应用程序的查询。 一个示例可能是单个屏幕从的移动应用程序需要显示用户拥有的购物篮、 目录和用户标识微服务的信息。 另一个示例将涉及位于多个微服务的多个表的复杂报表。 正确的解决方案取决于查询的复杂性。 但在任何情况下，你将需要聚合信息的方法，如果你想要改进你的系统的通信的效率。 最常用的解决方案如下所示。

**API 网关**。 用于从多个拥有不同的数据库的微服务的简单数据聚合、 建议的方法是称为 API 网关聚合微服务。 但是，你需要小心有关实现此模式中，因为它可以压点处于您的系统，并且它可以违反 microservice 自治的原则。 若要缓解这种可能性，可以具有多个细粒度 API 网关每一个将重点放在垂直"切片"或业务区域的系统。 API 网关模式中一节中使用的详细说明了一个 API 网关更高版本。

**与查询/读取表 CQRS**。 用于从多个微服务聚合数据的另一个解决方案是[具体化视图模式](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)。 在此方法中，你生成，请提前 （之前准备好非规范化的数据的实际查询发生这种情况），具有拥有的多个微服务的数据的只读的表。 表的格式适合客户端应用程序的需求。

请考虑用于移动应用程序的屏幕类似。 如果你有一个数据库，你可能使用的 SQL 查询来执行复杂的联接涉及多个表该屏幕的数据获取在一起。 但是，当你有多个数据库，并且每个数据库拥有的不同微服务，您无法查询这些数据库和创建 SQL 联接。 复杂查询是一项挑战。 你可以处理使用 CQRS 方法要求-仅用于查询的不同数据库中创建一个非规范化的表。 表可以专为具有所需的应用程序的屏幕和查询表中的列的字段之间的一对一关系的复杂查询所需的数据。 它也无法提供用于报告的数据。

此方法不仅解决了原始的问题 （如何查询和联接跨微服务）;它还改进了性能显著时与复杂的联接，进行比较，因为你已有该应用程序需要查询表中的数据。 当然，查询/读取表中使用命令和查询责任分离 (CQRS) 意味着额外的开发工作，并且将需要采用最终一致性。 但是，对性能和中的高可伸缩性要求[协作方案](http://udidahan.com/2011/10/02/why-you-should-be-using-cqrs-almost-everywhere/)（或者竞争的方案，具体取决于角度来看） 是你应在何处应用的多个数据库存在 CQRS。

**在中心数据库中的"冷数据"**。 对于复杂的报表可能不需要实时数据的查询，常见的方法是导出你"热数据"（从微服务的事务数据） 作为到大型数据库，仅用于报告的"冷数据"。 该中央数据库系统可以是基于大数据的系统，如 Hadoop，类似于基于 Azure SQL 数据仓库或甚至单个 SQL 数据库仅用于报表，（如果大小将不会出现问题） 的数据仓库。

请记住，此集中的数据库将仅用于进行查询和不需要实时数据的报表。 原始的更新和事务，为你资料来源，一定要处于微服务数据。 将同步数据的方法是通过使用事件驱动的通信 （在后面的部分中介绍） 或使用其他数据库基础结构导入/导出工具。 如果你使用事件驱动的通信，则该集成过程将类似于前面所述的 CQRS 查询表传播数据的方式。

但是，如果你的应用程序设计涉及不断地聚合从对于复杂的查询的多个微服务的信息，则可能是不好的设计的症状-microservice 应尽可能从其他微服务作为独立。 （这不包括报表/分析始终应使用冷数据中心数据库。）通常遇到此问题可能的原因合并微服务。 你需要平衡的变化情况自主性和的强依赖关系、 内聚，与数据聚合的每个微服务的部署。

## <a name="challenge-3-how-to-achieve-consistency-across-multiple-microservices"></a>质询\#3： 如何跨多个微服务实现一致性

如前面所述，并将数据拥有的每个微服务专用于该微服务仅可通过使用其微服务 API 访问。 因此，提供一个难题是如何在跨多个微服务保持一致性的同时实现端到端业务流程。

若要分析此问题，让我们看一个示例从[eShopOnContainers 引用应用程序](http://aka.ms/eshoponcontainers)。 目录微服务会维护有关所有产品，包括其库存级别的信息。 排序 microservice 管理订单，并必须验证新的顺序不能超过可用的编录产品库存。 （或方案可能涉及处理延期交货产品的逻辑。）在此应用程序的假设整体版本，排序子系统无法只需使用 ACID 事务可以检查可用的库存、 订单表中创建订单和更新产品表中的可用库存。

但是，在基于微服务的应用中，顺序和产品表由拥有其各自的微服务。 没有 microservice 曾经应包括数据库拥有的另一个微服务在其自己的事务或查询，在图 4-9 中所示。

![](./media/image9.PNG)

**图 4-9**。 Microservice 不能直接访问另一个微服务中的表

因为产品表拥有的目录 microservice 排序微服务不应直接，更新产品表。 若要对目录 microservice 进行更新，排序 microservice 永远只有应使用异步通信，例如集成事件 （邮件和基于事件的通信）。 这是如何[eShopOnContainers](http://aka.ms/eshoponcontainers)引用应用程序执行此类型的更新。

中所述[CAP 定理](https://en.wikipedia.org/wiki/CAP_theorem)，你需要可用性和 ACID 强一致性之间进行选择。 大多数基于微服务构成的方案要求可用性和而不是强一致性的高可伸缩性。 任务关键型应用程序必须始终打开和运行时，开发人员可以使用和工作围绕强一致性技术用于使用弱或最终一致性。 这是通过大多数基于微服务的体系结构而采取的做法。

此外，ACID 样式或两阶段提交事务不只是针对微服务原则;大多数 NoSQL 数据库 （如 Azure Cosmos DB、 MongoDB 等） 不支持两阶段提交事务。 但是，维护数据在服务和数据库之间的一致性至关重要。 应对此挑战还与如何在多个微服务之间传播更改，某些数据需要冗余时这一问题 — 例如，当你需要拥有该产品的名称或目录微服务和购物篮中的说明微服务。

此问题很好的解决方案是使用微服务说明哪些情况下通过事件驱动的通信和发布和订阅系统之间的最终一致性。 这些主题涵盖在部分[事件驱动的异步通信](#async_event_driven_communication)本指南中更高版本。

## <a name="challenge-4-how-to-design-communication-across-microservice-boundaries"></a>质询\#4： 如何设计跨微服务边界的通信

在微服务通信边界是真正的挑战。 在此上下文中，通信不是指什么协议你应使用 （HTTP 和 REST，AMQP，消息传递，等等）。 相反，它解决了应使用何种通信样式，尤其是如何耦合你微服务应为。 根据耦合的级别，出现故障时，你的系统上该失败的影响将变化很大。

在类似于基于微服务的应用程序，与移动的许多项目和分布式服务分散在许多服务器或主机，分布式系统组件最终将会失败。 部分的失败和甚至更大的服务中断将会发生，因此你需要在这些考虑风险常见此类型的分布式系统中设计你微服务以及的通信。

常用方法是实现 HTTP (REST)-基于微服务，由于其简单性。 基于 HTTP 的另一方法是完全可以接受;这里的主要问题与如何使用它。 如果使用 HTTP 请求和响应只是为了与你微服务从客户端应用程序或 API 网关进行交互，那也不错。 但如果跨微服务创建的同步的 HTTP 调用的长链，就像微服务是在整体应用程序中，对象在其边界通信你的应用程序最终会遇到问题。

例如，假设客户端应用程序可以对如排序 microservice 单个微服务的 HTTP API 调用。 如果排序 microservice 反过来调用其他微服务在相同的请求/响应使用 HTTP 周期，你正在使用的 HTTP 调用链。 它听起来合理最初。 但是，有停运此路径时要考虑的重要事项：

-   阻塞和低性能。 由于 HTTP 同步性质，原始请求不会获得响应，直到所有内部的 HTTP 调用已完成。 假设是否这些调用的数量会显著增加，到微服务构成一个中间的 HTTP 调用的同时被阻止。 结果是，性能会受到影响，并且将作为其他 HTTP 请求增加指数级增长影响总体可伸缩性。

-   与 HTTP 耦合微服务。 不应与其他业务微服务结合业务微服务。 理想情况下，它们应不"知道"有关的其他微服务存在。 如果你的应用程序依赖于耦合如示例所示的微服务，实现每个微服务构成的自治将几乎不可能。

-   在任何一个的微服务时失败。 如果你实现了微服务时任意微服务失败 （和最终它们将会失败） 的微服务的整个链链接通过 HTTP 调用的链将失败。 应设计基于微服务构成的系统能够继续在部分故障期间以及可能工作。 即使你实现重试使用指数退让或断路器机制的客户端逻辑，详细的复杂 HTTP 调用链也，它是实现基于 HTTP 的失败策略变得更加复杂。

事实上，如果你的内部微服务进行通信通过所述创建的 HTTP 请求的链，它无法将指出性具有整体的应用程序，但根据 HTTP 而不是 intraprocess 通信机制的进程之间。

因此，为了强制实施 microservice 自主性和具有更好的可恢复性，你应尽量少使用的请求/响应通信链跨微服务。 建议你将用于虚拟网络间微服务构成通信仅异步交互通过使用异步消息和基于事件的通信，或通过使用 HTTP 轮询与原始 HTTP 请求/响应周期无关。

异步通信介绍了如何将包含在部分中的本指南后面的其他详细信息[异步微服务集成将强制使用微服务构成的自治](#asynchronous-microservice-integration-enforce-microservices-autonomy)和[异步基于消息的通信](#asynchronous-message-based-communication)。

## <a name="additional-resources"></a>其他资源

-   **CAP 定理**
    [*https://en.wikipedia.org/wiki/CAP\_定理*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **最终一致性**
    [*https://en.wikipedia.org/wiki/Eventual\_一致性*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **数据一致性入门**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)

-   **Martin Fowler。CQRS （命令和查询责任分离）**
    [*http://martinfowler.com/bliki/CQRS.html*](http://martinfowler.com/bliki/CQRS.html)

-   **具体化视图**
    [*https://docs.microsoft.com/azure/architecture/patterns/materialized-view*](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

-   **Charles 行。ACID vs。基本： 数据库事务处理的 Shifting pH**
    [*http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/*](http://www.dataversity.net/acid-vs-base-the-shifting-ph-of-database-transaction-processing/)

-   **补偿事务**
    [*https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction*](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

-   **Udi Dahan。面向服务的组合**
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)


>[!div class="step-by-step"]
[以前](逻辑-而不是-物理-architecture.md) [下一步] (标识-微服务构成的域-模型-boundaries.md)
