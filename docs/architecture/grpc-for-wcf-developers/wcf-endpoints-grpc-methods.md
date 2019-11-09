---
title: Wcf 终结点和 gRPC 方法-WCF 开发人员 gRPC
description: 与在 Protobuf 中声明的 ServiceContract 和 OperationContract 特性和 gRPC 方法进行比较的 WCF 终结点比较
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841299"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="d465f-103">WCF 终结点和 gRPC 方法</span><span class="sxs-lookup"><span data-stu-id="d465f-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="d465f-104">在 WCF 中，编写应用程序代码时，可以使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="d465f-104">In WCF, when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="d465f-105">在类中编写应用程序代码，并使用[OperationContract](xref:System.ServiceModel.OperationContractAttribute)特性修饰方法。</span><span class="sxs-lookup"><span data-stu-id="d465f-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="d465f-106">为服务声明接口，并将[OperationContract](xref:System.ServiceModel.OperationContractAttribute)特性添加到接口。</span><span class="sxs-lookup"><span data-stu-id="d465f-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="d465f-107">例如，`greet.proto` Greeter 服务的 WCF 等效项可能按如下方式编写：</span><span class="sxs-lookup"><span data-stu-id="d465f-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="d465f-108">第3章说明了 Protobuf 消息定义用于生成数据类。</span><span class="sxs-lookup"><span data-stu-id="d465f-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="d465f-109">服务和方法声明用于生成从中继承以实现服务的基类。</span><span class="sxs-lookup"><span data-stu-id="d465f-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="d465f-110">只需声明要在 `.proto` 文件中实现的方法，编译器将使用必须重写的虚拟方法生成基类。</span><span class="sxs-lookup"><span data-stu-id="d465f-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="d465f-111">OperationContract 属性</span><span class="sxs-lookup"><span data-stu-id="d465f-111">OperationContract properties</span></span>

<span data-ttu-id="d465f-112">[OperationContract](xref:System.ServiceModel.OperationContractAttribute)属性具有控制或优化其工作方式的属性。</span><span class="sxs-lookup"><span data-stu-id="d465f-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="d465f-113">gRPC 方法不提供此类型的控件。</span><span class="sxs-lookup"><span data-stu-id="d465f-113">gRPC methods don’t offer this type of control.</span></span> <span data-ttu-id="d465f-114">下表设置了这些 `OperationContract` 属性和它们指定的功能在 gRPC 中的处理方式：</span><span class="sxs-lookup"><span data-stu-id="d465f-114">The following table sets out those `OperationContract` properties and how the functionality they specify is (or isn’t) dealt with in gRPC:</span></span>

| <span data-ttu-id="d465f-115">`OperationContract` 属性</span><span class="sxs-lookup"><span data-stu-id="d465f-115">`OperationContract` property</span></span> | <span data-ttu-id="d465f-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="d465f-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="d465f-117">标识操作的 URI。</span><span class="sxs-lookup"><span data-stu-id="d465f-117">URI identifying the operation.</span></span> <span data-ttu-id="d465f-118">gRPC 使用 `package`的名称，`service` 并 `rpc` `.proto` 文件中。</span><span class="sxs-lookup"><span data-stu-id="d465f-118">gRPC uses the name of the `package`, `service` and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="d465f-119">所有 gRPC 服务方法都返回 `Task` 对象。</span><span class="sxs-lookup"><span data-stu-id="d465f-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="d465f-120">请参见下面的注释。</span><span class="sxs-lookup"><span data-stu-id="d465f-120">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="d465f-121">单向 gRPC 方法返回 `Empty` 结果或使用客户端流式处理。</span><span class="sxs-lookup"><span data-stu-id="d465f-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="d465f-122">请参见下面的注释。</span><span class="sxs-lookup"><span data-stu-id="d465f-122">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="d465f-123">SOAP 相关，gRPC 中没有意义。</span><span class="sxs-lookup"><span data-stu-id="d465f-123">SOAP-related, no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="d465f-124">无消息加密;在传输层处理网络加密（HTTP/2 上的 TLS）。</span><span class="sxs-lookup"><span data-stu-id="d465f-124">No message encryption; network encryption handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="d465f-125">SOAP 相关，gRPC 中没有意义。</span><span class="sxs-lookup"><span data-stu-id="d465f-125">SOAP-related, no meaning in gRPC.</span></span> |

<span data-ttu-id="d465f-126">利用 `IsInitiating` 属性，您可以指示[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)内的方法不能是作为会话的一部分进行调用的第一个方法。</span><span class="sxs-lookup"><span data-stu-id="d465f-126">The `IsInitiating` property lets you indicate that a method within a [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="d465f-127">`IsTerminating` 属性会导致服务器在调用操作（或客户端，如果在回调客户端上使用）后关闭会话。</span><span class="sxs-lookup"><span data-stu-id="d465f-127">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if used on a callback client).</span></span> <span data-ttu-id="d465f-128">在 gRPC 中，流由单一方法创建并显式关闭。</span><span class="sxs-lookup"><span data-stu-id="d465f-128">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="d465f-129">请参阅[gRPC 流式处理](rpc-types.md#grpc-streaming)。</span><span class="sxs-lookup"><span data-stu-id="d465f-129">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="d465f-130">有关 gRPC 安全性和加密的详细信息，请参阅[第6章](security.md)。</span><span class="sxs-lookup"><span data-stu-id="d465f-130">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d465f-131">[上一页](wcf-services-to-grpc-comparison.md)
>[下一页](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d465f-131">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
