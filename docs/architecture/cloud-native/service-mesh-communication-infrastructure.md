---
title: 服务网格通信基础结构
description: 了解服务网格技术如何简化云原生微服务通信
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 8bb57e990dbf1baf8c246fe4aacfbb2904a251e6
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805748"
---
# <a name="service-mesh-communication-infrastructure"></a>服务网格通信基础结构

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

在本章中，我们探讨了微服务通信的挑战。 我们说过，开发团队需要对后端服务如何相互沟通敏感。 理想情况下，服务间通信越少越好。 但是，由于后端服务通常相互依赖来完成操作，因此并非始终能够避免。

我们探讨了实现同步 HTTP 通信和异步消息传递的不同方法。 在每种情况下，开发人员都肩负着实现通信代码的负担。 通信代码复杂且耗时。 不正确的决策可能会导致严重的性能问题。

一种更现代的微服务通信方法围绕一种名为 *"服务网格*"的新的、快速发展的技术。 [服务网格](https://www.nginx.com/blog/what-is-a-service-mesh/)是一个可配置的基础结构层，具有处理服务到服务的通信、恢复能力和许多交叉问题的能力。 它将这些问题的责任从微服务转移到服务网格层中。 通信从微服务中抽象出来。

服务网格的关键组件是代理。 在云本机应用程序中，代理的实例通常与每个微服务共存。 当它们在单独的进程中执行时，两者是紧密相连的，并且共享相同的生命周期。 此模式称为[侧车模式](https://docs.microsoft.com/azure/architecture/patterns/sidecar)，如图 4-24 所示。

![带侧车的服务网](./media/service-mesh-with-side-car.png)

图 4-24****。 带侧车的服务网

请注意，在上图中，与每个微服务一起运行的代理如何截获消息。 每个代理都可以配置特定于微服务的流量规则。 它了解消息，并可以路由它们跨越您的服务和外部世界。

除了管理服务到服务的通信外，服务网格还提供对服务发现和负载平衡的支持。

配置后，服务网格功能极致。 网格从服务发现终结点检索相应的实例池。 它将请求发送到特定的服务实例，记录结果的延迟和响应类型。 它根据不同因素（包括最近请求的观察延迟）选择最有可能返回快速响应的实例。

服务网格在应用程序级别管理流量、通信和网络问题。 它了解消息和请求。 服务网格通常与容器协调器集成。 Kubernetes 支持一种可扩展的体系结构，可以在其中添加服务网格。

在第 6 章中，我们深入探讨了服务网格技术，包括讨论其体系结构和可用的开源实现。

## <a name="summary"></a>总结

在本章中，我们讨论了云原生通信模式。 我们首先研究前端客户端如何与后端微服务通信。 在此过程中，我们讨论了 API 网关平台和实时通信。 然后，我们研究了微服务如何与其他后端服务通信。 我们研究了同步 HTTP 通信和跨服务的异步消息传递。 我们介绍了 gRPC，这是云原生世界中即将推出的技术。 最后，我们推出了一种名为"服务网格"的快速发展的新技术，该技术可以简化微服务通信。

特别强调托管 Azure 服务，这些服务可帮助在云本机系统中实现通信：

- [Azure 应用程序网关](https://docs.microsoft.com/azure/application-gateway/overview)
- [Azure API 管理](https://azure.microsoft.com/services/api-management/)
- [Azure SignalR 服务](https://azure.microsoft.com/services/signalr-service/)
- [Azure 存储队列](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Azure 服务总线](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure 事件网格](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure 事件中心](https://azure.microsoft.com/services/event-hubs/)

接下来，我们将转向云原生系统中的分布式数据及其带来的益处和挑战。

### <a name="references"></a>参考

- [.NET 微服务：容器化 .NET 应用程序的体系结构](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [为微服务设计服务间通信](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Azure SignalR 服务，一个完全托管的服务，用于添加实时功能](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Azure API 网关入口控制器](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [关于 Azure 库伯内斯服务 （AKS） 中的入口](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [gRPC 文档](https://grpc.io/docs/guides/)

- [适用于 WCF 开发人员的 gRPC](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [将 gRPC 服务与 HTTP API 进行比较](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [使用 .NET 视频构建 gRPC 服务](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[上一页](grpc.md)
>[下一页](database-per-microservice.md)
