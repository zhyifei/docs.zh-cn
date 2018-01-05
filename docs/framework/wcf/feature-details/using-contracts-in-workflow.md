---
title: "在工作流中使用协定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ff40241bd48a4355738ca93ef2c80ceec55db11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="38736-102">在工作流中使用协定</span><span class="sxs-lookup"><span data-stu-id="38736-102">Using Contracts in Workflow</span></span>
<span data-ttu-id="38736-103">当实现服务时，您可以定义一些协定来描述此服务及其收发的数据。</span><span class="sxs-lookup"><span data-stu-id="38736-103">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="38736-104">这些数据表示为数据协定和消息协定；[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和工作流服务均在服务说明中使用数据协定和消息协定定义。</span><span class="sxs-lookup"><span data-stu-id="38736-104">The data is represented as data contracts and message contracts; both [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="38736-105">服务自身以 WSDL 形式公开元数据，以便描述服务的操作。</span><span class="sxs-lookup"><span data-stu-id="38736-105">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="38736-106">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，服务协定和操作协定将定义该框架支持的服务和操作。</span><span class="sxs-lookup"><span data-stu-id="38736-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="38736-107">但在工作流服务中，这些协定属于业务流程自身，它们由称为协定推理的过程在元数据中公开。</span><span class="sxs-lookup"><span data-stu-id="38736-107">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="38736-108">协定推理</span><span class="sxs-lookup"><span data-stu-id="38736-108">Contract Inference</span></span>  
 <span data-ttu-id="38736-109">使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流服务时，将检查工作流定义，并根据在工作流中找到的消息传递活动集生成协定。</span><span class="sxs-lookup"><span data-stu-id="38736-109">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="38736-110">具体而言，是使用下面的活动和属性来生成协定：</span><span class="sxs-lookup"><span data-stu-id="38736-110">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="38736-111"><xref:System.ServiceModel.Activities.Receive> 活动</span><span class="sxs-lookup"><span data-stu-id="38736-111"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <span data-ttu-id="38736-112"><xref:System.ServiceModel.Activities.SendReply> 活动</span><span class="sxs-lookup"><span data-stu-id="38736-112"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <span data-ttu-id="38736-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动</span><span class="sxs-lookup"><span data-stu-id="38736-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="38736-114">协定推理的最终结果是具有与 WCF 服务和操作协定相同的数据结构的服务说明。</span><span class="sxs-lookup"><span data-stu-id="38736-114">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="38736-115">然后，将使用此信息对工作流服务公开 WSDL。</span><span class="sxs-lookup"><span data-stu-id="38736-115">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38736-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="38736-116">See Also</span></span>  
 [<span data-ttu-id="38736-117">工作流服务</span><span class="sxs-lookup"><span data-stu-id="38736-117">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="38736-118">消息传递活动</span><span class="sxs-lookup"><span data-stu-id="38736-118">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [<span data-ttu-id="38736-119">如何：使用消息传递活动创建工作流服务</span><span class="sxs-lookup"><span data-stu-id="38736-119">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [<span data-ttu-id="38736-120">如何：创建使用现有服务协定的工作流服务</span><span class="sxs-lookup"><span data-stu-id="38736-120">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
