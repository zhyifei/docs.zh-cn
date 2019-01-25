---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: c8e476ab90fda9214831fbd5beaba518f3e3bd20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491423"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="9c5c2-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9c5c2-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="9c5c2-103">拒绝的病毒消息。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c5c2-104">描述</span><span class="sxs-lookup"><span data-stu-id="9c5c2-104">Description</span></span>  
 <span data-ttu-id="9c5c2-105">该跟踪指示遇到病毒消息并随后将其拒绝。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="9c5c2-106">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="9c5c2-107">将被拒绝的消息传递回发件人[死信队列](https://go.microsoft.com/fwlink/?LinkId=99544)。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="9c5c2-108">请参阅[病毒消息处理](https://go.microsoft.com/fwlink/?LinkId=99546)有关消息何时成为病毒和如何将服务配置为适当地处理更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-108">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="9c5c2-109">请参阅[MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548)有关被拒绝的消息在 MSMQ 中的含义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c5c2-109">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5c2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c5c2-110">See also</span></span>
- [<span data-ttu-id="9c5c2-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="9c5c2-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9c5c2-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="9c5c2-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9c5c2-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="9c5c2-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="9c5c2-114">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="9c5c2-114">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkId=99546)
- [<span data-ttu-id="9c5c2-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9c5c2-115">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkId=99548)
