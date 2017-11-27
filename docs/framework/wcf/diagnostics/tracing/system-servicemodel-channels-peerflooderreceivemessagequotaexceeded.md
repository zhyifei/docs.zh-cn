---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2931eec5646b44eea19d70b11eb43c056b0ee0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="91f04-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="91f04-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="91f04-103">消息的入站接收速率过高。</span><span class="sxs-lookup"><span data-stu-id="91f04-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="91f04-104">描述</span><span class="sxs-lookup"><span data-stu-id="91f04-104">Description</span></span>  
 <span data-ttu-id="91f04-105">此跟踪在尝试处理入站消息时发生。</span><span class="sxs-lookup"><span data-stu-id="91f04-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="91f04-106">无法将消息转发给特定的邻居，因为已经超过了为该邻居设置的配额。</span><span class="sxs-lookup"><span data-stu-id="91f04-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="91f04-107">当无响应邻居无法清除为该邻居挂起的积压消息时会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="91f04-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="91f04-108">疑难解答</span><span class="sxs-lookup"><span data-stu-id="91f04-108">Troubleshooting</span></span>  
 <span data-ttu-id="91f04-109">降低在网格中发送消息的速率。</span><span class="sxs-lookup"><span data-stu-id="91f04-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f04-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91f04-110">See Also</span></span>  
 [<span data-ttu-id="91f04-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="91f04-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="91f04-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="91f04-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="91f04-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="91f04-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
