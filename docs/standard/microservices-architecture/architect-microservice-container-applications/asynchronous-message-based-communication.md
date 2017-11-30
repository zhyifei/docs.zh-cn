---
title: "基于消息的异步通信"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |基于消息的异步通信"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df39771295d12e122edbe27e91cd899e3318e301
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="asynchronous-message-based-communication"></a>基于消息的异步通信

异步消息传送和事件驱动的通信，都是关键，这是在跨多个微服务和其相关的域模型中传播更改时。 如前面所述的讨论微服务和绑定的上下文 (BCs)，（用户、 客户、 产品、 帐户等） 的模型不同的含义到不同的微服务或 BCs。 这意味着未发生更改，你需要某种方式来协调跨不同的模型更改。 解决方案是最终一致性和基于异步消息传送的事件驱动的通信。

在使用消息传递时，进程进行通信通过以异步方式交换消息。 客户端向服务发出的命令或请求通过将其发送一条消息。 如果服务需要进行答复，它将不同的消息发送回客户端。 由于这是基于消息的通信，客户端会假设，将立即，不会收到答复和，可能有无响应根本。

一条消息由标头 （如标识或安全信息的元数据） 和正文撰写。 通常会通过异步如 AMQP 协议发送消息。

这种微服务社区中类型的首选基础结构是通信的轻量的消息代理，这不同于大型中转站和 orchestrators 在 SOA 中使用。 轻量的消息代理，在基础结构是通常"笨拙，"仅充当消息代理，使用简单的实现，如 RabbitMQ 或在类似 Azure Service Bus 云的可缩放的服务总线。 在此方案中，大部分"智能"考虑仍驻留在生成和使用的消息的终结点-即，在微服务。

应尝试照搬，尽最大可能的另一个规则是使用仅异步消息传送之间的内部服务，并为使用同步通信 （如 HTTP) 只能从客户端应用程序的前端服务 （API 网关以及第一个级别微服务）。

有两种类型的异步消息传送的通信： 单一接收方基于消息的通信和多个接收方基于消息的通信。 下列部分中，我们提供它们的详细信息。

## <a name="single-receiver-message-based-communication"></a>单-接收方基于消息的通信 

基于消息的异步通信单一接收方意味着将一条消息传递给恰好有一个使用者，从通道中进行读取和消息处理只需一次的点到点通信。 但是，有一些特殊的情形。 例如，在尝试自动从故障中恢复的云系统，同一消息可能多次发送。 由于网络或其他故障，客户端必须能够重试发送消息和服务器都必须实现一个操作是幂等，以便只需一次处理特定的消息。

单-接收方基于消息的通信尤其适合从一个微服务的异步命令发送到另一个在图 4-18，演示了此方法所示。

一旦开始发送基于消息的通信 （不管是使用命令或事件），应避免混合与同步 HTTP 通信的基于消息的通信。

![](./media/image18.PNG)

**图 4-18**。 接收异步消息单个微服务

请注意，当命令来自客户端应用程序，它们可以作为实现 HTTP 同步命令。 当您需要更高版本的可伸缩性，或者已处于基于消息的业务流程中时，应使用基于消息的命令。

## <a name="multiple-receivers-message-based-communication"></a>多个接收方基于消息的通信 

为更灵活的方法，你可能还想要使用发布/订阅机制，从而使您从发件人的通信将其他订阅服务器微服务或外部应用程序可用。 因此，它可帮助你按照[打开/关闭原则](https://en.wikipedia.org/wiki/Open/closed_principle)发送服务中。 这样一来，而无需修改发件人服务将来，可以添加其他订阅服务器。

当你使用的发布/订阅的通信时，你可能使用到任何订阅服务器的发布事件的事件总线接口。

## <a name="asynchronous-event-driven-communication"></a>事件驱动的异步通信

在使用事件驱动的异步通信时，microservice 发布集成事件时出现在其域内，另一个微服务需要注意的如产品目录微服务的价格更改。 其他微服务订阅的事件，以便它们可以以异步方式接收它们。 在这种情况下，接收方可能会更新其自己的域实体，这可能会导致多个集成事件要发布。 通过使用的事件总线实现通常执行此发布/订阅系统。 事件总线可以设计为抽象或接口，使用 API 所需订阅或取消订阅事件以及发布事件。 事件总线还可以将一个或多个实现基于任何进程间和消息传送的 broker，类似于消息队列或服务总线支持异步通信和发布/订阅模型。

如果系统使用由集成事件驱动的最终一致性，建议，此方法将完全清除给最终用户。 系统不应使用一种方法，以模拟集成事件，例如 SignalR 或从客户端的轮询系统。 最终用户和业务所有者必须显式接受系统中的最终一致性并请注意，在许多情况下业务没有使用此方法时，任何问题，只要它是显式。

如上文中所述[的挑战和解决方案分布式数据管理](#challenges-and-solutions-for-distributed-data-management)部分中，你可以使用集成事件来实现跨多个微服务的业务任务。 这样你便可以将这些服务之间的最终一致性。 最终一致的事务是分布式的操作的集合组成。 在每个操作相关的 microservice 更新域实体，并将发布引发同样的端到端业务任务中的下一步操作的另一个集成事件。

重要的一点是，你可能想要与同一事件订阅的多个微服务通信。 若要执行此操作，你可以使用发布/订阅消息传送基于事件驱动的通信，在图 4-19 中所示。 此发布/订阅机制不专用于微服务体系结构。 它是类似的方式[绑定上下文](http://martinfowler.com/bliki/BoundedContext.html)中应传达 DDD，或将从写入数据库中的读取数据库的更新传播的方式[命令和查询责任分离 (CQRS)](http://martinfowler.com/bliki/CQRS.html)体系结构模式。 目标是能够跨分布式系统的多个数据源之间的最终一致性。

![](./media/image19.png)

**图 4-19**。 事件驱动的异步消息通信

您的实现将确定什么协议用于事件驱动的、 基于消息的通信。 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)可帮助实现可靠的排队的通信。

当你使用的事件总线时，你可能想要使用基于与使用从消息代理等 API 的代码的相关类中实现的抽象层 （如事件总线接口） [RabbitMQ](https://www.rabbitmq.com/)或如servicebus[主题使用的 azure 服务总线](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)。 或者，你可能想要使用更高级别的服务总线如 NServiceBus、 MassTransit 或 Brighter 清楚地表述事件总线以及发布/订阅系统。

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>有关消息传送技术用于生产系统的注意事项

在不同级别均可用于实现抽象事件总线消息传送技术。 例如，产品，如 RabbitMQ （消息的 broker 传输） 和 Azure Service Bus 坐在较低级别比其他产品，如、 NServiceBus、 MassTransit 或 Brighter，之上 RabbitMQ 和 Azure 服务总线可以工作。 你的选择取决于在应用程序级别和你的应用程序需要的全新的可伸缩性的多少丰富功能。 对于实现只是为开发环境的概念证明事件总线，因为我们已完成在 eShopOnContainers 示例中，在运行 Docker 容器上的 RabbitMQ 之上的简单实现可能不够。

但是，对于执行关键任务的并且需要超可伸缩性的生产系统，你可能想要评估 Azure Service Bus。 有关高级抽象和简化的分布式应用程序开发的功能，我们建议你评估其他商业和开放源代码服务总线，如 NServiceBus、 MassTransit 和 Brighter。 当然，你可以构建自己在 RabbitMQ 和 Docker 等较低级别技术之上的服务总线功能。 但该联结工作可能成本太多的自定义的企业应用程序。

## <a name="resiliently-publishing-to-the-event-bus"></a>弹性发布到事件总线

在跨多个微服务实现事件驱动的体系结构挑战是如何在恢复到某种程度上基于的事件总线发布其相关的集成事件时，以原子方式更新中原始微服务状态事务。 如下几种方法可以实现此目的，尽管可能有其他方法以及。

-   使用像 MSMQ 这样的事务 （基于 DTC） 队列。 （但是，这是旧方法）。

-   使用[事务日志挖掘](http://www.scoop.it/t/sql-server-transaction-log-mining)。

-   使用完整[事件来源](https://msdn.microsoft.com/en-us/library/dn589792.aspx)模式。

-   使用[发件箱模式](http://gistlabs.com/2014/05/the-outbox/)： 事务的数据库表作为消息队列将会创建事件，并将其发布的活动创建者组件的基。

使用异步通信时要考虑的其他主题是消息幂等性和消息重复数据删除。 这些主题涵盖在部分[实现基于事件的微服务 （集成事件） 之间的通信](#implementing_event_based_comms_microserv)本指南中更高版本。

## <a name="additional-resources"></a>其他资源

-   **事件驱动的消息传送**
    [*http://soapatterns.org/design\_模式/事件\_驱动\_消息传送*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **发布/订阅通道**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **Udi Dahan。阐明了 CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **命令和查询责任分离 (CQRS)**
    [*https://docs.microsoft.com/azure/architecture/patterns/cqrs*](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

-   **之间的通信绑定上下文**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)

-   **最终一致性**
    [*https://en.wikipedia.org/wiki/Eventual\_一致性*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Jimmy Bogard。重构入恢复能力： 评估耦合**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)


>[!div class="step-by-step"]
[以前](通信-中的微服务-architecture.md) [下一步] (维护-microservice-apis.md)
