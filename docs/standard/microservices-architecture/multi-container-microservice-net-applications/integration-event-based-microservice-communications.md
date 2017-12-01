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
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>实现基于事件的微服务 （集成事件） 之间的通信

如前所述，当你使用基于事件的通信时，microservice 发布发生一些值得注意的事情，例如当它更新业务实体时发生的事件。 其他微服务订阅这些事件。 当 microservice 收到事件时，它可以更新其自己的业务实体，这可能会导致正在发布的详细事件。 通过使用的事件总线实现通常执行此发布/订阅系统。 事件总线可以设计为接口中，使用订阅和取消订阅事件以及发布事件所需的 API 中。 它还可以具有任何进程间或消息传送的通信，如消息传递队列或 service bus 支持异步通信和发布/订阅模型所基于的一个或多个实现。

你可以使用事件来实现业务事务跨越多个服务，这为你提供这些服务之间的最终一致性。 最终一致事务由一系列分布式操作组成。 在每个操作，microservice 更新业务实体，并将发布触发下一步操作的事件。

![](./media/image19.PNG)

**图 8-18**。 基于事件总线上的事件驱动的通信

本部分介绍如何通过使用通用事件总线接口，如图 8-18 中所示实现这种类型的与.NET 的通信。 有多个潜在的实现，每个使用不同的技术或例如 RabbitMQ、 Azure Service Bus，任何其他第三方开源或商业服务总线的基础结构。

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>对生产系统使用消息中转站和服务总线

如体系结构节中所述，你可以从多个消息传送技术用于实现抽象事件总线中进行选择。 但这些技术是在不同级别。 例如，RabbitMQ，消息的 broker 传输，是在商业产品，如 Azure Service Bus、 NServiceBus、 MassTransit 或 Brighter 比较低级别。 大部分这些产品可基于 RabbitMQ 或 Azure Service Bus。 你选择的产品取决于多少功能和多少扩展-可用的可伸缩性你需要为你的应用程序。

对于实现只需事件总线的概念证明为开发环境，如 eShopOnContainers 的示例中，在运行作为容器的 RabbitMQ 之上的简单实现可能不够。 但对于任务关键型和需要高可伸缩性的生产系统，你可能想要评估，使用 Azure Service Fabric。 如果需要高级抽象，并且更丰富的功能要[sagas](https://docs.particular.net/nservicebus/sagas/)使 NServiceBus，MassTransit，类似更简单、 其他商业和开放源代码服务总线的分布式的开发的长时间运行进程和亮的值得评估。 当然，你始终可以生成自己 RabbitMQ 和 Docker，等的较低级别技术之上的服务总线功能，但需从头的工作可能会过于昂贵的自定义的企业应用程序。

重申一遍： 示例事件总线抽象和实现在 eShopOnContainers 示例展示用于只能用作概念证明。 一旦你已决定要具有异步和事件驱动的通信，如当前节中所述，你应选择最适合你需要的服务总线产品。

## <a name="integration-events"></a>集成事件

集成事件用于跨多个微服务或外部系统使域状态同步。 这可通过发布集成事件超出微服务。 在事件发布到多个接收方微服务 （到尽可能多的微服务如集成事件订阅） 中每个接收方微服务构成, 的相应的事件处理程序处理事件。

集成事件基本上是数据保持类，如以下示例所示：

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

集成事件类可以是简单;例如，它可能包含其 id 的 GUID

可以在每个微服务应用程序级别定义集成事件，以便从其他微服务，方式类似于 Viewmodel 服务器和客户端中的定义方式相互脱耦。 不建议跨多个微服务; 共享一个通用集成事件库执行该操作将会耦合这些微服务与单个事件定义数据库。 你不想要这样做，出于相同原因，您不想要在多个微服务之间共享通用的域模型： 微服务必须是完全自治。

有仅几种您应在微服务之间共享的库。 其中一个是像是最终应用程序块的库[事件总线客户端 API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus)，如下所示 eShopOnContainers。 另一种是构成也无法共享为 NuGet 组件，如 JSON 序列化程序的工具的库。

## <a name="the-event-bus"></a>事件总线

事件总线发布/订阅样式允许之间进行通信而无需显式请注意，在图 8-19 中所示的组件的微服务。

![](./media/image20.png)

**图 8-19**。 发布/订阅使用事件总线基础知识

事件总线与观察程序模式和发布-订阅模式。

### <a name="observer-pattern"></a>观察程序模式

在[观察程序模式](https://en.wikipedia.org/wiki/Observer_pattern)，主对象 （称为可观察对象） 包含相关信息 （事件） 通知其他感的对象 （称为观察者）。

### <a name="publish-subscribe-pubsub-pattern"></a>发布-订阅 （发布/订阅） 模式 

用途[Pub/Sub 模式](https://msdn.microsoft.com/en-us/library/ff649664.aspx)等同于观察程序模式： 你想要在某些事件发生时通知其他服务。 但没有间的观察者和发布/订阅模式的语义重要差异。 在发布/订阅模式中的重点是广播消息。 与此相反，在观察程序模式中，该可观测对象不知道谁事件将转到，就是这些都熄灭。换而言之，可观测对象 （发布者） 不知道都观察者 （订阅服务器）。

### <a name="the-middleman-or-event-bus"></a>中间人或事件总线 

如何实现发布服务器和订阅服务器之间的匿名？ 简单方法是通信的让中间人负责所有。 事件总线是一个此类中间人。

事件总线通常的两部分组成：

-   抽象或接口。

-   一个或多个实现。

图 8-19 中可以看到如何操作，请从应用程序角度来看，事件总线只不过是 Pub/Sub 通道。 实现此异步通信的方式而异。 它可以具有多个实现，以便你可以交换它们，具体取决于环境要求 （例如，开发环境与生产） 之间。

图 8-20 你可以使用基于消息传送技术，如 RabbitMQ、 Azure Service Bus 或如 NServiceBus、 MassTransit 等其他服务总线的基础结构的多个实现看事件总线的抽象。

![](./media/image21.png)

**图 8-20。** 事件总线的多个实现

但是，突出显示部分以前，使用抽象 （事件总线接口） 是可能仅当您需要支持你的抽象基本事件总线功能。 如果您需要更丰富的服务总线功能，你可能应使用你的首选的 service bus，而不是自己抽象提供的 API。

### <a name="defining-an-event-bus-interface"></a>定义的事件总线接口

让我们开始使用事件总线接口某些实现代码和用于浏览目的可能的实现。 泛型和简单，如下所示的以下接口，应为接口。

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

发布方法非常简单。 事件总线将传播到订阅该事件任何 microservice 传递给它的集成事件。 将事件发布微服务使用此方法。

想要接收事件在内的微服务使用 Subscribe 方法。 此方法具有两个部分。 第一个是要订阅 (IntegrationEvent) 的集成事件。 第二部分是集成事件处理程序 （或回调方法） 调用 (IIntegrationEventHandler&lt;T&gt;) 当 microservice 收到该集成事件消息。


>[!div class="step-by-step"]
[以前](数据库的服务器-container.md) [下一步] (rabbitmq-event-bus-development-test-environment.md)
