---
title: "如何：检查和修改服务上的消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64d9ccf97533be6be0da5d1e23763e8174aead3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inspect-and-modify-messages-on-the-service"></a><span data-ttu-id="cc5b5-102">如何：检查和修改服务上的消息</span><span class="sxs-lookup"><span data-stu-id="cc5b5-102">How to: Inspect and Modify Messages on the Service</span></span>
<span data-ttu-id="cc5b5-103">通过实现 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 并将其插入服务运行时，可以检查或修改 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> 客户端上的传入或传出消息。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-103">You can inspect or modify the incoming or outgoing messages across a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client by implementing a <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> and inserting it into the service runtime.</span></span> <span data-ttu-id="cc5b5-104">有关详细信息，请参阅[扩展调度程序](../../../../docs/framework/wcf/extending/extending-dispatchers.md)。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-104">For more information, see [Extending Dispatchers](../../../../docs/framework/wcf/extending/extending-dispatchers.md).</span></span> <span data-ttu-id="cc5b5-105">服务上的等效功能为 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="cc5b5-106">检查或修改消息</span><span class="sxs-lookup"><span data-stu-id="cc5b5-106">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="cc5b5-107">实现 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-107">Implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="cc5b5-108">根据您希望轻松插入服务消息检查器的范围，实现 <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>、<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-108">Implement a <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>, or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> interface depending upon the scope at which you want to easily insert your service message inspector.</span></span>  
  
3.  <span data-ttu-id="cc5b5-109">在 <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> 上调用 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 方法之前，先插入行为。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-109">Insert your behavior prior to calling the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cc5b5-110">有关详细信息，请参阅[配置和扩展的运行时带有行为](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-110">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc5b5-111">示例</span><span class="sxs-lookup"><span data-stu-id="cc5b5-111">Example</span></span>  
 <span data-ttu-id="cc5b5-112">下面的代码示例按顺序演示以下各项：</span><span class="sxs-lookup"><span data-stu-id="cc5b5-112">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="cc5b5-113">服务检查器实现。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-113">A service inspector implementation.</span></span>  
  
-   <span data-ttu-id="cc5b5-114">插入检查器的服务行为。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-114">A service behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="cc5b5-115">在服务应用程序中加载和运行该行为的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc5b5-115">A configuration file that loads and runs the behavior in a service application.</span></span>  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 [!code-xml[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  
  
## <a name="see-also"></a><span data-ttu-id="cc5b5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc5b5-116">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [<span data-ttu-id="cc5b5-117">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="cc5b5-117">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
