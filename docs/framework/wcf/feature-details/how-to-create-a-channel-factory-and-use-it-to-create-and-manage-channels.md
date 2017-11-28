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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cb2e8384fca96149babb5df01e25a1b890db6ad3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a><span data-ttu-id="b6791-102">如何：创建通道工厂并用它创建和管理通道</span><span class="sxs-lookup"><span data-stu-id="b6791-102">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>
<span data-ttu-id="b6791-103">通过 <xref:System.ServiceModel.DuplexChannelFactory%601> 类可以创建和管理不同类型的双工通道，客户端可以使用这些通道在服务终结点之间发送和接收消息。</span><span class="sxs-lookup"><span data-stu-id="b6791-103">The <xref:System.ServiceModel.DuplexChannelFactory%601> class provides the means to create and manage duplex channels of different types that clients use to send and receive messages to and from service endpoints.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6791-104">示例</span><span class="sxs-lookup"><span data-stu-id="b6791-104">Example</span></span>  
 <span data-ttu-id="b6791-105">下面的代码演示如何创建通道工厂并用它来创建和管理通道。</span><span class="sxs-lookup"><span data-stu-id="b6791-105">The following code shows how to create a channel factory and use it to create and manage channels.</span></span>  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b6791-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6791-106">See Also</span></span>  
 <xref:System.ServiceModel.DuplexChannelFactory%601>
