---
title: "请求-答复相关"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29286950cfef7d8e3e2c453bbdcc307c26e641de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="request-reply-correlation"></a>请求-答复相关
请求-答复相关用于<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对配合使用的工作流服务与实现双向操作<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>中调用双向操作在另一个站点中的对服务。 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务中调用双向操作时，该服务可以是传统的基于命令性代码的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务，也可以是工作流服务。 若要使用请求-答复相关，必须使用双向绑定，例如 <xref:System.ServiceModel.BasicHttpBinding>。 无论是调用还是实现双向操作，相关初始化步骤都非常相似，本节涵盖了这些步骤。  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>在双向操作中配合使用相关和 Receive/SendReply  
 A <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对用于在工作流服务中实现双向操作。 运行时使用请求-答复相关，确保将答复调度到正确的调用方。 如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流（这属于工作流服务），默认相关初始化足以满足需要。 在此方案中， <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对可供工作流，并不需要任何特定相关配置。  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>显式初始化请求-答复相关  
 如果存在其他并行的双向操作，则应显式配置相关。 这可以通过指定<xref:System.ServiceModel.Activities.CorrelationHandle>和<xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>，或通过将<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>内<xref:System.ServiceModel.Activities.CorrelationScope>。 在此示例中，在配置请求-答复相关<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对。  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 可以使用 <xref:System.ServiceModel.Activities.CorrelationScope> 活动来取代显式配置关联。 <xref:System.ServiceModel.Activities.CorrelationScope> 向其包含的消息传递活动提供隐式 <xref:System.ServiceModel.Activities.CorrelationHandle>。 在此示例中， <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对包含在<xref:System.ServiceModel.Activities.CorrelationScope>。 无需执行任何显式相关配置。  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 如果需要其他相关，可以使用相应消息传递活动（使用所需 <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> 类型）的 `CorrelationInitializer` 属性来配置这些相关。  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>在双向操作中配合使用相关和 Send/ReceiveReply  
 虽然<xref:System.ServiceModel.Activities.Receive>活动仅可由承载的工作流服务在<xref:System.ServiceModel.Activities.WorkflowServiceHost>，<xref:System.ServiceModel.Activities.Send>和<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>对可用于必须调用 Web 服务上的方法的任何工作流中。 如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流，将应用上一节中介绍的默认相关，否则，必须显式使用所需 <xref:System.ServiceModel.Activities.CorrelationInitializer> 和 <xref:System.ServiceModel.Activities.CorrelationHandle>，或者使用 <xref:System.ServiceModel.Activities.CorrelationScope> 的隐式句柄管理来配置相关。  
  
 使用时**添加服务引用**活动生成上使用双向操作的服务，该包装<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>显式对内部与请求/答复关联的活动指定。
