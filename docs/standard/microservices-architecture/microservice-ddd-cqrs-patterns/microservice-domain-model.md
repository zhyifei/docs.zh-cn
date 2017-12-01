---
title: "设计 microservice 域模型"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计 microservice 域模型"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a>设计 microservice 域模型

*定义为每个业务 microservice 或绑定上下文的一个丰富的域模型*

你的目标是创建每个业务 microservice 或绑定上下文 (BC) 的单个凝聚力域模型。 请记住，但是的业务连续性或业务 microservice 有时无法组成共享单一域模型的多个物理服务。 域模型必须捕获规则、 行为、 业务语言和单个绑定上下文或业务 microservice 它所表示的约束。

## <a name="the-domain-entity-pattern"></a>域实体模式

实体表示域对象，并由其标识、 连续性和持久性随着时间推移，以及不仅包含它们的属性主要定义。 如 Eric Evans 说:"主要由其标识定义的对象称为实体。" 实体是在域模型中中, 非常重要，因为它们是一种模型的基。 因此，你应确定并仔细设计它们。

*实体的标识可以跨多个微服务或绑定上下文。*

相同的标识 （但不相同的实体） 可以跨多个绑定的上下文或微服务建模。 但是，，并不意味着，将在多个绑定的上下文中实现相同的实体，具有相同的属性和逻辑。 相反，每个绑定的上下文中的实体限制它们的属性和行为所需的绑定上下文的域中。

例如，buyer 实体可能具有大部分中配置文件或标识微服务，包括标识中的用户实体定义的人员的属性。 但中排序微服务构成的 buyer 实体可能具有较少的属性，因为仅某些 buyer 数据与订单过程。 每个微服务构成的上下文或绑定上下文会影响其域模型。

*域实体必须实现除了实现数据属性的行为*

DDD 中的域实体必须实现的域逻辑或与实体数据 （在内存中访问的对象） 相关的行为。 例如，作为 order 实体类的一部分必须具有业务逻辑和操作作为任务，如添加顺序项、 数据验证和总计算的方法实现。 实体的方法负责的固定条件及而不是让分布在应用程序层这些规则的实体的规则。

图 9-8 显示实现不仅数据属性，但操作或具有相关的域逻辑的方法的域实体。

![](./media/image9.png)

**图 9-8**。 实现的数据以及行为域实体设计的示例

当然，有时你可以具有的未作为实体类的一部分实现的任何逻辑实体。 如果子实体没有任何特殊逻辑，因为在聚合根中定义的大部分逻辑，这可能发生在聚合子实体中。 如果你有具有大量逻辑而不是域实体中的服务类中实现的复杂微服务，你无法落到贫乏域模型中下, 一节中所述。

### <a name="rich-domain-model-versus-anemic-domain-model"></a>与贫乏域模型的丰富域模型

在他的博客文章[AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html)，Martin Fowler 描述贫乏域模型这种方式：

贫乏的域模型的基本症状是，乍一看上去像真实存在。 没有对象，许多命名的名词中的域空间中，并且这些对象已连接到的丰富关系和 true 域模型具有的结构。 在 catch 时看行为，且您实现这些对象上没有几乎任何行为稍有多个包的 getter 和 setter 使它们提出建议。

当然，当你使用贫乏域模型，这些数据模型将使用从一组的服务对象 (传统上命名*业务层*) 的捕获所有的域或业务逻辑。 业务层位于数据模型之上，并且只需将数据模型用作数据。

贫乏域模型是只是一种过程样式设计。 贫乏实体对象不是真正的对象，因为它们缺少行为 （方法）。 它们只包含数据属性，因此它不是面向对象的设计。 通过将缩小置于服务对象 （业务层） 的所有行为你实质上是最终得到[复式代码](https://en.wikipedia.org/wiki/Spaghetti_code)或[事务脚本](https://martinfowler.com/eaaCatalog/transactionScript.html)，并因此会丢失优点，域模型提供。

不论你的 microservice 或绑定上下文不非常简单 （CRUD 服务），只需数据属性的实体对象的形式贫乏域模型可能已经足够，好和可能不值得实现更复杂的 DDD 模式。 在这种情况下，它将只需持久性模型，因为您有意使用仅供 CRUD 的数据创建实体。

这是为什么微服务体系结构是特别适合于一种多体系结构方法，具体取决于每个绑定的上下文。 例如，在 eShopOnContainers，排序 microservice 实现 DDD 模式，但目录微服务，这是一个简单 CRUD 服务，不。

一些人有提示贫乏域模型是反模式。 它实际上取决于你要实现。 如果要创建 microservice 是简单足够 （例如，CRUD 服务），以下贫乏域模型中不是反模式。 但是，如果你需要为处理独特的微服务构成的域中具有大量不断变化的业务规则的复杂性，贫乏域模型可能会为该 microservice 或绑定上下文反模式。 在这种情况下，将其设计为丰富的模型包含的数据以及行为，以及实现其他 DDD 模式 （聚合、 值对象等） 的实体可能具有长期成功的微服务构成的巨大优势。

#### <a name="additional-resources"></a>其他资源

-   **DevIQ。域实体**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)

-   **Martin Fowler。域模型**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martin Fowler。贫乏域模型**

    <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>值对象模式

如 Eric Evans 已经注意到，"许多对象没有概念的标识。 这些对象描述一件事情某些的特征"。

实体需要有标识，但不是这样做，系统中有多个对象与值对象模式。 值对象是具有描述域方面没有概念标识的对象。 这些是在实例化来表示仅暂时有关你的设计元素的对象。 你关注*什么*它们是，不*人员*它们。 示例包括数字和字符串，但也可以是类似的特性组的更高级别的概念。

因为在第二个情况下，绑定上下文可能具有不同的含义，这一点微服务中的实体可能不是另一个微服务中的实体。 例如，电子商务应用程序中的地址可能没有标识，因为它也可以仅表示一组个人或公司的客户的配置文件的属性。 在这种情况下，该地址应归类为值对象。 但是，电力实用工具公司的应用程序，客户地址可能是重要的业务领域。 因此，该地址必须具有一个标识，因此计费系统可以直接链接到的地址。 在这种情况下，一个地址应归类为域实体。

具有名称和姓氏的用户通常是一个实体由于个人具有标识，即使与另一组值的名称和姓氏同时发生，例如，如果这些名称还指另一个人。

值对象难以管理中的关系数据库和 EF，如 Orm 而文档中面向它们是更轻松地实现和使用的数据库。

#### <a name="additional-resources"></a>其他资源

-   **Martin Fowler。值对象模式**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **值对象**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)

-   **值 Test-Driven 开发中的对象**
    [*https://leanpub.com/tdd-ebook/read\#leanpub 自动值对象*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans。域驱动的设计： 解决软件核心的复杂性。** （本书; 包括的值对象的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>聚合模式

域模型包含不同的数据实体和可以控制功能，如顺序执行或清单的重要区域的进程的群集。 更细粒度的 DDD 单位是聚合计算，其中介绍了的群集或组的实体和被视为凝聚力单元的行为。

通常定义基于所需的事务的聚合。 一个典型示例是也包含订单项的列表顺序。 订单项通常为实体。 但是，它将顺序聚合，还将包含作为其根实体，通常称为聚合根的订单实体中的一个子实体。

标识聚合会感到不便。 聚合是一组一起使用，必须使用相同的对象，但你无法只选择一组对象并将其标记聚合。 您必须首先域概念，考虑到这一概念相关的最常见事务中使用的实体。 需要事务上一致的那些实体是什么窗体聚合。 考虑事务操作可能是标识聚合的最佳方法。

### <a name="the-aggregate-root-or-root-entity-pattern"></a>聚合根或根实体模式

聚合组成，至少一个实体： 也称为根实体或主 ientity 的聚合根。 此外，它可具有多个子实体和值对象，包含所有实体和协同工作以便实现所需的行为和事务的对象。

聚合根的目的是确保聚合; 的一致性它应为通过方法对聚合的更新的唯一入口点，或者操作在聚合根类。 你应更改仅通过聚合根聚合内的实体。 它是聚合的一致性的保护者，考虑到所有固定条件及可能需要符合你聚合中的一致性规则。 如果更改了独立的子实体或值对象，聚合的根不能确保聚合处于有效状态。 它就好像具有松散路线的表。 维护一致性是聚合根的主要用途。

在图 9-9 中，你可以看到 buyer 聚合，其中包含单个实体 （聚合根 Buyer） 类似的示例聚合。 顺序聚合包含多个实体和值对象。

![](./media/image10.png)

**图 9-9**。 使用多个聚合函数的示例或单个实体

请注意，Buyer 聚合无法其他子实体，具体取决于你的域，eShopOnContainers 引用应用程序中排序的微服务中的一样。 图 9-9 只阐释了在其中买家单个实体，已作为示例，了解包含仅聚合根的聚合的情况。

在 DDD 域模型中不允许直接导航之间聚合并仅具有外键 (FK) 字段中，实现的一样好的做法是为了维护的聚合的分离，并保留它们间的清晰边界，请[排序 microservice 域模型](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs)eShopOnContainers 中。 订单实体只有 FK 字段 buyer，但不是 EF 核心导航属性，如下面的代码中所示：

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

标识和使用聚合需要研究和体验。 有关详细信息，请参阅以下的其他资源列表。

#### <a name="additional-resources"></a>其他资源

-   **Vaughn Vernon。有效的聚合设计的一部分： 建模单个聚合**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_社区\_论述\_聚合\_一部分\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon。有效的聚合设计的第二部分： 进行聚合工作一起**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*

-   **Vaughn Vernon。有效的聚合设计的第三部分： 深入探索通过发现**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*

-   **Sergey Grybniak。DDD 战术性设计模式**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Richardson。开发使用聚合的事务微服务**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ。聚合模式**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)


>[!div class="step-by-step"]
[以前](ddd-面向-microservice.md) [下一步] (net-核心-微服务构成的域-model.md)
