---
title: "应用中的微服务构成的简化的 CQRS 和 DDD 模式"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |应用中的微服务构成的简化的 CQRS 和 DDD 模式"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 99fd7ce32039742e23f8e01aa4c33cddd7a9f698
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>应用中的微服务构成的简化的 CQRS 和 DDD 模式

CQRS 是分隔用于读取和写入数据的模型的体系结构模式。 相关的术语[命令查询分离 (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html)书籍最初定义通过 Bertrand Meyer*对象面向软件构造*。 基本理念都是你可以将划分为两个清晰地分隔类别的系统的操作：

-   查询。 这些返回结果，不会更改系统的状态，并且它们是免费的副作用。

-   命令。 这些更改系统的状态。

CQS 是一个简单的概念-即将中同一对象的方法正在查询或命令。 每个方法返回状态，或时会改变状态，但不是两个。 CQS 可以符合甚至单个存储库模式对象。 CQS 可考虑的基本原则 CQRS。

[命令和查询责任分离 (CQRS)](https://martinfowler.com/bliki/CQRS.html)已引入了 Greg Young 又强提升 Udi Dahan 和其他用户。 尽管更详细，它基于 CQS 原则。 它可被视为基于对命令和事件以及 （可选） 在异步消息模式。 在许多情况下，CQRS 与更高级的方案，如具有不同的物理数据库，从而可以读取 （查询） 比为写入操作 （更新）。 此外，多系统要求的 CQRS 系统可能会实现[事件来源 (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)更新数据库，因此你将仅将事件存储在域模型中而不是存储的当前状态数据。 但是，这不是使用此指南; 中的方法我们正在使用的最简单的 CQRS 方法，其中包括只需将查询与命令区分开来。

CQRS 分离方面被通过分组一个层中的查询操作和另一个层中的命令。 每一层具有其自己的数据模型 （请注意，我们实质模型，不一定是不同的数据库），并使用其自己的模式和技术的组合进行构建。 更重要的是，有两个层可以在同一层或 microservice，如下所示 （排序微服务） 的示例用于本指南中。 或，以便它们可以优化和向外扩展单独而不会影响另一个无法在不同的微服务或进程上实现它们。

CQRS 是指存在两个对象的读/写操作，在其他上下文中还有一个。 没有具有非规范化的读取数据库，你可以在更高级的 CQRS 文献中了解有关的原因。 但我们不使用这种方法在这里，其目标在查询而不是限制的约束从类聚合 DDD 模式的查询具有更大的灵活性。

此类服务的一个示例是排序的微服务构成从 eShopOnContainers 引用应用程序。 此服务实现基于简化 CQRS 方法微服务。 它使用单个数据源或数据库，但两个逻辑模型以及 DDD 模式的事务的域，如图 9-2 中所示。

![](./media/image2.png)

**图 9-2**。 简化基于 CQRS 和 DDD 的微服务

应用程序层可以为 Web API 本身。 此处的重要设计方面是查询和 Viewmodel （尤其是创建客户端应用程序的数据模型），有了拆分微服务构成从命令、 域模型中和以下 CQRS 模式的事务。 此方法保留查询独立于限制和约束来自 DDD 模式仅用于事务和更新，有意义，更高版本的部分中所述。


>[!div class="step-by-step"]
[以前](index.md) [下一步] (eshoponcontainers-cqrs-ddd-microservice.md)
