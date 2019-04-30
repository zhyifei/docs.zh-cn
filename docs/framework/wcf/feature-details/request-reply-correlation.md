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
# <a name="request-reply-correlation"></a><span data-ttu-id="6f1bb-102">请求-答复相关</span><span class="sxs-lookup"><span data-stu-id="6f1bb-102">Request-Reply Correlation</span></span>
<span data-ttu-id="6f1bb-103">与使用请求-答复相关<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对实现双向操作，在工作流服务，并使用<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>中调用双向操作在另一个 Web 中的对服务。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="6f1bb-104">该服务调用 WCF 服务中的双向操作时，可以在传统命令性代码基于 Windows Communication Foundation (WCF) 服务，也可以是工作流服务。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="6f1bb-105">若要使用请求-答复相关，必须使用双向绑定，例如 <xref:System.ServiceModel.BasicHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="6f1bb-106">无论是调用还是实现双向操作，相关初始化步骤都非常相似，本节涵盖了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="6f1bb-107">在双向操作中配合使用相关和 Receive/SendReply</span><span class="sxs-lookup"><span data-stu-id="6f1bb-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="6f1bb-108">一个<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对用于在工作流服务中实现双向操作。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="6f1bb-109">运行时使用请求-答复相关，确保将答复调度到正确的调用方。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="6f1bb-110">如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流（这属于工作流服务），默认相关初始化足以满足需要。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="6f1bb-111">在此方案中， <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对由工作流，并不需要任何特定相关配置。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
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
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="6f1bb-112">显式初始化请求-答复相关</span><span class="sxs-lookup"><span data-stu-id="6f1bb-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="6f1bb-113">如果存在其他并行的双向操作，则应显式配置相关。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="6f1bb-114">这可以通过指定<xref:System.ServiceModel.Activities.CorrelationHandle>并<xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>，或者将<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>内<xref:System.ServiceModel.Activities.CorrelationScope>。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="6f1bb-115">在此示例中上, 配置请求-答复相关<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
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
  
 <span data-ttu-id="6f1bb-116">可以使用 <xref:System.ServiceModel.Activities.CorrelationScope> 活动来取代显式配置关联。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="6f1bb-117"><xref:System.ServiceModel.Activities.CorrelationScope> 向其包含的消息传递活动提供隐式 <xref:System.ServiceModel.Activities.CorrelationHandle>。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="6f1bb-118">在此示例中， <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>对包含在<xref:System.ServiceModel.Activities.CorrelationScope>。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="6f1bb-119">无需执行任何显式相关配置。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-119">No explicit correlation configuration is required.</span></span>  
  
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
  
 <span data-ttu-id="6f1bb-120">如果需要其他相关，可以使用相应消息传递活动（使用所需 <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> 类型）的 `CorrelationInitializer` 属性来配置这些相关。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="6f1bb-121">在双向操作中配合使用相关和 Send/ReceiveReply</span><span class="sxs-lookup"><span data-stu-id="6f1bb-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="6f1bb-122">虽然<xref:System.ServiceModel.Activities.Receive>活动仅可用于在托管的工作流服务<xref:System.ServiceModel.Activities.WorkflowServiceHost>，<xref:System.ServiceModel.Activities.Send>并且<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>对可用于所有必须调用 Web 服务上的方法的工作流中。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="6f1bb-123">如果使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流，将应用上一节中介绍的默认相关，否则，必须显式使用所需 <xref:System.ServiceModel.Activities.CorrelationInitializer> 和 <xref:System.ServiceModel.Activities.CorrelationHandle>，或者使用 <xref:System.ServiceModel.Activities.CorrelationScope> 的隐式句柄管理来配置相关。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="6f1bb-124">使用时**添加服务引用**活动会生成在具有双向操作的服务，该包装<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>显式对在内部使用请求/答复关联的活动指定。</span><span class="sxs-lookup"><span data-stu-id="6f1bb-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
