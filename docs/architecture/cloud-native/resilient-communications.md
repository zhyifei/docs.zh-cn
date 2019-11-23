---
title: 可复原通信
description: 构建适用于 Azure 的云本机 .NET 应用 |弹性通信
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "73841221"
---
# <a name="resilient-communications"></a>弹性通信

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

在本指南中，我们已 evangelized 了超越传统的单一应用程序设计并使用基于微服务的体系结构，在该体系结构中，一组分布式、独立服务独立运行并与每个服务通信其他使用标准通信协议，例如 HTTP 和 HTTPS。 尽管此类体系结构会为你提供许多重要的好处，但它也带来了许多挑战。 例如，请考虑以下问题：

- *进程外网络通信。* 每个服务通过网络协议进行通信，该协议引入了网络拥塞、延迟和暂时性故障。
- *服务发现。* 每个服务都在使用其自己的 IP 地址和端口的计算机群集上运行，服务如何彼此发现并相互通信？
- *复原.* 如何管理短暂的故障并使系统保持稳定？
- *负载均衡。* 如何将入站流量分布到多个服务实例？
- *安全性。* 安全问题（例如传输级加密和证书管理）如何强制实施？
- *分布式监视。* -你如何跨多个使用服务的单个请求关联和捕获可跟踪性和监视？

尽管可以使用各种库和框架来解决这些问题，但在代码库中实现它们可能会消耗大量资源、复杂且耗时。 而且，最终会出现一个解决方案，其中基础结构问题与业务逻辑耦合在一起。

## <a name="service-mesh"></a>服务网格

更好的方法是，考虑一种新的、快速发展的技术，该技术以*服务网格*为依据。 [服务网格](https://www.nginx.com/blog/what-is-a-service-mesh/)是一种可配置的基础结构层，其中内置了用于处理服务通信的功能和上面提到的许多挑战。 它将这些问题从业务代码中分离出来，并将其移到服务代理（每个服务附带的实例）中。 服务网格代理通常称为[挎斗模式](https://docs.microsoft.com/azure/architecture/patterns/sidecar)，可将其部署到单独的进程中，以提供业务代码的隔离和封装。 但是，该代理与正在创建的服务以及共享其生命周期的方法密切相关。 图6-9 显示了这种情况。

![使用侧面汽车的服务网格](./media/service-mesh-with-side-car.png)

图 6-9。 使用侧面汽车的服务网格

在上图中，请注意代理如何截获和管理微服务与群集之间的通信。

服务网格以逻辑方式拆分为两个不同的组件：[数据平面](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)和[控制平面](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)。 图6-10 显示了这些组件及其责任。

![服务网格控制和数据平面](./media/istio-control-and-data-plane.png)

**图6-10。** 服务网格控制和数据平面

一旦配置后，服务网格就会非常有效。 它可以从服务发现终结点中检索相应的实例池。 然后，它可以将请求发送到特定的实例，记录结果的延迟和响应类型。 网格可以根据许多因素选择最有可能返回快速响应的实例，包括其观察到的最近请求的延迟。

如果实例无响应或失败，网格可以在另一个实例上重试该请求。 如果池总是返回错误，则网格可以将其从负载平衡池中逐出，以后在修复后定期重试。 如果请求超时，网格可能会失败，然后重试该请求。 网格以度量值和分布式跟踪的形式捕获行为，然后可以将其发送到集中式指标系统。

## <a name="istio-and-envoy"></a>Istio 和 Envoy

虽然目前存在一些服务网格选项，但在撰写本文的时候， [Istio](https://istio.io/docs/concepts/what-is-istio/)是最常用的。 这是一种可集成到新的或现有的分布式应用程序中的开源产品，来自 IBM、Google 和 Lyft 的合作。 它提供一致的完整解决方案来保护、连接和监视微服务。 其功能包括：

- 使用基于标识的强身份验证和授权在群集中保护服务间通信。
- 自动负载均衡，适用于 HTTP、 [gRPC](https://grpc.io/)、WEBSOCKET 和 TCP 流量。
- 通过丰富的路由规则、重试、故障转移和故障注入对流量行为进行精细控制。
- 支持访问控制、速率限制和配额的可插入策略层和配置 API。
- 针对群集中的所有流量（包括流入和出口）的自动指标、日志和跟踪。

Istio 实现的关键组件是一种名为[Envoy 代理](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)的代理服务。 从 Lyft 开始，到[云本机计算基础](https://www.cncf.io/)（在第1章讨论），Envoy 代理与每个服务一起运行，并为以下功能提供平台无关的基础：

- 动态服务发现。
- 负载平衡。
- TLS 终止。
- HTTP 和 gRPC 代理。
- 断路器复原。
- 运行状况检查。
- [用不](https://martinfowler.com/bliki/CanaryRelease.html)到的部署滚动更新。

如前文所述，Envoy 作为挎斗部署到群集中的每个微服务。

## <a name="integration-with-azure-kubernetes-services"></a>与 Azure Kubernetes 服务集成

Azure 云支持 Istio，并在 Azure Kubernetes 服务中提供对该服务的直接支持。 以下链接可帮助你入门：

- [在 AKS 中安装 Istio](https://docs.microsoft.com/azure/aks/istio-install)
- [使用 AKS 和 Istio](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
>[上一页](infrastructure-resiliency-azure.md)
>[下一页](monitoring-health.md)
