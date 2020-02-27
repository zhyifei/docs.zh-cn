---
title: 网络协议-适用于 WCF 开发人员的 gRPC
description: GRPC 网络协议的概述。
ms.date: 09/02/2019
ms.openlocfilehash: 1ceb140f7b7ac7e796a87612ebb9d21e28d33968
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628483"
---
# <a name="network-protocols"></a>网络协议

与 Windows Communication Foundation （WCF）不同，gRPC 使用 HTTP/2 作为其网络的基础。 这与 WCF 和 SOAP 相比具有明显的优势，后者仅在 HTTP/1.1 上操作。 对于想要使用 gRPC 的开发人员，如果没有 HTTP/2 的替代方法，则似乎更详细地探讨 HTTP/2，并识别使用 gRPC 的其他优点。

HTTP/2 （由2015中的 Internet 工程任务组发布）派生自 Google 已在使用的实验 SPDY 协议。 它经过专门设计，比 HTTP/1.1 更高效、更快、更安全。

## <a name="key-features-of-http2"></a>HTTP/2 的主要功能

此列表显示了 HTTP/2 的一些主要功能和优势：

### <a name="binary-protocol"></a>二进制协议

请求/响应周期不再需要文本命令。 这可以简化和加速命令的实现。 具体而言，分析数据的速度更快，使用的内存更少，网络延迟会因速度的明显相关改进而降低，同时还能提供更好的网络资源。

### <a name="streams"></a>流

流允许你在发送方和接收方之间创建长时间连接，可以通过这些连接以异步方式发送多个消息或帧。 多个流可以独立于单个 HTTP/2 连接进行操作。

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>通过单个 TCP 连接请求多路复用

此功能是 HTTP/2 最重要的一项创新。 因为它允许对数据进行多次并行请求，所以现在可以从一台服务器同时下载 web 文件。 网站加载速度更快，并减少了优化需求。 已准备就绪的标头（逾越）阻塞，在之前的请求完成之前，必须等待发送响应（尽管在 TCP 传输级别仍可能出现闭锁阻塞）。

### <a name="nettcp-like-performance-cross-platform"></a>Net.tcp 类似的性能，跨平台

从根本上讲，gRPC 和 HTTP/2 的组合为开发人员提供了与 WCF 的 Net.tcp 绑定相同的速度和效率，在某些情况下，其速度更快，效率更高。 但与 Net.tcp 不同，HTTP/2 上的 gRPC 不会被限制为 .NET 应用程序。

>[!div class="step-by-step"]
>[上一页](interface-definition-language.md)
>[下一页](why-grpc.md)
