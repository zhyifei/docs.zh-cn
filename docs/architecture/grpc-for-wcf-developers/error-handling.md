---
title: 错误处理-针对 WCF 开发人员的 gRPC
description: 与 gRPC 中的错误处理相关的主题。 包含一个最常用状态代码的表。
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542788"
---
# <a name="error-handling"></a>错误处理。

Windows Communication Foundation （WCF）使用 <xref:System.ServiceModel.FaultException%601> 和[FaultContract](xref:System.ServiceModel.FaultContractAttribute)提供详细的错误信息，包括支持 SOAP 错误标准。

遗憾的是，当前版本的 gRPC 缺少 WCF 发现的复杂性，并且基于简单状态代码和元数据仅限制了内置错误处理。 下表是最常用的状态代码的快速指南：

| 状态代码 | 问题 |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | 尚未写入方法。 |
| `GRPC_STATUS_UNAVAILABLE` | 整个服务有问题。 |
| `GRPC_STATUS_UNKNOWN` | 响应无效。 |
| `GRPC_STATUS_INTERNAL` | 编码/解码问题。 |
| `GRPC_STATUS_UNAUTHENTICATED` | 身份验证失败。 |
| `GRPC_STATUS_PERMISSION_DENIED` | 授权失败。 |
| `GRPC_STATUS_CANCELLED` | 调用已取消，通常由调用方。 |

## <a name="raise-errors-in-aspnet-core-grpc"></a>ASP.NET Core gRPC 中引发错误

ASP.NET Core gRPC 服务可以通过引发 `RpcException`发送错误响应，客户端可以将其视为同一进程中。 `RpcException` 必须包含状态代码和说明，并且可以选择包括元数据和较长的异常消息。 元数据可用于发送支持数据，类似于 `FaultContract` 对象如何为 WCF 错误携带额外的数据。

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

## <a name="catch-errors-in-grpc-clients"></a>捕获 gRPC 客户端中的错误

就像 WCF 客户端可以捕捉 <xref:System.ServiceModel.FaultException%601> 错误一样，gRPC 客户端可以捕获 `RpcException` 来处理错误。 由于 `RpcException` 不是泛型类型，因此不能在不同的块中捕获不同的错误类型。 但你可以使用C#的*异常筛选器*功能为不同的状态代码声明单独的 `catch` 块，如以下示例中所示：

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
> 为错误提供其他元数据时，请确保在 API 文档中记录相关的密钥和值，或者在 `.proto` 文件中记录注释。

## <a name="grpc-richer-error-model"></a>gRPC 更丰富的错误模型

Google 开发了更[丰富的错误模型](https://cloud.google.com/apis/design/errors#error_model)，此模型更像 WCF 的[FaultContract](xref:System.ServiceModel.FaultContractAttribute)，但目前C#尚不支持此模型。 目前，它仅适用于中转、Java、Python 和C++。

>[!div class="step-by-step"]
>[上一页](metadata.md)
>[下一页](ws-protocols.md)
