---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674798"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="c2702-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="c2702-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="c2702-103">MSMQ 已删除该消息。</span><span class="sxs-lookup"><span data-stu-id="c2702-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c2702-104">说明</span><span class="sxs-lookup"><span data-stu-id="c2702-104">Description</span></span>  
 <span data-ttu-id="c2702-105">该跟踪指示已丢弃 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="c2702-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="c2702-106">当 Windows 通信基础 （WCF） （与 NetMmqBinding 或 Msmq 集成绑定一起使用） 无法处理它们时，MSMQ 消息可以被删除。</span><span class="sxs-lookup"><span data-stu-id="c2702-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="c2702-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="c2702-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="c2702-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Drop` 时，将丢弃病毒消息。</span><span class="sxs-lookup"><span data-stu-id="c2702-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="c2702-109">丢弃的消息会从队列中移除而不再可恢复。</span><span class="sxs-lookup"><span data-stu-id="c2702-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="c2702-110">有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="c2702-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2702-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2702-111">See also</span></span>

- [<span data-ttu-id="c2702-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="c2702-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="c2702-113">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="c2702-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c2702-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="c2702-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="c2702-115">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="c2702-115">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
