---
title: 错误处理 - GRPC，适用于 WCF 开发人员
description: 与 gRPC 中的错误处理相关的主题。 包括最常用的状态代码的表。
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988942"
---
# <a name="error-handling"></a><span data-ttu-id="c2985-104">错误处理。</span><span class="sxs-lookup"><span data-stu-id="c2985-104">Error handling</span></span>

<span data-ttu-id="c2985-105">Windows 通信基础 （WCF） 使用<xref:System.ServiceModel.FaultException%601>和[故障合同](xref:System.ServiceModel.FaultContractAttribute)提供详细的错误信息，包括支持 SOAP 故障标准。</span><span class="sxs-lookup"><span data-stu-id="c2985-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="c2985-106">遗憾的是，gRPC 的当前版本缺乏 WCF 的成熟度，并且仅根据简单的状态代码和元数据进行有限的内置错误处理。</span><span class="sxs-lookup"><span data-stu-id="c2985-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="c2985-107">下表是最常用的状态代码的快速指南：</span><span class="sxs-lookup"><span data-stu-id="c2985-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="c2985-108">状态代码</span><span class="sxs-lookup"><span data-stu-id="c2985-108">Status code</span></span> | <span data-ttu-id="c2985-109">问题</span><span class="sxs-lookup"><span data-stu-id="c2985-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="c2985-110">方法尚未编写。</span><span class="sxs-lookup"><span data-stu-id="c2985-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="c2985-111">整个服务有问题。</span><span class="sxs-lookup"><span data-stu-id="c2985-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="c2985-112">无效响应。</span><span class="sxs-lookup"><span data-stu-id="c2985-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="c2985-113">编码/解码问题。</span><span class="sxs-lookup"><span data-stu-id="c2985-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="c2985-114">身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="c2985-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="c2985-115">授权失败。</span><span class="sxs-lookup"><span data-stu-id="c2985-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="c2985-116">呼叫已取消，通常由呼叫者取消。</span><span class="sxs-lookup"><span data-stu-id="c2985-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="c2985-117">引发ASP.NET核心 gRPC 中的错误</span><span class="sxs-lookup"><span data-stu-id="c2985-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="c2985-118">ASP.NET Core gRPC 服务可以通过引发 一个`RpcException`发送 错误响应来发送错误响应，客户端可以捕获该响应，就像它处于同一进程中一样。</span><span class="sxs-lookup"><span data-stu-id="c2985-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="c2985-119">`RpcException`必须包括状态代码和说明，并且可以选择包括元数据和较长的异常消息。</span><span class="sxs-lookup"><span data-stu-id="c2985-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="c2985-120">元数据可用于发送支持数据，类似于对象如何`FaultContract`为 WCF 错误携带其他数据。</span><span class="sxs-lookup"><span data-stu-id="c2985-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="c2985-121">捕获 gRPC 客户端中的错误</span><span class="sxs-lookup"><span data-stu-id="c2985-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="c2985-122">就像 WCF 客户端可以<xref:System.ServiceModel.FaultException%601>捕获错误一样，gRPC 客户端`RpcException`可以捕获处理错误的。</span><span class="sxs-lookup"><span data-stu-id="c2985-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="c2985-123">因为`RpcException`不是泛型类型，因此无法捕获不同块中的不同错误类型。</span><span class="sxs-lookup"><span data-stu-id="c2985-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="c2985-124">但是，您可以使用 C# 的*异常筛选器*功能为不同的状态代码`catch`声明单独的块，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="c2985-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="c2985-125">为错误提供其他元数据时，请确保在 API 文档中或`.proto`文件中的注释中记录相关键和值。</span><span class="sxs-lookup"><span data-stu-id="c2985-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="c2985-126">gRPC 更丰富的错误模型</span><span class="sxs-lookup"><span data-stu-id="c2985-126">gRPC richer error model</span></span>

<span data-ttu-id="c2985-127">谷歌已经开发出一个更[丰富的错误模型](https://cloud.google.com/apis/design/errors#error_model)，更像WCF的[故障合同](xref:System.ServiceModel.FaultContractAttribute)，但这种模式在C#中还不受支持。</span><span class="sxs-lookup"><span data-stu-id="c2985-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="c2985-128">目前，它仅适用于 Go、Java、Python 和C++。</span><span class="sxs-lookup"><span data-stu-id="c2985-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c2985-129">[上一页](metadata.md)
>[下一页](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="c2985-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
