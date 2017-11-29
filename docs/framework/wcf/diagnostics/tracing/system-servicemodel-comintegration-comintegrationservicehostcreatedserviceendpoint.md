---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="b21e0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="b21e0-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="b21e0-103">无法移动或删除消息。</span><span class="sxs-lookup"><span data-stu-id="b21e0-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b21e0-104">描述</span><span class="sxs-lookup"><span data-stu-id="b21e0-104">Description</span></span>  
 <span data-ttu-id="b21e0-105">跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。</span><span class="sxs-lookup"><span data-stu-id="b21e0-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="b21e0-106">MSMQ 消息由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 使用（当与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用时）。此跟踪与 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性的选定值相关。</span><span class="sxs-lookup"><span data-stu-id="b21e0-106">MSMQ messages are employed by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="b21e0-107">此跟踪不会指示出全部的系统失败。</span><span class="sxs-lookup"><span data-stu-id="b21e0-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="b21e0-108">但是，它会指示某条消息的选定病毒消息处理失败。</span><span class="sxs-lookup"><span data-stu-id="b21e0-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="b21e0-109">请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b21e0-109">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21e0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b21e0-110">See Also</span></span>  
 [<span data-ttu-id="b21e0-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="b21e0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b21e0-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="b21e0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b21e0-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b21e0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
