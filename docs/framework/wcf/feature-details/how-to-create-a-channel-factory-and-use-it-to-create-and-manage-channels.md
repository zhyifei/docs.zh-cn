---
title: 如何：创建通道工厂并用它创建和管理通道
ms.date: 03/30/2017
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
ms.openlocfilehash: f0855da00a70dff3ef7ffdb85b2011a9bda00688
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489965"
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="1c86e-102">如何：创建通道工厂并用它创建和管理通道</span><span class="sxs-lookup"><span data-stu-id="1c86e-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>
<span data-ttu-id="1c86e-103">通过 <xref:System.ServiceModel.DuplexChannelFactory%601> 类可以创建和管理不同类型的双工通道，客户端可以使用这些通道在服务终结点之间发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="1c86e-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c86e-104">示例</span><span class="sxs-lookup"><span data-stu-id="1c86e-104">Example</span></span>  
 <span data-ttu-id="1c86e-105">下面的代码演示如何创建通道工厂并用它来创建和管理通道。</span><span class="sxs-lookup"><span data-stu-id="1c86e-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c86e-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c86e-106">See Also</span></span>  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
