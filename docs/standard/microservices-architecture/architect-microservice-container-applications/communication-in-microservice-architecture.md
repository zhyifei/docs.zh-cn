---
title: "在微服务体系结构的通信"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |微服务体系结构体系结构中的通信"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8d38095a151b7568619b17340d768eff684d3271
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="communication-in-a-microservice-architecture"></a>在微服务体系结构的通信

在单个进程上运行的整体应用程序，在组件调用另一个使用语言级别方法或函数调用一样。 这些也可以紧密耦合，如果你要创建对象，与代码 (例如， `new ClassName()`)，或如果你使用的依赖关系注入通过引用抽象，而不是具体的对象实例可以在去耦方法中调用。 两种方式的同一进程中运行的对象。 从到基于微服务的应用程序的整体应用程序版本更改时的最大挑战在于于更改的通信机制。 从过程中方法调用转换为对服务的 RPC 调用的直接转换将导致聊天式并且将不会执行中的不有效通信分布式环境。 很好地为偶数称为 canon 已知的正确设计分布式的系统的挑战[的分布式计算 fallacies](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) ，它列出在开发人员通常提出从移动时的假设整体分布式设计。

没有不一个解决方案中，但几个。 一个解决方案涉及隔离尽可能多地业务微服务。 然后，你将使用内部微服务之间进行异步通信并替代细化通常会在进程内通信中使用较粗粒度的通信的对象之间的通信。 通过分组调用，并返回聚合结果的多个内部调用，客户端的数据时，可以执行此操作。

基于微服务的应用程序是在多个进程或服务，通常甚至跨多个服务器或主机上运行的分布式的系统。 每个服务实例通常是一个过程。 因此，使用进程间通信协议，如 HTTP、 AMQP 或如 TCP，具体取决于每个服务的性质的二进制协议服务必须进行交互。

Microservice 社区提升这一理念"[智能终结点和笨拙管道](http://simplicable.com/new/smart-endpoints-and-dumb-pipes)。" 此广告语鼓励为分离尽可能之间微服务，并尽可能在单个 microservice 好地设计。 如前面所述，每个微服务将拥有其自己的数据和它自己域的逻辑。 但微服务组成的端到端应用程序通常只通过使用 REST 通信，而不是复杂的协议，如 WS-choreographed\*的灵活事件驱动的通信，而不是集中式业务流程 orchestrators。

两个常用的协议为 HTTP 请求/响应与资源 Api （查询其中的绝大部分） 时，并跨多个微服务轻型异步消息传送通信时更新。 下列部分中的更详细地对它们进行了解释。

## <a name="communication-types"></a>通信类型

客户端和服务可以通过许多不同类型的通信，每个面向不同的方案和目标进行通信。 最初，这些类型的通信可以分为两个轴。

如果协议是同步还是异步定义的第一个轴：

-   同步的协议。 HTTP 是同步的协议。 客户端发送一个请求，并等待从服务响应。 这是独立于客户端代码执行可同步 （线程被阻止） 或异步 （线程不会被阻止，和响应将最终到达回调）。 重要的一点是，协议 (HTTP/HTTPS) 是同步的当它收到 HTTP 服务器响应时，客户端代码仅可以继续其任务。

-   异步协议。 其他协议，如 AMQP （许多操作系统和云环境支持的协议） 使用异步消息。 客户端代码或消息发件人通常不会等待响应。 它只是将消息发送到 RabbitMQ 队列或任何其他消息代理时将发送形式的消息。

如果通信具有单一的接收方或多个接收方，第二个轴定义：

-   一个接收方。 每个请求必须由恰好一个接收方或服务来处理。 此通信的一个示例是[命令模式](https://en.wikipedia.org/wiki/Command_pattern)。

-   多个接收方。 每个请求可以由零到多个接收方处理。 这种通信类型必须是异步的。 一个示例是[发布/订阅](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)机制在类似的模式下使用[事件驱动的体系结构](http://microservices.io/patterns/data/event-driven-architecture.html)。 这基于事件 bus 接口或消息代理时传播事件; 通过多个微服务之间的数据更新它通常通过 service bus 或类似的类似项目实现[Azure Service Bus](https://azure.microsoft.com/services/service-bus/)使用[主题和订阅](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)。

基于微服务构成的应用程序通常将使用这些通信样式的组合。 最常见的类型时调用常规的 Web API HTTP 服务，将使用类似 HTTP/HTTPS 同步协议的单个接收方通信。 微服务通常还使用微服务之间进行异步通信的消息传递协议。

这些轴不很有必要知道，以便清楚起见对可能出现的通信机制，但它们不是生成微服务时的重要问题。 集成微服务时，所选协议的客户端线程执行即使的异步性质的异步性质是重要事项。 什么*是*重要正在能够将集成你微服务以异步方式同时保持独立微服务，如下面的部分中所述。

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>异步微服务集成将强制使用微服务构成的自主性

如前文所述，生成基于微服务的应用程序时，重要的一点是集成你微服务的方法。 理想情况下，你应尝试尽量减少内部微服务之间的通信。 较少之间的通信微服务，越好。 但当然，在许多情况下你将需要以某种方式集成微服务。 当你需要执行此操作时，关键的规则是微服务之间的通信应为异步。 并不意味着你需要使用特定协议 （例如，异步消息传送与同步 HTTP）。 它只是微服务之间的通信应仅通过以异步方式将数据传播完成，但不是尝试依赖于其他内部微服务作为初始服务的 HTTP 请求/响应操作的一部分。

如果可能，永远不会依赖于多个微服务，即使对于查询之间的同步通信 （请求/响应）。 每个微服务的目标是为自治上并供客户端使用者，即使是端到端应用程序的一部分的其他服务都已关闭或不正常。 如果你认为中的需要进行其他微服务 （如执行 HTTP 请求的数据查询） 从一个 microservice 调用以便能够提供对客户端应用程序的响应，必须将不会某些弹性的体系结构微服务失败。

此外，不仅有 HTTP 依赖项之间微服务，如图 4-15 的第一部分中所示，使用 HTTP 请求/响应周期创建长时请求链，使你微服务不自治但其性能也是影响只要该链中的服务之一表现不佳。 

越添加微服务，例如查询请求之间的同步依赖关系，总体响应时间获取客户端应用程序的事情就越麻烦。

![](./media/image15.png)

**图 4-15**。 反模式和微服务之间的通信模式

如果你的 microservice 需要提升另一个微服务中的其他操作，如果可能，请不要执行该操作以同步方式和作为原始的微服务请求和答复操作的一部分。 而应以异步方式执行 （使用异步消息传送或集成事件、 队列，等等）。 但是，尽可能多地，不调用同步作为原始的同步请求和答复操作的一部分操作。

最后 （，这是其中大部分问题出现时生成微服务），如果初始 microservice 需要最初归其他微服务的数据时，不依赖于发出该数据的同步请求。 而是复制或传播到初始服务的数据库数据 （仅需要的属性），通过使用最终一致性 （通常通过使用集成事件，如在后面几节所述）。

如前文所述的部分中[标识每个微服务的域模型边界](#identifying-domain-model-boundaries-for-each-microservice)，复制跨多个微服务的某些数据不是设计错误 — 相反，当执行操作，您可以将数据转换到特定语言或其他域或绑定上下文的条款。 例如，在[eShopOnContainers](http://aka.ms/MicroservicesArchitecture)具有名为含有名为用户的实体都负责大部分用户的数据的 identity.api 微服务构成的应用程序。 但是，当你需要存储有关排序微服务内的用户数据，则将其存储作为名为 Buyer 不同实体。 买方实体共享相同的标识与原始用户实体，但它可能具有仅需要按排序域和而非整个用户配置文件的几个属性。

你可以使用任何协议进行通信和数据以异步方式在之间传播微服务以便具有最终一致性。 如前文所述，你可以使用集成事件，请使用事件总线或 broker 或你甚至可以通过轮询其他服务改为使用 HTTP 的消息。 并不重要。 重要的规则是创建您微服务之间的同步依赖关系。

以下各节介绍你可以考虑使用基于微服务构成的应用程序中的多个通信样式。

## <a name="communication-styles"></a>通信样式

有许多协议和你可以将用于通信，具体取决于你想要使用的通信类型的选项。 如果你使用的一种同步基于请求/响应的通信机制，协议，如 HTTP 和 REST 的方法是最常见的尤其是如果您要发布你的 Docker 主机或 microservice 群集外部服务。 如果内部 （在你的 Docker 主机或微服务群集） 的服务之间通信可能还想要使用二进制格式 （如 Service Fabric 远程处理或 WCF 中使用 TCP 和二进制格式） 的通信机制。 或者，你可以使用基于消息的异步通信机制，例如 AMQP。

也有多个消息格式，如 JSON 或 XML 或甚至是二进制格式，可能会更有效。 如果你选择的二进制格式不是一种标准，它可能并不是一个好办法公开发布你的服务使用该格式。 你微服务之间进行内部通信都可以使用非标准的格式。 （Docker orchestrators 或 Azure Service Fabric） 的你的 Docker 主机或 microservice 群集内或专有的客户端应用程序与微服务通信的微服务之间进行通信时，你可能需要这样做。

### <a name="requestresponse-communication-with-http-and-rest"></a>使用 HTTP 和 REST 请求/响应通信 

当客户端使用请求/响应通信时，它将请求发送到服务，然后服务处理请求并发送回的响应。 请求/响应通信尤其适合对于实时 UI （实时用户接口） 从客户端应用程序查询数据。 因此，在微服务体系结构中你将可能使用此通信机制对于大多数查询，在图 4-16 中所示。

![](./media/image16.png)

**图 4-16**。 使用 HTTP 请求/响应通信 （同步或异步）

当客户端使用请求/响应通信时，它假设，响应将到达在短时间，通常少于一秒或几秒钟后最多。 对于响应延迟，你需要实施基于异步通信[消息传递模式](https://docs.microsoft.com/azure/architecture/patterns/category/messaging)和[消息传送技术](https://en.wikipedia.org/wiki/Message-oriented_middleware)，这是我们在下一部分中介绍的不同方法。

请求/响应通信的常用体系结构样式是[REST](https://en.wikipedia.org/wiki/Representational_state_transfer)。 此方法为基础，并且紧密耦合的[HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)协议，使用 HTTP 谓词，如 GET、 POST 和 PUT。 创建服务时，其余部分将是最常用的体系结构的通信方法。 当你开发 ASP.NET 核心 Web API 服务时，你可以实现 REST 服务。

使用 HTTP REST 服务作为你的接口定义语言时，没有其他值。 例如，如果你使用[Swagger 元数据](http://swagger.io/)来描述服务 API，你可以使用生成可以直接发现和使用你的服务的客户端存根的工具。

### <a name="additional-resources"></a>其他资源

-   **Martin Fowler。Richardson 成熟度模型。** REST 模型的说明。
    [*http://martinfowler.com/articles/richardsonMaturityModel.html*](http://martinfowler.com/articles/richardsonMaturityModel.html)

-   **Swagger。** 官方网站。
    [*http://swagger.io/*](http://swagger.io/)

### <a name="push-and-real-time-communication-based-on-http"></a>推送和基于 HTTP 的实时通信

（通常用于比 REST 的不同目的） 的另一种可能是与更高级别的框架的实时和一对多通信，如[ASP.NET SignalR](https://www.asp.net/signalr)和协议，例如[Websocket](https://en.wikipedia.org/wiki/WebSocket)。

如图 4-17 所示，实时 HTTP 通信意味着你可以将内容推送到连接的客户端，当数据变为可用，而不必等待客户端请求新数据的服务器的服务器代码。

![](./media/image17.png)

**图 4-17**。 一对一实时的异步消息通信

由于实时是通信，客户端应用程序几乎立刻显示所做的更改。 这通常由如 WebSockets，使用多个 Websocket 连接 （每个客户端一个） 协议进行处理。 一个典型示例是当服务同时通信中的许多客户端 web 应用到体育游戏的分数的更改时。


>[!div class="step-by-step"]
[以前](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) [下一步] (异步-消息-基于-communication.md)
