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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 136baabc0760826aa9ba76dc19862c9c4b60e16e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="93c42-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="93c42-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="93c42-103">消息的入站接收速率过高。</span><span class="sxs-lookup"><span data-stu-id="93c42-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="93c42-104">描述</span><span class="sxs-lookup"><span data-stu-id="93c42-104">Description</span></span>  
 <span data-ttu-id="93c42-105">此跟踪在尝试处理入站消息时发生。</span><span class="sxs-lookup"><span data-stu-id="93c42-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="93c42-106">无法将消息转发给特定的邻居，因为已经超过了为该邻居设置的配额。</span><span class="sxs-lookup"><span data-stu-id="93c42-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="93c42-107">当无响应邻居无法清除为该邻居挂起的积压消息时会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="93c42-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="93c42-108">疑难解答</span><span class="sxs-lookup"><span data-stu-id="93c42-108">Troubleshooting</span></span>  
 <span data-ttu-id="93c42-109">降低在网格中发送消息的速率。</span><span class="sxs-lookup"><span data-stu-id="93c42-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93c42-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="93c42-110">See Also</span></span>  
 [<span data-ttu-id="93c42-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="93c42-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="93c42-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="93c42-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="93c42-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="93c42-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
