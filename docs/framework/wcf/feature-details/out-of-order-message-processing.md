---
title: "无序消息处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19ab5afbc1eb13a3126e94a040d51204fea131a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="4b08c-102">无序消息处理</span><span class="sxs-lookup"><span data-stu-id="4b08c-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="4b08c-103">工作流服务可能依赖于按特定顺序发送的消息。</span><span class="sxs-lookup"><span data-stu-id="4b08c-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="4b08c-104">工作流服务包含一个或多个 <xref:System.ServiceModel.Activities.Receive> 活动，而每个 <xref:System.ServiceModel.Activities.Receive> 活动需要一条特定消息。</span><span class="sxs-lookup"><span data-stu-id="4b08c-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="4b08c-105">如果无法保证单独传递传输，客户端发送的消息可能会延迟，从而可能无法按工作流服务所需的顺序传递消息。</span><span class="sxs-lookup"><span data-stu-id="4b08c-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="4b08c-106">实现无需按特定顺序传送消息的工作流服务时，通常使用并行活动来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="4b08c-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="4b08c-107">对于更复杂的应用程序协议，工作流将很快变得极其复杂。</span><span class="sxs-lookup"><span data-stu-id="4b08c-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="4b08c-108">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的无序消息处理功能可用于创建此类工作流，而且能够避免嵌套并行活动中的所有复杂性。</span><span class="sxs-lookup"><span data-stu-id="4b08c-108">The out-of-order message processing feature in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="4b08c-109">只有支持 <xref:System.ServiceModel.Channels.ReceiveContext> 的通道（如 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ 绑定）才支持无序消息处理。</span><span class="sxs-lookup"><span data-stu-id="4b08c-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="4b08c-110">启用无序消息处理</span><span class="sxs-lookup"><span data-stu-id="4b08c-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="4b08c-111">在 WorkflowService 上将 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 属性设置为`true` 即会启用无序消息处理。</span><span class="sxs-lookup"><span data-stu-id="4b08c-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="4b08c-112">下面的示例演示如何在代码中设置 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="4b08c-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="4b08c-113">还可以将 `AllowBufferedReceive` 特性应用到 XAML 中的工作流服务，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="4b08c-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b08c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b08c-114">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [<span data-ttu-id="4b08c-115">工作流服务</span><span class="sxs-lookup"><span data-stu-id="4b08c-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="4b08c-116">队列和可靠会话</span><span class="sxs-lookup"><span data-stu-id="4b08c-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
