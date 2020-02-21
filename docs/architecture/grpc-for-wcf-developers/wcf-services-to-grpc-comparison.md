---
title: 为 WCF 开发人员比较 WCF 与 gRPC-gRPC
description: 用于生成分布式应用程序的 WCF 和 gRPC 框架比较。
ms.date: 09/02/2019
ms.openlocfilehash: 4f54db76c9512b770b4dd993496d95437dd89753
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503340"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="20e9d-103">将 WCF 与 gRPC 进行比较</span><span class="sxs-lookup"><span data-stu-id="20e9d-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="20e9d-104">上一章介绍了 Protobuf 和 gRPC 如何处理消息。</span><span class="sxs-lookup"><span data-stu-id="20e9d-104">The previous chapter gave you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="20e9d-105">在处理从 Windows Communication Foundation （WCF）到 gRPC 的详细转换之前，请务必了解 WCF 中的功能在 gRPC 中的处理方式，以及在没有 gRPC 等效项时可以使用的解决方法。</span><span class="sxs-lookup"><span data-stu-id="20e9d-105">Before you work through a detailed conversion from Windows Communication Foundation (WCF) to gRPC, it's important know how the features available in WCF are handled in gRPC and what workarounds you can use when there's no gRPC equivalent.</span></span> <span data-ttu-id="20e9d-106">具体而言，本章将涵盖以下主题：</span><span class="sxs-lookup"><span data-stu-id="20e9d-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="20e9d-107">操作和方法</span><span class="sxs-lookup"><span data-stu-id="20e9d-107">Operations and methods</span></span>
- <span data-ttu-id="20e9d-108">绑定和传输</span><span class="sxs-lookup"><span data-stu-id="20e9d-108">Bindings and transports</span></span>
- <span data-ttu-id="20e9d-109">RPC 类型</span><span class="sxs-lookup"><span data-stu-id="20e9d-109">RPC types</span></span>
- <span data-ttu-id="20e9d-110">元数据</span><span class="sxs-lookup"><span data-stu-id="20e9d-110">Metadata</span></span>
- <span data-ttu-id="20e9d-111">错误处理。</span><span class="sxs-lookup"><span data-stu-id="20e9d-111">Error handling</span></span>
- <span data-ttu-id="20e9d-112">WS\* 协议</span><span class="sxs-lookup"><span data-stu-id="20e9d-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="20e9d-113">gRPC 示例</span><span class="sxs-lookup"><span data-stu-id="20e9d-113">gRPC example</span></span>

<span data-ttu-id="20e9d-114">当你从 Visual Studio 2019 或命令行创建新的 ASP.NET Core 3.0 gRPC 项目时，将为你生成 gRPC 等效的 "Hello World"。</span><span class="sxs-lookup"><span data-stu-id="20e9d-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="20e9d-115">它包含一个用于定义服务及其消息的 `greeter.proto` 文件，以及一个包含服务实现的 `GreeterService.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="20e9d-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
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

<span data-ttu-id="20e9d-116">本章介绍了 gRPC 的不同概念和功能。</span><span class="sxs-lookup"><span data-stu-id="20e9d-116">This chapter will refer to this example code when explaining different concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="20e9d-117">[上一页](protobuf-maps.md)
>[下一页](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="20e9d-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
