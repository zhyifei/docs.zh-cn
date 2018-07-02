---
title: 设计微服务应用层和 Web API
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 设计微服务应用层和 Web API
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: e5c7e0acb0496aebce4d9cbe8cb51ced0c7166a2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106601"
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>设计微服务应用层和 Web API

## <a name="using-solid-principles-and-dependency-injection"></a>使用 SOLID 原则和依赖关系注入

SOLID 原则是应用于所有新式任务关键型应用的重要技术，例如使用 DDD 模式开发微服务。 SOLID 是五个基本原则的缩写，它们分别是：

-   单一责任原则

-   开闭原则

-   Liskov 替换原则

-   接口分隔原则

-   依赖关系反转原则

SOLID 不仅仅是关于如何设计应用程序或微服务内部层以及如何分离它们之间的依赖关系。 它与域无关，而与应用程序的技术设计相关。 最后一个原则，依赖关系反转 (DI) 原则，让使用者能够将基础结构层从其余层中分离出来，这样便能够更好地分离 DDD 层的实现。

DI 是实现依赖关系反转原则的一种方法。 它是一种用于在对象与其依赖项之间实现松散耦合的技术。 该技术不是直接实例化协作者或使用静态引用，而是向类提供（或“注入”）该类执行其操作所需的对象。 大多数情况下，类通过其构造函数声明它们的依赖项，从而允许它们遵循显式依赖关系原则。 DI 通常基于特定的控制反向 (IoC) 容器。 ASP.NET Core 提供简单的内置 IoC 容器，但也可以使用其他 IoC 容器，如 Autofac 或 Ninject。

使用 SOLID 原则，往往会获得构造良好和易于测试的小型类。 但如何知道注入类的依赖关系是否将过多？ 如果通过构造函数使用 DI，只需通过查看构造函数的参数数目便可轻松检测依赖关系的数量。 如果依赖关系过多，通常表明类需要做的工作太多（[代码异味](http://deviq.com/code-smells/)），而且可能违反了单一责任原则。

如果要深入了解 SOLID，需要参阅另一相关指南。 因此，本指南仅要求读者掌握有关这些主题的最基本的知识。

#### <a name="additional-resources"></a>其他资源

-   **SOLID: Fundamental OOP Principles**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)（SOLID：基本 OOP 原则）

-   **Inversion of Control Containers and the Dependency Injection pattern**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)（控制反转容器和依赖关系注入模式）

-   **Steve Smith.New is Glue**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)（新颖粘附）


>[!div class="step-by-step"]
[上一页](nosql-database-persistence-infrastructure.md)
[下一页](microservice-application-layer-implementation-web-api.md)
