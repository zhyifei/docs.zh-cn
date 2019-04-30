---
title: 请求-答复相关
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: c38854ad42ad4dddce5171482f3ddcfe5bd16b61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991128"
---
# <a name="request-reply-correlation"></a>请求-答复相关
与使用请求-答复相关<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对实现双向操作，在工作流服务，并使用<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>中调用双向操作在另一个 Web 中的对服务。 该服务调用 WCF 服务中的双向操作时，可以在传统命令性代码基于 Windows Communication Foundation (WCF) 服务，也可以是工作流服务。 若要使用请求-答复相关，必须使用双向绑定，例如 <xref:System.ServiceModel.BasicHttpBinding>。 无论是调用还是实现双向操作，相关初始化步骤都非常相似，本节涵盖了这些步骤。  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>在双向操作中配合使用相关和 Receive/SendReply  
 一个<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对用于在工作流服务中实现双向操作。 运行时使用请求-答复相关，确保将答复调度到正确的调用方。 如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流（这属于工作流服务），默认相关初始化足以满足需要。 在此方案中， <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对由工作流，并不需要任何特定相关配置。  
  
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
 如果存在其他并行的双向操作，则应显式配置相关。 这可以通过指定<xref:System.ServiceModel.Activities.CorrelationHandle>并<xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>，或者将<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>内<xref:System.ServiceModel.Activities.CorrelationScope>。 在此示例中上, 配置请求-答复相关<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对。  
  
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
 虽然<xref:System.ServiceModel.Activities.Receive>活动仅可用于在托管的工作流服务<xref:System.ServiceModel.Activities.WorkflowServiceHost>，<xref:System.ServiceModel.Activities.Send>并且<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>对可用于所有必须调用 Web 服务上的方法的工作流中。 如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流，将应用上一节中介绍的默认相关，否则，必须显式使用所需 <xref:System.ServiceModel.Activities.CorrelationInitializer> 和 <xref:System.ServiceModel.Activities.CorrelationHandle>，或者使用 <xref:System.ServiceModel.Activities.CorrelationScope> 的隐式句柄管理来配置相关。  
  
 使用时**添加服务引用**活动会生成在具有双向操作的服务，该包装<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>显式对在内部使用请求/答复关联的活动指定。
