---
title: "订阅事件"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |订阅事件"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a>订阅事件

使用事件总线的第一步是订阅他们想要接收的事件微服务。 应该在接收方微服务来完成。

下面的简单代码显示每个接收方 microservice 需要实现启动服务时 （即，在启动类） 以便它所订阅的事件它需要。 例如，basket.api microservice 需要订阅 ProductPriceChangedIntegrationEvent 消息。 这对产品价格进行 microservice 了解的任何更改，并允许它则在用户的购物篮中是该产品的情况下发出警告的更改的相关用户。

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

此代码运行后，订阅服务器微服务将侦听通过 RabbitMQ 通道中。 当类型 ProductPriceChangedIntegrationEvent 的任何消息到达时，则代码将调用的事件处理程序传递给它并处理该事件。

## <a name="publishing-events-through-the-event-bus"></a>通过事件总线发布事件

最后，消息发送方 (原点 microservice) 发布具有类似于下面的示例代码的集成事件。 （这是不会考虑在内的原子性的简化的示例。）每当必须跨多个微服务，在提交的数据或从原点 microservice 事务后通常右传播事件时，将实现类似的代码。

首先，将在控制器构造函数，如以下代码所示插入事件总线实现对象 （基于 RabbitMQ 或基于服务总线）：

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

然后你将其用于从控制器的方法，如 UpdateProduct 方法：

```csharp
[Route("update")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

在这种情况下，由于源 microservice 是简单 CRUD 微服务，该代码位于右转变为 Web API 控制器。 在更高级的微服务，它无法实现在 CommandHandler 类中，右提交的原始数据后。

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>发布到事件总线时设计原子性和复原能力

发布通过分布式消息传递集成事件时系统喜欢事件 bus，你可以以原子方式更新原始数据库和发布事件的问题。 例如，在前面所示简化示例中，代码提交数据到数据库时产品价格已更改，然后发布 ProductPriceChangedIntegrationEvent 消息。 最初，可能看起来基本以原子方式执行这两个操作。 但是，如果你使用分布式的事务涉及数据库和消息代理，如在较旧的系统，如[Microsoft 消息队列 (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)，不推荐针对所描述的原因，这[CAP 定理](https://www.quora.com/What-Is-CAP-Theorem-1)。

基本上，你可以使用微服务来生成可缩放且高度可用的系统。 CAP 定理简化某种程度上，指出无法生成数据库 （或拥有其模型 microservice） 持续可用、 坚实的一致性，*和*允许的任何分区。 你必须选择两个这三个属性。

中基于微服务的体系结构，应选择可用性和容错能力，并应降低强一致性。 因此，在大多数现代基于微服务构成的应用程序，你通常不希望使用消息传送中的分布式的事务实现时那样[分布式事务](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c)基于 Windows 的分布式事务协调器 (DTC) 与使用[MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)。

让我们回到初始问题和其示例。 如果在服务崩溃后更新数据库 (在这种情况下，使用代码的行后右键\_上下文。SaveChangesAsync())，但在集成事件发布之前，总体系统可能会变得不一致。 这可能是业务非常重要，具体取决于你处理的特定业务操作。

如前文所体系结构节中，你可以通过几种方法可以处理此问题：

-   使用完整[事件来源模式](https://msdn.microsoft.com/en-us/library/dn589792.aspx)。

-   使用[事务日志挖掘](http://www.scoop.it/t/sql-server-transaction-log-mining)。

-   使用[发件箱模式](http://gistlabs.com/2014/05/the-outbox/)。 这是用于存储 （扩展本地事务） 的集成事件的事务表。

对于此方案中，使用完整的事件来源 (ES) 模式是之一的最佳方法，如果不最佳。 但是，在许多应用程序方案中，你可能不能实现完整的 ES 系统。 ES 意味着将仅域事件存储在事务数据库中，而不是存储当前状态数据。 存储仅域事件可能会很多好处，例如具有你可用的系统的历史记录，并且能够在过去任意时间点确定你的系统的状态。 但是，实现完整的 ES 系统需要构建你的系统的大部分并且引入了许多其他复杂性和要求。 例如，你想要使用数据库专门所做的事件来源，如[事件存储](https://geteventstore.com/)，或如 Azure Cosmos DB、 MongoDB、 Cassandra、 CouchDB 或 RavenDB 面向文档的数据库。 ES 是非常好的方法，此问题，但不是最简单的解决方案，除非你已熟悉事件来源。

使用最初挖掘的事务日志的选项看起来非常透明。 但是，若要使用此方法，microservice 程序耦合到你 RDBMS 的事务日志，如 SQL Server 事务日志。 这可能是不可取。 另一个缺点是在与高级集成事件相同的级别可能不是在事务日志中记录的低级别更新。 如果是这样，反向工程处理的过程这些事务日志操作可能很困难。

平衡的方法是事务的数据库表和简化的 ES 模式的组合。 你可以使用如"已准备好发布事件，"在原始事件时将其提交到集成事件表中设置的状态。 然后尝试将事件发布到事件总线。 如果发布事件操作成功，你在 origin 服务中启动另一个事务，并将状态从"准备好发布事件"移到"事件已发布"。

如果发布事件操作在事件总线失败，数据仍将不会原点 microservice 内不一致-它仍标记为"已准备好发布事件，"，针对服务的其余部分，它最终将一致。 你始终可以检查事务或集成事件的状态的后台作业。 如果作业中的"准备好发布事件"状态中查找事件，它可以尝试重新发布到事件总线该事件。

请注意，使用此方法，保存在你想要与其他微服务或外部系统通信的事件和仅每个源 microservice，集成事件。 与此相反，在完整 ES 系统中，您存储所有域事件。

因此，此平衡的方法是一个简化的 ES 系统。 你需要使用其当前状态的集成事件的列表 （"准备发布"与"发布"）。 但你只需以实现集成事件这些状态。 并在此方法中，你不必将所有域数据都存储为事件在事务的数据库中，就像在完整的 ES 系统。

如果你已使用关系数据库，可以使用事务的表来存储集成事件。 若要实现应用程序中的原子性，你可以使用两步骤过程基于本地事务。 基本上，你必须域实体位于同一数据库中有一个 IntegrationEvent 表。 该表的工作与实现原子性，使你包含的保险保存到同一个事务正在提交你的域数据集成事件。

这个过程步骤，可以如下： 应用程序开始一个本地数据库事务。 然后，将更新你的域实体的状态，并将事件插入到集成事件表。 最后，它会将提交事务。 获取所需的原子性。

在实现时发布事件的步骤，你可选择以下选项：

-   提交事务后立即发布集成事件并使用另一个本地事务将标记与正在发布的表中的事件。 然后，就像项目中使用表来跟踪远程微服务，在问题发生的集成事件并执行基于存储的集成事件的补偿性操作。

-   表可以用作一种类型的队列。 单独的应用程序线程或进程查询集成事件表，将事件发布到事件总线，然后使用本地事务将事件标记为已发布。

图 8-22 显示这些方法的第一个体系结构。

![](./media/image23.png)

**图 8-22**。 在将事件发布到事件总线原子性

阐释图 8-22 的方法缺少都负责检查和确认的已发布的集成事件成功附加辅助进程微服务。 如果出现故障，该检查器中其他辅助微服务可以从表读取事件，并重新发布它们。

有关第二种方法： 使用事件日志表作为队列和始终使用辅助微服务来发布消息。 在这种情况下，该过程是类似的显示图 8-23。 下面的示例演示其他的微服务，并且表比较的单个来源，发布事件时。

![](./media/image24.png)

**图 8-23**。 在将事件发布到与辅助 microservice 事件总线原子性

为简单起见，eShopOnContainers 示例加事件总线上使用 （没有其他进程或检查器微服务） 的第一种方法。 但是，eShopOnContainers 不处理所有可能的失败情况。 在实际的应用程序部署到云，你必须接受最终，将出现问题，则必须实现，检查和重新发送逻辑的事实。 如果你有该表作为单个源的事件的事件总线通过发布它们时，使用作为队列的表可能会比第一种方法更有效。

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>发布通过事件总线集成事件时实现原子性

下面的代码演示如何创建一个事务涉及多个 DbContext 对象 — 一个与正在更新的原始数据相关的上下文和 IntegrationEventLog 表相关的第二个上下文。

请注意，下面的示例代码中的事务将不会有弹性，如果连接到数据库时运行代码时有任何问题。 这会在基于云的系统，如 Azure SQL DB，可能会在服务器之间移动数据库。 有关跨多个上下文中实现弹性事务，请参阅[实现弹性 Entity Framework 核心 SQL 连接](#implementing_resilient_EFCore_SQL_conns)在本指南后面的部分。

为清楚起见，下面的示例演示在一段单独的代码中的整个过程。 但是，eShopOnContainers 实现实际重构，并将此逻辑拆分为多个类，因此很易于维护。

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

    if (catalogItem == null) return NotFound();

    bool raiseProductPriceChangedEvent = false;

    IntegrationEvent priceChangedEvent = null;

    if (catalogItem.Price != productToUpdate.Price)
        raiseProductPriceChangedEvent = true;

    if (raiseProductPriceChangedEvent) // Create event if price has changed
    {
        var oldPrice = catalogItem.Price;
        priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
            productToUpdate.Price,
            oldPrice);
    }

    // Update current product
    catalogItem = productToUpdate;
    // Achieving atomicity between original DB and the IntegrationEventLog
    // with a local transaction

    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);

        await _catalogContext.SaveChangesAsync();

        // Save to EventLog only if product price changed
        if(raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
   }

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

创建 ProductPriceChangedIntegrationEvent 集成事件后，将存储原始域操作 （更新的目录项） 的事务事件日志表中还包括事件的持久性。 这样，可以单个事务，而且你将始终能够检查是否已发送事件消息。

使用原始数据库操作时，使用针对该数据库的本地事务以原子方式更新事件日志表。 如果任一操作失败，将引发异常，并且事务能够回滚任何已完成的操作，因此维护域操作和发送的事件消息之间的一致性。

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>从订阅接收消息： 在接收方微服务中的事件处理程序

除了事件订阅逻辑，你需要实现 （如回调方法） 的集成事件处理程序的内部代码。 事件处理程序可以指定将接收和处理特定类型的事件消息。

事件处理程序首先从事件总线接收事件实例。 然后它将定位要处理的组件与该集成事件，传播和在接收方微服务的状态的更改作为保持事件相关。 例如，如果 ProductPriceChanged 事件起源于目录微服务，它在购物篮微服务中处理，并更改以及，此接收方购物篮微服务中的状态，如下面的代码中所示。

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

事件处理程序需要验证中的任何购物篮实例是否存在产品。 它还会更新每个相关的购物篮行项的项价格。 最后，它会创建警报以指示要显示给用户有关此价格更改，请在图 8-24 中所示。

![](./media/image25.png)

**图 8-24**。 通过集成事件进行通信时，显示在购物篮中项价格更改

## <a name="idempotency-in-update-message-events"></a>更新消息事件中的幂等性

更新消息事件的一个重要方面是在通信中的任何位置的失败会导致重试的消息。 否则后台任务可能会尝试发布已发布，创建了争用条件的事件。 你需要确保更新是幂等或它们提供足够的信息来确保你可以检测到有重复，放弃它，并发送回只有一个响应。

如前文所述，幂等性意味着操作可以执行多次而无需更改结果。 在消息传递环境中，如当通讯事件，事件是幂等的如果就可以将它传递多次而无需更改接收方微服务构成的结果。 这可能是必要的事件本身，性质，因此，或由于系统处理事件。 在使用消息传递任何应用程序，而不仅仅是在应用程序中实现事件总线模式重要消息幂等性。

幂等操作的示例是将数据插入到表中，仅当该数据已不在表中的 SQL 语句。 它并不重要多少次你运行插入 SQL 语句;结果将是相同-表将包含该数据。 如果可能无法发送消息处理消息时的需要和因此处理的超过一次，也可以是幂等性如下。 例如，如果重试逻辑导致发件人将完全相同的消息发送多次，你需要确保它是幂等。

很可能设计幂等消息。 例如，可以创建事件，指出"设置为产品价格\$25"而不是"添加\$5 到产品价格。" 你无法安全地处理第一条消息任意次数，结果将相同。 不适用于第二条消息。 但是，即使在第一种情况，你可能不想处理的第一个事件，因为系统无法也发送的较新的价格更改事件，并且你将覆盖新价格。

另一个示例可能是未传播至多个订阅服务器的顺序完成事件。 很重要，订单信息更新在其他系统中只需一次，即使没有为相同的顺序完成事件重复的消息事件。

它很方便地具有某种类型的每个事件的标识，以便您可以创建强制实施的接收方每一次处理每个事件的逻辑。

某些消息处理本质上是幂等。 例如，如果系统生成的缩略图，也不可能会影响此多少次处理有关生成缩略图的消息;结果是生成缩略图，并且它们基本相同，每次。 另一方面，例如在调用支付网关，要收取信用卡号的操作可能不在所有是幂等。 在这些情况下，你需要确保处理多次的消息具有预期的效果。

### <a name="additional-resources"></a>其他资源

-   **遵循消息幂等性**（在此页上的副标题） [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)

## <a name="deduplicating-integration-event-messages"></a>消除重复集成事件消息

你可以确保发送和每个不同级别的订阅服务器只需一次处理的消息事件。 一种方法是使用提供的使用消息传递基础结构的重复数据删除功能。 另一种是在目标微服务中实现自定义逻辑。 在传输级别和应用程序级别具有验证是最佳选择。

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>消除重复消息 EventHandler 级事件

请确保将由任何接收方只需一次处理事件的一种方法是通过实现某些逻辑处理事件处理程序中的消息事件时。 例如，这是 eShopOnContainers 应用程序中使用的方法在中可以看到[源代码](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs)OrdersController 类在接收 CreateOrderCommand 命令时。 （在这种情况下，我们使用的 HTTP 请求命令，而不是基于消息的命令，但你需要进行基于消息的命令幂等的逻辑是类似。）

### <a name="deduplicating-messages-when-using-rabbitmq"></a>消除重复的消息时使用 RabbitMQ

间歇性网络故障发生时，可以重复消息，并且消息接收方必须准备好以处理这些重复的消息。 如果可能，接收方应处理以幂等方式，即显式使用重复数据删除处理它们更好的消息。

根据[RabbitMQ 文档](https://www.rabbitmq.com/reliability.html#consumer)，"如果一条消息是发送到使用者，然后重新排队，（因为它无法确认之前使用者断开连接，例如） 则 RabbitMQ 将对设置重新发送的标志它是否为同一使用者或另一个） 再次传递时。

如果已设置的"重新发送"标志，接收方必须考虑的帐户，因为消息可能已处理。 但是，不能保证;消息可能永远不会已达到接收方后它保持消息代理中，可能是由于网络问题。 另一方面，如果未设置"重新发送"标志，因而可以保证，消息未发送一次以上。 因此，接收方需要进行重复数据删除以幂等方式处理消息仅当"重新发送"标志设置消息中。

### <a name="additional-resources"></a>其他资源

-   **事件驱动的消息传送**
    [*http://soapatterns.org/design\_模式/事件\_驱动\_消息传送*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Jimmy Bogard。重构入恢复能力： 评估耦合**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)

-   **发布-订阅通道**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **之间的通信绑定上下文**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)

-   **最终一致性**
    [*https://en.wikipedia.org/wiki/Eventual\_一致性*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Philip 部分。集成的策略限制上下文**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)

-   **Chris Richardson。开发使用聚合、 事件来源和 CQRS-第 2 部分的事务微服务**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)

-   **Chris Richardson。事件采购模式**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)

-   **引入了事件来源**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)

-   **事件存储数据库**。 官方网站。
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   **Patrick Nommensen。事件驱动的微服务的数据管理**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*

-   **CAP 定理**
    [*https://en.wikipedia.org/wiki/CAP\_定理*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **什么是 CAP 定理？** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)

-   **数据一致性入门**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)

-   **Rick Saling。CAP 定理中： 原因"的所有内容原样不同"云和 Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)

-   **Eric Brewer。CAP 十二年更高版本： 如何更改了"规则"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)

-   **参与外部 (DTC) 事务**(MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)

-   **Azure Service Bus。中转消息传送： 重复检测**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)

-   **可靠性指南**（RabbitMQ 文档） [ *https://www.rabbitmq.com/reliability.html\#使用者*](https://www.rabbitmq.com/reliability.html%23consumer)




>[!div class="step-by-step"]
[以前](rabbitmq-event-bus-development-test-environment.md) [下一步] (test-aspnet-core-services-web-apps.md)
