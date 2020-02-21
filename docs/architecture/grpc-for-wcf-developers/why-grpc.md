---
title: 为什么我们建议为 wcf 开发人员 gRPC-gRPC for WCF 开发人员
description: 讨论为什么 gRPC 非常适合要迁移到现代体系结构和平台的 WCF 开发人员。
ms.date: 09/02/2019
ms.openlocfilehash: fc93ca4c8f2a28dc4d3a0b0466d19c86273b40b8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503317"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>为什么我们建议为 WCF 开发人员 gRPC

在深入探讨 gRPC 的语言和技术之前，值得探讨为什么 gRPC 是适用于要迁移到 .NET Core 的 Windows Communication Foundation （WCF）开发人员的正确解决方案。

## <a name="similarity-to-wcf"></a>与 WCF 的相似性

虽然实现和方法对于 gRPC 是不同的，但使用 gRPC 开发和使用服务的体验应对 WCF 开发人员来说是直观的。 基本目标是相同的：可以将客户端和服务器置于相同平台上，而无需担心网络。 

这两个平台共享声明并实现接口的原则，即使用于声明该接口的过程不同。 正如你将在第5章中看到的那样，gRPC 支持映射到 WCF 服务可使用的绑定的不同类型的 RPC 调用。

## <a name="benefits-of-grpc"></a>GRPC 的优点

由于以下原因，gRPC 会出现在其他解决方案之上。

### <a name="performance"></a>性能

使用 HTTP/2 而不是 HTTP/1.1 将不再要求用户可读的消息，而是使用更快、更快的二进制协议。 这更有效率于计算机进行分析。 HTTP/2 还支持通过单个连接进行多路复用请求。 通过此支持，可以在无需在队列中等待即可立即发送响应。 （在 HTTP/1.1 中，此问题称为 "线路主管（逾越）阻塞"。）当使用 gRPC 时，需要较少的资源，这使其成为适用于移动设备和速度较慢的网络的良好解决方案。

### <a name="interoperability"></a>互操作性

对于所有主要编程语言和平台（包括 .NET、Java、Python、中转、 C++Node.js、Swift、Dart、RUBY 和 PHP），都有一些 gRPC 的工具和库。 由于协议缓冲区的二进制网络格式和每个平台的有效代码生成，开发人员可以构建具有高性能的应用程序，同时仍享有完全的跨平台支持。

### <a name="usability-and-productivity"></a>易用性和工作效率

gRPC 是一个综合性 RPC 解决方案。 它在多个语言和平台之间保持一致。 它还提供了极佳的工具，其中包含自动生成的很多必要样板代码。 因此，更多的开发人员时间更多，可以专注于业务逻辑。

### <a name="streaming"></a>流式处理

gRPC 具有完全双向流式处理，为 WCF 的全双工服务提供类似的功能。 gRPC 流式处理可通过常规 internet 连接、负载均衡器和服务网格运行。

### <a name="deadlinetimeouts-and-cancellation"></a>截止时间/超时和取消

gRPC 允许客户端指定 RPC 完成的最长时间。 如果超过指定的截止时间，则服务器可以独立于客户端取消该操作。 截止时间和取消可通过进一步的 gRPC 调用进行传播，以帮助强制实施资源使用限制。 超过截止时间时，客户端还可以停止操作，或在需要时停止操作（例如，由于用户交互）。

### <a name="security"></a>安全性

当 gRPC 在 TLS 端到端加密连接上使用 HTTP/2 时，它会隐式保护。 支持客户端证书身份验证（请参阅[第6章](security.md)），进一步提高客户端和服务器之间的安全性和信任。

>[!div class="step-by-step"]
>[上一页](network-protocols.md)
>[下一页](protocol-buffers.md)
