---
title: GRPC for WCF 开发人员
description: 如何在 gRPC 中使用元数据在客户端和服务器之间传递附加上下文
ms.date: 09/02/2019
ms.openlocfilehash: 723d877bfbf0c2b0785949ff15939aedbac4d4e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971974"
---
# <a name="metadata"></a>元数据

"元数据" 是指在处理请求和响应时可能有用，但不是实际应用程序数据的一部分的其他数据。 元数据可能包括身份验证令牌、请求标识符和标记以用于监视，或者数据集中有关数据的信息。

可以使用 <xref:System.ServiceModel.OperationContextScope> 和 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> 属性将泛型键/值标头添加到 WCF 消息，并使用 <xref:System.ServiceModel.Channels.MessageProperties>处理它们。

gRPC 调用和响应还可以包含类似于 HTTP 标头的元数据。 它们在 gRPC 本身中是不可见的，并且传递到由应用程序代码或中间件进行处理。 元数据表示为键/值对，其中键是字符串，而值是字符串或二进制数据。 不需要在 `.proto` 文件中指定元数据。

使用[Grpc](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet 包中的 `Metadata` 类处理元数据。 此类可以与集合初始值设定项语法一起使用。

下面的示例演示如何将元数据添加到C#客户端的调用：

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

gRPC 服务可以从 `ServerCallContext` 参数的 `RequestHeaders` 属性访问元数据：

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

服务可以使用 `ServerCallContext`的 `ResponseTrailers` 属性，将元数据发送到客户端：

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
>[上一页](rpc-types.md)
>[下一页](error-handling.md)
