---
title: "如何：创建通道工厂并用它创建和管理通道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d41dfc85df1b706028fd95465596a980c040d512
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="3cbd9-102">如何：创建通道工厂并用它创建和管理通道</span><span class="sxs-lookup"><span data-stu-id="3cbd9-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>
<span data-ttu-id="3cbd9-103">通过 <xref:System.ServiceModel.DuplexChannelFactory%601> 类可以创建和管理不同类型的双工通道，客户端可以使用这些通道在服务终结点之间发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="3cbd9-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cbd9-104">示例</span><span class="sxs-lookup"><span data-stu-id="3cbd9-104">Example</span></span>  
 <span data-ttu-id="3cbd9-105">下面的代码演示如何创建通道工厂并用它来创建和管理通道。</span><span class="sxs-lookup"><span data-stu-id="3cbd9-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3cbd9-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cbd9-106">See Also</span></span>  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
