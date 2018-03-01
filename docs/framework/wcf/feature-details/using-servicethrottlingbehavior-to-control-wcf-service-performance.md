---
title: "使用 ServiceThrottlingBehavior 控制 WCF 服务性能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b7e00e70bab0c5652bbc721d582a1b276e6a3fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>使用 ServiceThrottlingBehavior 控制 WCF 服务性能
<xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 类公开的属性可用于限制在应用程序级别创建实例或会话的数量。 使用此行为，您可以精细调整 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序的性能。  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>控制服务实例和并发调用  
 使用 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 属性指定在 <xref:System.ServiceModel.ServiceHost> 类上主动处理的最大消息数，并使用 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 属性指定服务中 <xref:System.ServiceModel.InstanceContext> 对象的最大数目。  
  
 因为通常确定这些属性的设置发生后运行针对对应用程序的实际经验加载，有关设置<xref:System.ServiceModel.Description.ServiceThrottlingBehavior>通常在应用程序配置文件中使用指定属性[ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)元素。  
  
 下面的代码示例演示如何使用将 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>、<xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> 和 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 属性设置为 1（作为最小示例）的应用程序配置文件中的 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 类。 实际体验确定任何特定应用程序的最佳设置。  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 确切的运行时行为取决于 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 和 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 属性的值，这两种属性分别控制操作一次可执行的消息数以及有关传入通道会话的服务 <xref:System.ServiceModel.InstanceContext> 的生存期。  
  
 有关详细信息，请参见 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 和 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
