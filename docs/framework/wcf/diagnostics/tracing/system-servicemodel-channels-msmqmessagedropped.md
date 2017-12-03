---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d4b819b47d682a81bdcc031cc6b09604b072be7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="6baa7-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="6baa7-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="6baa7-103">MSMQ 已删除该消息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6baa7-104">描述</span><span class="sxs-lookup"><span data-stu-id="6baa7-104">Description</span></span>  
 <span data-ttu-id="6baa7-105">该跟踪指示已丢弃 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="6baa7-106">当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]（与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用时）无法处理 MSMQ 消息时，可以丢弃这些消息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-106">MSMQ messages can be dropped when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="6baa7-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="6baa7-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Drop` 时，将丢弃病毒消息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="6baa7-109">丢弃的消息会从队列中移除而不再可恢复。</span><span class="sxs-lookup"><span data-stu-id="6baa7-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="6baa7-110">请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6baa7-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6baa7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6baa7-111">See Also</span></span>  
 [<span data-ttu-id="6baa7-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="6baa7-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6baa7-113">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="6baa7-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6baa7-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="6baa7-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="6baa7-115">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="6baa7-115">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)
