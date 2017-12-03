---
title: "上下文交换相关"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18f6501d2c5a97f7f267321e9cf0b06737afa5bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="context-exchange-correlation"></a><span data-ttu-id="7b548-102">上下文交换相关</span><span class="sxs-lookup"><span data-stu-id="7b548-102">Context Exchange Correlation</span></span>
<span data-ttu-id="7b548-103">上下文相关基于中所述的上下文交换机制[.NET 上下文交换协议规范](http://go.microsoft.com/fwlink/?LinkId=166059)。</span><span class="sxs-lookup"><span data-stu-id="7b548-103">Context correlation is based on the context exchange mechanism described in the [.NET Context Exchange Protocol Specification](http://go.microsoft.com/fwlink/?LinkId=166059).</span></span> <span data-ttu-id="7b548-104">上下文相关使用已知的上下文头或 cookie 将消息与正确的实例相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-104">Context correlation uses a well-known context header or cookie to relate messages to the correct instance.</span></span> <span data-ttu-id="7b548-105">若要使用上下文相关，必须在提供给 <xref:System.ServiceModel.BasicHttpContextBinding> 的终结点上使用诸如 <xref:System.ServiceModel.WSHttpContextBinding>、<xref:System.ServiceModel.NetTcpContextBinding> 或 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 之类的基于上下文的绑定。</span><span class="sxs-lookup"><span data-stu-id="7b548-105">To use context correlation, a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, or <xref:System.ServiceModel.NetTcpContextBinding> must be used on the endpoint provided to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7b548-106">此主题说明如何在工作流服务中将上下文相关用于消息传送活动。</span><span class="sxs-lookup"><span data-stu-id="7b548-106">This topic explains how to use context correlation with messaging activities in a workflow service.</span></span>  
  
## <a name="using-context-correlation"></a><span data-ttu-id="7b548-107">使用上下文相关</span><span class="sxs-lookup"><span data-stu-id="7b548-107">Using Context Correlation</span></span>  
 <span data-ttu-id="7b548-108">如果客户端必须重复调用工作流服务，并且系统使用一个上下文绑定承载该服务，此时可以使用上下文相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-108">Context correlation is used when a client must make repeated calls into a workflow service and the service is hosted using one of the context bindings.</span></span> <span data-ttu-id="7b548-109">这种类型的相关初始化由<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对工作流服务中的。</span><span class="sxs-lookup"><span data-stu-id="7b548-109">This type of correlation is initialized by a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair in the workflow service.</span></span> <span data-ttu-id="7b548-110">上下文将与答复一起发送回客户端，客户端随后将此上下文附加到对服务的后续调用。</span><span class="sxs-lookup"><span data-stu-id="7b548-110">The context is sent back to the client together with the reply, and then the client attaches this context on subsequent calls to the service.</span></span>  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a><span data-ttu-id="7b548-111">在工作流服务中配置上下文相关</span><span class="sxs-lookup"><span data-stu-id="7b548-111">Configuring Context Correlation in a Workflow Service</span></span>  
 <span data-ttu-id="7b548-112">使用与答复初始传入消息的 <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> 活动相关联的 <xref:System.ServiceModel.Activities.SendReply> 初始化上下文相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-112">Context correlation is initialized by using a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> that is associated with the <xref:System.ServiceModel.Activities.SendReply> activity that replies to the initial incoming message.</span></span> <span data-ttu-id="7b548-113">在下面的实例中，配置了 <xref:System.ServiceModel.Activities.SendReply> 来初始化上下文相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-113">In the following example, the <xref:System.ServiceModel.Activities.SendReply> is configured to initialize a context correlation.</span></span>  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  <span data-ttu-id="7b548-114">在此示例中，实际上使用了两种类型的相关：上下文相关和请求-答复相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-114">In this example, there are actually two types of correlation being used: context correlation and request-reply correlation.</span></span> <span data-ttu-id="7b548-115">使用上下文相关是为了将来自客户端的调用路由到正确的实例。</span><span class="sxs-lookup"><span data-stu-id="7b548-115">The context correlation is used so that calls from clients are routed to the correct instance.</span></span> <span data-ttu-id="7b548-116">请求-答复相关由 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 活动一起使用，以实现这些活动建模的双向操作。</span><span class="sxs-lookup"><span data-stu-id="7b548-116">The request-reply correlation is used by the <xref:System.ServiceModel.Activities.Receive> and the <xref:System.ServiceModel.Activities.SendReply> activities together to implement the two-way operation modeled by these activities.</span></span> <span data-ttu-id="7b548-117">在此示例中，显式配置仅上下文相关，与<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对使用由的隐式提供的默认请求-答复相关<xref:System.ServiceModel.Activities.CorrelationHandle>管理<xref:System.ServiceModel.Activities.WorkflowServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="7b548-117">In this example, only the context correlation is explicitly configured, and the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is using the default request-reply correlation that is provided by the implicit <xref:System.ServiceModel.Activities.CorrelationHandle> management of <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="7b548-118">使用时**ReceiveAndSendReply**显式配置在工作流设计器中，请求-答复相关的活动模板。</span><span class="sxs-lookup"><span data-stu-id="7b548-118">When using the **ReceiveAndSendReply** activity template in the workflow designer, request-reply correlation is explicitly configured.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7b548-119">请求-答复相关和隐式相关句柄管理，请参阅[请求-答复](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)和[相关概述](../../../../docs/framework/wcf/feature-details/correlation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7b548-119"> request-reply correlation and implicit correlation handle management, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) and [Correlation Overview](../../../../docs/framework/wcf/feature-details/correlation-overview.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7b548-120">**ReceiveAndSendReply**活动模板，请参阅[ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer)。</span><span class="sxs-lookup"><span data-stu-id="7b548-120"> the **ReceiveAndSendReply** activity template, see [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).</span></span>  
  
 <span data-ttu-id="7b548-121">工作流服务中的后续 <xref:System.ServiceModel.Activities.Receive> 活动可以引用由上一示例中的 <xref:System.ServiceModel.Activities.CorrelationHandle> 初始化的 <xref:System.ServiceModel.Activities.SendReply>。</span><span class="sxs-lookup"><span data-stu-id="7b548-121">Subsequent <xref:System.ServiceModel.Activities.Receive> activities in the workflow service can reference the <xref:System.ServiceModel.Activities.CorrelationHandle> that was initialized by the <xref:System.ServiceModel.Activities.SendReply> in the previous example.</span></span>  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 <span data-ttu-id="7b548-122">随后，在 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 上配置终结点以使用基于上下文的绑定，如 <xref:System.ServiceModel.BasicHttpContextBinding>。</span><span class="sxs-lookup"><span data-stu-id="7b548-122">The endpoint is then configured on the <xref:System.ServiceModel.Activities.WorkflowServiceHost> to use a context-based binding, such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span>  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a><span data-ttu-id="7b548-123">在工作流客户端中配置上下文相关</span><span class="sxs-lookup"><span data-stu-id="7b548-123">Configuring Context Correlation in a Workflow Client</span></span>  
 <span data-ttu-id="7b548-124">客户端为其他工作流时，也必须在客户端配置上下文相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-124">When the client is another workflow, context correlation must be configured on the client as well.</span></span> <span data-ttu-id="7b548-125">在客户端工作流，<xref:System.ServiceModel.Activities.ReceiveReply>的<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>必须使用配置进行初始调用到工作流服务的对<xref:System.ServiceModel.Activities.ContextCorrelationInitializer>。</span><span class="sxs-lookup"><span data-stu-id="7b548-125">On the client workflow, the <xref:System.ServiceModel.Activities.ReceiveReply> of the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that makes the initial call to the workflow service must be configured with a <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.</span></span>  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 <span data-ttu-id="7b548-126">初始化相关后，后续 <xref:System.ServiceModel.Activities.Send> 活动即可使用 <xref:System.ServiceModel.Activities.CorrelationHandle> 调用同一服务实例上的方法。</span><span class="sxs-lookup"><span data-stu-id="7b548-126">After the correlation is initialized, subsequent <xref:System.ServiceModel.Activities.Send> activities can use the <xref:System.ServiceModel.Activities.CorrelationHandle> to invoke methods on the same service instance.</span></span>  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 <span data-ttu-id="7b548-127">请注意，在上面这些示例中，已显式配置上下文相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-127">Note that in these examples, the context correlation has been explicitly configured.</span></span> <span data-ttu-id="7b548-128">如果客户端工作流也未在 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中承载，除非活动都包含在一个 <xref:System.ServiceModel.Activities.CorrelationScope> 活动中，否则必须显式配置相关。</span><span class="sxs-lookup"><span data-stu-id="7b548-128">If the client workflow is not also hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, then correlation must be explicitly configured, unless the activities are contained within a <xref:System.ServiceModel.Activities.CorrelationScope> activity.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7b548-129">上下文相关，请参阅[NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf)示例。</span><span class="sxs-lookup"><span data-stu-id="7b548-129"> context correlation, see the [NetContextExchangeCorrelation](http://msdn.microsoft.com/en-us/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) sample.</span></span>  
  
 <span data-ttu-id="7b548-130">如果调用工作流服务的客户端不是工作流，则只要客户端将首次调用工作流服务时返回的上下文显式传递回去，它仍然可以进行重复调用。</span><span class="sxs-lookup"><span data-stu-id="7b548-130">If the client that is making calls to the workflow service is not a workflow, then it can still make repeated calls as long as it explicitly passes back the context that is returned from the first call to the workflow service.</span></span> <span data-ttu-id="7b548-131">默认情况下，通过添加服务而生成的代理在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 存储中引用此上下文，并传递此上下文。</span><span class="sxs-lookup"><span data-stu-id="7b548-131">Proxies generated by adding a service reference in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] store and pass this context by default.</span></span>
