---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674817"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="ed50e-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="ed50e-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="ed50e-103">拒绝的病毒消息。</span><span class="sxs-lookup"><span data-stu-id="ed50e-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed50e-104">说明</span><span class="sxs-lookup"><span data-stu-id="ed50e-104">Description</span></span>  

 <span data-ttu-id="ed50e-105">该跟踪指示遇到病毒消息并随后将其拒绝。</span><span class="sxs-lookup"><span data-stu-id="ed50e-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="ed50e-106">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="ed50e-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="ed50e-107">被拒绝的邮件将传递回发件人[的死信队列](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)。</span><span class="sxs-lookup"><span data-stu-id="ed50e-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="ed50e-108">有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="ed50e-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="ed50e-109">有关被拒绝的邮件在 MSMQ 中的含义的详细信息，请参阅[MQMarkMessage 拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))。</span><span class="sxs-lookup"><span data-stu-id="ed50e-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed50e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed50e-110">See also</span></span>

- [<span data-ttu-id="ed50e-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="ed50e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ed50e-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="ed50e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ed50e-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="ed50e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="ed50e-114">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="ed50e-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="ed50e-115">[MQMark消息被拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="ed50e-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
