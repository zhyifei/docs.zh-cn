---
title: "设计基础结构持久性层"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计基础结构持久性层"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a>设计基础结构持久性层

数据持久性组件提供对托管微服务 （即，微服务构成的数据库） 的边界内的数据访问。 它们包含的组件，如存储库的实际实现和[工作单元](http://martinfowler.com/eaaCatalog/unitOfWork.html)类，如自定义 EF Dbcontext。

## <a name="the-repository-pattern"></a>存储库模式

存储库类或组件，用于封装各种访问数据源所需的逻辑。 它们集中处理通用数据访问功能，提供更好的可维护性和分离的基础结构或用来从域模型层访问数据库技术。 如果你使用如实体框架 ORM，则必须实现的代码被简化，感谢 LINQ 和强类型化。 这允许您将精力集中在数据持久性逻辑上，而不是在数据访问管道。

存储库模式是使用与数据源的完备的方法。 书中[模式的企业应用程序体系结构](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/)，Martin Fowler 描述存储库，如下所示：

存储库执行的任务之间的域模型层和数据映射到内存中的域对象的一组类似的方式中起作用的媒介。 客户端对象以声明方式生成查询，并将其发送给答案的存储库。 从概念上讲，一个存储库中封装一组对象存储在数据库中，可以对它们，执行提供更接近于持久性层一种方法的操作。 存储库，此外，支持将分离开来，明确并按一个方向工作域和数据分配之间的依赖关系或映射的用途。

### <a name="define-one-repository-per-aggregate"></a>定义每个聚合的一个存储库

对于每个聚合或聚合的根，您应该创建一个存储库类。 在基于域驱动的设计模式微服务，应使用以更新数据库的唯一通道应存储库。 这是因为它们具有与聚合根域，它控制聚合的固定条件及事务一致性一对一的关系。 可以通过其他数据库中查询通道 （如你可以执行以下 CQRS 方法），因为查询不会更改数据库的状态。 但是，事务区域-更新-必须始终控制存储库和聚合根。

基本上，一个存储库，可填充来自的域实体的窗体中的数据库的内存中的数据。 在内存中的实体后，可以更改以及然后将其保存回通过事务的数据库。

如前所述，如果你使用 CQS/CQRS 体系结构模式，将由域模型中，执行简单的 SQL 语句，使用 Dapper 外侧查询执行的初始查询。 这种方法是更多，你需要比存储库灵活因为您可以查询和联接任何表，并且这些查询不会限制由规则聚合。 该数据将转到演示文稿层或客户端应用程序。

如果用户进行更改，要更新的数据将来自客户端应用程序或演示文稿层到应用程序层 （如 Web API 服务）。 当命令处理程序中收到 （具有数据） 的命令时，请使用存储库来获取你想要从数据库进行更新的数据。 你在内存中与使用命令，传递的信息进行更新，然后添加或更新事务通过数据库中的数据 （域实体）。

我们必须强调再次的是，应为每个聚合根定义仅一个存储库，在图 9-17 中所示。 若要实现的聚合根的目标为维护聚合内的所有对象之间的事务一致性，应永远不会在数据库中创建的每个表的存储库。

![](./media/image18.png)

**图 9-17**。 存储库、 聚合和数据库表之间的关系

### <a name="enforcing-one-aggregate-root-per-repository"></a>强制实施每个存储库的一个聚合根

可以是很有价值实现存储库设计的方式，它会强制实施仅聚合根应具有存储库的规则。 你可以创建泛型数据或基数据存储库类型约束与配合工作以确保其具有 IAggregateRoot 标记接口的实体的类型。

因此，在基础结构层实现每个存储库类实现其自己的协定或接口，如下面的代码中所示：

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

每个特定的存储库接口实现的泛型 IRepository 接口：

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

但是，更好的方法让代码强制实施约定每个存储库应与单个聚合可以实现泛型存储库类型，因此很显式使用的存储库的目的面向特定的聚合。 可以通过实现该泛型 IRepository 基接口，如以下代码所示中轻松地完成：

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>存储库模式，更便于测试应用程序逻辑

存储库模式，你可以轻松地具有单元测试中测试你的应用程序。 请记住，单元测试仅测试你的代码、 非基础结构，因此存储库抽象更加轻松地实现该目标。

如前面部分所述，建议你定义，并放置的存储库接口在域模型层中以便应用程序层 (例如，Web API microservice) 不直接依赖基础结构层中必须使用实现的实际存储库类。 通过执行此操作，并在你的 Web api 控制器中使用依赖关系注入，你可以实现模拟从数据库返回假数据而不是数据的存储库。 去耦的方法允许你创建和运行的单元测试，可以测试只是你的应用程序的逻辑，而无需连接到数据库。

连接到数据库可能会失败，并更重要的是，针对数据库运行数百个测试是错误的两个原因。 首先，因为大量测试可能需要大量时间。 其次，数据库记录可能会更改，并影响你测试的结果，以便它们可能不一致。 针对数据库的测试不是单元测试集成测试。 你应多个单元测试运行速度快，而较少的集成测试对数据库。

方面的单元测试的关注点分离，你的逻辑在内存中的域实体进行操作。 它假定存储库类传递那些。 一旦你的逻辑修改域实体，该示例假定存储库类将正确存储它们。 重要的一点是创建针对您的域模型和其域逻辑单元测试。 聚合根是 DDD 中的主要一致性边界。

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>存储库模式和旧的数据访问类 （DAL 类） 模式之间的差异

数据访问对象直接执行了针对存储的数据访问和持久性操作。 将不会立即执行与你想要在单元的工作对象 （如所示 EF 使用 DbContext 时)，但这些更新内存中执行的操作数据存储库标记。

工作单元被称之为作为单个事务涉及多个插入、 更新或删除操作。 简单地说，这意味着，对于特定的用户操作 （例如，在网站上的注册），所有插入、 更新和删除事务在都处理单个事务中。 这是比 chattier 方式处理多个数据库事务更高效。

应用程序层中的代码命令它时，将更高版本在单个操作中执行这些多个持久性操作。 将内存中更改应用于实际的数据库存储的决定通常基于[单元的工作模式](http://martinfowler.com/eaaCatalog/unitOfWork.html)。 在 EF，作为 DBContext 实现单元的工作模式。

在许多情况下，此模式或将应用对存储操作的方式可以提高应用程序性能并降低出现不一致的可能性。 此外，它减少了事务阻止在数据库表中，因为所有预期的操作是作为一个事务的一部分提交。 这是与执行对数据库的多个独立的操作相比更高效。 因此，所选的 ORM 将能够通过对同一事务，而不是许多小型和单独的事务执行中的多个更新操作进行分组来优化对数据库执行。

### <a name="repositories-should-not-be-mandatory"></a>存储库不应为必填

自定义存储库可用于更早版本，提到的原因，这是在 eShopOnContainers 排序微服务构成的方法。 但是，它不是在 DDD 设计中实现，甚至在一般情况下开发.NET 中的基本模式。

例如，Jimmy Bogard，本指南提供直接反馈时称以下：

这可能会我最大的反馈。 我实际上不风扇的存储库，主要是因为它们会隐藏基础持久性机制的重要详细信息。 它的为什么我转 MediatR 命令，请过。 我可以使用持久性层的完整功能，并将所有该域行为推送到我的聚合根。 我通常不想模拟我的存储库 – 我仍需要该集成测试与真实存在。 转 CQRS 意味着，我们实际上没有存储库需要更。

我们发现存储库有用，但我们确认它们并不是你 DDD 中的聚合模式和丰富的域模型的方式。 因此，或不使用的存储库模式，如上所示符合。

#### <a name="additional-resources"></a>其他资源

##### <a name="the-repository-pattern"></a>存储库模式

-   **Edward Hieatt 和 Rob me。存储库模式。** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)

-   **存储库模式**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)

-   **存储库模式： 数据持久性抽象**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)

-   **Eric Evans。域驱动的设计： 解决软件核心的复杂性。** （本书; 包括的存储库模式的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

##### <a name="unit-of-work-pattern"></a>单元的工作模式

-   **Martin Fowler。单元的工作模式。** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)

<!-- -->

-   **在 ASP.NET MVC 应用程序中实现的存储库和单元的工作模式**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)


>[!div class="step-by-step"]
[以前](域的事件的设计-implementation.md) [下一步] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
