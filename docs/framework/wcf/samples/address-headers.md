---
title: "地址标头"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aafd6ec911464dcc2b936b9f9fc74b9bc39808bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="address-headers"></a><span data-ttu-id="4c3b9-102">地址标头</span><span class="sxs-lookup"><span data-stu-id="4c3b9-102">Address Headers</span></span>
<span data-ttu-id="4c3b9-103">“地址标头”示例演示客户端如何将引用参数传递给使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的服务。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c3b9-104">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4c3b9-105">WS-Addressing 规范将终结点引用的概念定义为对特定 Web 服务终结点寻址的方式。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="4c3b9-106">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，使用 `EndpointAddress` 类对终结点引用建模，`EndpointAddress` 是 `ServiceEndpoint` 类的“地址”字段的类型。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>  
  
 <span data-ttu-id="4c3b9-107">作为终结点引用模型的一部分，每个引用都可以携带一些可添加额外标识信息的引用参数。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="4c3b9-108">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，将这些引用参数建模为 `AddressHeader` 类的实例。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], these reference parameters are modeled as instances of `AddressHeader` class.</span></span>  
  
 <span data-ttu-id="4c3b9-109">在本示例中，客户端将向客户端终结点的 `EndpointAddress` 添加一个引用参数。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="4c3b9-110">服务将查找此引用参数并在其“Hello”服务操作的逻辑中使用此参数的值。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>  
  
## <a name="client"></a><span data-ttu-id="4c3b9-111">客户端</span><span class="sxs-lookup"><span data-stu-id="4c3b9-111">Client</span></span>  
 <span data-ttu-id="4c3b9-112">若要使客户端发送引用参数，该客户端必须向 `AddressHeader` 的 `EndpointAddress` 添加一个 `ServiceEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="4c3b9-113">由于 `EndpointAddress` 类是不可变的，因此必须使用 `EndpointAddressBuilder` 类来完成终结点地址的修改。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="4c3b9-114">下面的代码将客户端初始化为作为其消息的一部分来发送引用参数。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 <span data-ttu-id="4c3b9-115">代码使用原始 `EndpointAddressBuilder` 作为初始值创建 `EndpointAddress`。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="4c3b9-116">然后，它添加新创建的地址标头；调用 `CreateAddressHeadercreates` 将使用特定名称、命名空间和值创建一个标头。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-116">It then adds a newly created address header; the call to `CreateAddressHeadercreates` a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="4c3b9-117">此处值为“John”。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-117">Here the value is "John".</span></span> <span data-ttu-id="4c3b9-118">将标头添加到生成器后，`ToEndpointAddress()` 方法会将生成器（可变）转换回终结点地址（不可变），该地址将分配回给客户端终结点的“地址”字段。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>  
  
 <span data-ttu-id="4c3b9-119">现在，当客户端调用 `Console.WriteLine(client.Hello());` 时，服务能够获取此地址参数的值，如客户端生成的输出所示。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>  
  
 `Hello, John`  
  
## <a name="server"></a><span data-ttu-id="4c3b9-120">服务器</span><span class="sxs-lookup"><span data-stu-id="4c3b9-120">Server</span></span>  
 <span data-ttu-id="4c3b9-121">服务操作 `Hello()` 的实现使用当前 `OperationContext` 来检查传入消息上标头的值。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 <span data-ttu-id="4c3b9-122">代码循环访问传入消息上的所有标头，查找具有特定名称并作为引用参数的标头。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="4c3b9-123">该找到参数时，代码将读取参数的值并将其保存在“id”变量中。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c3b9-124">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="4c3b9-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4c3b9-125">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4c3b9-126">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4c3b9-127">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c3b9-128">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c3b9-129">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4c3b9-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4c3b9-130">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="4c3b9-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c3b9-131">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4c3b9-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a><span data-ttu-id="4c3b9-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c3b9-132">See Also</span></span>
