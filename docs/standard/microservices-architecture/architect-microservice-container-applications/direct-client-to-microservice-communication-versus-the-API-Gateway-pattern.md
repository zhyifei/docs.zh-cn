---
title: 客户端到微服务直接通信与 API 网关模式
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 客户端到微服务直接通信与 API 网关模式
keywords: Docker, 微服务, ASP.NET, 容器, API 网关
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa3f4bb97cf942ee7698b1efa1dcd09b3f2ca571
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>客户端到微服务直接通信与 API 网关模式

在微服务体系结构中，每个微服务都会公开（通常）一组精细终结点。 这种情况可能会影响客户端到微服务通信，如本节所述。

## <a name="direct-client-to-microservice-communication"></a>客户端到微服务直接通信

使用客户端到微服务直接通信体系结构是一种可行方法。 在此方法中，客户端应用可以直接向某些微服务发出请求，如图 4-12 所示。

![](./media/image12.png)

图 4-12。 使用客户端到微服务直接通信体系结构

在此方法中， 每个微服务都有一个公共终结点，有时每个微服务会有不同的 TCP 端口。 特定服务的 URL 示例可能是 Azure 中的以下 URL：

<http://eshoponcontainers.westus.cloudapp.azure.com:88/>

在基于群集的生产环境中，该 URL 将映射到群集中使用的负载均衡器，该负载均衡器随后在微服务中分布请求。 在生产环境中，可以在微服务和 Internet 之间使用 [Azure 应用程序网关](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction)等应用程序传送控制器 (ADC)。 该控制器将充当透明层，不仅执行负载均衡，还可通过提供 SSL 终端来保护服务。 这通过卸载 CPU 密集型 SSL 终端和其他到 Azure 应用程序网关的路由任务来提高主机负载。 在任何情况下，从逻辑应用程序体系结构的角度看，负载均衡器和 ADC 都是透明的。

客户端到微服务直接通信体系结构已能满足基于微服务的小型应用程序的需求，尤其是在客户端应用为服务器端 Web 应用程序（如 ASP.NET MVC 应用）的情况下。 但是，若要生成基于微服务的大型复杂应用程序（例如处理大量微服务类型），尤其是客户端应用是远程移动应用或 SPA Web 应用程序时，该方法将面临一些问题。

开发基于微服务的大型应用程序时，请考虑以下问题：

-   客户端应用如何最大限度地减少对后端发出的请求数并减少与多个微服务的聊天通信？

与多个微服务交互构建单个 UI 屏幕可增加 Internet 中的往返次数。 这会增加 UI 端的延迟时间和复杂性。 理想情况下，响应会在服务端高效聚合。 这便减少了延迟时间，因为可以并行返回多条数据，并且某些 UI 可在准备就绪后立即显示。

-   如何处理诸如授权、数据转换和动态请求调度之类的整合问题？

在每个微服务上实现安全和授权等安全性和整合问题需要进行大量的开发工作。 其中一种可行方法是在 Docker 主机或内部群集中提供这些服务，以限制从外部直接访问它们，并在集中位置（如 API 网关）实现这些整合问题。

-   客户端应用如何与使用非 Internet 友好协议的服务进行通信？

通常，客户端应用不支持服务端使用的协议（如 AMQP 或二进制协议）。 因此，必须通过 HTTP/HTTPS 等协议执行请求并随后将请求转换为其他协议。 在此情况下，中间人方法可提供帮助。

-   如何塑造一个专为移动应用设计的外观？

多个微服务的 API 设计可能无法满足不同客户端应用程序的需求。 例如，移动应用的需求可能不同于 Web 应用的需求。 移动应用可能需要进一步优化，以便数据响应能更有效。 若要实现这一点，可以聚合多个微服务的数据并返回单组数据，有时还需从响应中删除移动应用不需要的所有数据。 当然，也可以压缩该数据。 同样，在此方案中，使用移动应用和微服务之间的外观或 API 会非常便捷。

## <a name="using-an-api-gateway"></a>使用 API 网关

使用多个客户端应用来设计和生成基于微服务的大型复杂应用程序时，[API 网关](https://microservices.io/patterns/apigateway.html) 是非常不错的方法。 这一服务可为某些微服务组提供单一入口点。 这类似于面向对象设计的[外观模式](https://en.wikipedia.org/wiki/Facade_pattern)，但在此情况下，它是分布式系统的一部分。 因为构建时考虑了客户端应用的需求，所以 API 网关模式有时也称为“用于前端的后端”[(BFF)](https://samnewman.io/patterns/architectural/bff/)。

图 4-13 演示自定义 API 网关如何适应基于微服务的体系结构。
将使用面向多个不同客户端应用的单个自定义 API 网关服务，在该图中突出显示这一点非常重要。 这一事实可能存在很大风险，因为 API 网关服务将根据客户端应用的多种不同要求而不断增长和发展。 最终，它将因这些不同的需求而膨胀，实际上，它会类似于整体式应用程序或整体式服务。 正因如此，强烈建议将 API 网关拆分成多个服务或多个更小的 API 网关（例如每种外形规格一个网关）。

![](./media/image13.png)

图 4-13。 使用作为自定义 Web API 服务实现的 API 网关

在此示例中，API 网关将作为自定义 Web API 服务实现，并作为容器运行。

如前所述，应实现多个 API 网关，以便具备不同外观，满足每个客户端应用的需求。 每个 API 网关可以专为每个客户端应用提供不同的 API，甚至可以通过实现特定的适配器代码（该代码在下方调用多个内部微服务），根据客户端外形规格提供不同 API。

由于自定义 API 网关通常是数据聚合器，因此需要谨慎使用。 通常，不建议使用单个 API 网关聚合应用程序的所有内部微服务。 如果使用这种方式，它将作为整体式聚合器或业务流程协调程序，且会耦合所有微服务，违背微服务的自主性。 因此，应根据业务边界分隔 API 网关，并且不将其用作整个应用程序的聚合器。

有时精细 API 网关自身也可以是微服务，甚至可以包含域或业务名称以及相关数据。 使用由业务或域指示的 API 网关边界将有助于更好地设计。

由于精细 API 网关的概念类似于 UI 组合服务，因此 API 网关层中的粒度特别适用于基于微服务的高级复合 UI 应用程序。 稍后我们将在[创建基于微服务的复合 UI](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices) 中介绍这一点。

因此，对于许多大中型应用程序，使用自定义创建的 API 网关通常是一种好方法，但不能作为单个整体式聚合器或唯一的中央自定义 API 网关。

另一种方法是使用 [Azure API 管理](https://azure.microsoft.com/services/api-management/) 等产品，如图 4-14 所示。 这种方法不仅能够满足 API 网关需求，还提供从 API 收集见解等功能。 如果正在使用 API 管理解决方案，则 API 网关仅是整个 API 管理解决方案中的一个组成部分。

![](./media/image14.png)

图 4-14。 为 API 网关使用 Azure API 管理

在这种情况下，使用如 Azure API 管理之类的产品时，拥有单个 API 网关不会存在较大风险，因为这类 API 网关“更精细”，这意味着不会实现可能发展成整体式组件的自定义 C# 代码。 

这类产品更像是用于入口通信的反向代理，也可以从内部微服务筛选 API，并授权此单层中的已发布 API。

API 管理系统中提供的见解有助于理解 API 的使用方式与性能表现。 通过查看近实时分析报告并标识可能影响业务的趋势，从而实现这一点。 此外，还可获取有关请求和响应活动的日志记录，以进一步进行联机和脱机分析。

借助 Azure API 管理，可以使用密钥、令牌和 IP 筛选器来保护 API。 通过这些功能，可以执行灵活且细化的配额和速率限制，使用策略修改 API 的形状和行为，并通过响应缓存提高性能。

在本指南和参考示例应用程序 (eShopOnContainers) 中，我们仅讨论较简单的自定义容器化体系结构，以便将重点放在未使用 PaaS 产品（如 Azure API 管理）的普通容器上。 但是对于部署到 Microsoft Azure 的基于微服务的大型应用程序，我们建议查看并采用 Azure API 管理作为 API 网关的基础。

## <a name="drawbacks-of-the-api-gateway-pattern"></a>API 网关模式的缺点

-   实现 API 网关时，会将该层与内部微服务进行耦合，这是它的最大缺点。 此类耦合可能会给应用程序带来严重问题。 Azure 服务总线团队的架构师 Clemens Vaster 在 GOTO 2016 的“[Messaging and Microservices](https://www.youtube.com/watch?v=rXi5CLjIQ9k)”（消息传递和微服务）一节中将此潜在问题描述为“新的 ESB”。

-   使用微服务 API 网关创建其他可能的单一故障点。

-   由于其他网络调用，API 网关可能会导致响应时间加长。 但是，相较于经常直接调用内部微服务的客户端接口，这种额外调用的影响更小。

-   如果未正确扩展，API 网关可能成为瓶颈。

-   如果 API 网关包含自定义逻辑和数据聚合，则它需要额外的开发成本并且需要在日后进行维护。 开发人员必须更新 API 网关，公开每个微服务的终结点。 此外，内部微服务中的实现更改可能引起 API 网关级别的代码更改。 但是，如果 API 网关仅应用安全性、日志记录和版本控制（与使用 Azure API 管理时一样），则可能不会产生额外开发成本。

-   如果是由一个团队开发的 API 网关，则可能出现开发瓶颈。 这也是最好使用多个精细 API 网关满足不同客户端需求的另一原因。 还可以将 API 网关内部分隔到多个区域或多个层，这些区域或层由使用内部微服务的不同团队所有。

## <a name="additional-resources"></a>其他资源

-   **Charles Richardson。Pattern: API Gateway / Backend for Front-End**（模式：API 网关/用于前端的后端）
    [https://microservices.io/patterns/apigateway.html](https://microservices.io/patterns/apigateway.html)

-   **Azure API 管理**
    [https://azure.microsoft.com/services/api-management/](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan.Service Oriented Composition**\（面向服务的组合）
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters。Messaging and Microservices at GOTO 2016**（GOTO 2016 的消息传递和微服务）视频[https://www.youtube.com/watch?v=rXi5CLjIQ9k](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[上一页] (identify-microservice-domain-model-boundaries.md) [下一页] (communication-in-microservice-architecture.md)
