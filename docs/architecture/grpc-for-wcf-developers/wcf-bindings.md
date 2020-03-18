---
title: WCF 绑定和传输 - gRPC 面向 WCF 开发人员
description: 了解不同的 WCF 绑定和传输与 gRPC 的比较情况。
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147719"
---
# <a name="wcf-bindings-and-transports"></a>WCF 绑定和传输

Windows 通信基础 （WCF） 具有内置*绑定*，用于指定不同的网络协议、线格式和其他实现详细信息。 gRPC 实际上只有一个网络协议和一个线格式。 （从技术上讲，*您可以*自定义线格式，但这超出了本书的范围。您可能会发现 gRPC 在大多数情况下提供了最佳解决方案。

以下是关于最相关的 WCF 绑定及其与 gRPC 中的等效绑定的比较的简短讨论。

## <a name="nettcp"></a>NetTCP

WCF 的 NetTCP 绑定允许持久连接、小消息和双向消息传送。 但它仅在 .NET 客户端和服务器之间工作。 gRPC 允许相同的功能，但支持跨多个编程语言和平台。

gRPC 具有 WCF NetTCP 绑定的许多功能，但它们并不总是以相同的方式实现。 例如，在 WCF 中，加密通过配置进行控制，并在框架中处理。 在 gRPC 中，通过 TLS 的 HTTP/2 在连接级别实现加密。

## <a name="http"></a>HTTP

称为 BasicHttpBinding 的 WCF 绑定通常基于文本，并使用 SOAP 作为线格式。 与 NetTCP 绑定相比，它的速度很慢。 它通常用于提供跨平台互操作性或通过 Internet 基础结构进行连接。

gRPC 中的等效项使用 HTTP/2 作为具有二进制 Protobuf 线格式的消息的基础传输层。 因此，它可以提供 NetTCP 服务级别的性能，并与所有现代编程语言和框架实现全跨平台互操作性。

## <a name="named-pipes"></a>Named pipes

WCF 提供了一*个命名管道*绑定，用于在同一物理计算机上的进程之间的通信。 ASP.NET核心 gRPC 的第一个版本不支持命名管道。 添加命名管道（和 Unix 域套接字）的客户端和服务器支持是未来版本的目标。

## <a name="msmq"></a>MSMQ

MSMQ 是一个专有的 Windows 消息队列。 WCF 与 MSMQ 的绑定允许来自客户端的"触发和忘记"请求，这些请求将来可能随时处理。 gRPC 不本机提供任何消息队列功能。

最好的选择是直接使用消息传递系统，如 Azure 服务总线、兔子MQ或 Kafka。 可以通过将消息直接放在队列上的客户端或对消息进行排队的 gRPC 客户端流服务来实现此项。

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding（也称为 WCF REST），具有`WebGet`和`WebInvoke`属性，使您能够开发 RESTful API，在不太常见时可以讲 JSON。 如果使用 WCF REST 构建了 RESTful API，请考虑将其迁移到常规ASP.NET核心 MVC Web API 应用程序。 此迁移将提供与转换为 gRPC 相同的功能。

>[!div class="step-by-step"]
>[上一个](wcf-endpoints-grpc-methods.md)
>[下一个](rpc-types.md)
