---
title: Wcf 绑定和传输-适用于 WCF 开发人员的 gRPC
description: 了解不同的 WCF 绑定和传输如何与 gRPC 进行比较。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 34321395ddd7059ac7e3c268e313a03251662911
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841317"
---
# <a name="wcf-bindings-and-transports"></a>WCF 绑定和传输

WCF 具有许多不同的内置*绑定*，它们指定不同的网络协议、线路格式和其他实现详细信息。 gRPC 实际上只包含一个网络协议和一种线路格式（从技术上讲，*可以*自定义网络格式，但这超出了本书的范围）。 在大多数情况下，你可能会发现 gRPC 提供了最佳解决方案。 下面是有关最相关的 WCF 绑定的简短讨论，以及它们如何与 gRPC 中的等效项进行比较。

## <a name="nettcp"></a>Wcf-nettcp

WCF 的 Wcf-nettcp 绑定允许永久性连接、小消息和双向消息传递，但只能在 .NET 客户端和服务器之间工作。 gRPC 允许相同的功能，但跨多个编程语言和平台支持。 gRPC 具有 WCF Wcf-nettcp 绑定的许多功能，但并不总是以相同的方式实现。 例如，在 WCF 中，通过配置控制加密，并在框架中进行处理。 在 gRPC 中，使用 HTTP/2 over TLS 在连接级别实现加密。

## <a name="http"></a>HTTP

WCF 的 BasicHttpBinding 通常是基于文本的，它使用 SOAP 作为线路格式，并且比 Wcf-nettcp 绑定慢。 它通常用于提供跨平台的互操作性或通过 internet 基础结构进行连接。 GRPC 中的等效项，因为它使用 HTTP/2 作为消息的二进制 Protobuf 传输层的基础传输层，可以提供 Wcf-nettcp 的服务级别性能，但具有与所有新式编程语言和框架的完全跨平台互操作性。

## <a name="named-pipes"></a>命名管道

WCF 提供了一个命名管道绑定，用于在同一物理计算机上的进程之间进行通信。 ASP.NET Core gRPC 的第一个版本不支持命名管道。 为命名管道（和 Unix 域套接字）添加客户端和服务器支持是将来版本的目标。

## <a name="msmq"></a>MSMQ

MSMQ 是专有的 Windows 消息队列。 通过 WCF 绑定到 MSMQ，可以在将来随时处理的客户端发出 "火灾" 和 "忘记" 请求。 gRPC 本身不提供任何消息队列功能。 最佳的替代方法是直接使用消息传递系统，例如 Azure 服务总线、RabbitMQ 或 Kafka。 这可以通过将消息直接放入队列的客户端来实现，也可以使用 gRPC 客户端流式处理服务（排队消息）来实现。

## <a name="webhttpbinding"></a>WebHttpBinding

使用 "`WebGet`" 和 "`WebInvoke`" 属性的 WebHttpBinding （也称为 WCF ReST），可以开发 ReSTful Api，在这种情况不太常见的情况下，这些 Api 可能会说出 JSON。 因此，如果你有使用 WCF REST 生成的 RESTful API，请考虑将其迁移到常规 ASP.NET Core MVC Web API 应用程序，该应用程序将提供等效的功能，而不是转换为 gRPC。

>[!div class="step-by-step"]
>[上一页](wcf-endpoints-grpc-methods.md)
>[下一页](rpc-types.md)
