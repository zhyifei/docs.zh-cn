---
title: 针对 WCF 开发人员的负载均衡 gRPC-gRPC
description: 选择要使用 gRPC services 的负载均衡器。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841551"
---
# <a name="load-balancing-grpc"></a>负载均衡 gRPC

GRPC 应用程序的典型部署包含多个相同的服务实例，提供复原能力和水平可扩展性。 跨这些实例对分布式传入请求进行负载均衡，以完全利用所有可用资源。 若要使此负载平衡对客户端不可见，通常使用代理负载均衡器服务器来处理来自客户端的请求，并将这些请求路由到后端实例。

负载均衡器根据其运行的*层*进行分类。 第4层负载均衡器适用于*传输*级别，例如，使用 TCP 套接字、连接和数据包。 第7层负载均衡器在*应用程序*级别工作，专用于处理 gRPC 应用程序的 HTTP/2 请求。

## <a name="l4-load-balancers"></a>L4 负载均衡器

L4 负载均衡器接受来自客户端的 TCP 连接请求，打开与某个后端实例的另一个连接，并在两个连接之间复制数据，无实际处理。 L4 提供出色的性能和低延迟，但控制或智能非常少。 只要客户端使连接保持打开状态，所有请求都将定向到相同的后端实例。

下面是一个 L4 负载均衡器的示例： [Azure 负载均衡器](https://azure.microsoft.com/services/load-balancer/)。

## <a name="l7-load-balancers"></a>L7 负载均衡器

L7 负载均衡器分析传入的 HTTP/2 请求，并按请求将这些请求按请求传递到后端实例，无论客户端保持连接的时间长短。

L7 负载均衡器的示例包括：

- [Nginx](https://www.nginx.com/)
- [HAproxy](https://www.haproxy.com/)
- [Traefik](https://traefik.io/)

作为经验法则，L7 负载均衡器是 gRPC 和其他 HTTP/2 应用程序（事实上，对于 HTTP 应用程序）的最佳选择。 L4 负载均衡器*适用*于 gRPC 应用程序，但在低延迟和低开销的重要性最高时，它们主要非常有用。

> [!IMPORTANT]
> 撰写本文时，并非所有 L7 负载均衡器都支持 gRPC 服务所需的 HTTP/2 规范的所有部分，例如尾随标头。

使用 TLS 加密时，负载均衡器可以终止 TLS 连接并将未加密的请求传递到后端应用程序，或传递加密的请求。 无论采用哪种方式，都需要将负载均衡器配置为具有服务器的公钥和私钥，以便它可以解密处理请求。

请参阅首选负载均衡器的文档，了解如何将其配置为通过后端服务处理 HTTP/2 请求。

## <a name="load-balancing-within-kubernetes"></a>Kubernetes 中的负载均衡

有关 Kubernetes 上内部服务之间的负载平衡的讨论，请参阅[服务网格部分](service-mesh.md)。

>[!div class="step-by-step"]
>[上一页](service-mesh.md)
>[下一页](application-performance-management.md)
