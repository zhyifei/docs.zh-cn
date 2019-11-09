---
title: 错误处理-针对 WCF 开发人员的 gRPC
description: 待撰写
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 91f5789d8ed0f01f3ce2f3f9a6c6ccf14f245290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73842001"
---
# <a name="error-handling"></a><span data-ttu-id="37b7a-103">错误处理</span><span class="sxs-lookup"><span data-stu-id="37b7a-103">Error handling</span></span>

<span data-ttu-id="37b7a-104">WCF 使用 `FaultException<T>` 和 `FaultContract` 来提供详细的错误信息，包括支持 SOAP 错误标准。</span><span class="sxs-lookup"><span data-stu-id="37b7a-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="37b7a-105">遗憾的是，当前版本的 gRPC 缺少 WCF 发现的复杂性，并且基于简单状态代码和元数据仅限制了内置错误处理。</span><span class="sxs-lookup"><span data-stu-id="37b7a-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="37b7a-106">下表是最常用的状态代码的快速指南：</span><span class="sxs-lookup"><span data-stu-id="37b7a-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="37b7a-107">状态代码</span><span class="sxs-lookup"><span data-stu-id="37b7a-107">Status Code</span></span> | <span data-ttu-id="37b7a-108">问题</span><span class="sxs-lookup"><span data-stu-id="37b7a-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="37b7a-109">尚未写入方法。</span><span class="sxs-lookup"><span data-stu-id="37b7a-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="37b7a-110">整个服务有问题。</span><span class="sxs-lookup"><span data-stu-id="37b7a-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="37b7a-111">响应无效。</span><span class="sxs-lookup"><span data-stu-id="37b7a-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="37b7a-112">编码/解码问题。</span><span class="sxs-lookup"><span data-stu-id="37b7a-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="37b7a-113">身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="37b7a-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="37b7a-114">授权失败。</span><span class="sxs-lookup"><span data-stu-id="37b7a-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="37b7a-115">调用已取消，通常由调用方。</span><span class="sxs-lookup"><span data-stu-id="37b7a-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="37b7a-116">ASP.NET Core gRPC 中引发错误</span><span class="sxs-lookup"><span data-stu-id="37b7a-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="37b7a-117">ASP.NET Core gRPC 服务可以通过引发 `RpcException`发送错误响应，客户端可以将其视为同一进程中。</span><span class="sxs-lookup"><span data-stu-id="37b7a-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="37b7a-118">`RpcException` 必须包含状态代码和说明，并且可以选择包括元数据和较长的异常消息。</span><span class="sxs-lookup"><span data-stu-id="37b7a-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="37b7a-119">元数据可用于发送支持数据，类似于 `FaultContract` 对象如何为 WCF 错误携带额外的数据。</span><span class="sxs-lookup"><span data-stu-id="37b7a-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="37b7a-120">捕获 gRPC 客户端中的错误</span><span class="sxs-lookup"><span data-stu-id="37b7a-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="37b7a-121">就像 WCF 客户端可以捕捉 <xref:System.ServiceModel.FaultException%601> 错误一样，gRPC 客户端可以捕获 `RpcException` 来处理错误。</span><span class="sxs-lookup"><span data-stu-id="37b7a-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="37b7a-122">由于 `RpcException` 不是泛型类型，因此你不能在不同的块中捕获不同的错误类型C#，但你可以使用的*异常筛选器*功能为不同的状态代码声明单独的 `catch` 块，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="37b7a-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="37b7a-123">为错误提供其他元数据时，请确保在 API 文档中记录相关的密钥和值，或者在 `.proto` 文件中记录注释。</span><span class="sxs-lookup"><span data-stu-id="37b7a-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="37b7a-124">gRPC 更丰富的错误模型</span><span class="sxs-lookup"><span data-stu-id="37b7a-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="37b7a-125">到C#目前为止，Google 已开发出更[丰富的错误模型](https://cloud.google.com/apis/design/errors#error_model)，此模型更像 WCF 的[FaultContract](xref:System.ServiceModel.FaultContractAttribute)，但目前尚不支持。</span><span class="sxs-lookup"><span data-stu-id="37b7a-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="37b7a-126">目前，它仅适用于转到 Java、Python 和C++，但对的C#支持将于明年到来。</span><span class="sxs-lookup"><span data-stu-id="37b7a-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="37b7a-127">[上一页](metadata.md)
>[下一页](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="37b7a-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
