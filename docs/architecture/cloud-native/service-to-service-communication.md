---
title: 服务到服务通信
description: 了解后端云原生微服务如何与其他后端微服务进行通信。
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: a5124b8b83f62ff17b1230ead63db26e0c1f2a5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401759"
---
# <a name="service-to-service-communication"></a>服务到服务通信

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

从前端客户端，我们现在处理后端微服务相互通信。

构建云本机应用程序时，您需要对后端服务如何相互通信敏感。 理想情况下，服务间通信越少越好。 但是，由于后端服务通常相互依赖来完成操作，因此并非始终能够避免。

实施跨服务通信的方法被广泛接受。 *通信交互的类型*通常将决定最佳方法。

请考虑以下交互类型：

- *查询*– 当调用微服务需要来自被调用的微服务的响应时，例如"嘿，给我给定客户 ID 的买方信息。

- *命令*– 当调用微服务需要另一个微服务来执行操作，但不需要响应时，例如"嘿，只需发出此订单"。

- *事件*— 当称为发布服务器的微服务引发状态已更改或已发生操作的事件时。 其他微服务（称为订阅者）有兴趣，可以对事件做出适当的反应。 发布者和订阅者彼此不知道。

在执行需要跨服务交互的操作时，微服务系统通常使用这些交互类型的组合。 让我们仔细看看每个以及如何实现它们。

## <a name="queries"></a>查询

很多时候，一个微服务可能需要*查询*另一个微服务，需要立即响应才能完成操作。 购物篮微服务可能需要产品信息和价格才能将商品添加到其购物篮中。 实现查询操作的方法有很多种。

### <a name="requestresponse-messaging"></a>请求/响应消息传送

实现此方案的一个选项是调用后端微服务，以便直接向需要查询的微服务发出 HTTP 请求，如图 4-8 所示。

![直接 HTTP 通信](./media/direct-http-communication.png)

**图4-8**。 直接 HTTP 通信

虽然微服务之间的直接 HTTP 调用执行起来相对简单，但应注意将这种做法降至最低。 要启动，这些调用始终是*同步*的，并将阻止操作，直到返回结果或请求超时。 曾经自成一体的独立服务能够独立发展并频繁部署，现在却相互耦合。 随着微服务之间的耦合增加，其体系结构优势逐渐降低。

执行对另一个微服务进行单个直接 HTTP 调用的不常见请求对于某些系统可能是可以接受的。 但是，不建议调用对多个微服务直接 HTTP 调用的高容量调用。 它们会增加延迟，并产生负面影响系统的性能、可扩展性和可用性。 更糟糕的是，一系列直接 HTTP 通信可能导致同步微服务调用的深层和复杂链，如图 4-9 所示：

![链接 HTTP 查询](./media/chaining-http-queries.png)

**图4-9**。 链接 HTTP 查询

您当然可以想象前一张图片中显示的设计中的风险。 如果步骤\#3 失败，会发生什么情况？ 还是步骤\#8 失败？ 你如何恢复？ 如果步骤\#6 由于基础服务繁忙而速度较慢，该怎么办？ 你如何继续？ 即使所有操作都正常工作，也想想此调用产生的延迟，即每个步骤的延迟总和。

上图中大量耦合表明，服务没有进行最佳建模。 团队应该重新审视他们的设计。

### <a name="materialized-view-pattern"></a>具体化视图模式

删除微服务耦合的一个常用选项是[具体化视图模式](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)。 使用此模式，微服务存储其自己的本地、非规范化数据副本，这些副本由其他服务拥有。 它维护自己的本地数据副本，而不是查询产品目录和定价微服务的购物篮微服务。 此模式消除了不必要的耦合，提高了可靠性和响应时间。 整个操作在单个进程内执行。 我们在第 5 章中探讨此模式和其他数据问题。

### <a name="service-aggregator-pattern"></a>服务聚合器模式

消除微服务到微服务耦合的另一个选项是[聚合器微服务](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/)，如图 4-10 中紫色所示。

![聚合器服务](./media/aggregator-service.png)

**图 4-10**。 聚合器微服务

该模式隔离了对多个后端微服务进行调用的操作，将其逻辑集中到专用微服务中。  上图中的紫色签出聚合器微服务协调签出操作的工作流。 它包括按顺序顺序对多个后端微服务的调用。 来自工作流的数据将聚合并返回到调用方。 虽然它仍然实现直接 HTTP 调用，但聚合器微服务减少了后端微服务之间的直接依赖关系。

### <a name="requestreply-pattern"></a>请求/回复模式

分离同步 HTTP 消息的另一种方法是[请求回复模式](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html)，它使用队列通信。 使用队列的通信始终是单向通道，生产者发送消息并接收使用者。 使用此模式，将实现请求队列和响应队列，如图 4-11 所示。

![请求-回复模式](./media/request-reply-pattern.png)

**图 4-11**。 请求-回复模式

在这里，消息生成器创建一个基于查询的消息，其中包含唯一的相关性 ID 并将其放入请求队列中。 使用服务取消消息排队，处理消息，并将响应放在具有相同关联 ID 的响应队列中。 生产者服务取消消息的排队，将其与相关 ID 匹配并继续处理。 我们将在下一节中详细介绍队列。

## <a name="commands"></a>命令

另一种类型的通信交互是*命令*。 微服务可能需要另一个微服务来执行操作。 订购微服务可能需要运输微服务为已批准的订单创建货件。 在图 4-12 中，一个称为"生产者"的微服务向另一个微服务"使用者"发送消息，命令它执行某些操作。

![命令与队列的交互](./media/command-interaction-with-queue.png)

图 4-12****。 命令与队列的交互

通常，生产者不需要响应，可能会*触发和忘记*消息。 如果需要回复，使用者将发送单独的消息回另一个通道上的生产者。 命令消息最好使用消息队列异步发送。 由轻量级消息代理支持。 在上图中，请注意队列如何分离和分离两个服务。

消息队列是一种中间构造，生产者和使用者通过它传递消息。 队列实现异步点对点消息传递模式。 生产者知道需要发送命令的位置并相应地路由。 队列保证消息由从通道读取的使用者实例之一处理。 在这种情况下，生产者或使用者服务可以横向扩展，而不会影响其他服务。 同样，技术在两侧可能各不相同，这意味着我们可能有一个 Java 微服务，称为[Golang](https://golang.org)微服务。

在第 1 章中，我们讨论了*支持服务*。 支持服务是云原生系统所依赖的辅助资源。 消息队列是支持服务。 Azure 云支持两种类型的消息队列，云原生系统可用于实现命令消息传递：Azure 存储队列和 Azure 服务总线队列。

### <a name="azure-storage-queues"></a>Azure 存储队列

Azure 存储队列提供快速、经济实惠并由 Azure 存储帐户提供支持的简单队列基础结构。

[Azure 存储队列](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)具有基于 REST 的排队机制，具有可靠且持久的消息传递。 它们提供最少的功能集，但价格低廉，并存储数百万条消息。 其容量范围可达 500 TB。 一条消息的大小可达 64 KB。

您可以使用 HTTP 或 HTTPS 通过经过身份验证的呼叫从世界任何地方访问消息。 存储队列可以扩展到大量并发客户端，以处理流量峰值。

也就是说，服务存在限制：

- 消息顺序不保证。

- 消息只能保留七天，然后才能自动删除。

- 不支持状态管理、重复检测或事务不可用。

图 4-13 显示了 Azure 存储队列的层次结构。

![存储队列层次结构](./media/storage-queue-hierarchy.png)

**图4-13**。 存储队列层次结构

在上图中，请注意存储队列如何将其消息存储在基础 Azure 存储帐户中。

对于开发人员，Microsoft 提供了多个客户端和服务器端库，用于存储队列处理。 大多数主要平台都受支持，包括 .NET、Java、JavaScript、Ruby、Python 和 Go。 开发人员绝不应直接与这些库通信。 这样做会将微服务代码与 Azure 存储队列服务紧密耦合。 最好隔离 API 的实现详细信息。 引入中介层或中间 API，该层公开泛型操作并封装具体库。 这种松散的耦合使您能够将一个队列服务交换到另一个队列服务，而无需更改主线服务代码。

Azure 存储队列是在云本机应用程序中实现命令消息传递的经济选择。 特别是当队列大小超过 80 GB 时，或者一个简单的功能集是可以接受的。 您只为邮件的存储付费;没有固定的小时费用。

### <a name="azure-service-bus-queues"></a>Azure 服务总线队列

对于更复杂的消息传递要求，请考虑 Azure 服务总线队列。

[Azure 服务总线](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)位于强大的消息基础结构之上，支持*中转消息传递模型*。 消息可靠地存储在代理（队列）中，直到使用者收到消息。 队列保证先到/先出 （FIFO） 消息传递，遵守消息添加到队列的顺序。

消息的大小可以大得多，高达 256 KB。 消息在队列中保留无限时间。 服务总线不仅支持基于 HTTP 的调用，而且还提供对[AMPQ 协议的](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview)完全支持。 AMPQ 是跨供应商的开放标准，支持二进制协议和更高可靠性度。

服务总线提供了一组丰富的功能，包括[事务支持](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions)和[重复检测功能](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection)。 队列保证每条消息"最多传递一次"。 它会自动丢弃已发送的消息。 如果生产者有疑问，它可以重新发送相同的消息，并且服务总线保证只处理一个副本。 重复检测使您不必构建其他基础结构管道。

另外两个企业功能是分区和会话。 传统的服务总线队列由单个消息代理处理并存储在单个消息存储中。 但是，[服务总线分区](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning)将队列分散到多个消息代理和消息存储中。 总体吞吐量不再受单个消息代理或消息存储的性能的限制。 消息存储的临时中断不会使分区队列不可用。

[服务总线会话](https://codingcanvas.com/azure-service-bus-sessions/)提供了一种组相关消息的方法。 想象一下工作流方案，其中消息必须一起处理，操作在结束时完成。 要利用此优势，必须为队列显式启用会话，并且每个相关消息必须包含相同的会话 ID。

但是，有一些重要的警告：服务总线队列大小限制为 80 GB，这比商店队列中可用的小得多。 此外，服务总线队列会产生基本成本和每次操作的费用。

图 4-14 概述了服务总线队列的高级体系结构。

![服务总线队列](./media/service-bus-queue.png)

图 4-14****。 服务总线队列

在上图中，请注意点对点关系。 同一提供程序的两个实例正在将消息排入单个服务总线队列中。 每条消息仅由右侧三个使用者实例中的一个使用。 接下来，我们将讨论如何在不同消费者都对同一消息感兴趣的地方实现消息传递。

## <a name="events"></a>事件

消息队列是实现通信的有效方法，其中生产者可以异步向使用者发送消息。 但是，当*许多不同的消费者对*同一消息感兴趣时，会发生什么情况？ 每个使用者的专用消息队列不会很好地扩展，并且将变得难以管理。

为了解决这个问题，我们转到第三种类型的消息交互，*事件*。 一个微服务宣布已发生操作。 其他微服务（如果有兴趣）对操作或事件做出反应。

事件是一个两步过程。 对于给定的状态更改，微服务将事件发布到消息代理，使其可用于任何其他感兴趣的微服务。 通过订阅消息代理中的事件来通知感兴趣的微服务。 您可以使用[发布/订阅](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber)模式来实现[基于事件的通信](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications)。

图 4-15 显示了购物篮微服务发布事件，其中另外两个微服务订阅了它。

![事件驱动消息](./media/event-driven-messaging.png)

**图 4-15**。 事件驱动消息

请注意位于通信通道中间*的事件总线*组件。 它是一个自定义类，它封装消息代理并将其与基础应用程序分离。 订购和库存微服务在彼此不知情的情况下独立操作事件，也无需购物篮微服务。 当注册事件发布到事件总线时，它们会对它执行操作。

通过事件，我们从排队技术转向*主题*。 [主题](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)类似于队列，但支持一对多消息传递模式。 一个微服务发布消息。 多个订阅微服务可以选择接收该消息并采取行动。 图 4-16 显示了主题体系结构。

![主题体系结构](./media/topic-architecture.png)

**图 4-16**。 主题体系结构

在上图中，发布者向主题发送消息。 最后，订阅者会从订阅接收消息。 在中间，主题根据一组*规则*将消息转发到订阅，这些规则显示在深蓝色框中。 规则充当将特定消息转发到订阅的筛选器。 此处，将"创建订单"事件发送到订阅\#1 和订阅\#3，但不会发送到订阅\#2。 "订单完成"事件将发送到订阅\#2 和订阅\#3。

Azure 云支持两种不同的主题服务：Azure 服务总线主题和 Azure 事件网格。

### <a name="azure-service-bus-topics"></a>Azure 服务总线主题

坐在 Azure 服务总线队列的相同强大代理消息模型的顶部是 Azure[服务总线主题](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)。 主题可以接收来自多个独立发布者的消息，并向多达 2，000 个订阅者发送消息。 订阅可以在运行时动态添加或删除，而无需停止系统或重新创建主题。

Azure 服务总线队列中的许多高级功能也可用于主题，包括[重复检测](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection)和[事务支持](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions)。 默认情况下，服务总线主题由单个消息代理处理并存储在单个消息存储中。 但是，[服务总线分区](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning)通过将主题传播到许多消息代理和消息存储中来扩展主题。

[计划邮件传递](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing)标记具有特定时间处理的邮件。 在此之前，该消息不会显示在主题中。 [消息延迟](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral)使您能够将邮件的检索推迟到以后。 这两种情况通常用于工作流处理方案，其中操作按特定顺序处理。 您可以推迟处理已接收的消息，直到完成之前的工作。

服务总线主题是一种强大且经过验证的技术，可在云本机系统中启用发布/订阅通信。

### <a name="azure-event-grid"></a>Azure 事件网格

虽然 Azure 服务总线是经过战斗测试的消息代理，具有一整套企业功能，但[Azure 事件网格](https://docs.microsoft.com/azure/event-grid/overview)是块上的新孩子。

乍一看，事件网格可能只是另一个基于主题的邮件系统。 然而，它在许多方面是不同的。 它专注于事件驱动的工作负载，支持实时事件处理、深度 Azure 集成和开放平台 - 所有这些都位于无服务器基础架构上。 它专为现代云原生和无服务器应用程序而设计

作为集中*式事件背板*或管道，事件网格对 Azure 资源内的事件和您自己的服务做出反应。

事件通知发布到事件网格主题，而事件网格主题又将每个事件路由到订阅。 订阅服务器映射到订阅并使用事件。 与服务总线一样，事件网格支持*筛选的订阅者模型*，其中订阅集其希望接收的事件的规则。 事件网格提供快速吞吐量，保证每秒 1000 万个事件，实现近乎实时的传递 -远远超过 Azure 服务总线所能生成的。

事件网格的一个最佳亮点是它深入集成到 Azure 基础结构的结构中。 Azure 资源（如 Cosmos DB）可以直接将内置事件发布到其他感兴趣的 Azure 资源，而无需自定义代码。 事件网格可以从 Azure 订阅、资源组或服务发布事件，使开发人员能够细粒度地控制云资源的生命周期。 但是，事件网格并不仅限于 Azure。 它是一个开放的平台，可以使用从应用程序或第三方服务发布的自定义 HTTP 事件，并将事件路由到外部订阅者。

从 Azure 资源发布和订阅本机事件时，不需要编码。 通过简单的配置，您可以利用主题和订阅的内置管道将事件从一个 Azure 资源集成到另一个 Azure 资源。 图 4-17 显示了事件网格的剖析。

![事件网格解剖](./media/event-grid-anatomy.png)

**图 4-17**。 事件网格解剖

事件网格和服务总线之间的一个主要区别是基础*消息交换模式*。

服务总线实现了较旧的样式*拉取模型*，其中下游订阅者主动轮询主题订阅的新消息。 有利的一面是，此方法使订阅者能够完全控制其处理消息的速度。 它控制在任意给定时间处理的时间和消息数。 未读邮件将保留在订阅中，直到处理。 一个重大缺点是生成事件的时间与将该消息拉至订阅者进行处理的轮询操作之间的延迟。 此外，下一个事件的恒定轮询开销会消耗资源和资金。

但是，事件网格是不同的。 它实现了一个*推送模型*，其中事件在接收时发送到事件处理程序，提供近乎实时的事件传递。 它还降低了成本，因为服务仅在需要使用事件时触发 -而不是与轮询那样持续。 也就是说，事件处理程序必须处理传入负载并提供限制机制，以防止自身不堪重负。 许多使用这些事件的 Azure 服务（如 Azure 函数和逻辑应用）提供自动自动缩放功能来处理增加的负载。  

事件网格是一个完全托管的无服务器云服务。 它根据您的流量动态扩展，仅针对实际使用情况收费，而不是预购买容量。 每月的前 100，000 个操作是免费的 - 操作定义为事件入口（传入事件通知）、订阅传递尝试、管理调用和按主题筛选。 凭借 99.99% 的可用性，EventGrid 保证在 24 小时内交付事件，并内置重试功能，以不成功交付。 未传递的消息可以移动到"死信"队列以进行解析。  与 Azure 服务总线不同，事件网格经过优化以获得快速性能，不支持有序消息传递、事务和会话等功能。

### <a name="streaming-messages-in-the-azure-cloud"></a>在 Azure 云中流式传输消息

Azure 服务总线和事件网格为公开单个离散事件（如新文档）的应用程序提供了极大的支持，这些事件已插入到 Cosmos DB 中。 但是，如果您的云原生系统需要处理*一系列相关事件*，该怎么办？ [事件流](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems)更为复杂。 它们通常是按时间顺序排列的，是相互关联的，必须作为一个组进行处理。

[Azure 事件中心](https://azure.microsoft.com/services/event-hubs/)是一个数据流平台和事件引入服务，用于收集、转换和存储事件。 它经过微调以捕获流数据，例如从遥测上下文中发出的连续事件通知。 该服务具有高度可扩展性，每秒可以存储[和处理数百万个事件](https://docs.microsoft.com/azure/event-hubs/event-hubs-about)。 如图 4-18 所示，它通常是事件管道的前门，将引入流与事件消耗分离。

![Azure 事件中心](./media/azure-event-hub.png)

**图 4-18**. Azure 事件中心

事件中心支持低延迟和可配置的时间保留。 与队列和主题不同，事件中心在使用者读取事件数据后保留事件数据。 此功能使内部和外部的其他数据分析服务能够重播数据以进行进一步分析。 存储在事件中心的事件仅在保留期到期时删除，默认情况下为一天，但可配置。

事件中心支持常见的事件发布协议，包括 HTTPS 和 AMQP。 它还支持卡夫卡1.0。 [现有的 Kafka 应用程序可以使用](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview)Kafka 协议与事件中心通信，为管理大型 Kafka 群集提供了替代方案。 许多开源云原生系统都拥抱卡夫卡。

事件中心通过[分区使用者模型](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)实现消息流，其中每个使用者只读取消息流的特定子集或分区。 此模式允许以极大的水平缩放规模进行事件处理，并提供队列和主题所不能提供的其他面向流的功能。 分区是事件中心内保留的有序事件。 当较新的事件到达时，它们将添加到此序列的末尾。图 4-19 显示了事件中心中的分区。

![事件中心分区](./media/event-hub-partitioning.png)

**图 4-19**. 事件中心分区

每个使用者组读取消息流的子集或分区不是从同一资源读取。

对于必须流式传输大量事件的云原生应用程序，Azure 事件中心可以是一个强大且经济实惠的解决方案。

>[!div class="step-by-step"]
>[上一个](front-end-communication.md)
>[下一个](rest-grpc.md)
