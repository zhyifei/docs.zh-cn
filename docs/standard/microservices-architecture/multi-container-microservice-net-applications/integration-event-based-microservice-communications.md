---
title: 在微服务（集成事件）之间实现基于事件的通信
description: 容器化 .NET 应用程序的 .NET Microservices 基础结构| 在微服务（集成事件）之间实现基于事件的通信
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 5d8ba76caab39db222c2ceba36a4d67cab3e8a3f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105789"
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a><span data-ttu-id="e06b7-103">在微服务（集成事件）之间实现基于事件的通信</span><span class="sxs-lookup"><span data-stu-id="e06b7-103">Implementing event-based communication between microservices (integration events)</span></span>

<span data-ttu-id="e06b7-104">如前所述，使用基于事件的通信时，当值得注意的事件发生时，微服务会发布事件，例如更新业务实体时。</span><span class="sxs-lookup"><span data-stu-id="e06b7-104">As described earlier, when you use event-based communication, a microservice publishes an event when something notable happens, such as when it updates a business entity.</span></span> <span data-ttu-id="e06b7-105">其他微服务订阅这些事件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-105">Other microservices subscribe to those events.</span></span> <span data-ttu-id="e06b7-106">微服务收到事件时，可以更新其自己的业务实体，这可能会导致发布更多事件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-106">When a microservice receives an event, it can update its own business entities, which might lead to more events being published.</span></span> <span data-ttu-id="e06b7-107">通常通过使用事件总线实现来执行此发布/订阅系统。</span><span class="sxs-lookup"><span data-stu-id="e06b7-107">This publish/subscribe system is usually performed by using an implementation of an event bus.</span></span> <span data-ttu-id="e06b7-108">事件总线可以设计为包含 API 的接口，该 API 是订阅和取消订阅事件和发布事件所需的。</span><span class="sxs-lookup"><span data-stu-id="e06b7-108">The event bus can be designed as an interface with the API needed to subscribe and unsubscribe to events and to publish events.</span></span> <span data-ttu-id="e06b7-109">它还可以包含一个或多个基于跨进程或消息通信的实现，例如支持异步通信和发布/订阅模型的消息队列或服务总线。</span><span class="sxs-lookup"><span data-stu-id="e06b7-109">It can also have one or more implementations based on any inter-process or messaging communication, such as a messaging queue or a service bus that supports asynchronous communication and a publish/subscribe model.</span></span>

<span data-ttu-id="e06b7-110">可以使用事件来实现跨多个服务的业务事务，这可提供这些服务间的最终一致性。</span><span class="sxs-lookup"><span data-stu-id="e06b7-110">You can use events to implement business transactions that span multiple services, which gives you eventual consistency between those services.</span></span> <span data-ttu-id="e06b7-111">最终一致事务由一系列分布式操作组成。</span><span class="sxs-lookup"><span data-stu-id="e06b7-111">An eventually consistent transaction consists of a series of distributed actions.</span></span> <span data-ttu-id="e06b7-112">在每个操作中，微服务会更新业务实体，并发布可触发下一个操作的事件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-112">At each action, the microservice updates a business entity and publishes an event that triggers the next action.</span></span>

![](./media/image19.PNG)

<span data-ttu-id="e06b7-113">**图 8-18**。</span><span class="sxs-lookup"><span data-stu-id="e06b7-113">**Figure 8-18**.</span></span> <span data-ttu-id="e06b7-114">基于事件总线的事件驱动的通信</span><span class="sxs-lookup"><span data-stu-id="e06b7-114">Event-driven communication based on an event bus</span></span>

<span data-ttu-id="e06b7-115">本部分介绍如何使用通用事件总线接口（如图 8-18 所示）实现这种与 .NET 的通信。</span><span class="sxs-lookup"><span data-stu-id="e06b7-115">This section describes how you can implement this type of communication with .NET by using a generic event bus interface, as shown in Figure 8-18.</span></span> <span data-ttu-id="e06b7-116">存在多种可能的实现，每种实现使用不同的技术或基础结构，例如 RabbitMQ、Azure 服务总线或任何其他第三方开源或商用服务总线。</span><span class="sxs-lookup"><span data-stu-id="e06b7-116">There are multiple potential implementations, each using a different technology or infrastructure such as RabbitMQ, Azure Service Bus, or any other third-party open source or commercial service bus.</span></span>

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a><span data-ttu-id="e06b7-117">将消息中转站和服务总线用于生产系统</span><span class="sxs-lookup"><span data-stu-id="e06b7-117">Using message brokers and services buses for production systems</span></span>

<span data-ttu-id="e06b7-118">如体系结构部分所述，可从多个消息技术中选择，用于实现抽象事件总线。</span><span class="sxs-lookup"><span data-stu-id="e06b7-118">As noted in the architecture section, you can choose from multiple messaging technologies for implementing your abstract event bus.</span></span> <span data-ttu-id="e06b7-119">但这些技术的级别不同。</span><span class="sxs-lookup"><span data-stu-id="e06b7-119">But these technologies are at different levels.</span></span> <span data-ttu-id="e06b7-120">例如，消息中转站传输 RabbitMQ 的级别比 Azure 服务总线、NServiceBus、MassTransit 或 Brighter 的级别低。</span><span class="sxs-lookup"><span data-stu-id="e06b7-120">For instance, RabbitMQ, a messaging broker transport, is at a lower level than commercial products like Azure Service Bus, NServiceBus, MassTransit, or Brighter.</span></span> <span data-ttu-id="e06b7-121">这些产品中的大部分可基于 RabbitMQ 或 Azure 服务总线运行。</span><span class="sxs-lookup"><span data-stu-id="e06b7-121">Most of these products can work on top of either RabbitMQ or Azure Service Bus.</span></span> <span data-ttu-id="e06b7-122">你对产品的选择取决于针对应用程序需要多少功能和现成的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="e06b7-122">Your choice of product depends on how many features and how much out-of-the-box scalability you need for your application.</span></span>

<span data-ttu-id="e06b7-123">如果只是为开发环境实现事件总线概念证明，那么正如 eShopOnContainers 示例所述，基于作为容器运行的 RabbitMQ 的简单实现可能已足够。</span><span class="sxs-lookup"><span data-stu-id="e06b7-123">For implementing just an event bus proof-of-concept for your development environment, as in the eShopOnContainers sample, a simple implementation on top of RabbitMQ running as a container might be enough.</span></span> <span data-ttu-id="e06b7-124">但对于任务关键型和需要高可伸缩性的生产系统，可能需要评估和使用 Azure 服务总线。</span><span class="sxs-lookup"><span data-stu-id="e06b7-124">But for mission-critical and production systems that need high scalability, you might want to evaluate and use Azure Service Bus.</span></span>

<span data-ttu-id="e06b7-125">如果需要高级别抽象和更丰富的功能（如 [Sagas](https://docs.particular.net/nservicebus/sagas/)），用于简化分布式开发的长时间运行进程，则可评估 NServiceBus、MassTransit 和 Brighter 等其他商用和开源服务总线。</span><span class="sxs-lookup"><span data-stu-id="e06b7-125">If you require high-level abstractions and richer features like [Sagas](https://docs.particular.net/nservicebus/sagas/) for long-running processes that make distributed development easier, other commercial and open-source service buses like NServiceBus, MassTransit, and Brighter are worth evaluating.</span></span> <span data-ttu-id="e06b7-126">在此情况下，通常需要使用由高级别服务总线直接提供的抽象和 API，而不是你自己的抽象（例如 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs) 提供的简单事件总线抽象）。</span><span class="sxs-lookup"><span data-stu-id="e06b7-126">In this case, the abstractions and API to use would usually be directly the ones provided by those high-level service buses instead of your own abstractions (like the [simple event bus abstractions provided at eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)).</span></span> <span data-ttu-id="e06b7-127">为此，可研究[使用 NServiceBus 的分叉 eShopOnContainer](http://go.particular.net/eShopOnContainers)（由特定软件实现的其他派生示例）</span><span class="sxs-lookup"><span data-stu-id="e06b7-127">For that matter, you can research the [forked eShopOnContainers using NServiceBus](http://go.particular.net/eShopOnContainers) (additional derived sample implemented by Particular Software)</span></span>

<span data-ttu-id="e06b7-128">当然，你可始终基于 RabbitMQ 和 Docker 等较低级别技术生成自己的服务总线功能，但“彻底改造”所需的工作可能对于自定义企业应用程序而言过于昂贵。</span><span class="sxs-lookup"><span data-stu-id="e06b7-128">Of course, you could always build your own service bus features on top of lower-level technologies like RabbitMQ and Docker, but the work needed to “reinvent the wheel” might be too costly for a custom enterprise application.</span></span>

## <a name="integration-events"></a><span data-ttu-id="e06b7-129">集成事件</span><span class="sxs-lookup"><span data-stu-id="e06b7-129">Integration events</span></span>

<span data-ttu-id="e06b7-130">集成事件用于跨多个微服务或外部系统保持域状态同步。</span><span class="sxs-lookup"><span data-stu-id="e06b7-130">Integration events are used for bringing domain state in sync across multiple microservices or external systems.</span></span> <span data-ttu-id="e06b7-131">这可通过在微服务外发布集成事件完成。</span><span class="sxs-lookup"><span data-stu-id="e06b7-131">This is done by publishing integration events outside the microservice.</span></span> <span data-ttu-id="e06b7-132">将事件发布到多个接收方微服务（订阅到集成事件的尽可能多个微服务）时，每个接收方微服务中的相应事件处理程序会处理该事件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-132">When an event is published to multiple receiver microservices (to as many microservices as are subscribed to the integration event), the appropriate event handler in each receiver microservice handles the event.</span></span>

<span data-ttu-id="e06b7-133">集成事件基本上是数据保持类，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e06b7-133">An integration event is basically a data-holding class, as in the following example:</span></span>

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

<span data-ttu-id="e06b7-134">可以在每个微服务的应用程序级别定义集成事件，以便将其从其他微服务分离，方式类似于在服务器和客户端中定义 ViewModel。</span><span class="sxs-lookup"><span data-stu-id="e06b7-134">The integration events can be defined at the application level of each microservice, so they are decoupled from other microservices, in a way comparable to how ViewModels are defined in the server and client.</span></span> <span data-ttu-id="e06b7-135">不建议跨多个微服务共享同一个集成事件库，这样做会导致这些微服务与一个事件定义数据库连接。</span><span class="sxs-lookup"><span data-stu-id="e06b7-135">What is not recommended is sharing a common integration events library across multiple microservices; doing that would be coupling those microservices with a single event definition data library.</span></span> <span data-ttu-id="e06b7-136">这与你不希望跨多个微服务共享同一个域模型的原因相同：微服务必须是完全独立的。</span><span class="sxs-lookup"><span data-stu-id="e06b7-136">You do not want to do that for the same reasons that you do not want to share a common domain model across multiple microservices: microservices must be completely autonomous.</span></span>

<span data-ttu-id="e06b7-137">仅应跨微服务共享一些类型的库。</span><span class="sxs-lookup"><span data-stu-id="e06b7-137">There are only a few kinds of libraries you should share across microservices.</span></span> <span data-ttu-id="e06b7-138">其中一种库是最终应用程序块，如 eShopOnContainer 中的[事件总线客户端 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)。</span><span class="sxs-lookup"><span data-stu-id="e06b7-138">One is libraries that are final application blocks, like the [Event Bus client API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), as in eShopOnContainers.</span></span> <span data-ttu-id="e06b7-139">另一种库是组成可作为 NuGet 组件共享的工具的库，如 JSON 序列化程序。</span><span class="sxs-lookup"><span data-stu-id="e06b7-139">Another is libraries that constitute tools that could also be shared as NuGet components, like JSON serializers.</span></span>

## <a name="the-event-bus"></a><span data-ttu-id="e06b7-140">事件总线</span><span class="sxs-lookup"><span data-stu-id="e06b7-140">The event bus</span></span>

<span data-ttu-id="e06b7-141">事件总线可实现发布/订阅式通信，无需组件之间相互显式识别，如图 8-19 所示。</span><span class="sxs-lookup"><span data-stu-id="e06b7-141">An event bus allows publish/subscribe-style communication between microservices without requiring the components to explicitly be aware of each other, as shown in Figure 8-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="e06b7-142">**图 8-19**。</span><span class="sxs-lookup"><span data-stu-id="e06b7-142">**Figure 8-19**.</span></span> <span data-ttu-id="e06b7-143">事件总线的发布/订阅基础知识</span><span class="sxs-lookup"><span data-stu-id="e06b7-143">Publish/subscribe basics with an event bus</span></span>

<span data-ttu-id="e06b7-144">事件总线与观察者模式和发布-订阅模式相关。</span><span class="sxs-lookup"><span data-stu-id="e06b7-144">The event bus is related to the Observer pattern and the publish-subscribe pattern.</span></span>

### <a name="observer-pattern"></a><span data-ttu-id="e06b7-145">观察者模式</span><span class="sxs-lookup"><span data-stu-id="e06b7-145">Observer pattern</span></span>

<span data-ttu-id="e06b7-146">在[观察者模式](https://en.wikipedia.org/wiki/Observer_pattern)中，主对象（称为可观察对象）将相关信息（事件）告知其他感兴趣的对象（称为观察者）。</span><span class="sxs-lookup"><span data-stu-id="e06b7-146">In the [Observer pattern](https://en.wikipedia.org/wiki/Observer_pattern), your primary object (known as the Observable) notifies other interested objects (known as Observers) with relevant information (events).</span></span>

### <a name="publish-subscribe-pubsub-pattern"></a><span data-ttu-id="e06b7-147">发布-订阅（发布/订阅）模式</span><span class="sxs-lookup"><span data-stu-id="e06b7-147">Publish-subscribe (Pub/Sub) pattern</span></span> 

<span data-ttu-id="e06b7-148">[发布/订阅模式](https://msdn.microsoft.com/library/ff649664.aspx) 的用途与观察者模式相同：某些事件发生时，需要告知其他服务。</span><span class="sxs-lookup"><span data-stu-id="e06b7-148">The purpose of the [Pub/Sub pattern](https://msdn.microsoft.com/library/ff649664.aspx) is the same as the Observer pattern: you want to notify other services when certain events take place.</span></span> <span data-ttu-id="e06b7-149">但观察者模式与发布/订阅模式之间存在重要区别。</span><span class="sxs-lookup"><span data-stu-id="e06b7-149">But there is an important difference between the Observer and Pub/Sub patterns.</span></span> <span data-ttu-id="e06b7-150">在观察者模式中，直接从可观察对象广播到观察者，因此它们“知道”彼此。</span><span class="sxs-lookup"><span data-stu-id="e06b7-150">In the observer pattern, the broadcast is performed directly from the observable to the observers, so they “know” each other.</span></span> <span data-ttu-id="e06b7-151">但在发布/订阅模式中，存在称为中转站、消息中转站或事件总线的第三个组件，发布服务器和订阅服务器都知道第三个组件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-151">But when using a Pub/Sub pattern, there is a third component, called broker or message broker or event bus, which is known by both the publisher and subscriber.</span></span> <span data-ttu-id="e06b7-152">因此，使用发布/订阅模式时，发布服务器和订阅服务器通过所述的事件总线或消息中转站精确分离。</span><span class="sxs-lookup"><span data-stu-id="e06b7-152">Therefore, when using the Pub/Sub pattern the publisher and the subscribers are precisely decoupled thanks to the mentioned event bus or message broker.</span></span>

### <a name="the-middleman-or-event-bus"></a><span data-ttu-id="e06b7-153">中转站或事件总线</span><span class="sxs-lookup"><span data-stu-id="e06b7-153">The middleman or event bus</span></span> 

<span data-ttu-id="e06b7-154">如何实现发布服务器和订阅服务器之间的匿名？</span><span class="sxs-lookup"><span data-stu-id="e06b7-154">How do you achieve anonymity between publisher and subscriber?</span></span> <span data-ttu-id="e06b7-155">一个简单方法是让中转站处理所有通信。</span><span class="sxs-lookup"><span data-stu-id="e06b7-155">An easy way is let a middleman take care of all the communication.</span></span> <span data-ttu-id="e06b7-156">事件总线是一个这样的中转站。</span><span class="sxs-lookup"><span data-stu-id="e06b7-156">An event bus is one such middleman.</span></span>

<span data-ttu-id="e06b7-157">事件总线通常由两部分组成：</span><span class="sxs-lookup"><span data-stu-id="e06b7-157">An event bus is typically composed of two parts:</span></span>

-   <span data-ttu-id="e06b7-158">抽象或接口。</span><span class="sxs-lookup"><span data-stu-id="e06b7-158">The abstraction or interface.</span></span>

-   <span data-ttu-id="e06b7-159">一个或多个实现。</span><span class="sxs-lookup"><span data-stu-id="e06b7-159">One or more implementations.</span></span>

<span data-ttu-id="e06b7-160">在图 8-19 中，从应用程序角度看，会发现事件总线实际上是一个发布/订阅通道。</span><span class="sxs-lookup"><span data-stu-id="e06b7-160">In Figure 8-19 you can see how, from an application point of view, the event bus is nothing more than a Pub/Sub channel.</span></span> <span data-ttu-id="e06b7-161">实现此异步通信的方式可能会有差异。</span><span class="sxs-lookup"><span data-stu-id="e06b7-161">The way you implement this asynchronous communication can vary.</span></span> <span data-ttu-id="e06b7-162">它可以具有多个实现，以便你进行交换，具体取决于环境要求（例如，生产和开发环境）。</span><span class="sxs-lookup"><span data-stu-id="e06b7-162">It can have multiple implementations so that you can swap between them, depending on the environment requirements (for example, production versus development environments).</span></span>

<span data-ttu-id="e06b7-163">在图 8-20 中，可看到事件总线的抽象，包含基于 RabbitMQ、Azure 服务总线或其他事件/消息中转站等基础结构消息技术的多个实现。</span><span class="sxs-lookup"><span data-stu-id="e06b7-163">In Figure 8-20 you can see an abstraction of an event bus with multiple implementations based on infrastructure messaging technologies like RabbitMQ, Azure Service Bus, or other event/message broker.</span></span> 

![](./media/image21.png)

<span data-ttu-id="e06b7-164">**图 8- 20。**</span><span class="sxs-lookup"><span data-stu-id="e06b7-164">**Figure 8- 20.**</span></span> <span data-ttu-id="e06b7-165">事件总线的多个实现</span><span class="sxs-lookup"><span data-stu-id="e06b7-165">Multiple implementations of an event bus</span></span>

<span data-ttu-id="e06b7-166">但是，如前所述，仅当需要由你的抽象支持的基本事件总线功能时，才适合使用你自己的抽象（事件总线接口）。</span><span class="sxs-lookup"><span data-stu-id="e06b7-166">However, and as mentioned previously, using your own abstractions (the event bus interface) is good only if you need basic event bus features supported by your abstractions.</span></span> <span data-ttu-id="e06b7-167">如果需要更丰富的服务总线功能，应使用你喜欢的商用服务总线提供的 API 和抽象，而不是你自己的抽象。</span><span class="sxs-lookup"><span data-stu-id="e06b7-167">If you need richer service bus features, you should probably use the API and abstractions provided by your preferred commercial service bus instead of your own abstractions.</span></span> 

### <a name="defining-an-event-bus-interface"></a><span data-ttu-id="e06b7-168">定义事件总线接口</span><span class="sxs-lookup"><span data-stu-id="e06b7-168">Defining an event bus interface</span></span>

<span data-ttu-id="e06b7-169">首先，让我们了解一下事件总线接口的一些实现代码和可能的实现。</span><span class="sxs-lookup"><span data-stu-id="e06b7-169">Let’s start with some implementation code for the event bus interface and possible implementations for exploration purposes.</span></span> <span data-ttu-id="e06b7-170">接口应是通用和简单的，如下所示接口。</span><span class="sxs-lookup"><span data-stu-id="e06b7-170">The interface should be generic and straightforward, as in the following interface.</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);

    void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>;

    void SubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void UnsubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void Unsubscribe<T, TH>()
        where TH : IIntegrationEventHandler<T>
        where T : IntegrationEvent;
}
```

<span data-ttu-id="e06b7-171">`Publish` 方法很简单。</span><span class="sxs-lookup"><span data-stu-id="e06b7-171">The `Publish` method is straightforward.</span></span> <span data-ttu-id="e06b7-172">事件总线会向订阅该事件的任何微服务或外部应用程序，广播经过它的集成事件。</span><span class="sxs-lookup"><span data-stu-id="e06b7-172">The event bus will broadcast the integration event passed to it to any microservice, or even an external application, subscribed to that event.</span></span> <span data-ttu-id="e06b7-173">该方法由发布事件的微服务使用。</span><span class="sxs-lookup"><span data-stu-id="e06b7-173">This method is used by the microservice that is publishing the event.</span></span>

<span data-ttu-id="e06b7-174">`Subscribe` 方法（你可能有多个实现，具体取决于参数）由要接收事件的微服务使用。</span><span class="sxs-lookup"><span data-stu-id="e06b7-174">The `Subscribe` methods (you can have several implementations depending on the arguments) are used by the microservices that want to receive events.</span></span> <span data-ttu-id="e06b7-175">此方法具有两个参数。</span><span class="sxs-lookup"><span data-stu-id="e06b7-175">This method has two arguments.</span></span> <span data-ttu-id="e06b7-176">第一个是要订阅的集成事件 (`IntegrationEvent`)。</span><span class="sxs-lookup"><span data-stu-id="e06b7-176">The first is the integration event to subscribe to (`IntegrationEvent`).</span></span> <span data-ttu-id="e06b7-177">第二个参数是名为 `IIntegrationEventHandler<T>` 的集成事件处理程序（或回调方法），用于在接收者微服务获得集成事件消息时执行。</span><span class="sxs-lookup"><span data-stu-id="e06b7-177">The second argument is the integration event handler (or callback method), named `IIntegrationEventHandler<T>`, to be executed when the receiver microservice gets that integration event message.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e06b7-178">[上一页](database-server-container.md)
[下一页](rabbitmq-event-bus-development-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e06b7-178">[Previous](database-server-container.md)
[Next](rabbitmq-event-bus-development-test-environment.md)</span></span>
