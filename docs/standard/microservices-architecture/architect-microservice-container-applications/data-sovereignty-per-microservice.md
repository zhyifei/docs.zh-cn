---
title: "每个微服务构成的数据自主性"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |每个微服务构成的数据自主性"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c51daae04215cfa6f5b5b8d2158a8ed1a8949652
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="data-sovereignty-per-microservice"></a>每个微服务构成的数据自主性

微服务体系结构的重要规则是每个微服务必须拥有其域数据和逻辑。 就像一个完整的应用程序拥有其逻辑和数据，因此必须每个微服务拥有其逻辑和下自治生命周期，与每个微服务的部署独立于数据。

这意味着域的概念模型将子系统或微服务之间有所不同。 请考虑企业应用程序，其中客户关系管理 (CRM) 应用程序，事务购买子系统和客户支持子系统上的唯一客户实体属性和数据，每个调用，且每个使用不同界限的上下文 (BC)。

此原则是在类似[域驱动设计 (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design)，其中每个[绑定上下文](https://martinfowler.com/bliki/BoundedContext.html)或自治子系统或服务必须拥有其域模型 （数据加上逻辑和行为）。 每个 DDD 绑定上下文对应于一个业务微服务 （一个或多个服务）。 （我们在上展开此点有关下一节中的绑定上下文模式。）

另一方面，在许多应用程序中使用传统 （整体数据） 方法是具有单个集中式的数据库或只需少量的数据库。 这通常是适用于整个应用程序和所有其内部子系统，规范化的 SQL 数据库，在图 4-7 中所示。

![](./media/image7.png)

**图 4-7**。 数据自主性比较： 整体数据库而不是微服务

集中式的 database 方法最初看起来更简单，并且看起来以确保以一致的所有内容的其他子系统中的实体的重复使用。 但事实是你最终会得到极大的表提供许多其他子系统，并且在大多数情况下包括属性和不需要的列。 这就像尝试使用相同的物理映射用于旅游短跟踪，花费的持续一天的汽车行程，和了解地理位置。

具有通常一个关系数据库的整体应用程序有两个重要的好处： [ACID 事务](https://en.wikipedia.org/wiki/ACID)和 SQL 语言，这两个跨所有表和与你的应用程序相关的数据。 此方法提供了一种方法轻松地编写合并来自多个表的数据的查询。

但是，数据访问变得更复杂，你将移动到微服务体系结构时。 但即使 ACID 事务可以或应在 microservice 或绑定上下文中使用，并将数据拥有的每个微服务专用于该 microservice 只能通过其微服务 API 访问。 封装数据可确保微服务松散耦合，可以独立于另一个变化。 如果多个服务访问相同的数据，架构更新将需要协调的更新到所有服务。 这将会破坏微服务生命周期自治。 但分布式的数据结构意味着您无法跨微服务进行单个 ACID 事务。 这反过来意味着当业务流程跨多个微服务时，必须使用最终一致性。 这是很难实现都比简单的 SQL 联接;同样，许多其他关系数据库功能将不可用跨多个微服务。

将更进一步，不同的微服务通常使用不同*类型*的数据库。 现代应用程序存储和处理不同类型的数据，以及关系数据库并不总是最佳选择。 对于某些用例，如 Azure DocumentDB 或 MongoDB 的 NoSQL 数据库可能会更方便的数据模型并提供更好的性能和可伸缩性，比 SQL 数据库类似于 SQL Server 或 Azure SQL 数据库。 在其他情况下，关系数据库仍是最佳的方法。 因此，基于微服务的应用程序通常将混合使用 SQL 和 NoSQL 数据库，这有时称为[polyglot 持久性](http://martinfowler.com/bliki/PolyglotPersistence.html)方法。

数据存储的分区、 polyglot 持续性持久体系结构带来诸多好处。 其中包括松散耦合的服务和更好性能、 可伸缩性、 成本和可管理性。 但是，它还会带来一些分布式的数据管理难题，因为我们将介绍在"[标识域模型边界](#identifying-domain-model-boundaries-for-each-microservice)"这一章中更高版本。

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>微服务和绑定上下文模式之间的关系

微服务构成的概念派生自[绑定上下文 (BC) 模式](http://martinfowler.com/bliki/BoundedContext.html)中[域驱动设计 (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design)。 DDD 通过将它们分割成多个 BCs 和有关其边界显式处理大的模型。 每个业务连续性必须具有其自己的模型和数据库;同样，每个微服务拥有其相关的数据。 此外，每个业务连续性通常都具有其自己[无处不在语言](http://martinfowler.com/bliki/UbiquitousLanguage.html)有助于软件开发人员和域专业人员之间的通信。

无处不在的语言中的这些术语 （主要域实体） 可以在不同的绑定上下文中具有不同的名称，即使不同域实体共享相同的标识 (即，用于从存储读取实体的唯一 ID)。 例如，在用户配置文件绑定上下文中，用户域实体可能共享标识与排序的绑定上下文中的购买域实体。

Microservice 因此类似界定的上下文，但它还指定它是一分布式的服务。 创建作为单独的进程的每个绑定的上下文，并且它必须使用前文所述，像 HTTP/HTTPS，Websocket，这样的分布式的协议或[AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)。 绑定上下文模式，但是，未指定绑定上下文是否是分布式的服务或它是否只是一种逻辑的边界，（例如泛型的子系统） 在整体部署应用程序。

请务必突出显示，定义每个绑定上下文的服务是启动的好时机。 但不是需要约束你设计到它。 有时必须设计绑定上下文或业务微服务组成的多个物理服务。 但从根本上讲，这两种模式-绑定上下文和 microservice-密切相关。

通过获取分布式微服务的窗体中的实际边界的情况下，DDD 受益于微服务状态。 但是，例如不共享之间微服务模型的想法是您还需要的绑定上下文中。

### <a name="additional-resources"></a>其他资源

-   **Chris Richardson。模式： 数据库每个服务**
    [*http://microservices.io/patterns/data/database-per-service.html*](http://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler。BoundedContext**
    [*http://martinfowler.com/bliki/BoundedContext.html*](http://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler。PolyglotPersistence**
    [*http://martinfowler.com/bliki/PolyglotPersistence.html*](http://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini。战略的域驱动的设计与上下文映射**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[以前](微服务-architecture.md) [下一步] (逻辑-而不是-物理-architecture.md)
