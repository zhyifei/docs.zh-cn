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
# <a name="subscribing-to-events"></a><span data-ttu-id="4a73f-104">订阅事件</span><span class="sxs-lookup"><span data-stu-id="4a73f-104">Subscribing to events</span></span>

<span data-ttu-id="4a73f-105">使用事件总线的第一步是订阅他们想要接收的事件微服务。</span><span class="sxs-lookup"><span data-stu-id="4a73f-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="4a73f-106">应该在接收方微服务来完成。</span><span class="sxs-lookup"><span data-stu-id="4a73f-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="4a73f-107">下面的简单代码显示每个接收方 microservice 需要实现启动服务时 （即，在启动类） 以便它所订阅的事件它需要。</span><span class="sxs-lookup"><span data-stu-id="4a73f-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the Startup class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="4a73f-108">例如，basket.api microservice 需要订阅 ProductPriceChangedIntegrationEvent 消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-108">For instance, the basket.api microservice needs to subscribe to ProductPriceChangedIntegrationEvent messages.</span></span> <span data-ttu-id="4a73f-109">这对产品价格进行 microservice 了解的任何更改，并允许它则在用户的购物篮中是该产品的情况下发出警告的更改的相关用户。</span><span class="sxs-lookup"><span data-stu-id="4a73f-109">This makes the microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

<span data-ttu-id="4a73f-110">此代码运行后，订阅服务器微服务将侦听通过 RabbitMQ 通道中。</span><span class="sxs-lookup"><span data-stu-id="4a73f-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="4a73f-111">当类型 ProductPriceChangedIntegrationEvent 的任何消息到达时，则代码将调用的事件处理程序传递给它并处理该事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="4a73f-112">通过事件总线发布事件</span><span class="sxs-lookup"><span data-stu-id="4a73f-112">Publishing events through the event bus</span></span>

<span data-ttu-id="4a73f-113">最后，消息发送方 (原点 microservice) 发布具有类似于下面的示例代码的集成事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="4a73f-114">（这是不会考虑在内的原子性的简化的示例。）每当必须跨多个微服务，在提交的数据或从原点 microservice 事务后通常右传播事件时，将实现类似的代码。</span><span class="sxs-lookup"><span data-stu-id="4a73f-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="4a73f-115">首先，将在控制器构造函数，如以下代码所示插入事件总线实现对象 （基于 RabbitMQ 或基于服务总线）：</span><span class="sxs-lookup"><span data-stu-id="4a73f-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="4a73f-116">然后你将其用于从控制器的方法，如 UpdateProduct 方法：</span><span class="sxs-lookup"><span data-stu-id="4a73f-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="4a73f-117">在这种情况下，由于源 microservice 是简单 CRUD 微服务，该代码位于右转变为 Web API 控制器。</span><span class="sxs-lookup"><span data-stu-id="4a73f-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> <span data-ttu-id="4a73f-118">在更高级的微服务，它无法实现在 CommandHandler 类中，右提交的原始数据后。</span><span class="sxs-lookup"><span data-stu-id="4a73f-118">In more advanced microservices, it could be implemented in the CommandHandler class, right after the original data is committed.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="4a73f-119">发布到事件总线时设计原子性和复原能力</span><span class="sxs-lookup"><span data-stu-id="4a73f-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="4a73f-120">发布通过分布式消息传递集成事件时系统喜欢事件 bus，你可以以原子方式更新原始数据库和发布事件的问题。</span><span class="sxs-lookup"><span data-stu-id="4a73f-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="4a73f-121">例如，在前面所示简化示例中，代码提交数据到数据库时产品价格已更改，然后发布 ProductPriceChangedIntegrationEvent 消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="4a73f-122">最初，可能看起来基本以原子方式执行这两个操作。</span><span class="sxs-lookup"><span data-stu-id="4a73f-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="4a73f-123">但是，如果你使用分布式的事务涉及数据库和消息代理，如在较旧的系统，如[Microsoft 消息队列 (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)，不推荐针对所描述的原因，这[CAP 定理](https://www.quora.com/What-Is-CAP-Theorem-1)。</span><span class="sxs-lookup"><span data-stu-id="4a73f-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="4a73f-124">基本上，你可以使用微服务来生成可缩放且高度可用的系统。</span><span class="sxs-lookup"><span data-stu-id="4a73f-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="4a73f-125">CAP 定理简化某种程度上，指出无法生成数据库 （或拥有其模型 microservice） 持续可用、 坚实的一致性，*和*允许的任何分区。</span><span class="sxs-lookup"><span data-stu-id="4a73f-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="4a73f-126">你必须选择两个这三个属性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="4a73f-127">中基于微服务的体系结构，应选择可用性和容错能力，并应降低强一致性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="4a73f-128">因此，在大多数现代基于微服务构成的应用程序，你通常不希望使用消息传送中的分布式的事务实现时那样[分布式事务](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c)基于 Windows 的分布式事务协调器 (DTC) 与使用[MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a73f-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="4a73f-129">让我们回到初始问题和其示例。</span><span class="sxs-lookup"><span data-stu-id="4a73f-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="4a73f-130">如果在服务崩溃后更新数据库 (在这种情况下，使用代码的行后右键\_上下文。SaveChangesAsync())，但在集成事件发布之前，总体系统可能会变得不一致。</span><span class="sxs-lookup"><span data-stu-id="4a73f-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="4a73f-131">这可能是业务非常重要，具体取决于你处理的特定业务操作。</span><span class="sxs-lookup"><span data-stu-id="4a73f-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="4a73f-132">如前文所体系结构节中，你可以通过几种方法可以处理此问题：</span><span class="sxs-lookup"><span data-stu-id="4a73f-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="4a73f-133">使用完整[事件来源模式](https://msdn.microsoft.com/en-us/library/dn589792.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a73f-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="4a73f-134">使用[事务日志挖掘](http://www.scoop.it/t/sql-server-transaction-log-mining)。</span><span class="sxs-lookup"><span data-stu-id="4a73f-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="4a73f-135">使用[发件箱模式](http://gistlabs.com/2014/05/the-outbox/)。</span><span class="sxs-lookup"><span data-stu-id="4a73f-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="4a73f-136">这是用于存储 （扩展本地事务） 的集成事件的事务表。</span><span class="sxs-lookup"><span data-stu-id="4a73f-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="4a73f-137">对于此方案中，使用完整的事件来源 (ES) 模式是之一的最佳方法，如果不最佳。</span><span class="sxs-lookup"><span data-stu-id="4a73f-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="4a73f-138">但是，在许多应用程序方案中，你可能不能实现完整的 ES 系统。</span><span class="sxs-lookup"><span data-stu-id="4a73f-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="4a73f-139">ES 意味着将仅域事件存储在事务数据库中，而不是存储当前状态数据。</span><span class="sxs-lookup"><span data-stu-id="4a73f-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="4a73f-140">存储仅域事件可能会很多好处，例如具有你可用的系统的历史记录，并且能够在过去任意时间点确定你的系统的状态。</span><span class="sxs-lookup"><span data-stu-id="4a73f-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="4a73f-141">但是，实现完整的 ES 系统需要构建你的系统的大部分并且引入了许多其他复杂性和要求。</span><span class="sxs-lookup"><span data-stu-id="4a73f-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="4a73f-142">例如，你想要使用数据库专门所做的事件来源，如[事件存储](https://geteventstore.com/)，或如 Azure Cosmos DB、 MongoDB、 Cassandra、 CouchDB 或 RavenDB 面向文档的数据库。</span><span class="sxs-lookup"><span data-stu-id="4a73f-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="4a73f-143">ES 是非常好的方法，此问题，但不是最简单的解决方案，除非你已熟悉事件来源。</span><span class="sxs-lookup"><span data-stu-id="4a73f-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="4a73f-144">使用最初挖掘的事务日志的选项看起来非常透明。</span><span class="sxs-lookup"><span data-stu-id="4a73f-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="4a73f-145">但是，若要使用此方法，microservice 程序耦合到你 RDBMS 的事务日志，如 SQL Server 事务日志。</span><span class="sxs-lookup"><span data-stu-id="4a73f-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="4a73f-146">这可能是不可取。</span><span class="sxs-lookup"><span data-stu-id="4a73f-146">This is probably not desirable.</span></span> <span data-ttu-id="4a73f-147">另一个缺点是在与高级集成事件相同的级别可能不是在事务日志中记录的低级别更新。</span><span class="sxs-lookup"><span data-stu-id="4a73f-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="4a73f-148">如果是这样，反向工程处理的过程这些事务日志操作可能很困难。</span><span class="sxs-lookup"><span data-stu-id="4a73f-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="4a73f-149">平衡的方法是事务的数据库表和简化的 ES 模式的组合。</span><span class="sxs-lookup"><span data-stu-id="4a73f-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="4a73f-150">你可以使用如"已准备好发布事件，"在原始事件时将其提交到集成事件表中设置的状态。</span><span class="sxs-lookup"><span data-stu-id="4a73f-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="4a73f-151">然后尝试将事件发布到事件总线。</span><span class="sxs-lookup"><span data-stu-id="4a73f-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="4a73f-152">如果发布事件操作成功，你在 origin 服务中启动另一个事务，并将状态从"准备好发布事件"移到"事件已发布"。</span><span class="sxs-lookup"><span data-stu-id="4a73f-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="4a73f-153">如果发布事件操作在事件总线失败，数据仍将不会原点 microservice 内不一致-它仍标记为"已准备好发布事件，"，针对服务的其余部分，它最终将一致。</span><span class="sxs-lookup"><span data-stu-id="4a73f-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="4a73f-154">你始终可以检查事务或集成事件的状态的后台作业。</span><span class="sxs-lookup"><span data-stu-id="4a73f-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="4a73f-155">如果作业中的"准备好发布事件"状态中查找事件，它可以尝试重新发布到事件总线该事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="4a73f-156">请注意，使用此方法，保存在你想要与其他微服务或外部系统通信的事件和仅每个源 microservice，集成事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="4a73f-157">与此相反，在完整 ES 系统中，您存储所有域事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="4a73f-158">因此，此平衡的方法是一个简化的 ES 系统。</span><span class="sxs-lookup"><span data-stu-id="4a73f-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="4a73f-159">你需要使用其当前状态的集成事件的列表 （"准备发布"与"发布"）。</span><span class="sxs-lookup"><span data-stu-id="4a73f-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="4a73f-160">但你只需以实现集成事件这些状态。</span><span class="sxs-lookup"><span data-stu-id="4a73f-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="4a73f-161">并在此方法中，你不必将所有域数据都存储为事件在事务的数据库中，就像在完整的 ES 系统。</span><span class="sxs-lookup"><span data-stu-id="4a73f-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="4a73f-162">如果你已使用关系数据库，可以使用事务的表来存储集成事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="4a73f-163">若要实现应用程序中的原子性，你可以使用两步骤过程基于本地事务。</span><span class="sxs-lookup"><span data-stu-id="4a73f-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="4a73f-164">基本上，你必须域实体位于同一数据库中有一个 IntegrationEvent 表。</span><span class="sxs-lookup"><span data-stu-id="4a73f-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="4a73f-165">该表的工作与实现原子性，使你包含的保险保存到同一个事务正在提交你的域数据集成事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="4a73f-166">这个过程步骤，可以如下： 应用程序开始一个本地数据库事务。</span><span class="sxs-lookup"><span data-stu-id="4a73f-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="4a73f-167">然后，将更新你的域实体的状态，并将事件插入到集成事件表。</span><span class="sxs-lookup"><span data-stu-id="4a73f-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="4a73f-168">最后，它会将提交事务。</span><span class="sxs-lookup"><span data-stu-id="4a73f-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="4a73f-169">获取所需的原子性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-169">You get the desired atomicity.</span></span>

<span data-ttu-id="4a73f-170">在实现时发布事件的步骤，你可选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="4a73f-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="4a73f-171">提交事务后立即发布集成事件并使用另一个本地事务将标记与正在发布的表中的事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="4a73f-172">然后，就像项目中使用表来跟踪远程微服务，在问题发生的集成事件并执行基于存储的集成事件的补偿性操作。</span><span class="sxs-lookup"><span data-stu-id="4a73f-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="4a73f-173">表可以用作一种类型的队列。</span><span class="sxs-lookup"><span data-stu-id="4a73f-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="4a73f-174">单独的应用程序线程或进程查询集成事件表，将事件发布到事件总线，然后使用本地事务将事件标记为已发布。</span><span class="sxs-lookup"><span data-stu-id="4a73f-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="4a73f-175">图 8-22 显示这些方法的第一个体系结构。</span><span class="sxs-lookup"><span data-stu-id="4a73f-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="4a73f-176">**图 8-22**。</span><span class="sxs-lookup"><span data-stu-id="4a73f-176">**Figure 8-22**.</span></span> <span data-ttu-id="4a73f-177">在将事件发布到事件总线原子性</span><span class="sxs-lookup"><span data-stu-id="4a73f-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="4a73f-178">阐释图 8-22 的方法缺少都负责检查和确认的已发布的集成事件成功附加辅助进程微服务。</span><span class="sxs-lookup"><span data-stu-id="4a73f-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="4a73f-179">如果出现故障，该检查器中其他辅助微服务可以从表读取事件，并重新发布它们。</span><span class="sxs-lookup"><span data-stu-id="4a73f-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="4a73f-180">有关第二种方法： 使用事件日志表作为队列和始终使用辅助微服务来发布消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="4a73f-181">在这种情况下，该过程是类似的显示图 8-23。</span><span class="sxs-lookup"><span data-stu-id="4a73f-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="4a73f-182">下面的示例演示其他的微服务，并且表比较的单个来源，发布事件时。</span><span class="sxs-lookup"><span data-stu-id="4a73f-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="4a73f-183">**图 8-23**。</span><span class="sxs-lookup"><span data-stu-id="4a73f-183">**Figure 8-23**.</span></span> <span data-ttu-id="4a73f-184">在将事件发布到与辅助 microservice 事件总线原子性</span><span class="sxs-lookup"><span data-stu-id="4a73f-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="4a73f-185">为简单起见，eShopOnContainers 示例加事件总线上使用 （没有其他进程或检查器微服务） 的第一种方法。</span><span class="sxs-lookup"><span data-stu-id="4a73f-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="4a73f-186">但是，eShopOnContainers 不处理所有可能的失败情况。</span><span class="sxs-lookup"><span data-stu-id="4a73f-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="4a73f-187">在实际的应用程序部署到云，你必须接受最终，将出现问题，则必须实现，检查和重新发送逻辑的事实。</span><span class="sxs-lookup"><span data-stu-id="4a73f-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="4a73f-188">如果你有该表作为单个源的事件的事件总线通过发布它们时，使用作为队列的表可能会比第一种方法更有效。</span><span class="sxs-lookup"><span data-stu-id="4a73f-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="4a73f-189">发布通过事件总线集成事件时实现原子性</span><span class="sxs-lookup"><span data-stu-id="4a73f-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="4a73f-190">下面的代码演示如何创建一个事务涉及多个 DbContext 对象 — 一个与正在更新的原始数据相关的上下文和 IntegrationEventLog 表相关的第二个上下文。</span><span class="sxs-lookup"><span data-stu-id="4a73f-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="4a73f-191">请注意，下面的示例代码中的事务将不会有弹性，如果连接到数据库时运行代码时有任何问题。</span><span class="sxs-lookup"><span data-stu-id="4a73f-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="4a73f-192">这会在基于云的系统，如 Azure SQL DB，可能会在服务器之间移动数据库。</span><span class="sxs-lookup"><span data-stu-id="4a73f-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="4a73f-193">有关跨多个上下文中实现弹性事务，请参阅[实现弹性 Entity Framework 核心 SQL 连接](#implementing_resilient_EFCore_SQL_conns)在本指南后面的部分。</span><span class="sxs-lookup"><span data-stu-id="4a73f-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="4a73f-194">为清楚起见，下面的示例演示在一段单独的代码中的整个过程。</span><span class="sxs-lookup"><span data-stu-id="4a73f-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="4a73f-195">但是，eShopOnContainers 实现实际重构，并将此逻辑拆分为多个类，因此很易于维护。</span><span class="sxs-lookup"><span data-stu-id="4a73f-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

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

<span data-ttu-id="4a73f-196">创建 ProductPriceChangedIntegrationEvent 集成事件后，将存储原始域操作 （更新的目录项） 的事务事件日志表中还包括事件的持久性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="4a73f-197">这样，可以单个事务，而且你将始终能够检查是否已发送事件消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="4a73f-198">使用原始数据库操作时，使用针对该数据库的本地事务以原子方式更新事件日志表。</span><span class="sxs-lookup"><span data-stu-id="4a73f-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="4a73f-199">如果任一操作失败，将引发异常，并且事务能够回滚任何已完成的操作，因此维护域操作和发送的事件消息之间的一致性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="4a73f-200">从订阅接收消息： 在接收方微服务中的事件处理程序</span><span class="sxs-lookup"><span data-stu-id="4a73f-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="4a73f-201">除了事件订阅逻辑，你需要实现 （如回调方法） 的集成事件处理程序的内部代码。</span><span class="sxs-lookup"><span data-stu-id="4a73f-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="4a73f-202">事件处理程序可以指定将接收和处理特定类型的事件消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="4a73f-203">事件处理程序首先从事件总线接收事件实例。</span><span class="sxs-lookup"><span data-stu-id="4a73f-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="4a73f-204">然后它将定位要处理的组件与该集成事件，传播和在接收方微服务的状态的更改作为保持事件相关。</span><span class="sxs-lookup"><span data-stu-id="4a73f-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="4a73f-205">例如，如果 ProductPriceChanged 事件起源于目录微服务，它在购物篮微服务中处理，并更改以及，此接收方购物篮微服务中的状态，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4a73f-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="4a73f-206">事件处理程序需要验证中的任何购物篮实例是否存在产品。</span><span class="sxs-lookup"><span data-stu-id="4a73f-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="4a73f-207">它还会更新每个相关的购物篮行项的项价格。</span><span class="sxs-lookup"><span data-stu-id="4a73f-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="4a73f-208">最后，它会创建警报以指示要显示给用户有关此价格更改，请在图 8-24 中所示。</span><span class="sxs-lookup"><span data-stu-id="4a73f-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="4a73f-209">**图 8-24**。</span><span class="sxs-lookup"><span data-stu-id="4a73f-209">**Figure 8-24**.</span></span> <span data-ttu-id="4a73f-210">通过集成事件进行通信时，显示在购物篮中项价格更改</span><span class="sxs-lookup"><span data-stu-id="4a73f-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="4a73f-211">更新消息事件中的幂等性</span><span class="sxs-lookup"><span data-stu-id="4a73f-211">Idempotency in update message events</span></span>

<span data-ttu-id="4a73f-212">更新消息事件的一个重要方面是在通信中的任何位置的失败会导致重试的消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="4a73f-213">否则后台任务可能会尝试发布已发布，创建了争用条件的事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="4a73f-214">你需要确保更新是幂等或它们提供足够的信息来确保你可以检测到有重复，放弃它，并发送回只有一个响应。</span><span class="sxs-lookup"><span data-stu-id="4a73f-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="4a73f-215">如前文所述，幂等性意味着操作可以执行多次而无需更改结果。</span><span class="sxs-lookup"><span data-stu-id="4a73f-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="4a73f-216">在消息传递环境中，如当通讯事件，事件是幂等的如果就可以将它传递多次而无需更改接收方微服务构成的结果。</span><span class="sxs-lookup"><span data-stu-id="4a73f-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="4a73f-217">这可能是必要的事件本身，性质，因此，或由于系统处理事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="4a73f-218">在使用消息传递任何应用程序，而不仅仅是在应用程序中实现事件总线模式重要消息幂等性。</span><span class="sxs-lookup"><span data-stu-id="4a73f-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="4a73f-219">幂等操作的示例是将数据插入到表中，仅当该数据已不在表中的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="4a73f-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="4a73f-220">它并不重要多少次你运行插入 SQL 语句;结果将是相同-表将包含该数据。</span><span class="sxs-lookup"><span data-stu-id="4a73f-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="4a73f-221">如果可能无法发送消息处理消息时的需要和因此处理的超过一次，也可以是幂等性如下。</span><span class="sxs-lookup"><span data-stu-id="4a73f-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="4a73f-222">例如，如果重试逻辑导致发件人将完全相同的消息发送多次，你需要确保它是幂等。</span><span class="sxs-lookup"><span data-stu-id="4a73f-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="4a73f-223">很可能设计幂等消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="4a73f-224">例如，可以创建事件，指出"设置为产品价格\$25"而不是"添加\$5 到产品价格。"</span><span class="sxs-lookup"><span data-stu-id="4a73f-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="4a73f-225">你无法安全地处理第一条消息任意次数，结果将相同。</span><span class="sxs-lookup"><span data-stu-id="4a73f-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="4a73f-226">不适用于第二条消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-226">That is not true for the second message.</span></span> <span data-ttu-id="4a73f-227">但是，即使在第一种情况，你可能不想处理的第一个事件，因为系统无法也发送的较新的价格更改事件，并且你将覆盖新价格。</span><span class="sxs-lookup"><span data-stu-id="4a73f-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="4a73f-228">另一个示例可能是未传播至多个订阅服务器的顺序完成事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="4a73f-229">很重要，订单信息更新在其他系统中只需一次，即使没有为相同的顺序完成事件重复的消息事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="4a73f-230">它很方便地具有某种类型的每个事件的标识，以便您可以创建强制实施的接收方每一次处理每个事件的逻辑。</span><span class="sxs-lookup"><span data-stu-id="4a73f-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="4a73f-231">某些消息处理本质上是幂等。</span><span class="sxs-lookup"><span data-stu-id="4a73f-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="4a73f-232">例如，如果系统生成的缩略图，也不可能会影响此多少次处理有关生成缩略图的消息;结果是生成缩略图，并且它们基本相同，每次。</span><span class="sxs-lookup"><span data-stu-id="4a73f-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="4a73f-233">另一方面，例如在调用支付网关，要收取信用卡号的操作可能不在所有是幂等。</span><span class="sxs-lookup"><span data-stu-id="4a73f-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="4a73f-234">在这些情况下，你需要确保处理多次的消息具有预期的效果。</span><span class="sxs-lookup"><span data-stu-id="4a73f-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4a73f-235">其他资源</span><span class="sxs-lookup"><span data-stu-id="4a73f-235">Additional resources</span></span>

-   <span data-ttu-id="4a73f-236">**遵循消息幂等性**（在此页上的副标题） [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a73f-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="4a73f-237">消除重复集成事件消息</span><span class="sxs-lookup"><span data-stu-id="4a73f-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="4a73f-238">你可以确保发送和每个不同级别的订阅服务器只需一次处理的消息事件。</span><span class="sxs-lookup"><span data-stu-id="4a73f-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="4a73f-239">一种方法是使用提供的使用消息传递基础结构的重复数据删除功能。</span><span class="sxs-lookup"><span data-stu-id="4a73f-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="4a73f-240">另一种是在目标微服务中实现自定义逻辑。</span><span class="sxs-lookup"><span data-stu-id="4a73f-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="4a73f-241">在传输级别和应用程序级别具有验证是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="4a73f-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="4a73f-242">消除重复消息 EventHandler 级事件</span><span class="sxs-lookup"><span data-stu-id="4a73f-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="4a73f-243">请确保将由任何接收方只需一次处理事件的一种方法是通过实现某些逻辑处理事件处理程序中的消息事件时。</span><span class="sxs-lookup"><span data-stu-id="4a73f-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="4a73f-244">例如，这是 eShopOnContainers 应用程序中使用的方法在中可以看到[源代码](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs)OrdersController 类在接收 CreateOrderCommand 命令时。</span><span class="sxs-lookup"><span data-stu-id="4a73f-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="4a73f-245">（在这种情况下，我们使用的 HTTP 请求命令，而不是基于消息的命令，但你需要进行基于消息的命令幂等的逻辑是类似。）</span><span class="sxs-lookup"><span data-stu-id="4a73f-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="4a73f-246">消除重复的消息时使用 RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="4a73f-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="4a73f-247">间歇性网络故障发生时，可以重复消息，并且消息接收方必须准备好以处理这些重复的消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="4a73f-248">如果可能，接收方应处理以幂等方式，即显式使用重复数据删除处理它们更好的消息。</span><span class="sxs-lookup"><span data-stu-id="4a73f-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="4a73f-249">根据[RabbitMQ 文档](https://www.rabbitmq.com/reliability.html#consumer)，"如果一条消息是发送到使用者，然后重新排队，（因为它无法确认之前使用者断开连接，例如） 则 RabbitMQ 将对设置重新发送的标志它是否为同一使用者或另一个） 再次传递时。</span><span class="sxs-lookup"><span data-stu-id="4a73f-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="4a73f-250">如果已设置的"重新发送"标志，接收方必须考虑的帐户，因为消息可能已处理。</span><span class="sxs-lookup"><span data-stu-id="4a73f-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="4a73f-251">但是，不能保证;消息可能永远不会已达到接收方后它保持消息代理中，可能是由于网络问题。</span><span class="sxs-lookup"><span data-stu-id="4a73f-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="4a73f-252">另一方面，如果未设置"重新发送"标志，因而可以保证，消息未发送一次以上。</span><span class="sxs-lookup"><span data-stu-id="4a73f-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="4a73f-253">因此，接收方需要进行重复数据删除以幂等方式处理消息仅当"重新发送"标志设置消息中。</span><span class="sxs-lookup"><span data-stu-id="4a73f-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4a73f-254">其他资源</span><span class="sxs-lookup"><span data-stu-id="4a73f-254">Additional resources</span></span>

-   <span data-ttu-id="4a73f-255">**事件驱动的消息传送**
    [*http://soapatterns.org/design\_模式/事件\_驱动\_消息传送*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="4a73f-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="4a73f-256">**Jimmy Bogard。重构入恢复能力： 评估耦合**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="4a73f-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="4a73f-257">**发布-订阅通道**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="4a73f-257">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="4a73f-258">**之间的通信绑定上下文**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a73f-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="4a73f-259">**最终一致性**
    [*https://en.wikipedia.org/wiki/Eventual\_一致性*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="4a73f-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="4a73f-260">**Philip 部分。集成的策略限制上下文**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="4a73f-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="4a73f-261">**Chris Richardson。开发使用聚合、 事件来源和 CQRS-第 2 部分的事务微服务**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="4a73f-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="4a73f-262">**Chris Richardson。事件采购模式**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="4a73f-262">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="4a73f-263">**引入了事件来源**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a73f-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="4a73f-264">**事件存储数据库**。</span><span class="sxs-lookup"><span data-stu-id="4a73f-264">**Event Store database**.</span></span> <span data-ttu-id="4a73f-265">官方网站。</span><span class="sxs-lookup"><span data-stu-id="4a73f-265">Official site.</span></span>
    [<span data-ttu-id="4a73f-266">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="4a73f-266">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="4a73f-267">**Patrick Nommensen。事件驱动的微服务的数据管理**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*</span><span class="sxs-lookup"><span data-stu-id="4a73f-267">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="4a73f-268">**CAP 定理**
    [*https://en.wikipedia.org/wiki/CAP\_定理*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="4a73f-268">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="4a73f-269">**什么是 CAP 定理？** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="4a73f-269">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="4a73f-270">**数据一致性入门**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a73f-270">**Data Consistency Primer**
[*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="4a73f-271">**Rick Saling。CAP 定理中： 原因"的所有内容原样不同"云和 Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="4a73f-271">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="4a73f-272">**Eric Brewer。CAP 十二年更高版本： 如何更改了"规则"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="4a73f-272">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="4a73f-273">**参与外部 (DTC) 事务**(MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="4a73f-273">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="4a73f-274">**Azure Service Bus。中转消息传送： 重复检测**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="4a73f-274">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="4a73f-275">**可靠性指南**（RabbitMQ 文档） [ *https://www.rabbitmq.com/reliability.html\#使用者*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="4a73f-275">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="4a73f-276">[以前](rabbitmq-event-bus-development-test-environment.md) [下一步] (test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4a73f-276">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
