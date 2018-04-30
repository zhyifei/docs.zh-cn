---
title: 如何：控制服务实例化
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fee03ba3c8f959e9a022cf1bdc561b79046121cc
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="92b7d-102">如何：控制服务实例化</span><span class="sxs-lookup"><span data-stu-id="92b7d-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="92b7d-103">通过设置服务的实例模式，可以指定创建 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>（及其关联的用户定义服务对象）的时间。</span><span class="sxs-lookup"><span data-stu-id="92b7d-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="92b7d-104">有关可能模式，请参见 <xref:System.ServiceModel.InstanceContextMode> 枚举。</span><span class="sxs-lookup"><span data-stu-id="92b7d-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="92b7d-105">有关各种行为的详细信息，请参阅[配置和扩展的运行时带有行为](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="92b7d-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="92b7d-106">有关工作示例，请参阅[行为](../../../../docs/framework/wcf/samples/behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="92b7d-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="92b7d-107">使用代码控制服务实例生存期</span><span class="sxs-lookup"><span data-stu-id="92b7d-107">To control the service instance lifetime using code</span></span>  
  
1.  <span data-ttu-id="92b7d-108">将 <xref:System.ServiceModel.ServiceBehaviorAttribute> 应用于服务类。</span><span class="sxs-lookup"><span data-stu-id="92b7d-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2.  <span data-ttu-id="92b7d-109">将 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 属性设置为下列值之一：<xref:System.ServiceModel.InstanceContextMode.PerCall>、<xref:System.ServiceModel.InstanceContextMode.PerSession> 或 <xref:System.ServiceModel.InstanceContextMode.Single>。</span><span class="sxs-lookup"><span data-stu-id="92b7d-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="92b7d-110">示例</span><span class="sxs-lookup"><span data-stu-id="92b7d-110">Example</span></span>  
 <span data-ttu-id="92b7d-111">下面的代码示例将 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 属性（attribute）的 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性（property）设置为 <xref:System.ServiceModel.InstanceContextMode.PerCall>。</span><span class="sxs-lookup"><span data-stu-id="92b7d-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="92b7d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="92b7d-112">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [<span data-ttu-id="92b7d-113">服务： 行为示例</span><span class="sxs-lookup"><span data-stu-id="92b7d-113">Service: Behaviors Samples</span></span>](http://msdn.microsoft.com/library/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
