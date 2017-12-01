---
title: "域事件。 设计和实现"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |域事件、 设计和实现"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2d98b302be4ee72d8225526944fc3e41cbadcb5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="domain-events-design-and-implementation"></a>域事件： 设计和实现

使用域事件显式实现你的域中的更改的副作用。 在其他字，和使用 DDD 术语中，使用域事件显式实现跨多个聚合的副作用。 （可选） 来更好的可伸缩性中数据库锁的影响更小，请使用在同一域中的聚合之间的最终一致性。

## <a name="what-is-a-domain-event"></a>什么是域事件？

事件是发生在过去的内容。 域事件，在逻辑上是，这发生在特定域中，并且你想同一个域 （进程内） 可以注意并可能做出响应的其他部分的内容。

域事件的一个重要好处是，可以显式表示后出现了问题的域中的副作用而不是隐式。 效果必须一致，因此会发生的任何相关的所有操作的业务任务，这些端或其中任何一个。 此外，域事件启用在同一域中的类之间的问题的更好的隔离。

例如，如果你只需使用实体框架和实体或甚至聚合，如果必须有导致由用例的副作用，这些将作为实现耦合的代码中的一个隐式概念后出现了问题。 但是，如果你只需查看该代码，你可能不知道如果该代码 （副作用） 是在主系统操作的一部分，或如果它确实是会产生副作用。 另一方面，如果使用域事件使这一概念显式并无处不在的语言的一部分。 例如，在 eShopOnContainers 应用程序，创建顺序是不只是关于的顺序;它更新，或创建基于原始的用户，buyer 聚合，因为直到就地没有订单后，用户不是购买者。 如果使用域事件时，你可以显式地表达无处不在提供的域专业人员的语言中基于该域规则。

域事件在某种程度上类似于消息样式事件，有一个重要的区别。 与实际的消息传送、 消息队列，消息代理或服务总线使用 AMPQ，一条消息会始终以异步方式发送，并跨进程和计算机进行通信。 这可用于将多个绑定的上下文、 微服务或甚至不同的应用程序集成。 但是，使用域事件，你想要从当前正在运行，域操作中引发事件，但你想在同一个域内任何副作用。

域事件和其副作用 （操作之后触发管理的事件处理程序） 应几乎会立即发生，通常在进程，并在同一域中。 因此，域事件可以同步或异步。 集成事件，但是，应始终是异步的。

## <a name="domain-events-versus-integration-events"></a>与集成事件域事件

在语义上，域和集成事件是相同的操作： 有关某些刚刚发生的通知。 但是，其实现必须不同。 域事件是只是消息推送到就可以实现基于 IoC 容器或任何其他方法中内存中介为域事件调度程序。

另一方面，集成事件的目的是传播已提交的事务和更新到其他子系统，无论它们是其他微服务、 绑定上下文或甚至外部应用程序。 因此，它们应仅当成功保留该实体，因为在许多情况下如果失败，整个操作有效地永远不会发生。

此外，并作为提到的那样，集成事件必须基于多个微服务 （其他绑定上下文中） 或甚至外部系统/应用程序之间进行异步通信。 因此，事件总线接口需要一些基础结构允许间进程并分发可能远程服务之间的通信。 它可以基于商业服务总线、 队列、 应用作的邮箱的共享的数据库或任何其他分发，理想情况下推基于消息的系统。

## <a name="domain-events-as-a-preferred-way-to-trigger-side-effects-across-multiple-aggregates-within-the-same-domain"></a>在同一域中的多个聚合跨触发副作用的首选方法作为域事件

如果执行命令与一个聚合实例需要在一个或多个其他聚合上运行的其他域规则，你应设计和实现由域事件触发这些副作用。 如图所示在图 9-14，以及为管理员的最重要用例，应使用域事件通过相同的域模型中的多个聚合传播状态更改。

![](./media/image15.png)

**图 9-14**。 若要强制在同一域中的多个聚合之间的一致性的域事件

在图中，当用户启动顺序，OrderStarted 域事件会触发 Buyer 对象中排序 microservice，基于标识微服务构成从原始的用户信息 （与 CreateOrder 命令中提供的信息） 创建。 创建第一个位置时，将通过顺序聚合生成域事件。

或者，你可以引发其聚合 （子实体） 的成员的事件订阅的聚合根。 例如，每个 OrderItem 子实体可以引发事件时项目价格高于特定量，或产品项目金额过高时。 然后，聚合根可以接收这些事件，并执行全局计算或聚合。

务必了解此基于事件的通信不直接在聚合; 内实现你需要实现域事件处理程序。 处理域事件是，一个应用程序的问题。 域模型层应只需关注的域逻辑-域专家理解的方面，不应用程序基础结构使用存储库的副作用的持久性操作处理程序等。 因此，应用程序层级别是其中应具有域事件处理程序引发域事件时触发的操作。

域事件还可用于触发任意数量的应用程序操作，并且更重要，必须打开要分离的方式提高该数字在将来。 例如，当启动顺序时，你可能想要发布的域事件传播到其他聚合该信息，或甚至以引发通知之类的应用程序操作。

关键在于打开域事件发生时要执行的操作的数量。 最后，将增长的操作和中的域和应用程序的规则。 复杂性或多个副作用的操作发生一些事情时将变大，但如果你的代码已结合"粘附"(即，只需实例化对象与在 C 中的新关键字\#)，然后，每次您需要添加新操作时你将需要更改的原始代码。 因为与每个新的需求，你将需要更改原始代码流，这将导致新 bug 中。 这有违[打开/关闭原则](https://en.wikipedia.org/wiki/Open/closed_principle)从[纯色](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))。 不仅如此，已安排操作原始类将增加和增长，这有违[单个责任原则 (SRP)](https://en.wikipedia.org/wiki/Single_responsibility_principle)。

另一方面，如果你使用域事件，你可以通过将隔开职责使用此方法创建细粒度的并且分离实现：

1.  发送一条命令 (例如，CreateOrder)。
2.  命令处理程序中接收命令。
    -   执行单个聚合的事务。
    -   （可选）引发副作用 (例如，OrderStartedDomainDvent) 的域事件。
1.  句柄域 （在当前进程中） 的事件 thast 会在多个聚合或应用程序操作中执行的打开副作用数目。 例如: 
    -   验证或创建购买者和付款方法。
    -   创建并将相关的集成事件发送到事件总线通过向买家发送一封电子邮件之类的微服务或触发器外部操作传播状态。
    -   处理其他副作用。

如所示图 9-15，从同一域事件中，你可以处理与其他域或你需要执行跨微服务使用集成事件和事件总线连接的其他应用程序操作中的聚合相关的多个操作。

![](./media/image16.png)

**图 9-15**。 处理每个域的多个操作

事件处理程序通常是在应用程序层中，因为你将使用基础结构对象，如存储库或应用程序 API 微服务的行为。 这种意义上，事件处理程序类似于命令处理程序，因此两者都在应用程序层的一部分。 重要的区别是，应只需一次处理多个命令。 域事件可能处理零或 *n* 超时，因为如果可由多个接收方或具有每个处理程序不同的用途的事件处理程序接收。

打开每个域事件处理程序数的可能性，可添加许多其他域规则而不会影响你当前的代码。 例如，实现必须发生的事件之后的右侧的以下业务规则可以是简单地添加几个事件处理程序 （或即使只是一个）：

当跨任意数量的订单，通过存储中的客户购买的总金额超过 6000 美元时，适用于每个新的订单的 10%的折扣并通知该折扣将来订单有关的电子邮件的客户。

## <a name="implementing-domain-events"></a>实现域事件

在 C# 中，域事件只是数据保持的结构或类，如 DTO，与所有相关发生在域中，如下面的示例中所示：

```csharp
public class OrderStartedDomainEvent : IAsyncNotification
{
    public int CardTypeId { get; private set; }
    public string CardNumber { get; private set; }
    public string CardSecurityNumber { get; private set; }
    public string CardHolderName { get; private set; }
    public DateTime CardExpiration { get; private set; }
    public Order Order { get; private set; }

    public OrderStartedDomainEvent(Order order,
        int cardTypeId, string cardNumber,
        string cardSecurityNumber, string cardHolderName,
        DateTime cardExpiration)
    {
        Order = order;
        CardTypeId = cardTypeId;
        CardNumber = cardNumber;
        CardSecurityNumber = cardSecurityNumber;
        CardHolderName = cardHolderName;
        CardExpiration = cardExpiration;
    }
}
```

这是实质上是一个包含与 OrderStarted 事件相关的所有数据的类。

根据无处不在域的语言，因为事件是指发生在过去，事件的类名称应表示为过去时谓词，如 OrderStartedDomainEvent 或 OrderShippedDomainEvent。 这是如何在中 eShopOnContainers 排序微服务中实现域事件。

我们前面提到，事件的一个重要特性是由于事件是发生在过去，它不应更改的内容。 因此，它必须是一个不可变的类。 你可以看到在上面的属性是只读的从外部对象的代码。 在创建事件对象时，可以更新的对象的唯一方法是通过构造函数。

### <a name="raising-domain-events"></a>引发域事件

下一个问题是如何引发域的事件，因此它达到其相关的事件处理程序。 你可以使用多个方法。

Udi Dahan 最初建议 (例如，在多个相关文章，如[域事件 – 执行 2](http://udidahan.com/2008/08/25/domain-events-take-2/)) 用于管理和引发事件的静态类。 这可能包括名为 DomainEvents 将域时引发事件立即调用该实例，使用 DomainEvents.Raise (事件 myEvent) 类似的语法的静态类。 Jimmy Bogard 编写博客文章 ([增强你的域： 域事件](https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/)) 建议类似的方法。

但是，如果域事件类是静态的它还将调度给处理程序立即。 这使得测试和调试更加困难，因为引发该事件后立即执行负面影响逻辑的事件处理程序。 当你测试和调试时，你想专注于并仅发生了什么情况中当前聚合类;您不想要突然重定向到其他事件处理程序与其他聚合或应用程序逻辑相关的副作用。 这就是原因已演变其他方法，如在下一部分中所述。

#### <a name="the-deferred-approach-for-raising-and-dispatching-events"></a>引发和调度事件延迟的方法

更好的方法是将域事件添加到集合而不是立即调度给域事件处理程序，然后调度这些域事件*靠右侧*或*右* *后*（与 EF 中的 SaveChanges) 提交事务。 (这种方法中此文章 Jimmy Bogard 所述[更好的域事件模式](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)。)

决定你是否将域事件发送后提交事务之前或向右立即很重要，因为它将确定是否将作为同一事务的或在不同事务中的一部分包括副作用。 在后一种情况，你需要跨多个聚合处理最终一致性。 本主题将在下一部分中讨论。

延迟的方法是何种 eShopOnContainers 使用。 首先，你添加到集合或列表的每个实体的事件实体中发生的事件。 该列表应为属于实体对象，或甚至更好地，基实体类的一部分，如下面的示例中所示：

```csharp
public abstract class Entity
{
    private List<IAsyncNotification> _domainEvents;

    public List<IAsyncNotification> DomainEvents => _domainEvents;

    public void AddDomainEvent(IAsyncNotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<IAsyncNotification>();
        _domainEvents.Add(eventItem);
    }

    public void RemoveDomainEvent(IAsyncNotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }
    // ...
}
```

如果你想要引发事件，你只需将其添加到要将放在聚合实体方法，如以下代码所示的事件集合：

```csharp
var orderStartedDomainEvent = new OrderStartedDomainEvent(this, //Order object
    cardTypeId,
    cardNumber,
    cardSecurityNumber,
    cardHolderName,
    cardExpiration);
this.AddDomainEvent(orderStartedDomainEvent);
```

请注意只能执行 AddDomainEvent 方法将事件添加到列表。 尚未，会引发任何事件，并且尚未调用任何事件处理程序。

您确实想要更高版本上调度事件，如果提交到数据库事务。 如果使用实体框架核心，这意味着你 EF DbContext，如以下代码所示的 SaveChanges 方法中：

```csharp
// EF Core DbContext
public class OrderingContext : DbContext, IUnitOfWork
{
    // ...
    public async Task<int> SaveEntitiesAsync()
    {
        // Dispatch Domain Events collection.
        // Choices:
        // A) Right BEFORE committing data (EF SaveChanges) into the DB. This makes
        // a single transaction including side effects from the domain event
        // handlers that are using the same DbContext with Scope lifetime
        // B) Right AFTER committing data (EF SaveChanges) into the DB. This makes
        // multiple transactions. You will need to handle eventual consistency and
        // compensatory actions in case of failures.
        await _mediator.DispatchDomainEventsAsync(this);
        // After this line runs, all the changes (from the Command Handler and Domain
        // event handlers) performed through the DbContext will be commited
        var result = await base.SaveChangesAsync();
    }
}
```

使用此代码中，你调度到其相应的事件处理程序的实体事件。

总结果是，你具有 （到内存中的列表添加一个简单） 域事件的引发从分离调度到事件处理程序。 此外，具体取决于你使用哪种类型的调度程序，你无法调度事件，同步或异步。

请注意这里扮演进入重要的事务边界。 如果你的工作和事务的单元可以跨多个聚合 （如使用 EF 核心应用程序和关系数据库时），这可以很好地。 但是，如果事务不能跨越聚合，例如，当你将使用 Azure DocumentDB 等 NoSQL 数据库，你必须以实现额外的步骤，以实现一致性。 这是为什么持久性无感知不是通用; 的另一个原因它依赖于您使用的存储系统。

### <a name="single-transaction-across-aggregates-versus-eventual-consistency-across-aggregates"></a>与跨聚合的最终一致性的聚合在单个事务

这一问题是否与依赖于最终一致性跨这些聚合的聚合跨执行单个事务是一个很有争议。 许多 DDD 作者像 Eric Evans 和 Vaughn Vernon 提倡规则该一个事务 = 一个聚合，因此在聚合对象需要考虑最终一致性。 例如，在书籍*Domain-Driven 设计*，Eric Evans 的说明如下：

跨越聚合任何规则不将需要在任何时候都保持最新。 通过事件处理、 批处理或其他更新机制，其他依赖关系可以在某些特定的时间内进行解析。 (pg。 128)

Vaughn Vernon 显示以下消息的中[有效的聚合设计。第二部分： 进行聚合工作一起](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf):

因此，如果其中一个聚合实例需要更多的业务规则执行上一个或多个聚合上执行命令，使用最终一致性\[...\]没有切实可行的方法，以支持 DDD 模型中的最终一致性。 聚合方法发布时间传递到一个或多个异步订阅服务器的域事件。

持有这种观点基于接纳细化事务而不是跨越多个聚合或实体的事务。 思路是在第二种情况，数据库锁的数目将是大量在大型应用程序具有高可伸缩性的需要。 使用高可扩展的应用程序需要具有多个聚合之间的即时事务一致性事实帮助接受最终一致性的概念。 原子更改通常不需要由业务，而它在任何情况下是域专家说或不特定操作是否需要原子事务的责任。 如果操作始终需要多个聚合之间原子事务，可能会要求你聚合是否应为更大或不正确设计。

但是，其他开发人员和架构师如 Jimmy Bogard 被认为可以跨多个聚合跨越单个事务，但仅当这些其他的聚合相关的同一个原始命令的副作用。 例如，在[更好的域事件模式](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)，Bogard 的说明如下：

通常情况下，我想域事件发生在相同的逻辑事务，但不是一定引发域事件的相同作用域中的副作用\[...\]我们只需提交我们事务之前，我们将调度我们事件写入其各自的处理程序。

如果调度域事件右*之前*提交原来的事务，这是因为你想要在同一事务中包括这些事件的副作用。 例如，如果 EF DbContext SaveChanges 方法失败，事务将回滚所有更改，包括由相关的域事件处理程序实现任何副作用操作的结果。 这是因为 DbContext 生命作用域是默认情况下定义为"作用域。" 因此，DbContext 对象被共享跨多个存储库对象进行实例化，在同一作用域或对象图中。 这与一致的 HttpRequest 作用域开发 Web API 或 MVC 的应用时。

实际上，这两种方法 （单个原子事务和最终一致性） 可以是右。 它实际上取决域或业务要求以及什么域专家告诉你。 它还取决于需要要进行的服务的方式可缩放 （更精细的事务的影响较小方面数据库锁）。 它依赖于多少投资您愿意为使在代码中，因为最终一致性需要更复杂的代码，以便在聚合和需要实现补偿性操作检测可能不一致。 考虑到原始的聚合，以及之后，当正在调度事件提交更改，如果没有问题并且事件处理程序无法提交其副作用，则将必须聚合之间的不一致。

若要允许补偿性操作的方式可以是事务的要在其他数据库表中存储域事件，因此它们可以是事务的原来的一部分。 然后，你可以检测到不一致和聚合的当前状态的事件的列表进行比较运行补偿性操作的批处理。 补偿性操作属于复杂的主题，它将需要从你端，其中包括讨论与业务用户和域专家的深入分析。

在任何情况下，你可以选择所需的方法。 但初始延迟方法-在提交之前，引发事件，因此使用单个事务-使用 EF 核心应用程序和关系数据库时，是最简单的方法。 它是更加轻松地实现，在许多业务案例中有效。 它也是在中 eShopOnContainers 排序微服务中使用的方法。

但如何执行你实际调度这些事件，以便将其各自的事件处理程序？ 什么是\_你在前面的示例中看到的中介对象？ 具有要使用的技术和可以使用事件和其事件处理程序之间进行映射的项目执行的操作。

### <a name="the-domain-event-dispatcher-mapping-from-events-to-event-handlers"></a>域事件调度程序： 从事件映射到事件处理程序

能够调度或发布事件后，你将需要某种类型的项目，以便每个相关的处理程序可以获取和进程副作用根据该事件将发布事件。

一种方法是实际消息系统或甚至是事件总线，可以基于服务总线而不是内存中的事件。 但是，对于第一种情况，实际消息可能不太适用处理域事件，因为你只需处理这些事件在同一进程内的 (即，在相同的域和应用程序层内)。

若要将事件映射到多个事件处理程序的另一种方法是使用 IoC 容器中的类型注册，以便你可以动态推导出调度事件的位置。 换而言之，你需要知道需要获取特定事件的事件处理程序。 图 9-16 显示，简化的方法。

![](./media/image17.png)

**图 9-16**。 域事件调度程序使用 IoC

你可以构建所有联结和要实现该方法通过自己项目。 但是，你还可以使用可用的库，如[MediatR](https://github.com/jbogard/MediatR)，实际上使用 IoT 容器。 因此，可以直接使用预定义的接口和中介对象的发布/调度方法。

在代码中，你首先需要注册事件处理程序类型在 IoC 容器，如下面的示例中所示：

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        // Other registrations ...
        // Register the DomainEventHandler classes (they implement
        // IAsyncNotificationHandler<>) in assembly holding the Domain Events
        builder.RegisterAssemblyTypes(
            typeof(ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler)
            .GetTypeInfo().Assembly)
            .Where(t => t.IsClosedTypeOf(typeof(IAsyncNotificationHandler<>)))
            .AsImplementedInterfaces();
        // Other registrations ...
    }
}
```

代码首先标识包含域事件处理程序通过查找程序集包含任何处理程序的程序集 （使用 typeof(ValidateOrAddBuyerAggregateWhenXxxx)，但你可能已选择任何其他事件处理程序来查找程序集）。 由于所有事件处理程序都实现 IAsyncNotificationHandler 接口，然后，此代码只是搜索这些类型，注册的所有事件处理程序。

### <a name="how-to-subscribe-to-domain-events"></a>如何订阅域事件

当你使用 MediatR 时，每个事件处理程序必须使用对 IAsyncNotificationHandler 接口的泛型参数提供的事件类型，如你所见下面的代码中：

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
  : IAsyncNotificationHandler<OrderStartedDomainEvent>
```

基于事件和事件处理程序，可被视为订阅，之间的关系 MediatR 项目可以发现每个事件的所有事件处理程序并触发每个这些事件处理程序。

### <a name="how-to-handle-domain-events"></a>如何处理域事件

最后，事件处理程序通常实现使用基础结构存储库，以获取所需的其他聚合并执行负面影响域逻辑的应用程序层代码。 以下代码显示一个示例。

```csharp
public class ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler
    : IAsyncNotificationHandler<OrderStartedDomainEvent>
{
    private readonly ILoggerFactory _logger;
    private readonly IBuyerRepository<Buyer> _buyerRepository;
    private readonly IIdentityService _identityService;
    public ValidateOrAddBuyerAggregateWhenOrderStartedDomainEventHandler(
        ILoggerFactory logger,
        IBuyerRepository<Buyer> buyerRepository,
        IIdentityService identityService)
    {
        // Parameter validations
        //...
    }

    public async Task Handle(OrderStartedDomainEvent orderStartedEvent)
    {
        var cardTypeId = (orderStartedEvent.CardTypeId != 0) ?
            orderStartedEvent.CardTypeId : 1;
        var userGuid = _identityService.GetUserIdentity();
        var buyer = await _buyerRepository.FindAsync(userGuid);
        bool buyerOriginallyExisted = (buyer == null) ? false : true;
        if (!buyerOriginallyExisted)
        {
            buyer = new Buyer(userGuid);
        }
        buyer.VerifyOrAddPaymentMethod(cardTypeId,
            $"Payment Method on {DateTime.UtcNow}",
            orderStartedEvent.CardNumber,
            orderStartedEvent.CardSecurityNumber,
            orderStartedEvent.CardHolderName,
            orderStartedEvent.CardExpiration,
            orderStartedEvent.Order.Id);
        var buyerUpdated = buyerOriginallyExisted ? _buyerRepository.Update(buyer) :
        _buyerRepository.Add(buyer);
        await _buyerRepository.UnitOfWork.SaveEntitiesAsync();
        // Logging code using buyerUpdated info, etc.
    }
}
```

此事件处理程序代码则被视为应用程序层代码因为它使用基础结构存储库下, 一节中所述基础结构持久性层上。 事件处理程序还可以使用其他基础结构组件。

#### <a name="domain-events-can-generate-integration-events-to-be-published-outside-of-the-microservice-boundaries"></a>域事件可以生成要在 microservice 边界之外发布的集成事件

最后，务必提及，你有时想要在多个微服务之间传播事件。 认为集成事件，并可通过从任何特定域事件处理程序的事件总线发布它。

## <a name="conclusions-on-domain-events"></a>结论域事件 

如所述，使用域事件显式实现你的域中的更改的副作用。 若要使用 DDD 术语，用于域事件显式实现副作用跨一个或多个聚合。 此外，和的更好的可伸缩性和有关数据库的锁的影响更小使用在同一域中的聚合之间的最终一致性。

#### <a name="additional-resources"></a>其他资源

-   **Greg Young。什么是域事件？** 
     [ *http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/*](http://codebetter.com/gregyoung/2010/04/11/what-is-a-domain-event/)

-   **年 1 月 Stenberg。域事件和最终一致性**
    [*https://www.infoq.com/news/2015/09/domain-events-consistency*](https://www.infoq.com/news/2015/09/domain-events-consistency)

-   **Jimmy Bogard。更好的域事件模式**
    [*https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/*](https://lostechies.com/jimmybogard/2014/05/13/a-better-domain-events-pattern/)

-   **Vaughn Vernon。有效聚合设计第 II 部分： 进行聚合在一起工作**
    [*http://dddcommunity.org/wp-content/uploads/files/pdf\_文章/Vernon\_2011\_2.pdf*](http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf)

-   **Jimmy Bogard。增强你的域： 域事件**
    *<https://lostechies.com/jimmybogard/2010/04/08/strengthening-your-domain-domain-events/>*

-   **Tony Truong。域事件模式示例**
    [*http://www.tonytruong.net/domain-events-pattern-example/*](http://www.tonytruong.net/domain-events-pattern-example/)

-   **Udi Dahan。如何创建完全封装域模型**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)

-   **Udi Dahan。域事件 – 执行 2**
    [*http://udidahan.com/2008/08/25/domain-events-take-2/*](http://udidahan.com/2008/08/25/domain-events-take-2/%20)

-   **Udi Dahan。域事件 – Salvation**
    [*http://udidahan.com/2009/06/14/domain-events-salvation/*](http://udidahan.com/2009/06/14/domain-events-salvation/)

-   **年 1 月 Kronquist。不发布域的事件，将它们返回 ！** 
     [ *https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/*](https://blog.jayway.com/2013/06/20/dont-publish-domain-events-return-them/)

-   **Cesar de la Torre。域事件 vs。DDD 和微服务体系结构中的集成事件**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/02/07/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/)


>[!div class="step-by-step"]
[以前](客户端-端-validation.md) [下一步] (基础结构的持久性-层-design.md)
