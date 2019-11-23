---
title: 为什么建议为 WCF 开发人员使用 gRPC-gRPC for WCF 开发人员
description: 讨论为什么 gRPC 非常适合要迁移到现代体系结构和平台的 WCF 开发人员。
ms.date: 09/02/2019
ms.openlocfilehash: da712e1ceee92f0a1a2661252dcda602f5dde9a0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966948"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a>为什么向 WCF 开发人员推荐 gRPC

在深入探讨 gRPC 的语言和技术之前，有必要讨论为什么 gRPC 是适用于要迁移到 .NET Core 的 WCF 开发人员的正确解决方案，但前提是有可用的替代方法。

## <a name="similarity-to-wcf"></a>与 WCF 的相似性

尽管其实现和方式不同，但使用 gRPC 开发和使用服务的实际经验对于 WCF 开发人员来说都应该非常直观。 使代码可以像客户端和服务器相同的平台上，而无需担心网络的基本目标是相同的。 这两个平台共享声明并实现接口的原则，即使用于声明该接口的过程不同。 你将在第5章中看到，gRPC 映射的不同类型的 RPC 调用非常适合 WCF 服务可用的不同绑定。

## <a name="benefits-of-grpc"></a>GRPC 的优点

GRPC 在其他解决方案上出现的其他原因包括：

### <a name="performance"></a>性能

正如前面所讨论的，使用 HTTP/2 而不是 HTTP/1.1 不再要求用户可读的消息，而是使用更快的更快的二进制协议。 这更有效率于计算机进行分析。 HTTP/2 还支持通过单一连接发送多路复用请求，从而在无需在队列中等待的情况下立即发送响应（HTTP/1.1 中的问题称为 "行式（逾越）阻塞"）。 使用 gRPC 时需要更少的资源，这使其成为适用于移动设备和速度较慢的网络的良好解决方案。

### <a name="interoperability"></a>互操作性

对于所有主要编程语言和平台（包括 .NET、Java、Python、中转、 C++Node.js、Swift、Dart、RUBY 和 PHP），都有一些 gRPC 的工具和库。 由于协议缓冲区的二进制网络格式和每个平台的有效代码生成，开发人员可以构建具有高性能的应用程序，同时仍享有完全的跨平台支持。

### <a name="usability-and-productivity"></a>可用性和生产力

gRPC 是一个综合性 RPC 解决方案。 它在多个语言和平台之间保持一致，并提供出色的工具，其中包含自动生成的很多必需的样板代码，因此，更多的开发人员时间将侧重于业务逻辑。

### <a name="streaming"></a>流式处理

gRPC 具有完全双向流式处理，它为 WCF 的全双工服务提供非常类似的功能。 gRPC 流式处理可通过常规 internet 连接、负载均衡器和服务网格运行。

### <a name="deadlinetimeouts-and-cancellation"></a>截止时间/超时和取消

gRPC 允许客户端指定 RPC 完成的最长时间。 如果超过指定的截止时间，则服务器可以独立于客户端取消该操作。 截止时间和取消可通过进一步的 gRPC 调用进行传播，以帮助强制实施资源使用限制。 超过截止时间时，客户端也可能会中止操作（例如，由于用户交互）。

### <a name="security"></a>安全性

在 TLS 端到端加密连接上使用 HTTP/2 时，gRPC 是隐式的。 支持客户端证书身份验证（请参阅第6章），进一步提高客户端和服务器之间的安全性和信任。

>[!div class="step-by-step"]
>[上一页](network-protocols.md)
>[下一页](protocol-buffers.md)
