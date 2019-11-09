---
title: 为 WCF 开发人员比较 WCF 与 gRPC-gRPC
description: 用于生成分布式应用程序的 WCF 和 gRPC 框架比较。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5ab1380d4ded52abff08c35c430adf2f3ed7c58b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841293"
---
# <a name="comparing-wcf-to-grpc"></a>将 WCF 与 gRPC 进行比较

上一章应为你提供一个很好的 Protobuf，以及 gRPC 如何处理消息。 在处理从 WCF 到 gRPC 的详细转换之前，请务必了解 WCF 中当前可用的功能范围如何在 gRPC 中进行处理，以及当没有 gRPC 等效项时可以使用的解决方法。 具体而言，本章将涵盖以下主题：

- 操作和方法
- 绑定和传输
- RPC 类型
- 元数据
- 错误处理
- WS\* 协议

## <a name="grpc-example"></a>gRPC 示例

当你从 Visual Studio 2019 或命令行创建新的 ASP.NET Core 3.0 gRPC 项目时，将为你生成 gRPC 等效的 "Hello World"。 它包含一个用于定义服务及其消息的 `greeter.proto` 文件，以及一个包含服务实现的 `GreeterService.cs` 文件。

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

本章介绍了 gRPC 的各种概念和功能。

>[!div class="step-by-step"]
>[上一页](protobuf-maps.md)
>[下一页](wcf-endpoints-grpc-methods.md)
