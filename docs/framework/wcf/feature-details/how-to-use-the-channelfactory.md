---
title: "如何：使用 ChannelFactory"
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
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd9c7c69ba65fe676e9ea0eba250fc3200e90c51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="f8a84-102">如何：使用 ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f8a84-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="f8a84-103"><xref:System.ServiceModel.ChannelFactory%601> 泛型类用于某些高级方案中，这些方案要求创建可用于创建多个通道的通道工厂。</span><span class="sxs-lookup"><span data-stu-id="f8a84-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="f8a84-104">创建和使用 ChannelFactory 类</span><span class="sxs-lookup"><span data-stu-id="f8a84-104">To create and use the ChannelFactory class</span></span>  
  
1.  <span data-ttu-id="f8a84-105">生成并运行一个 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="f8a84-105">Build and run an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f8a84-106">[设计和实现服务](../../../../docs/framework/wcf/designing-and-implementing-services.md)，[配置服务](../../../../docs/framework/wcf/configuring-services.md)，和[托管服务](../../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a84-106"> [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2.  <span data-ttu-id="f8a84-107">使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成客户端的协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="f8a84-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3.  <span data-ttu-id="f8a84-108">在客户端代码中，使用 <xref:System.ServiceModel.ChannelFactory%601> 类创建多个终结点侦听器。</span><span class="sxs-lookup"><span data-stu-id="f8a84-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8a84-109">示例</span><span class="sxs-lookup"><span data-stu-id="f8a84-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
