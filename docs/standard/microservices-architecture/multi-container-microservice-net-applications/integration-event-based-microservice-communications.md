---
title: "实现基于事件的微服务 （集成事件） 之间的通信"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现基于事件的微服务 （集成事件） 之间的通信"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e438607ab3549d63b89bef6af64c6723a4cac950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a><span data-ttu-id="e5ca6-104">实现基于事件的微服务 （集成事件） 之间的通信</span><span class="sxs-lookup"><span data-stu-id="e5ca6-104">Implementing event-based communication between microservices (integration events)</span></span>

<span data-ttu-id="e5ca6-105">如前所述，当你使用基于事件的通信时，microservice 发布发生一些值得注意的事情，例如当它更新业务实体时发生的事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-105">As described earlier, when you use event-based communication, a microservice publishes an event when something notable happens, such as when it updates a business entity.</span></span> <span data-ttu-id="e5ca6-106">其他微服务订阅这些事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-106">Other microservices subscribe to those events.</span></span> <span data-ttu-id="e5ca6-107">当 microservice 收到事件时，它可以更新其自己的业务实体，这可能会导致正在发布的详细事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-107">When a microservice receives an event, it can update its own business entities, which might lead to more events being published.</span></span> <span data-ttu-id="e5ca6-108">通过使用的事件总线实现通常执行此发布/订阅系统。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-108">This publish/subscribe system is usually performed by using an implementation of an event bus.</span></span> <span data-ttu-id="e5ca6-109">事件总线可以设计为接口中，使用订阅和取消订阅事件以及发布事件所需的 API 中。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-109">The event bus can be designed as an interface with the API needed to subscribe and unsubscribe to events and to publish events.</span></span> <span data-ttu-id="e5ca6-110">它还可以具有任何进程间或消息传送的通信，如消息传递队列或 service bus 支持异步通信和发布/订阅模型所基于的一个或多个实现。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-110">It can also have one or more implementations based on any inter-process or messaging communication, such as a messaging queue or a service bus that supports asynchronous communication and a publish/subscribe model.</span></span>

<span data-ttu-id="e5ca6-111">你可以使用事件来实现业务事务跨越多个服务，这为你提供这些服务之间的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-111">You can use events to implement business transactions that span multiple services, which gives you eventual consistency between those services.</span></span> <span data-ttu-id="e5ca6-112">最终一致事务由一系列分布式操作组成。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-112">An eventually consistent transaction consists of a series of distributed actions.</span></span> <span data-ttu-id="e5ca6-113">在每个操作，microservice 更新业务实体，并将发布触发下一步操作的事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-113">At each action, the microservice updates a business entity and publishes an event that triggers the next action.</span></span>

![](./media/image19.PNG)

<span data-ttu-id="e5ca6-114">**图 8-18**。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-114">**Figure 8-18**.</span></span> <span data-ttu-id="e5ca6-115">基于事件总线上的事件驱动的通信</span><span class="sxs-lookup"><span data-stu-id="e5ca6-115">Event-driven communication based on an event bus</span></span>

<span data-ttu-id="e5ca6-116">本部分介绍如何通过使用通用事件总线接口，如图 8-18 中所示实现这种类型的与.NET 的通信。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-116">This section describes how you can implement this type of communication with .NET by using a generic event bus interface, as shown in Figure 8-18.</span></span> <span data-ttu-id="e5ca6-117">有多个潜在的实现，每个使用不同的技术或例如 RabbitMQ、 Azure Service Bus，任何其他第三方开源或商业服务总线的基础结构。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-117">There are multiple potential implementations, each using a different technology or infrastructure such as RabbitMQ, Azure Service Bus, or any other third-party open source or commercial service bus.</span></span>

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a><span data-ttu-id="e5ca6-118">对生产系统使用消息中转站和服务总线</span><span class="sxs-lookup"><span data-stu-id="e5ca6-118">Using message brokers and services buses for production systems</span></span>

<span data-ttu-id="e5ca6-119">如体系结构节中所述，你可以从多个消息传送技术用于实现抽象事件总线中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-119">As noted in the architecture section, you can choose from multiple messaging technologies for implementing your abstract event bus.</span></span> <span data-ttu-id="e5ca6-120">但这些技术是在不同级别。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-120">But these technologies are at different levels.</span></span> <span data-ttu-id="e5ca6-121">例如，RabbitMQ，消息的 broker 传输，是在商业产品，如 Azure Service Bus、 NServiceBus、 MassTransit 或 Brighter 比较低级别。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-121">For instance, RabbitMQ, a messaging broker transport, is at a lower level than commercial products like Azure Service Bus, NServiceBus, MassTransit, or Brighter.</span></span> <span data-ttu-id="e5ca6-122">大部分这些产品可基于 RabbitMQ 或 Azure Service Bus。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-122">Most of these products can work on top of either RabbitMQ or Azure Service Bus.</span></span> <span data-ttu-id="e5ca6-123">你选择的产品取决于多少功能和多少扩展-可用的可伸缩性你需要为你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-123">Your choice of product depends on how many features and how much out-of-the-box scalability you need for your application.</span></span>

<span data-ttu-id="e5ca6-124">对于实现只需事件总线的概念证明为开发环境，如 eShopOnContainers 的示例中，在运行作为容器的 RabbitMQ 之上的简单实现可能不够。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-124">For implementing just an event bus proof-of-concept for your development environment, as in the eShopOnContainers sample, a simple implementation on top of RabbitMQ running as a container might be enough.</span></span> <span data-ttu-id="e5ca6-125">但对于任务关键型和需要高可伸缩性的生产系统，你可能想要评估，使用 Azure Service Fabric。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-125">But for mission-critical and production systems that need high scalability, you might want to evaluate and use Azure Service Fabric.</span></span> <span data-ttu-id="e5ca6-126">如果需要高级抽象，并且更丰富的功能要[sagas](https://docs.particular.net/nservicebus/sagas/)使 NServiceBus，MassTransit，类似更简单、 其他商业和开放源代码服务总线的分布式的开发的长时间运行进程和亮的值得评估。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-126">If you require high-level abstractions and richer features like [sagas](https://docs.particular.net/nservicebus/sagas/) for long-running processes that make distributed development easier, other commercial and open-source service buses like NServiceBus, MassTransit, and Brighter are worth evaluating.</span></span> <span data-ttu-id="e5ca6-127">当然，你始终可以生成自己 RabbitMQ 和 Docker，等的较低级别技术之上的服务总线功能，但需从头的工作可能会过于昂贵的自定义的企业应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-127">Of course, you could always build your own service bus features on top of lower-level technologies like RabbitMQ and Docker, but the work needed to reinvent the wheel might be too costly for a custom enterprise application.</span></span>

<span data-ttu-id="e5ca6-128">重申一遍： 示例事件总线抽象和实现在 eShopOnContainers 示例展示用于只能用作概念证明。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-128">To reiterate: the sample event bus abstractions and implementation showcased in the eShopOnContainers sample are intended to be used only as a proof of concept.</span></span> <span data-ttu-id="e5ca6-129">一旦你已决定要具有异步和事件驱动的通信，如当前节中所述，你应选择最适合你需要的服务总线产品。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-129">Once you have decided that you want to have asynchronous and event-driven communication, as explained in the current section, you should choose the service bus product that best fits your needs.</span></span>

## <a name="integration-events"></a><span data-ttu-id="e5ca6-130">集成事件</span><span class="sxs-lookup"><span data-stu-id="e5ca6-130">Integration events</span></span>

<span data-ttu-id="e5ca6-131">集成事件用于跨多个微服务或外部系统使域状态同步。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-131">Integration events are used for bringing domain state in sync across multiple microservices or external systems.</span></span> <span data-ttu-id="e5ca6-132">这可通过发布集成事件超出微服务。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-132">This is done by publishing integration events outside the microservice.</span></span> <span data-ttu-id="e5ca6-133">在事件发布到多个接收方微服务 （到尽可能多的微服务如集成事件订阅） 中每个接收方微服务构成, 的相应的事件处理程序处理事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-133">When an event is published to multiple receiver microservices (to as many microservices as are subscribed to the integration event), the appropriate event handler in each receiver microservice handles the event.</span></span>

<span data-ttu-id="e5ca6-134">集成事件基本上是数据保持类，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e5ca6-134">An integration event is basically a data-holding class, as in the following example:</span></span>

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

<span data-ttu-id="e5ca6-135">集成事件类可以是简单;例如，它可能包含其 id 的 GUID</span><span class="sxs-lookup"><span data-stu-id="e5ca6-135">The integration event class can be simple; for example, it might contain a GUID for its ID.</span></span>

<span data-ttu-id="e5ca6-136">可以在每个微服务应用程序级别定义集成事件，以便从其他微服务，方式类似于 Viewmodel 服务器和客户端中的定义方式相互脱耦。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-136">The integration events can be defined at the application level of each microservice, so they are decoupled from other microservices, in a way comparable to how ViewModels are defined in the server and client.</span></span> <span data-ttu-id="e5ca6-137">不建议跨多个微服务; 共享一个通用集成事件库执行该操作将会耦合这些微服务与单个事件定义数据库。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-137">What is not recommended is sharing a common integration events library across multiple microservices; doing that would be coupling those microservices with a single event definition data library.</span></span> <span data-ttu-id="e5ca6-138">你不想要这样做，出于相同原因，您不想要在多个微服务之间共享通用的域模型： 微服务必须是完全自治。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-138">You do not want to do that for the same reasons that you do not want to share a common domain model across multiple microservices: microservices must be completely autonomous.</span></span>

<span data-ttu-id="e5ca6-139">有仅几种您应在微服务之间共享的库。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-139">There are only a few kinds of libraries you should share across microservices.</span></span> <span data-ttu-id="e5ca6-140">其中一个是像是最终应用程序块的库[事件总线客户端 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)，如下所示 eShopOnContainers。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-140">One is libraries that are final application blocks, like the [Event Bus client API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), as in eShopOnContainers.</span></span> <span data-ttu-id="e5ca6-141">另一种是构成也无法共享为 NuGet 组件，如 JSON 序列化程序的工具的库。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-141">Another is libraries that constitute tools that could also be shared as NuGet components, like JSON serializers.</span></span>

## <a name="the-event-bus"></a><span data-ttu-id="e5ca6-142">事件总线</span><span class="sxs-lookup"><span data-stu-id="e5ca6-142">The event bus</span></span>

<span data-ttu-id="e5ca6-143">事件总线发布/订阅样式允许之间进行通信而无需显式请注意，在图 8-19 中所示的组件的微服务。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-143">An event bus allows publish/subscribe-style communication between microservices without requiring the components to explicitly be aware of each other, as shown in Figure 8-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="e5ca6-144">**图 8-19**。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-144">**Figure 8-19**.</span></span> <span data-ttu-id="e5ca6-145">发布/订阅使用事件总线基础知识</span><span class="sxs-lookup"><span data-stu-id="e5ca6-145">Publish/subscribe basics with an event bus</span></span>

<span data-ttu-id="e5ca6-146">事件总线与观察程序模式和发布-订阅模式。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-146">The event bus is related to the Observer pattern and the publish-subscribe pattern.</span></span>

### <a name="observer-pattern"></a><span data-ttu-id="e5ca6-147">观察程序模式</span><span class="sxs-lookup"><span data-stu-id="e5ca6-147">Observer pattern</span></span>

<span data-ttu-id="e5ca6-148">在[观察程序模式](https://en.wikipedia.org/wiki/Observer_pattern)，主对象 （称为可观察对象） 包含相关信息 （事件） 通知其他感的对象 （称为观察者）。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-148">In the [Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern), your primary object (known as the Observable) notifies other interested objects (known as Observers) with relevant information (events).</span></span>

### <a name="publish-subscribe-pubsub-pattern"></a><span data-ttu-id="e5ca6-149">发布-订阅 （发布/订阅） 模式</span><span class="sxs-lookup"><span data-stu-id="e5ca6-149">Publish-subscribe (Pub/Sub) pattern</span></span> 

<span data-ttu-id="e5ca6-150">用途[Pub/Sub 模式](https://msdn.microsoft.com/en-us/library/ff649664.aspx)等同于观察程序模式： 你想要在某些事件发生时通知其他服务。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-150">The purpose of the [Pub/Sub pattern](https://msdn.microsoft.com/en-us/library/ff649664.aspx) is the same as the Observer pattern: you want to notify other services when certain events take place.</span></span> <span data-ttu-id="e5ca6-151">但没有间的观察者和发布/订阅模式的语义重要差异。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-151">But there is an important semantic difference between the Observer and Pub/Sub patterns.</span></span> <span data-ttu-id="e5ca6-152">在发布/订阅模式中的重点是广播消息。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-152">In the Pub/Sub pattern, the focus is on broadcasting messages.</span></span> <span data-ttu-id="e5ca6-153">与此相反，在观察程序模式中，该可观测对象不知道谁事件将转到，就是这些都熄灭。换而言之，可观测对象 （发布者） 不知道都观察者 （订阅服务器）。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-153">In contrast, in the Observer pattern, the Observable does not know who the events are going to, just that they have gone out. In other words, the Observable (the publisher) does not know who the Observers (the subscribers) are.</span></span>

### <a name="the-middleman-or-event-bus"></a><span data-ttu-id="e5ca6-154">中间人或事件总线</span><span class="sxs-lookup"><span data-stu-id="e5ca6-154">The middleman or event bus</span></span> 

<span data-ttu-id="e5ca6-155">如何实现发布服务器和订阅服务器之间的匿名？</span><span class="sxs-lookup"><span data-stu-id="e5ca6-155">How do you achieve anonymity between publisher and subscriber?</span></span> <span data-ttu-id="e5ca6-156">简单方法是通信的让中间人负责所有。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-156">An easy way is let a middleman take care of all the communication.</span></span> <span data-ttu-id="e5ca6-157">事件总线是一个此类中间人。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-157">An event bus is one such middleman.</span></span>

<span data-ttu-id="e5ca6-158">事件总线通常的两部分组成：</span><span class="sxs-lookup"><span data-stu-id="e5ca6-158">An event bus is typically composed of two parts:</span></span>

-   <span data-ttu-id="e5ca6-159">抽象或接口。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-159">The abstraction or interface.</span></span>

-   <span data-ttu-id="e5ca6-160">一个或多个实现。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-160">One or more implementations.</span></span>

<span data-ttu-id="e5ca6-161">图 8-19 中可以看到如何操作，请从应用程序角度来看，事件总线只不过是 Pub/Sub 通道。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-161">In Figure 8-19 you can see how, from an application point of view, the event bus is nothing more than a Pub/Sub channel.</span></span> <span data-ttu-id="e5ca6-162">实现此异步通信的方式而异。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-162">The way you implement this asynchronous communication can vary.</span></span> <span data-ttu-id="e5ca6-163">它可以具有多个实现，以便你可以交换它们，具体取决于环境要求 （例如，开发环境与生产） 之间。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-163">It can have multiple implementations so that you can swap between them, depending on the environment requirements (for example, production versus development environments).</span></span>

<span data-ttu-id="e5ca6-164">图 8-20 你可以使用基于消息传送技术，如 RabbitMQ、 Azure Service Bus 或如 NServiceBus、 MassTransit 等其他服务总线的基础结构的多个实现看事件总线的抽象。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-164">In Figure 8-20 you can see an abstraction of an event bus with multiple implementations based on infrastructure messaging technologies like RabbitMQ, Azure Service Bus, or other service buses like NServiceBus, MassTransit, etc.</span></span>

![](./media/image21.png)

<span data-ttu-id="e5ca6-165">**图 8-20。**</span><span class="sxs-lookup"><span data-stu-id="e5ca6-165">**Figure 8- 20.**</span></span> <span data-ttu-id="e5ca6-166">事件总线的多个实现</span><span class="sxs-lookup"><span data-stu-id="e5ca6-166">Multiple implementations of an event bus</span></span>

<span data-ttu-id="e5ca6-167">但是，突出显示部分以前，使用抽象 （事件总线接口） 是可能仅当您需要支持你的抽象基本事件总线功能。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-167">However, as highlighted previously, using abstractions (the event bus interface) is possible only if you need basic event bus features supported by your abstractions.</span></span> <span data-ttu-id="e5ca6-168">如果您需要更丰富的服务总线功能，你可能应使用你的首选的 service bus，而不是自己抽象提供的 API。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-168">If you need richer service bus features, you should probably use the API provided by your preferred service bus instead of your own abstractions.</span></span>

### <a name="defining-an-event-bus-interface"></a><span data-ttu-id="e5ca6-169">定义的事件总线接口</span><span class="sxs-lookup"><span data-stu-id="e5ca6-169">Defining an event bus interface</span></span>

<span data-ttu-id="e5ca6-170">让我们开始使用事件总线接口某些实现代码和用于浏览目的可能的实现。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-170">Let’s start with some implementation code for the event bus interface and possible implementations for exploration purposes.</span></span> <span data-ttu-id="e5ca6-171">泛型和简单，如下所示的以下接口，应为接口。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-171">The interface should be generic and straightforward, as in the following interface.</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);
    void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T: IntegrationEvent;

    void Unsubscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent;
}
```

<span data-ttu-id="e5ca6-172">发布方法非常简单。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-172">The Publish method is straightforward.</span></span> <span data-ttu-id="e5ca6-173">事件总线将传播到订阅该事件任何 microservice 传递给它的集成事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-173">The event bus will broadcast the integration event passed to it to any microservice subscribed to that event.</span></span> <span data-ttu-id="e5ca6-174">将事件发布微服务使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-174">This method is used by the microservice that is publishing the event.</span></span>

<span data-ttu-id="e5ca6-175">想要接收事件在内的微服务使用 Subscribe 方法。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-175">The Subscribe method is used by the microservices that want to receive events.</span></span> <span data-ttu-id="e5ca6-176">此方法具有两个部分。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-176">This method has two parts.</span></span> <span data-ttu-id="e5ca6-177">第一个是要订阅 (IntegrationEvent) 的集成事件。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-177">The first is the integration event to subscribe to (IntegrationEvent).</span></span> <span data-ttu-id="e5ca6-178">第二部分是集成事件处理程序 （或回调方法） 调用 (IIntegrationEventHandler&lt;T&gt;) 当 microservice 收到该集成事件消息。</span><span class="sxs-lookup"><span data-stu-id="e5ca6-178">The second part is the integration event handler (or callback method) to be called (IIntegrationEventHandler&lt;T&gt;) when the microservice receives that integration event message.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e5ca6-179">[以前](数据库的服务器-container.md) [下一步] (rabbitmq-event-bus-development-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e5ca6-179">[Previous] (database-server-container.md) [Next] (rabbitmq-event-bus-development-test-environment.md)</span></span>
