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
ms.openlocfilehash: 5c13da32e304e54d1826c6dd4ad83d5fbb17702a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="using-contracts-in-workflow"></a>在工作流中使用协定
当实现服务时，您可以定义一些协定来描述此服务及其收发的数据。 这些数据表示为数据协定和消息协定；[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和工作流服务均在服务说明中使用数据协定和消息协定定义。 服务自身以 WSDL 形式公开元数据，以便描述服务的操作。 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，服务协定和操作协定将定义该框架支持的服务和操作。 但在工作流服务中，这些协定属于业务流程自身，它们由称为协定推理的过程在元数据中公开。  
  
## <a name="contract-inference"></a>协定推理  
 使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 承载工作流服务时，将检查工作流定义，并根据在工作流中找到的消息传递活动集生成协定。 具体而言，是使用下面的活动和属性来生成协定：  
  
 <xref:System.ServiceModel.Activities.Receive> 活动  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <xref:System.ServiceModel.Activities.SendReply> 活动  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动  
  
 协定推理的最终结果是具有与 WCF 服务和操作协定相同的数据结构的服务说明。 然后，将使用此信息对工作流服务公开 WSDL。  
  
## <a name="see-also"></a>另请参阅  
 [工作流服务](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [消息传递活动](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [如何： 使用消息传递活动创建工作流服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [如何：创建使用现有服务协定的工作流服务](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
