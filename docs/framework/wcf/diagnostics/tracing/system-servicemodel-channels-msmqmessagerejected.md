---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674777"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="1b967-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="1b967-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="1b967-103">MSMQ 已拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="1b967-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1b967-104">说明</span><span class="sxs-lookup"><span data-stu-id="1b967-104">Description</span></span>  
 <span data-ttu-id="1b967-105">此跟踪指示已拒绝 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="1b967-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="1b967-106">当 Windows 通信基础 （WCF） （与 NetMmqBinding 或 Msmq 集成绑定一起使用） 无法处理 MSMQ 消息时，MSMQ 消息可能会被拒绝。</span><span class="sxs-lookup"><span data-stu-id="1b967-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="1b967-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="1b967-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="1b967-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将拒绝病毒消息。</span><span class="sxs-lookup"><span data-stu-id="1b967-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="1b967-109">被拒绝的邮件将传递回发件人[的死信队列](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)。</span><span class="sxs-lookup"><span data-stu-id="1b967-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="1b967-110">有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="1b967-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="1b967-111">有关被拒绝的邮件在 MSMQ 中的含义的详细信息，请参阅[MQMarkMessage 拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))。</span><span class="sxs-lookup"><span data-stu-id="1b967-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b967-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b967-112">See also</span></span>

- [<span data-ttu-id="1b967-113">跟踪</span><span class="sxs-lookup"><span data-stu-id="1b967-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1b967-114">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="1b967-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1b967-115">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="1b967-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="1b967-116">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="1b967-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="1b967-117">[MQMark消息被拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="1b967-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
