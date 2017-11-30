---
title: "直接与 API 网关模式的微服务构成客户端通信"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |直接与 API 网关模式的微服务构成客户端通信"
keywords: "Docker 微服务、 ASP.NET、 容器、 API 网关"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8227ec47888c7cf361f34c4c85a09c0666f886e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>直接与 API 网关模式的微服务构成客户端通信

在微服务体系结构，每个微服务公开一组 （通常） fine‑grained 终结点。 这种情况可能会影响 client‑to‑microservice 通信，如本部分中所述。

## <a name="direct-client-to-microservice-communication"></a>直接微服务构成客户端通信

可能的方法是使用直接微服务构成客户端通信体系结构。 在此方法中，客户端应用程序可以直接向提出请求一些微服务，如图 4-12 中所示。

![](./media/image12.png)

**图 4-12**。 使用直接微服务构成客户端通信体系结构

在这种方法。 每个微服务具有有时具有每个微服务的其他 TCP 端口的公共终结点。 为特定服务的 URL 的示例可能是在 Azure 中的以下 URL:

<http://eshoponcontainers.westus.cloudapp.azure.com:88 />

在生产环境中基于 URL 将映射到负载平衡器使用在群集中的群集，这反过来之间分配请求微服务。 在生产环境中，你可以像应用程序传递控制器 (ADC) [Azure 应用程序网关](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction)你微服务和 Internet 之间。 充当一个透明层之间进行负载平衡，不仅保护你的服务通过提供 SSL 终止。 这将通过卸载 CPU 密集型 SSL 终止和 Azure 应用程序网关到其他路由职责提高你的主机的负载。 在任何情况下，负载平衡器和 ADC 都是从逻辑的应用程序体系结构角度来看透明的。

直接微服务构成客户端通信体系结构无法对已经足够好一个小基于微服务构成的应用程序，尤其是当客户端应用程序服务器端 web 应用程序，如 ASP.NET MVC 应用程序。 但是，当你生成大型和复杂基于微服务构成的应用程序 （例如，当处理大量微服务类型），并且尤其是在客户端应用程序是远程的移动应用或 SPA web 应用程序时，该方法将面临一些问题。

开发大型应用程序基于微服务时，请考虑以下问题：

-   *如何客户端应用程序最大程度减少到后端的请求数和减少到多个微服务的聊天式通信？*

通过 Internet 与多个微服务生成单个 UI 屏幕进行交互增加往返的次数。 这会增加延迟和 UI 一端的复杂性。 理想情况下，响应应进行高效聚合服务器端中 — 这一功能减少了延迟，因为数据的多个部分回来并行和某些用户界面可以显示数据，只要它是准备。

-   *如何处理如授权、 数据转换和动态请求调度的跨领域问题？*

实现安全和跨领域问题，如安全和授权上每个微服务可能需要大量的开发工作。 可能的方法是让在 Docker 主机或内部群集中，这些服务，以便从外部，限制对它们的直接访问和实现在一个集中的位置，例如，API 网关的这些跨领域问题。

-   *客户端应用程序如何使用非 internet 协议的服务进行通信？*

通常客户端应用中不支持使用在服务器端 （如 AMQP 或二进制协议） 协议。 因此，必须通过类似 HTTP/HTTPS 协议执行请求并将其转换为其他协议之后。 A*拦截中*方法可帮助在此情况下。

-   *你可以如何形成尤其是对移动应用的外观？*

多个微服务的 API 可能并非很好地设计为不同的客户端应用程序的需求。 例如，移动应用程序的需求可能不同于 web 应用程序的需求。 对于移动应用程序，你可能需要进一步优化，以便数据响应可能更有效。 你可能会执行此方法是从多个微服务聚合数据并返回单个组数据，并有时消除不需要的移动应用程序的响应中的任何数据。 并且，当然，你可能会压缩该数据。 同样，外观或移动应用程序和微服务之间的 API 会很方便对于此方案。

## <a name="using-an-api-gateway"></a>使用 API 网关

当你在设计和构建大型或复杂基于微服务构成的应用程序使用多个客户端应用程序时，可以是一个不错的方法要考虑[API 网关](http://microservices.io/patterns/apigateway.html)。 这是提供单一入口点，对于某些微服务的组的服务。 它是类似于[外观模式](https://en.wikipedia.org/wiki/Facade_pattern)从 object‑oriented 设计，但在此情况下，它是一个分布式系统的一部分。 API 网关模式有时也称为"后端个前端" [(BFF)](http://samnewman.io/patterns/architectural/bff/)因为构建时考虑客户端应用程序的需求。

图 4-13 演示如何自定义 API 网关可以放入基于微服务的体系结构。
务必要在该关系图中突出显示的你将会使用面向多个单个自定义 API 网关服务和不同的客户端应用。 因为你的 API 网关服务将不断增长和演化，事实可以是重要的风险基于从客户端应用程序的许多不同的要求。 最终，它将是臃肿由于这些不同的需求而有效地它可以是非常类似于整体应用程序或整体服务。 正因为如此很大程度建议例如拆分多个服务或多个较小 API 网关，每个外形规格类型之一中的 API 网关。

![](./media/image13.png)

**图 4-13**。 使用 API 网关实现为自定义的 Web API 服务

在此示例中，将作为运行作为容器的自定义 Web API 服务实现 API 网关。

如前文所述，应实现多个 API 网关，以便你可以为每个客户端应用程序的需求的不同外观。 每个 API 网关可以提供其他 API 针对每个客户端应用程序中，可能是甚至基于客户端外形因素通过实现哪些在调用多个内部微服务特定的适配器代码。

由于自定义 API 网关通常是数据聚合器，你需要请小心使用它。 通常，它不具有一个 API 网关聚合所有内部微服务应用程序的一个好办法。 如果是这样，它充当整体聚合器或 orchestrator，并与冲突 microservice 自主性耦合所有微服务。 因此，API 网关应分离取决于业务边界和不 act 作为聚合器对整个应用程序。

有时精细 API 网关可以独自，同时 microservice，甚至可以安排域或公司名称和相关的数据。 具有的业务或域由指定的 API 网关的边界将帮助你获得更好的设计。

API 网关层中的粒度可能更高级复合 UI 根据对应用程序微服务，尤其有用，因为细化 API 网关的概念是类似于 UI 组合服务。 我们将讨论这更高版本中[创建复合 UI 基于微服务](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices)。

因此，对于许多中等和较大的规模应用程序，使用自定义 API 网关通常是一个不错的方法，但不是作为一个整体的聚合器或唯一中央自定义 API 网关。

另一种方法是使用这样的产品[Azure API 管理](https://azure.microsoft.com/services/api-management/)图 4-14 中所示。 此方法不仅解决了你 API 网关的需求，但提供功能，如收集 insights 从您的 Api。 如果你使用 API 管理解决方案，API 网关是仅在该完整的 API 管理解决方案中的组件。

![](./media/image14.png)

**图 4-14**。 使用 Azure API 管理 API 网关

在这种情况下，当使用 Azure API 管理中，你可能具有单个 API 网关这样的产品不是因此危险因为这些类型的 API 网关是"越窄"，这意味着你不实现的自定义 C# 代码可能演变朝向整体组件。 

这种类型的产品更像的入站通信，你可以还筛选从内部微服务的 Api 和应用于此单个层中的已发布的 Api 的授权的反向代理。

Insights 可从 API 管理系统帮助你了解如何使用您的 API 的性能如何。 这样做允许您查看接近实时分析报表，确定可能会影响你的业务的趋势。 此外，你可以有关请求和响应的活动，以进行进一步联机和脱机的分析日志。

使用 Azure API 管理中，你可以保护您的 Api 使用密钥、 令牌，和 IP 筛选。 这些功能允许你强制执行灵活和细化配额和速率限制，修改的形状和使用策略，您的 api 的行为，并随着响应缓存可以提高性能。

在本指南和参考示例应用程序 (eShopOnContainers) 中，我们以便将重点放在纯容器上而无需使用 PaaS 产品，如 Azure API 管理限制到一种更简单的自定义的容器化体系结构的体系结构。 但对于大型基于微服务构成的应用程序部署到 Microsoft Azure，我们建议你查看并为您的 API 网关作为基础采用 Azure API 管理。

## <a name="drawbacks-of-the-api-gateway-pattern"></a>API 网关模式的缺点

-   最重要的缺点是，当您实现 API 网关，你将与内部微服务耦合该层。 此类耦合可能会引入你的应用程序的严重问题。 Clemens Vaster，架构师在 Azure Service Bus 团队中，引用此潜在的难度，可与"新 ESB"在他"[消息传递和微服务](https://www.youtube.com/watch?v=rXi5CLjIQ9k)"会话在 GOTO 2016。

-   使用微服务 API 网关创建其他可能单点故障。

-   API 网关可以引入响应时间变的长由于其他网络调用。 但是，此额外调用通常具有不是让客户端接口是太烦琐直接调用内部的微服务的影响更小。

-   如果不正确扩展，API 网关可能成为瓶颈。

-   如果它包括自定义逻辑和数据聚合，API 网关需要额外的开发成本和将来的维护。 开发人员必须更新 API 网关，以便公开每个微服务的终结点。 此外，在内部微服务的实现更改可能会导致 API 网关级别的代码更改。 但是，如果安全、 日志记录和版本控制，只需将应用 API 网关 （比如在使用 Azure API 管理），此额外的开发成本可能不适用于。

-   如果 API 网关开发了一个组，可以有开发瓶颈。 这是为什么更好的方法是让多个细粒度 API 网关对不同的客户端需要作出响应的另一个原因。 你无法为多个区域或图层所拥有的不同的团队处理内部微服务内部分离 API 网关。

## <a name="additional-resources"></a>其他资源

-   **Charles Richardson。模式： API 网关 / 后的端前端**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Azure API 管理**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan。面向服务的组合**\
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters。消息传递和微服务在 GOTO 2016** （视频） [ *https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[以前](标识-微服务构成的域-模型-boundaries.md) [下一步] (通信-中的微服务-architecture.md)
