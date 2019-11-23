---
title: GRPC 如何为 WCF 开发人员提供 RPC gRPC
description: 比较 WCF 的主要功能和 gRPC。
ms.date: 09/02/2019
ms.openlocfilehash: 1ebfd102217c9685c5ff5200386c642b2017e98f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968121"
---
# <a name="how-grpc-approaches-rpc"></a>gRPC 如何处理 RPC

Windows Communication Foundation （WCF）和 gRPC 都是*远程过程调用*（RPC）模式的实现，这是为了调用在另一台计算机上或在不同进程中运行的服务，就像它们只是客户端应用程序中的方法调用一样。 尽管 WCF 和 gRPC 的目标是相同的，但实现的详细信息是完全不同的。

下表设置了 WCF 的主要功能与 gRPC 的关系，以及可以在本书的其余部分找到更详细说明的位置。

| 功能 | WCF | gRPC |
| -------- | --- | ---- |
| 目标 | 独立于网络实现的业务代码 | 从接口定义和网络实现分离业务代码 |
| 定义服务和消息（第3-4 章）  | 服务协定、操作协定和数据协定 | 使用 proto 文件声明服务和消息 |
| 语言（第3-5 章） | 用或编写C#的协定 Visual Basic | 协议缓冲区语言 |
| 线路格式（第3章） | 可配置，包括 SOAP/XML、纯 XML、JSON、.NET 二进制文件等。 | 协议缓冲区二进制格式（尽管可以使用其他格式）。
| 互操作性（第4章） | 使用 SOAP over HTTP 时 | 官方支持： .NET、Java、Python、JavaScript、C/C++、中转、Rust、Ruby、Swift、DART、PHP。 来自社区的其他语言的非正式支持。 |
| 网络（第4章） | 在运行时配置。 在 Wcf-nettcp、HTTP、MSMQ 等之间切换。 | HTTP/2，当前通过 TCP ASP.NET Core gRPC。 |
| 方法（第4章） | 在基类中生成序列化/deserialization 和网络代码的运行时 | 生成时生成序列化/deserialization 和网络代码 |
| 安全性（第6章） | 身份验证，WS 安全性，消息加密 | 凭据，ASP.NET Core 安全性，TLS 网络 |

>[!div class="step-by-step"]
>[上一页](grpc-overview.md)
>[下一页](interface-definition-language.md)
