---
title: "添加联机和脱机状态"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1a9f4cf65febd955e69d81f8dbb8f97aaa24e68c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="19641-102">添加联机和脱机状态</span><span class="sxs-lookup"><span data-stu-id="19641-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="19641-103">在很多情况下，应用程序必须监控有关对等通道连接状态的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="19641-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="19641-104">通过对 `GetProperty` 接口的实现调用 <xref:System.ServiceModel.IOnlineStatus> 方法可以获取此信息。</span><span class="sxs-lookup"><span data-stu-id="19641-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="19641-105">实现此接口的对象可以监视连接状态或注册事件处理程序（如 `OnOnline` 和 `OnOffline`），并对联机状态的更改立即做出反应。</span><span class="sxs-lookup"><span data-stu-id="19641-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="19641-106">在对等通道基础结构中，如果客户端连接到至少一个其他对等客户端，则将此客户端视为联机；否则，视为脱机。</span><span class="sxs-lookup"><span data-stu-id="19641-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="19641-107">在调试开发应用程序或向最终用户显示详细信息时，此功能特别有用。</span><span class="sxs-lookup"><span data-stu-id="19641-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19641-108">联机事件处理程序首先应确保节点在发送消息之前处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="19641-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19641-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19641-109">See Also</span></span>  
 [<span data-ttu-id="19641-110">生成对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="19641-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
