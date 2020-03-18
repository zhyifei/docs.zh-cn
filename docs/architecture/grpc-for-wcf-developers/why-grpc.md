---
title: 为什么我们为 WCF 开发人员推荐 gRPC - gRPC 面向 WCF 开发人员
description: 讨论 gRPC 为什么非常适合想要迁移到现代体系结构和平台的 WCF 开发人员。
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147641"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>我们为什么建议适用于 WCF 开发人员的 gRPC

在我们深入探讨 gRPC 的语言和技术之前，值得讨论为什么 gRPC 是 Windows 通信基础 （WCF） 开发人员想要迁移到 .NET Core 的正确解决方案。

## <a name="similarity-to-wcf"></a>与 WCF 的相似性

尽管 gRPC 的实现和方法不同，但使用 gRPC 开发和使用服务的经验对于 WCF 开发人员来说应该是直观的。 基本目标是相同的：使客户端和服务器位于同一平台上，无需担心网络，可以编写代码。

两个平台共享声明然后实现接口的原则，即使声明该接口的过程是不同的。 正如您将在第 5 章中看到的，gRPC 支持的不同类型的 RPC 调用很好地映射到 WCF 服务可用的绑定。

## <a name="benefits-of-grpc"></a>gRPC 的好处

gRPC 高于其他解决方案，原因如下。

### <a name="performance"></a>性能

使用 HTTP/2 而不是 HTTP/1.1 可消除对人可读消息的要求，而是使用更小、更快的二进制协议。 这对计算机进行分析的效率更高。 HTTP/2 还支持通过单个连接进行多路复用请求。 此支持允许在响应准备就绪后立即发送，而无需在队列中等待。 （在 HTTP/1.1 中，此问题称为"线头 （HOL） 阻塞"。使用 gRPC 时需要的资源更少，这使得它成为用于移动设备和速度较慢的网络的良好解决方案。

### <a name="interoperability"></a>互操作性

所有主要编程语言和平台都有 gRPC 工具和库，包括 .NET、Java、Python、Go、C++、Node.js、Swift、Dart、Ruby 和 PHP。 得益于协议缓冲区二进制线格式和每个平台的有效代码生成，开发人员可以构建执行应用程序，同时仍然享受全面的跨平台支持。

### <a name="usability-and-productivity"></a>易用性和工作效率

gRPC 是一个全面的 RPC 解决方案。 它在多种语言和平台上一致工作。 它还提供了出色的工具，自动生成许多必要的样板代码。 因此，可以腾出更多开发人员时间来关注业务逻辑。

### <a name="streaming"></a>流式处理

gRPC 具有完全双向流式处理，提供与 WCF 全双工服务类似的功能。 gRPC 流可以通过常规互联网连接、负载均衡器和服务联结运行。

### <a name="deadlinetimeouts-and-cancellation"></a>截止日期/超时和取消

gRPC 允许客户端指定 RPC 完成的最大时间。 如果超过指定的截止时间，服务器可以独立于客户端取消操作。 截止和取消可以通过进一步的 gRPC 调用传播，以帮助强制实施资源使用限制。 客户端也可以在超过截止时间时停止操作，或者在必要时更早停止操作（例如，由于用户交互）。

### <a name="security"></a>安全性

gRPC 在 TLS 端到端加密连接上使用 HTTP/2 时具有隐式安全。 对客户端证书身份验证的支持（参见[第 6 章](security.md)）进一步增强了客户端和服务器之间的安全性和信任。

>[!div class="step-by-step"]
>[上一个](network-protocols.md)
>[下一个](protocol-buffers.md)
