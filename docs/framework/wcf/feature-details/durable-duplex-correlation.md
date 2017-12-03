---
title: "持久双工相关"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9371729dcac22b0611f8ea3ec29cc59daf5d67b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="durable-duplex-correlation"></a><span data-ttu-id="e646e-102">持久双工相关</span><span class="sxs-lookup"><span data-stu-id="e646e-102">Durable Duplex Correlation</span></span>
<span data-ttu-id="e646e-103">当工作流服务要求向初始调用方发送回调时，持久双工相关性（也称为回调相关性）非常有用。</span><span class="sxs-lookup"><span data-stu-id="e646e-103">Durable duplex correlation, also known as callback correlation, is useful when a workflow service has a requirement to send a callback to the initial caller.</span></span> <span data-ttu-id="e646e-104">与 WCF 双工不同的是，该回调可以在将来的任何时间发生，并且不会绑定到同一通道或通道生存期；唯一要求是，调用方应具有一个用于侦听回调消息的活动终结点。</span><span class="sxs-lookup"><span data-stu-id="e646e-104">Unlike WCF duplex, the callback can happen at any time in the future and is not tied to the same channel or the channel lifetime; the only requirement is that the caller have an active endpoint listening for the callback message.</span></span> <span data-ttu-id="e646e-105">这样，这两个工作流服务便可在长期运行的对话中进行通信。</span><span class="sxs-lookup"><span data-stu-id="e646e-105">This allows two workflow services to communicate in a long-running conversation.</span></span> <span data-ttu-id="e646e-106">本主题概述了持久双工相关性。</span><span class="sxs-lookup"><span data-stu-id="e646e-106">This topic provides an overview of durable duplex correlation.</span></span>  
  
## <a name="using-durable-duplex-correlation"></a><span data-ttu-id="e646e-107">使用持久双工相关性</span><span class="sxs-lookup"><span data-stu-id="e646e-107">Using Durable Duplex Correlation</span></span>  
 <span data-ttu-id="e646e-108">若要使用持久双工相关性，这两个服务必须使用启用了上下文且支持双向操作的绑定，如 <xref:System.ServiceModel.NetTcpContextBinding> 或 <xref:System.ServiceModel.WSHttpContextBinding>。</span><span class="sxs-lookup"><span data-stu-id="e646e-108">To use durable duplex correlation, the two services must use a context-enabled binding that supports two-way operations, such as <xref:System.ServiceModel.NetTcpContextBinding> or <xref:System.ServiceModel.WSHttpContextBinding>.</span></span> <span data-ttu-id="e646e-109">调用服务使用所需绑定向其客户端 <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> 注册 <xref:System.ServiceModel.Endpoint>。</span><span class="sxs-lookup"><span data-stu-id="e646e-109">The calling service registers a <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> with the desired binding on their client <xref:System.ServiceModel.Endpoint>.</span></span> <span data-ttu-id="e646e-110">接收服务将接收初始调用中的上述数据，然后在回调调用服务的 <xref:System.ServiceModel.Endpoint> 活动中对自己的 <xref:System.ServiceModel.Activities.Send> 使用此数据。</span><span class="sxs-lookup"><span data-stu-id="e646e-110">The receiving service receives this data in the initial call and then uses it on its own <xref:System.ServiceModel.Endpoint> in the <xref:System.ServiceModel.Activities.Send> activity that makes the call back to the calling service.</span></span> <span data-ttu-id="e646e-111">在本示例中，这两个服务互相通信。</span><span class="sxs-lookup"><span data-stu-id="e646e-111">In this example, two services communicate with each other.</span></span> <span data-ttu-id="e646e-112">第一个服务对第二个服务调用某个方法，然后等待答复。</span><span class="sxs-lookup"><span data-stu-id="e646e-112">The first service invokes a method on the second service and then waits for a reply.</span></span> <span data-ttu-id="e646e-113">第二个服务知晓回调方法的名称，但在设计时，实现该方法的服务的终结点是未知的。</span><span class="sxs-lookup"><span data-stu-id="e646e-113">The second service knows the name of the callback method, but the endpoint of the service that implements this method is not known at design time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e646e-114">仅当终结点的 <xref:System.ServiceModel.Channels.AddressingVersion> 配置有 <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A> 时，才能使用持久双工。</span><span class="sxs-lookup"><span data-stu-id="e646e-114">Durable duplex can only be used when the <xref:System.ServiceModel.Channels.AddressingVersion> of the endpoint is configured with <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>.</span></span> <span data-ttu-id="e646e-115">如果不是，则<xref:System.InvalidOperationException>异常并显示以下消息:"消息中包含的 AddressingVersion 具有终结点引用的回调上下文标头 Addressing200408 （超链接"http://schemas.xmlsoap.org/ws/2004/08/寻址"http://schemas.xmlsoap.org/ws/2004/08/addressing）。</span><span class="sxs-lookup"><span data-stu-id="e646e-115">If it is not, then an <xref:System.InvalidOperationException> exception is thrown with the following message: "The message contains a callback context header with an endpoint reference for AddressingVersion 'Addressing200408 ( HYPERLINK "http://schemas.xmlsoap.org/ws/2004/08/addressing" http://schemas.xmlsoap.org/ws/2004/08/addressing)'.</span></span> <span data-ttu-id="e646e-116">仅当 AddressingVersion 配置有‘WSAddressing10’时，才能传输回调上下文。”</span><span class="sxs-lookup"><span data-stu-id="e646e-116">Callback context can only be transmitted when the AddressingVersion is configured with 'WSAddressing10'."</span></span>  
  
 <span data-ttu-id="e646e-117">在下面的示例中，使用 <xref:System.ServiceModel.Endpoint> 承载工作流服务，该服务将创建回调 <xref:System.ServiceModel.WSHttpContextBinding>。</span><span class="sxs-lookup"><span data-stu-id="e646e-117">In the following example, a workflow service is hosted that creates a callback <xref:System.ServiceModel.Endpoint> using <xref:System.ServiceModel.WSHttpContextBinding>.</span></span>  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 <span data-ttu-id="e646e-118">实现此工作流服务的工作流通过其 <xref:System.ServiceModel.Activities.Send> 活动初始化回调相关性，并从与 <xref:System.ServiceModel.Activities.Receive> 相关的 <xref:System.ServiceModel.Activities.Send> 活动引用此回调终结点。</span><span class="sxs-lookup"><span data-stu-id="e646e-118">The workflow that implements this workflow service initializes the callback correlation with its <xref:System.ServiceModel.Activities.Send> activity, and references this callback endpoint from the <xref:System.ServiceModel.Activities.Receive> activity that correlates with the <xref:System.ServiceModel.Activities.Send>.</span></span> <span data-ttu-id="e646e-119">下面的示例表示通过 `GetWF1` 方法返回的工作流。</span><span class="sxs-lookup"><span data-stu-id="e646e-119">The following example represents the workflow that is returned from the `GetWF1` method.</span></span>  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")                          
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="e646e-120">使用系统提供的基于上下文的绑定来承载第二个工作流服务。</span><span class="sxs-lookup"><span data-stu-id="e646e-120">The second workflow service is hosted using a system-provided, context-based binding.</span></span>  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 <span data-ttu-id="e646e-121">实现此工作流服务的工作流以 <xref:System.ServiceModel.Activities.Receive> 活动开头。</span><span class="sxs-lookup"><span data-stu-id="e646e-121">The workflow that implements this workflow service begins with a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="e646e-122">此 Receive 活动初始化此服务的回调相关性，延迟一段时间以模拟长时间运行的工作，然后使用第一次调用第一个服务时传递的回调上下文回调来该服务。</span><span class="sxs-lookup"><span data-stu-id="e646e-122">This receive activity initializes the callback correlation for this service, delays for a period of time to simulate long-running work, and then calls back into the first service using the callback context that was passed in the first call into the service.</span></span> <span data-ttu-id="e646e-123">下面的示例表示通过调用 `GetWF2` 返回的工作流。</span><span class="sxs-lookup"><span data-stu-id="e646e-123">The following example represents the workflow that is returned from a call to `GetWF2`.</span></span> <span data-ttu-id="e646e-124">请注意，<xref:System.ServiceModel.Activities.Send> 活动包含占位符地址 `http://www.contoso.com`；在运行时使用的实际地址即为提供的回调地址。</span><span class="sxs-lookup"><span data-stu-id="e646e-124">Note that the <xref:System.ServiceModel.Activities.Send> activity has a placeholder address of `http://www.contoso.com`; the actual address used at runtime is the supplied callback address.</span></span>  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =   
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 <span data-ttu-id="e646e-125">当对第一个工作流调用 `StartOrder` 方法时，将显示以下输出，该输出显示经过两个工作流的执行流。</span><span class="sxs-lookup"><span data-stu-id="e646e-125">When the `StartOrder` method is invoked on the first workflow, the following output is displayed, which shows the flow of execution through the two workflows.</span></span>  
  
```Output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.   
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 <span data-ttu-id="e646e-126">在本示例中，两个工作流均使用 <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer> 显式管理相关性。</span><span class="sxs-lookup"><span data-stu-id="e646e-126">In this example, both workflows explicitly manage correlation using a <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.</span></span> <span data-ttu-id="e646e-127">由于上述示例工作流中仅存在一个相关性，因此默认的 <xref:System.ServiceModel.Activities.CorrelationHandle> 管理足以满足需求。</span><span class="sxs-lookup"><span data-stu-id="e646e-127">Because there was only a single correlation in these sample workflows, the default <xref:System.ServiceModel.Activities.CorrelationHandle> management would have been sufficient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e646e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e646e-128">See Also</span></span>  
 [<span data-ttu-id="e646e-129">持久双工 &#91;WF 示例 &#93;</span><span class="sxs-lookup"><span data-stu-id="e646e-129">Durable Duplex &#91;WF Samples&#93;</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/durable-duplex.md)
