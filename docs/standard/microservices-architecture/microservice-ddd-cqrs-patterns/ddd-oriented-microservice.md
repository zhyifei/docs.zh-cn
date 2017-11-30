---
title: "设计 DDD 面向微服务"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计 DDD 面向微服务"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df45441089fd59d5e0e52b4bcec409adcc11fb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-ddd-oriented-microservice"></a>设计 DDD 面向微服务

域驱动设计 (DDD) 律师有帮助基于商业版作为与你使用的用例的现实的建模。 在生成应用程序的上下文中，DDD 介绍为域的问题。 它描述独立问题区域作为绑定上下文 （每个绑定的上下文对应于微服务），并强调一种通用的语言来讨论的这些问题。 此外，还推荐了许多的技术概念和模式，如具有丰富的模型的域实体 (没有[贫乏域模型](https://martinfowler.com/bliki/AnemicDomainModel.html))，值对象、 聚合和聚合根 （或根实体） 规则以支持内部实现。 本部分介绍的设计和实现这些内部的模式。

有时这些 DDD 技术规则和模式被公认为有用于实现 DDD 方法陡峭学习曲线的障碍。 但重要的部分是不模式本身，但组织代码以便对齐到的业务问题，并使用相同的业务术语表示 （无处不在语言）。 此外，仅当你要实现复杂的微服务，与重要的业务规则，则应该应用 DDD 方法。 可以使用更简单的方法管理更简单的职责，与 CRUD 服务，类似。

绘制边界的位置是在设计和定义微服务时的关键任务。 DDD 模式可帮助你了解域中的复杂性。 对于每个绑定上下文的域模型，你将标识，并定义实体、 值对象和模型你的域的聚合。 生成并优化包含定义您的上下文的边界内的域模型。 这也很明确微服务的形式。 这些边界内的组件最终将你微服务，但在某些情况下，业务连续性或多个物理服务可由业务微服务组成。 有关边界是 DDD 和微服务也是如此。

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>保留 microservice 上下文边界相对较小

确定绑定的上下文之间的边界的放置位置平衡两个竞争的目标。 首先，你想要最初创建最小可能微服务，但是，不应为主要的驱动程序;你应创建周围需要内聚的内容的边界。 其次，你想要避免微服务之间的聊天式通信。 这些目标可以标相互矛盾。 应通过将系统分解成尽可能多的小微服务因为你可以直到您看到与每个再尝试进行单独的新的绑定上下文快速增长的通信边界来对它进行平衡它们。 内聚是单个的界限上下文中的密钥。

它是类似于[不适合关系密切，这样代码告知](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy)实现类时。 如果两个微服务需要大量相互配合，它们可能应该相同微服务。

另一种方法可以看到这是自治。 如果 microservice 必须依赖于其他服务进行直接为请求提供服务，它不是真正自治。

## <a name="layers-in-ddd-microservices"></a>中 DDD 微服务层

重要的业务和技术的复杂性的大多数企业应用程序由多个层定义。 层是一个逻辑的项目，并与服务的部署不相关。 它们存在可帮助开发人员管理代码中的复杂性。 （如域模型层与表示层，等等） 的不同层可能具有不同的类型，这要求这些类型之间的转换。

例如，无法从数据库加载实体。 然后该信息或聚合的信息，包括其他数据从其他实体的一部分可发送到客户端通过 REST Web API 的 UI。 此处的一点是，域实体包含在域模型层中，不应将传播到它不属于，如给表示层的其他区域。

此外，你需要始终有效的实体 (请参阅[设计域模型层中的验证](#designing-validations-in-the-domain-model-layer)部分) 由聚合根 （根实体） 控制。 因此，实体应不绑定到客户端视图，因为 UI 级别一些数据可能仍不验证。 这就是视图模型的用途。 视图模型是专用于演示文稿层所需的数据模型。 直接向视图模型不属于域实体。 相反，你需要转换 Viewmodel 和域实体之间，反之亦然。

当应对复杂性，务必要有受 （我们依次转到此更详细地更高版本），以确保所有的固定条件和规则相关的聚合根域模型，该组实体 （聚合） 将执行通过单个条目点或入口，聚合根。

图 9-5 演示如何在 eShopOnContainers 应用程序中实施一种分层的设计。

![](./media/image6.png)

**图 9-5**。 在中 eShopOnContainers 排序微服务构成的 DDD 层

你想要将系统设计，以便只与某些其他层的每一层通信。 这可能是更轻松地强制实施如果层作为不同类库实现，因为你可以明确识别哪些依赖项都设置库之间。 例如，域模型层不会花费依赖其他层上 (域模型类应为纯旧 CLR 对象，或[POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)，类)。 图 9-6 所示**Ordering.Domain**层库具有依赖关系，仅在.NET 核心库上但不是能在任何其他自定义库 （数据库、 持久性库等）。

![](./media/image7.PNG)

**图 9-6**。 层实现因为库允许更好地控制各层之间的依赖关系

### <a name="the-domain-model-layer"></a>域模型层

Eric Evans 绝佳簿[域驱动设计](http://domainlanguage.com/ddd/)显示以下消息的有关域模型层和应用程序层。

**域模型层**： 负责表示的业务、 了解业务情形和业务规则的概念。 反映业务情形的状态是控制，并使用在这里，即使将其存储的技术细节委派向基础结构。 此层是业务软件的核心。

域模型层是其中用表示业务。 当你在.NET 中实现 microservice 域模型层时，该层被编码为类库所捕获的数据以及行为 （使用逻辑的方法） 的域实体。

以下[持久性无感知](http://deviq.com/persistence-ignorance/)和[基础结构无知](https://ayende.com/blog/3137/infrastructure-ignorance)原则，此层必须完全忽略数据持久性详细信息。 由基础结构层执行这些持久性任务。 因此，此层不会花费直接的依赖关系的基础结构，这意味着重要规则不应为你的域模型实体类上[POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s。

域实体于如实体框架或 nhibernate 进行任何数据访问基础结构框架中应没有任何直接的依赖关系 （如派生自的基类）。 理想情况下，你的域实体不应派生自或实现基础结构的任何框架中定义的任何类型。

如实体框架核心的大多数现代 ORM 框架允许这种方法，以便你的域模型类未耦合到基础结构。 但是，具有 POCO 实体并不总是可能时使用某些 NoSQL 数据库和框架，如 Actors 和 Reliable Collections Azure Service Fabric 中。

请务必遵循你的域模型持久性无感知原则，即使你不应忽略持久性问题。 它仍然是非常重要，以了解物理数据模型和如何映射到您的实体对象模型。 否则，您可以创建不可能的设计。

此外，这并不意味着你可以获取一种关系数据库的模式，并直接将其移到 NoSQL 或面向文档的数据库。 在某些实体模型中，可能适合模型，但通常不能。 仍有实体模型必须遵守，基于存储技术和 ORM 技术的约束。

### <a name="the-application-layer"></a>应用程序层

继续转移到应用程序层中，我们可以再次涉及 Eric Evans 簿[域驱动设计](http://domainlanguage.com/ddd/):

**应用程序层：**定义软件为你做并指导来计算出问题的表达的域对象的作业。 此层负责任务是对业务有意义还是需要与其他系统的应用程序层之间的交互。 此层是保持精简。 它不包含业务规则或知识，但仅坐标任务和委托工作到域中的对象的下一层的协作下。 它不具有状态反映业务情形中，但它可以将反映用户或程序的任务的进度的状态。

.NET 中的微服务构成的应用程序层通常被编码为 ASP.NET 核心 Web API 项目中。 项目实现微服务的交互、 远程网络访问和 UI 或客户端应用中使用外部 Web Api。 如果使用 CQRS 方法，命令接受微服务，以及微服务 （集成事件） 之间甚至事件驱动的通信，它包括查询。 表示应用程序层 ASP.NET 核心 Web API 不能包含业务规则或域知识 （尤其是域规则为事务或更新）;这些应拥有的域模型类库。 应用程序层必须唯一坐标任务并必须不保存或定义任何域状态 （域模型）。 它将委托到的域模型类本身 （聚合根和域实体），这最终将更新这些域实体内的数据的业务规则的执行。

基本上，应用程序逻辑是其中实现依赖于给定的前端的所有用例。 例如，Web API 服务相关的实现。

目标是在域模型层、 其固定协定，数据模型和相关的业务规则的域逻辑，必须是完全独立于演示文稿和应用程序层。 最重要的是，域模型层必须不直接依赖于任何基础结构框架中。

### <a name="the-infrastructure-layer"></a>基础结构层

基础结构层是如何最初 （内存中） 的域实体中存放的数据保持在数据库或其他持久存储。 一个示例使用实体框架核心代码来实现创建的 DBContext 用于将保存在关系数据库中的数据的存储库模式类。

根据前面所述[持久性无感知](http://deviq.com/persistence-ignorance/)和[基础结构无知](https://ayende.com/blog/3137/infrastructure-ignorance)原则，基础结构层必须不"污染"域模型层。 你必须通过不在框架上会占用的硬依赖项用于将保存数据 （EF 或任何其他框架） 的基础结构保留域模型实体类不可知。 你的域模型层类库应正好有只有你的域代码， [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)实体类实现你的软件的核心和完全脱离基础结构技术。

因此，您的层或类库和项目应最终取决于你的域模型层 （库）、 反之则不然，如图 9-7 中所示。

![](./media/image8.png)

**图 9-7**。 中 DDD 层之间的依赖关系

此层设计应是独立的每个微服务。 如前文所述，你可以实现最复杂的微服务遵循 DDD 模式，同时实施更简单数据驱动微服务 (在单个层的简单 CRUD) 中更简单的方法。

#### <a name="additional-resources"></a>其他资源

-   **DevIQ。持久性无感知原则**
    [*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)

-   **Oren Eini。基础结构无知**
    [*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)

-   **天使 Lopez。分层体系结构在域驱动设计**
    [*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)


>[!div class="step-by-step"]
[以前](cqrs-microservice-reads.md) [下一步] (microservice 域 model.md)
