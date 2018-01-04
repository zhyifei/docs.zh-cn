---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b433e5e3c0a961098f82ad601d127290b1d6bd73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="60d51-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="60d51-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="60d51-103">MSMQ 已拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="60d51-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="60d51-104">描述</span><span class="sxs-lookup"><span data-stu-id="60d51-104">Description</span></span>  
 <span data-ttu-id="60d51-105">此跟踪指示已拒绝 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="60d51-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="60d51-106">当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]（与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用时）无法处理 MSMQ 消息时可以拒绝这些消息。</span><span class="sxs-lookup"><span data-stu-id="60d51-106">MSMQ messages can be rejected when [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="60d51-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="60d51-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="60d51-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将拒绝病毒消息。</span><span class="sxs-lookup"><span data-stu-id="60d51-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="60d51-109">被拒绝的消息发送回发件人的[死信队列](http://go.microsoft.com/fwlink/?LinkID=99544)。</span><span class="sxs-lookup"><span data-stu-id="60d51-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="60d51-110">请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60d51-110">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="60d51-111">请参阅[MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)有关被拒绝的消息在 MSMQ 中的含义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60d51-111">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d51-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="60d51-112">See Also</span></span>  
 [<span data-ttu-id="60d51-113">跟踪</span><span class="sxs-lookup"><span data-stu-id="60d51-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="60d51-114">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="60d51-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="60d51-115">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="60d51-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="60d51-116">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="60d51-116">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="60d51-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="60d51-117">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkID=99548)
