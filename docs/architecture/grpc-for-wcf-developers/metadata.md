---
title: GRPC for WCF 开发人员
description: 如何在 gRPC 中使用元数据在客户端和服务器之间传递附加上下文。
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628574"
---
# <a name="metadata"></a><span data-ttu-id="b5207-103">元数据</span><span class="sxs-lookup"><span data-stu-id="b5207-103">Metadata</span></span>

<span data-ttu-id="b5207-104">*元数据*是指在处理请求和响应时可能有用，但不是实际应用程序数据的一部分的其他数据。</span><span class="sxs-lookup"><span data-stu-id="b5207-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="b5207-105">元数据可能包括身份验证令牌、请求标识符和标记以便监视，以及有关数据的信息，例如数据集中的记录数。</span><span class="sxs-lookup"><span data-stu-id="b5207-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="b5207-106">通过使用 <xref:System.ServiceModel.OperationContextScope> 和 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> 属性，并使用 <xref:System.ServiceModel.Channels.MessageProperties>处理它们，可以将泛型键/值标头添加到 Windows Communication Foundation （WCF）消息。</span><span class="sxs-lookup"><span data-stu-id="b5207-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="b5207-107">gRPC 调用和响应还可以包含类似于 HTTP 标头的元数据。</span><span class="sxs-lookup"><span data-stu-id="b5207-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="b5207-108">此元数据在 gRPC 本身中是不可见的，并且传递到由应用程序代码或中间件进行处理。</span><span class="sxs-lookup"><span data-stu-id="b5207-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="b5207-109">元数据表示为键/值对，其中键是字符串，而值是字符串或二进制数据。</span><span class="sxs-lookup"><span data-stu-id="b5207-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="b5207-110">不需要在 `.proto` 文件中指定元数据。</span><span class="sxs-lookup"><span data-stu-id="b5207-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="b5207-111">元数据由[Grpc](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet 包的 `Metadata` 类处理。</span><span class="sxs-lookup"><span data-stu-id="b5207-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="b5207-112">此类可以与集合初始值设定项语法一起使用。</span><span class="sxs-lookup"><span data-stu-id="b5207-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="b5207-113">此示例演示如何将元数据添加到C#客户端的调用：</span><span class="sxs-lookup"><span data-stu-id="b5207-113">This example shows how to add metadata to a call from a C# client:</span></span>

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

<span data-ttu-id="b5207-114">gRPC 服务可以从 `ServerCallContext` 参数的 `RequestHeaders` 属性访问元数据：</span><span class="sxs-lookup"><span data-stu-id="b5207-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

<span data-ttu-id="b5207-115">服务可以使用 `ServerCallContext`的 `ResponseTrailers` 属性将元数据发送到客户端：</span><span class="sxs-lookup"><span data-stu-id="b5207-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="b5207-116">[上一页](rpc-types.md)
>[下一页](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="b5207-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
