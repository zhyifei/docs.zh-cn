---
title: 前端客户端通信
description: 了解前端客户端如何与云本机系统通信
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: af26873381509df7807db6ecb37a7d73669adb37
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989072"
---
# <a name="front-end-client-communication"></a>前端客户端通信

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

在云本机系统中，前端客户端（移动、Web 和桌面应用程序）需要通信通道才能与独立的后端微服务进行交互。  

有哪些选择？

为了简单化，前端客户端可以直接与后端微服务*通信*，如图 4-2 所示。

![将客户端直接连接到服务通信](./media/direct-client-to-service-communication.png)

**图 4-2。** 将客户端直接连接到服务通信

使用此方法，每个微服务都有一个公共终结点，前端客户端可以访问该终结点。 在生产环境中，您将负载均衡器放在微服务前面，按比例路由流量。

虽然易于实现，但直接客户端通信仅对简单的微服务应用程序是可以接受的。 这种模式紧密耦合前端客户的核心后端服务，为许多问题打开了大门，包括：

- 客户端对后端服务重构的易感性。
- 核心后端服务会直接暴露出更大的攻击面。
- 重复每个微服务之间的交叉问题。
- 过于复杂的客户端代码 - 客户端必须跟踪多个终结点，并以弹性方式处理故障。

相反，一个被广泛接受的云设计模式是在前端应用程序和后端服务之间实现[API 网关服务](../microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)。 图案如图 4-3 所示。

![API 网关模式](./media/api-gateway-pattern.png)

**图 4-3。** API 网关模式

在上图中，请注意 API 网关服务如何抽象后端核心微服务。 作为 Web API 实现，它充当*反向代理*，将传入的流量路由到内部微服务。

网关将客户端与内部服务分区和重构隔离。 如果更改后端服务，则可以在不中断客户端的情况下将其用于网关。 这也是您处理交叉问题（如身份、缓存、弹性、计量和限制）的第一道防线。 其中许多交叉问题可以从后端核心服务卸载到网关，从而简化了后端服务。

必须注意保持 API 网关简单快捷。 通常，业务逻辑会远离网关。 复杂的网关有可能成为瓶颈，最终成为一个整体。 较大的系统通常公开按客户端类型（移动、Web、桌面）或后端功能划分的多个 API 网关。 [前端后端](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends)模式为实现多个网关提供了方向。 图案如图 4-4 所示。

![API 网关模式](./media/backend-for-frontend-pattern.png)

**图 4-4。** 前端图案的后端

请注意，在上图中，如何根据客户端类型（Web、移动或桌面应用）将传入流量发送到特定 API 网关。 此方法有意义，因为每个设备的功能因外形、性能和显示限制而异。 通常，与浏览器或桌面应用程序相比，移动应用程序公开的功能较少。 每个网关都可以进行优化，以匹配相应设备的功能和功能。

首先，您可以构建自己的 API 网关服务。 快速搜索 GitHub 将提供许多示例。 但是，有几个框架和商业网关产品可用。

## <a name="ocelot-gateway"></a>Ocelot 网关

对于简单的 .NET 云本机应用程序，您可以考虑[Ocelot 网关](https://github.com/ThreeMammals/Ocelot)。 Ocelot 是为 .NET 微服务创建的开源 API 网关，需要统一的入口点才能进入其系统。 它重量轻、速度快、可扩展。

与任何 API 网关一样，其主要功能是将传入的 HTTP 请求转发到下游服务。 此外，它还支持可在 .NET Core 中间件管道中配置的各种功能。 其功能集显示在下表中。

|Ocelot 功能  | |
| :-------- | :-------- |
| 路由 | 身份验证 |
| 请求聚合 | 授权 |
| 服务发现（与领事和尤里卡） | 限制 |
| 负载平衡 | 日志记录、跟踪 |
| Caching | 标题/查询字符串转换 |
| 关联传递 | 自定义中间件 |
| 服务质量 | 重试策略 |

每个 Ocelot 网关指定 JSON 配置文件中的上游和下游地址和可配置功能。 客户端向 Ocelot 网关发送 HTTP 请求。 收到后，Ocelot 会通过其管道将 HttpRequest 对象传递到其配置指定的状态。 在管道结束时，Ocelot 会创建一个新的 HTTPResponseObject 并将其传递到下游服务。 对于响应，Ocelot 将反转管道，将响应发送回客户端。

Ocelot 可作为 NuGet 软件包提供。 它针对 NET 标准 2.0，使其与 .NET Core 2.0+ 和 .NET 框架 4.6.1+ 运行时兼容。 Ocelot 与任何讲 HTTP 并在 .NET Core 支持的平台上运行的函数集成：Linux、macOS 和 Windows。 Ocelot 是可扩展的，支持许多现代平台，包括 Docker 容器、Azure 库伯奈斯服务或其他公共云。  Ocelot 与开源套餐集成，如[领事](https://www.consul.io)[、GraphQL](https://graphql.org)和 Netflix 的[Eureka。](https://github.com/Netflix/eureka)

请考虑 Ocelot 的简单云原生应用程序，这些应用程序不需要商业 API 网关的丰富功能集。

## <a name="azure-application-gateway"></a>Azure 应用程序网关

对于简单的网关要求，可以考虑[Azure 应用程序网关](https://docs.microsoft.com/azure/application-gateway/overview)。 它作为 Azure [PaaS 服务](https://azure.microsoft.com/overview/what-is-paas/)提供，它包括基本的网关功能，如 URL 路由、SSL 终止和 Web 应用程序防火墙。 该服务支持[第 7 层负载平衡](https://www.nginx.com/resources/glossary/layer-7-load-balancing/)功能。 使用第 7 层，您可以基于 HTTP 消息的实际内容路由请求，而不仅仅是低级 TCP 网络数据包。

在这本书中，我们宣传在[库伯内斯](https://www.infoworld.com/article/3268073/what-is-kubernetes-your-next-application-platform.html)托管云原生系统。 Kubernetes 是容器协调器，可自动处理容器化工作负载的部署、扩展和操作问题。 Azure 应用程序网关可以配置为[Azure 库伯奈斯服务群集的](https://azure.microsoft.com/services/kubernetes-service/)API 网关。

应用程序[网关入口控制器](https://azure.github.io/application-gateway-kubernetes-ingress/)使 Azure 应用程序网关能够直接与[Azure 库伯奈斯服务](https://azure.microsoft.com/services/kubernetes-service/)配合使用。 图 4.5 显示了体系结构。

![应用程序网关入口控制器](./media/application-gateway-ingress-controller.png)

**图 4-5。** 应用程序网关入口控制器

Kubernets 包括一个内置功能，支持 HTTP （7 级） 负载平衡，称为[入口](https://kubernetes.io/docs/concepts/services-networking/ingress/)。 入口定义了一组规则，用于如何将 AKS 内的微服务实例暴露给外部世界。 在上一个映像中，入口控制器解释为群集配置的入口规则，并自动配置 Azure 应用程序网关。 根据这些规则，应用程序网关将流量路由到在 AKS 内运行的微服务。 入口控制器侦听入口规则的更改，并相应更改 Azure 应用程序网关。

## <a name="azure-api-management"></a>Azure API 管理

对于中度到大规模云本机系统，可以考虑 Azure [API 管理](https://azure.microsoft.com/services/api-management/)。 它是一种基于云的服务，不仅可满足您的 API 网关需求，而且还提供功能齐全的开发人员和管理体验。 API 管理如图 4-6 所示。

![Azure API 管理](./media/azure-api-management.png)

**图 4-6。** Azure API 管理

首先，API 管理公开了允许基于可配置规则和策略对后端服务的受控访问的网关服务器。 这些服务可以位于 Azure 云、上置数据中心或其他公共云中。 API 密钥和 JWT 令牌确定谁可以执行哪些操作。 出于分析目的，记录所有流量。

对于开发人员，API 管理提供了一个开发人员门户，提供对用于调用服务、文档和示例代码的访问。 开发人员可以使用 Swagger/Open API 来检查服务终结点并分析它们的使用情况。 该服务适用于主要开发平台：.NET、Java、Golang 等。

发布者门户公开管理仪表板，管理员在仪表板中公开 API 并管理其行为。 可以授予服务访问权限、监视服务运行状况以及收集服务遥测。 管理员将*策略*应用于每个终结点以影响行为。 [策略](https://docs.microsoft.com/azure/api-management/api-management-howto-policies)是预先构建的语句，每个服务调用按顺序执行。  策略配置为入站呼叫、出站呼叫或在错误时调用。 策略可以应用于不同的服务范围，以便在组合策略时启用确定性排序。 该产品附带了大量预先构建[的策略](https://docs.microsoft.com/azure/api-management/api-management-policies)。

以下是策略如何影响云原生服务的行为的示例：  

- 限制服务访问。
- 强制实施身份验证。  
- 如有必要，从单个源进行节流呼叫。
- 启用缓存。
- 阻止来自特定 IP 地址的呼叫。
- 控制服务流。
- 将请求从 SOAP 转换为 REST 或在不同的数据格式（如从 XML 转换为 JSON）之间。

Azure API 管理可以公开托管在云或数据中心的任何地方的后端服务。 对于可能在云本机系统中公开的旧式服务，它同时支持 REST 和 SOAP API。 甚至其他 Azure 服务也可通过 API 管理公开。 您可以将托管 API 放在 Azure 支持服务（如[Azure 服务总线](https://azure.microsoft.com/services/service-bus/)或[Azure 逻辑应用](https://azure.microsoft.com/services/logic-apps/)）之上。 Azure API 管理不包括内置负载平衡支持，应与负载平衡服务结合使用。

Azure API 管理可在[四个不同的层中](https://azure.microsoft.com/pricing/details/api-management/)：

- 开发人员
- Basic
- Standard
- Premium

开发人员层用于非生产工作负载和评估。 其他层提供更高的功率、功能和更高的服务级别协议 （SL）。 高级层提供[Azure 虚拟网络和](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview)[多区域支持](https://docs.microsoft.com/azure/api-management/api-management-howto-deploy-multi-region)。 所有层每小时都有固定价格。

最近，Microsoft 发布了 Azure [API 管理的 API 管理无服务器层](https://azure.microsoft.com/blog/announcing-azure-api-management-for-serverless-architectures/)。 该服务称为*消耗定价层*，是围绕无服务器计算模型设计的 API 管理的变体。 与之前显示的"预分配"定价层不同，消费层提供即时预配和按行动付费定价。

它为以下用例启用 API 网关功能：

- 使用无服务器技术（如 Azure[函数](https://docs.microsoft.com/azure/azure-functions/functions-overview)和[Azure 逻辑应用](https://azure.microsoft.com/services/logic-apps/)）实现的微服务。
- Azure 支持服务资源，如服务总线队列和主题、Azure 存储等。
- 微服务，其中流量偶尔有大峰值，但大部分时间仍然很低。

消耗层使用相同的基础服务 API 管理组件，但使用基于动态分配的资源的完全不同的体系结构。 它与无服务器计算模型完美一致：

- 没有要管理的基础结构。
- 无空闲容量。
- 高可用性。
- 自动缩放。
- 成本基于实际使用情况。
  
对于将无服务器资源公开为 API 的云原生系统而言，新的消费层是一个很好的选择。

> 在编写本文时，消费层处于 Azure 云中的预览状态。

## <a name="real-time-communication"></a>实时通信

实时通信或推送通信是前端应用程序通过 HTTP 与后端云原生系统通信的另一个选项。 应用程序（如财务代码、在线教育、游戏和工作进度更新）需要后端的即时实时响应。 使用正常的 HTTP 通信，客户端无法知道何时有新数据可用。 客户端必须持续*轮询*或向服务器发送请求。 通过*实时*通信，服务器可以随时将新数据推送到客户端。

实时系统通常以高频数据流和大量并发客户端连接为特征。 手动实现实时连接可能会很快变得复杂，需要非普通基础架构来确保可伸缩性和向连接的客户端发送可靠的消息。 您可以发现自己管理 Azure Redis Cache 的实例和一组负载均衡器，这些平衡器配置了用于客户端相关性的粘性会话。

[Azure SignalR 服务](https://azure.microsoft.com/services/signalr-service/)是一种完全托管的 Azure 服务，可简化云原生应用程序的实时通信。 技术实现详细信息（如容量配置、扩展和持久连接）被抽象化。 他们处理你与99.9%的服务级别协议。 您专注于应用程序功能，而不是基础结构管道。

启用后，基于云的 HTTP 服务可以直接将内容更新推送到连接的客户端，包括浏览器、移动和桌面应用程序。 客户端将更新，而无需轮询服务器。 Azure SignalR 抽象了创建实时连接的传输技术，包括 WebSocket、服务器端事件和长期轮询。 开发人员专注于向连接客户端的所有或特定子集发送消息。

图 4-7 显示了一组 HTTP 客户端，这些客户端连接到启用了 Azure SignalR 的云本机应用程序。

![Azure SignalR](./media/azure-signalr-service.png)

**图 4-7。** Azure SignalR

Azure SignalR 服务的另一个优势是实现无服务器云本机服务。 也许您的代码是按需使用 Azure 函数触发器执行的。 这种情况可能比较棘手，因为代码不会与客户端保持长连接。 Azure SignalR 服务可以处理这种情况，因为该服务已为用户管理连接。

Azure SignalR 服务与其他 Azure 服务（如 Azure SQL 数据库、服务总线或 Redis Cache）紧密集成，为云本机应用程序开辟了许多可能性。

>[!div class="step-by-step"]
>[上一页](communication-patterns.md)
>[下一页](service-to-service-communication.md)
