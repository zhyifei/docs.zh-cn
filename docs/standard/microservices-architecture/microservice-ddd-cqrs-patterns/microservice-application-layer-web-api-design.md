---
title: "设计微服务应用程序层和 Web API"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计微服务应用程序层和 Web API"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>设计微服务应用程序层和 Web API

## <a name="using-solid-principles-and-dependency-injection"></a>使用稳定的原则和依赖关系注入

稳定的原则是用于任何现代和任务关键型应用程序，例如开发使用 DDD 模式 microservice 的关键技术。 实体是缩写该组五个基本原则：

-   单个责任原则

-   打开/关闭原则

-   Liskov 替换原则

-   反转分隔原则

-   依赖项反向原则

实体是更多有关如何设计你的应用程序或 microservice 内部层以及分离它们之间的依赖关系。 它不与加入域，但应用程序的技术设计。 最终的原则，依赖项反向 (DI) 原则，允许你分离的其他层，它允许的更好地分离的 DDD 层实现的基础结构层。

DI 是一种方法实现的依赖项反向原则。 它是一种，这些技术可以实现对象和其依赖项之间的松散耦合。 而不是直接实例化协作者，或使用的静态引用，需要一个类，以便执行其操作的对象是提供给 （或"注入"） 的类。 大多数情况下，类将声明通过其构造函数，从而使它们可以遵循显式依赖关系原则及其依赖项。 DI 通常基于特定控制反向 (IoC) 容器。 ASP.NET Core 提供简单的内置 IoC 容器中，但你也可以使用你最喜欢的 IoC 容器，如 Autofac 或 Ninject。

按照稳定的原则，你的类将自然往往会很小，分解，且轻松地测试。 但你如何知道是否正在过多的依赖关系注入到你的类？ 如果通过构造函数使用 DI，它将轻松地检测通过只查看您的构造函数的参数的数目。 如果有依赖项太多，这通常是一个符号 ([代码告知](http://deviq.com/code-smells/)) 您的类尝试执行的操作过多，而且可能违反单独责任原则。

它将需要另一个指南详细介绍实线。 因此，本指南还要求你能够仅这些主题的最少知识。

#### <a name="additional-resources"></a>其他资源

-   **实线： 基本 OOP 原则**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **反向的控件容器和依赖关系注入模式**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith。新是粘附**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[以前](nosql-数据库-持久性-infrastructure.md) [下一步] (microservice-application-layer-implementation-web-api.md)
