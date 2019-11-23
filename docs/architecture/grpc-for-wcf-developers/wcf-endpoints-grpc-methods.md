---
title: Wcf 终结点和 gRPC 方法-WCF 开发人员 gRPC
description: 与在 Protobuf 中声明的 ServiceContract 和 OperationContract 特性和 gRPC 方法进行比较的 WCF 终结点比较
ms.date: 09/02/2019
ms.openlocfilehash: 763862a363afc6aab72335050cf4822754816c7a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966932"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>WCF 终结点和 gRPC 方法

在 WCF 中，编写应用程序代码时，可以使用以下方法之一：

- 在类中编写应用程序代码，并使用[OperationContract](xref:System.ServiceModel.OperationContractAttribute)特性修饰方法。
- 为服务声明接口，并将[OperationContract](xref:System.ServiceModel.OperationContractAttribute)特性添加到接口。

例如，`greet.proto` Greeter 服务的 WCF 等效项可能按如下方式编写：

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

第3章说明了 Protobuf 消息定义用于生成数据类。 服务和方法声明用于生成从中继承以实现服务的基类。 只需声明要在 `.proto` 文件中实现的方法，编译器将使用必须重写的虚拟方法生成基类。

## <a name="operationcontract-properties"></a>OperationContract 属性

[OperationContract](xref:System.ServiceModel.OperationContractAttribute)属性具有控制或优化其工作方式的属性。 gRPC 方法不提供此类型的控件。 下表设置了这些 `OperationContract` 属性和它们指定的功能在 gRPC 中的处理方式：

| `OperationContract` 属性 | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | 标识操作的 URI。 gRPC 使用 `package`的名称，`service` 并 `rpc` `.proto` 文件中。 |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | 所有 gRPC 服务方法都返回 `Task` 对象。 |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | 请参见下面的注释。 |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | 单向 gRPC 方法返回 `Empty` 结果或使用客户端流式处理。 |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | 请参见下面的注释。 |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | SOAP 相关，gRPC 中没有意义。 |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | 无消息加密;在传输层处理网络加密（HTTP/2 上的 TLS）。 |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | SOAP 相关，gRPC 中没有意义。 |

利用 `IsInitiating` 属性，您可以指示[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)内的方法不能是作为会话的一部分进行调用的第一个方法。 `IsTerminating` 属性会导致服务器在调用操作（或客户端，如果在回调客户端上使用）后关闭会话。 在 gRPC 中，流由单一方法创建并显式关闭。 请参阅[gRPC 流式处理](rpc-types.md#grpc-streaming)。

有关 gRPC 安全性和加密的详细信息，请参阅[第6章](security.md)。

>[!div class="step-by-step"]
>[上一页](wcf-services-to-grpc-comparison.md)
>[下一页](wcf-bindings.md)
