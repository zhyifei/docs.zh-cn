---
title: "实现使用 RabbitMQ 开发或测试环境事件总线"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现使用 RabbitMQ 开发或测试环境事件总线"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="b70bd-104">实现使用 RabbitMQ 开发或测试环境事件总线</span><span class="sxs-lookup"><span data-stu-id="b70bd-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="b70bd-105">我们应开始通过说，是否你创建你的自定义事件 bus 基于在容器中运行的 RabbitMQ eShopOnContainers 应用程序一样，它应仅用于开发和测试环境。</span><span class="sxs-lookup"><span data-stu-id="b70bd-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="b70bd-106">你不应使用它为你的生产环境，除非正在生成它作为生产就绪服务总线的一部分。</span><span class="sxs-lookup"><span data-stu-id="b70bd-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="b70bd-107">简单的自定义事件总线可能丢失了商业服务总线具有的许多生产就绪关键功能。</span><span class="sxs-lookup"><span data-stu-id="b70bd-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="b70bd-108">事件总线 eShopOnContainers 自定义实现基本上是使用 RabbitMQ API 的库。</span><span class="sxs-lookup"><span data-stu-id="b70bd-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="b70bd-109">实现允许微服务订阅事件，发布事件，并且接收事件，如图 8-21 中所示。</span><span class="sxs-lookup"><span data-stu-id="b70bd-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="b70bd-110">**图 8-21。**</span><span class="sxs-lookup"><span data-stu-id="b70bd-110">**Figure 8-21.**</span></span> <span data-ttu-id="b70bd-111">RabbitMQ 实现的事件总线</span><span class="sxs-lookup"><span data-stu-id="b70bd-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="b70bd-112">在代码中，EventBusRabbitMQ 类实现的泛型的 IEventBus 接口。</span><span class="sxs-lookup"><span data-stu-id="b70bd-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="b70bd-113">这基于依赖关系注入，以便你可以从此开发/测试版本交换到生产版本。</span><span class="sxs-lookup"><span data-stu-id="b70bd-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="b70bd-114">示例开发/测试事件总线 RabbitMQ 实现是样板文件代码。</span><span class="sxs-lookup"><span data-stu-id="b70bd-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="b70bd-115">它必须处理与 RabbitMQ 服务器的连接，并提供代码发布到队列的消息事件。</span><span class="sxs-lookup"><span data-stu-id="b70bd-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="b70bd-116">它还必须实现的字典的集合的每个事件类型; 集成事件处理程序图 8-21 中所示，这些事件类型可以具有的不同实例化和每个接收方 microservice，为不同订阅。</span><span class="sxs-lookup"><span data-stu-id="b70bd-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="b70bd-117">实现一个简单发布与 RabbitMQ 方法</span><span class="sxs-lookup"><span data-stu-id="b70bd-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="b70bd-118">下面的代码是 RabbitMQ，eShopOnContainers 事件总线实现的一部分，因此你通常不需要代码它，除非都在改进。</span><span class="sxs-lookup"><span data-stu-id="b70bd-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="b70bd-119">该代码获取连接以及 RabbitMQ 通道、 创建一条消息，并随后会将消息发布到队列。</span><span class="sxs-lookup"><span data-stu-id="b70bd-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="b70bd-120">[实际代码](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs)的发布方法在 eShopOnContainers 应用程序将会通过使用改进[Polly](https://github.com/App-vNext/Polly)重试策略，重试任务一定数量的时间，以防 RabbitMQ 容器未就绪。</span><span class="sxs-lookup"><span data-stu-id="b70bd-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="b70bd-121">发生这种情况时 docker compose 正在启动容器;例如，RabbitMQ 容器可能启动速度更慢于其他容器。</span><span class="sxs-lookup"><span data-stu-id="b70bd-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="b70bd-122">如前面所述，有许多可能的配置中 RabbitMQ，因此，应仅用于开发/测试环境中使用此代码。</span><span class="sxs-lookup"><span data-stu-id="b70bd-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="b70bd-123">实现 RabbitMQ API 使用的订阅代码</span><span class="sxs-lookup"><span data-stu-id="b70bd-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="b70bd-124">作为替换为发布代码，下面的代码都是一部分的 RabbitMQ 事件总线实现的简化形式。</span><span class="sxs-lookup"><span data-stu-id="b70bd-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="b70bd-125">同样，你通常不必更改它，除非你改善。</span><span class="sxs-lookup"><span data-stu-id="b70bd-125">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

<span data-ttu-id="b70bd-126">每个事件类型都有一个相关的通道，以获取 RabbitMQ 中的事件。</span><span class="sxs-lookup"><span data-stu-id="b70bd-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="b70bd-127">然后，你可以每个通道和事件类型，根据需要的任意多个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b70bd-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="b70bd-128">Subscribe 方法接受一个 IIntegrationEventHandler 对象，它相当于在当前的微服务的回调方法，以及其相关的 IntegrationEvent 对象。</span><span class="sxs-lookup"><span data-stu-id="b70bd-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="b70bd-129">然后，代码将该事件处理程序添加到的每个集成事件类型可以具有每个客户端微服务构成的事件处理程序的列表。</span><span class="sxs-lookup"><span data-stu-id="b70bd-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="b70bd-130">如果客户端代码不已订阅的事件，该代码将创建用于事件类型的通道，因此该事件发布从任何其他服务时，它可以从 RabbitMQ 推送样式收到事件。</span><span class="sxs-lookup"><span data-stu-id="b70bd-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b70bd-131">[以前](集成-事件-基于-microservice-communications.md) [下一步] (订阅 events.md)</span><span class="sxs-lookup"><span data-stu-id="b70bd-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
