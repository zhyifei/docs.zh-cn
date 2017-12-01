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
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>EShopOnContainers DDD 微服务中的应用 CQRS 和 CQS 方法

在 eShopOnContainers 引用应用程序排序微服务构成的设计基于 CQRS 原则。 但是，它使用的最简单的方法，只需将查询与命令分离并使用相同的数据进行这两种操作。

这些模式，并在这里，重要的一点的本质就是，查询也是幂等的： 无论多少次查询一个系统，该系统的状态将不会更改，你甚至可以使用不同的"读取"比"写入"的事务逻辑数据模型域模型，尽管排序微服务正在使用相同的数据库。 因此，这是简化的 CQRS 方法。

另一方面，命令，触发事务和数据更新，在系统中更改状态。 你需要使用命令，请注意与复杂性和不断变化的业务规则。 这就是你想要应用 DDD 技术能够更好地建模的系统。

本指南中讲述的 DDD 模式应不会全局应用。 它们引入你的设计的约束。 这些约束随着时间推移，特别是在命令和其他修改系统状态的代码提供的好处，例如更高的质量。 但是，这些约束添加较少的优势，用于读取和查询数据的复杂性。

这种模式之一是聚合模式，我们在后面几节中更检查。 简要，在聚合模式中，你将多个域对象作为单个单元由于在域中的关系。 你可能不始终获得从查询; 在此模式的优点它可以增加查询逻辑的复杂性。 对于只读查询，未得到的将多个对象视为单个聚合的优势。 你只能获取复杂性。

如所示图 9-2，本指南建议仅在你的 microservice 事务性/更新区域中使用 DDD 模式 （即，因为命令由触发）。 查询可以遵循更简单的方法，并应分开后面 CQRS 方法的命令。

用于实现"查询端"，你可以选择多种方法，从你全面 ORM EF 核心、 AutoMapper 投影、 存储的过程、 视图、 具体化的视图或微型 ORM 等。

本指南中和在 eShopOnContainers （专门排序微服务），我们选择实现直接查询使用 micro ORM 如[Dapper](https://github.com/StackExchange/dapper-dot-net)。 这样可以实现基于 SQL 语句，以获取最佳性能，使用极小的开销浅色 framework 感谢任何查询。

请注意，当你使用此方法时，与你的模型影响如何将实体保存到 SQL 数据库的任何更新也需要 to SQL 查询使用 Dapper 或查询到的任何其他单独的 (非 EF) 方法的单独更新。

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>CQRS 和 DDD 模式不是顶级体系结构

你必须知道该 CQRS 和 （如 DDD 层或具有聚合的域模型） 的大多数 DDD 模式不是体系结构风格，而是仅体系结构模式。 微服务、 SOA 和事件驱动体系结构 (EDA) 是体系结构风格的示例。 许多组件，如许多微服务将系统描述它们。 在单个系统或组件; 内的 CQRS 和 DDD 模式描述的内容在此情况下，内容在微服务。

不同的绑定上下文 (BCs) 将采用不同的模式。 它们都有不同的责任，并且这产生了不同的解决方案。 值得重视的强制 everywhere 会导致失败的相同模式。 无处不在不使用 CQRS 和 DDD 模式。 许多子系统、 BCs 或微服务选项要更为简单，并可以更轻松地使用简单 CRUD 服务或使用另一种方法实现。

没有只有一个应用程序体系结构： 你设计 （例如微服务体系结构） 的系统或端到端应用程序的体系结构。 但是，每个绑定的上下文或该应用程序中的微服务的设计反映其自己的折衷方案和体系结构模式级别的内部设计决策。 不要尝试将相同的体系结构模式如 CQRS 或 DDD 无处不在。

####  <a name="additional-resources"></a>其他资源

-   **Martin Fowler。CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young。CQS vs。CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young。CQRS 文档**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young。CQRS，任务基于的 Ui 和事件来源**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **Udi Dahan。阐明了 CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **事件来源 (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[以前](apply-simplified-microservice-cqrs-ddd-patterns.md) [下一步] (cqrs microservice reads.md)
