---
title: REST 和 gRPC
description: 了解 gRPC，它在云本机应用程序中的作用，以及它与 HTTP REST 有何不同
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: c77343e7a594d34cbd2c00ce11281bd6bf4000c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337076"
---
# <a name="rest-and-grpc"></a>REST 和 gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

到目前为止，我们致力于[基于 REST 的](https://docs.microsoft.com/azure/architecture/best-practices/api-design)通信。 REST 是促进分布式计算机系统之间的互操作性的体系结构样式。 它使用一个请求/响应模型，其中来自服务器的每个响应都是来自客户端的请求。 在广泛使用的情况下，REST 并不适合每个问题。 一种较新的、gRPC 的通信技术，它迅速获得普及，并使其进入云到云的世界。

## <a name="grpc"></a>gRPC

gRPC 是源自 Google 的开源通信。 它构建于[远程过程调用（RPC）](https://en.wikipedia.org/wiki/Remote_procedure_call)模型之上，在分布式计算中很常见。 按照此模型，本地客户端程序将公开一个进程内方法来执行操作。 在后台，对分布式网络上的进程外微服务调用此调用。 开发人员将操作编码为本地过程调用。 底层平台对点到点网络通信、序列化和执行进行了抽象。

gRPC 是一种轻型且高性能的新式 RPC 框架。 它使用 HTTP/2 作为其传输协议。 与 HTTP 1.1 兼容，HTTP/2 功能很多高级功能：

- HTTP 1.1 以明文形式发送数据，HTTP/2 是一种二进制协议。 它使用较少的内存更快地分析数据，降低网络延迟，同时提高速度并更有效地管理网络资源。
- 虽然 HTTP 1.1 限制为一次处理一个往返请求/响应，但 HTTP/2 支持多路复用或通过同一连接的多个并行请求。
- HTTP/2 支持全双工或双向通信，客户端和服务器都可同时进行通信。 当服务器发送回响应数据时，客户端可以上载请求数据。
- 流内置于 HTTP/2 中，这意味着请求和响应可以异步流式传输大型数据集。
- 结合 gRPC 和 HTTP/2，性能会大幅增加。 在[Windows Communication Foundation （WCF）](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf)行话中，gRPC 性能达到并超出[wcf-nettcp 绑定](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)的速度和效率。 但是，与 Wcf-nettcp 不同，gRPC 不会限制为 Microsoft 语言C# ，如或 Visual Basic。

跨最常用平台（包括 Java、 C#、Golang 和 NodeJS）支持 gRPC。

## <a name="protocol-buffers"></a>协议缓冲区

gRPC 涵盖了另一种开源技术，称为[协议缓冲区](https://developers.google.com/protocol-buffers/docs/overview)或 Protobuf 消息来发送和接收数据。 与[WCF 数据协定](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-data-contracts)类似，Protobuf 序列化要读写的系统的结构化数据。 它降低了用户可读的格式（如 XML 或 JSON）所产生的开销。

许多对象序列化技术在运行时跨数据对象的结构。 Protobuf 要求使用平台不可知的语言（协议缓冲区语言）预先定义结构。 每个定义都存储在一个 "proto" 文件中。 然后，使用 Protobuf 编译器 "Proton" 为任何支持的平台生成客户端代码和服务器代码。 生成的代码经过优化，可快速序列化/反序列化数据。 在运行时，每条消息都包装在强类型服务协定中，并序列化为标准的 Protobuf 表示形式。

## <a name="grpc-support-in-net"></a>.NET 中的 gRPC 支持

Microsoft .NET Core framework 3.0 包括工具和对 gRPC 的本机支持。 图4-20 显示了 Visual Studio 2019 模板，该模板基架用于 gRPC 服务的 gRPC 主干项目。 请注意 .NET Core 如何支持 Windows、Linux 和 macOS 平台。

![Visual Studio 2019 中的 gRPC 支持](./media/visual-studio-2019-grpc-template.png)

图 4-20。 Visual Studio 2019 中的 gRPC 支持

.NET Core 3.0 将 gRPC 无缝集成到其框架中，包括终结点路由、内置 IoC 支持和日志记录。 开源 Kestrel web 服务器完全支持 HTTP/2 连接。

图4-21 显示了 Visual Studio 2019 中的 gRPC 服务的结构。 请注意文件夹结构如何包含用于 proto 文件和服务代码的文件夹。

![Visual Studio 2019 中的 gRPC 项目](./media/grpc-project.png  )

图 4-21。 Visual Studio 2019 中的 gRPC 项目

## <a name="grpc-usage"></a>gRPC 用法

gRPC 适用于以下方案：

- 低延迟和高吞吐量通信。 gRPC 非常适合轻型微服务，其中效率非常重要。
- 点到点实时通信。 gRPC 具有对双向流式处理的出色支持。 gRPC services 无需轮询即可实时推送消息。
- Polyglot 环境– gRPC 工具支持最常用的开发语言，这使其成为多语言环境的不错选择。
- 网络约束环境–使用 Protobuf （一种轻量消息格式）对 gRPC 消息进行序列化。 GRPC 消息始终小于等效的 JSON 消息。

撰写本书时，大多数浏览器对 gRPC 的支持有限。 gRPC 大量使用 HTTP/2 功能，并且没有浏览器提供 web 请求所需的控制级别，以支持 gRPC 客户端。 gRPC 通常用于内部微服务到微服务通信。 图4-22 显示了一个简单但常用的模式。

![gRPC 使用模式](./media/grpc-usage.png)

**图 4-22**。 gRPC 使用模式

请注意，在上图中，在后端微服务到微服务使用 gRPC 时，如何使用 HTTP 调用前端通信。

在此之前，gRPC 可能会在 dethroning 中扮演一项重大角色，以实现云本机系统的 REST 控制。 性能优势和轻松开发太好了。 不过，请不要出错，REST 仍会长时间停留。 它仍为公开公开的 Api transact-sql，并出于向后兼容的原因。

>[!div class="step-by-step"]
>[上一页](service-to-service-communication.md)
>[下一页](service-mesh-communication-infrastructure.md)
