---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 7dc1e4120caae7c4a592067f5e77ed4f56e82e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33478161"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="8bbcf-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="8bbcf-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="8bbcf-103">拒绝的病毒消息。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8bbcf-104">描述</span><span class="sxs-lookup"><span data-stu-id="8bbcf-104">Description</span></span>  
 <span data-ttu-id="8bbcf-105">该跟踪指示遇到病毒消息并随后将其拒绝。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="8bbcf-106">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="8bbcf-107">被拒绝的消息发送回发件人的[死信队列](http://go.microsoft.com/fwlink/?LinkId=99544)。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](http://go.microsoft.com/fwlink/?LinkId=99544).</span></span>  
  
 <span data-ttu-id="8bbcf-108">请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkId=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-108">See [Poison-Message Handling](http://go.microsoft.com/fwlink/?LinkId=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span> <span data-ttu-id="8bbcf-109">请参阅[MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)有关被拒绝的消息在 MSMQ 中的含义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8bbcf-109">See [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbcf-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bbcf-110">See Also</span></span>  
 [<span data-ttu-id="8bbcf-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="8bbcf-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8bbcf-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="8bbcf-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8bbcf-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="8bbcf-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="8bbcf-114">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="8bbcf-114">Poison-Message Handling</span></span>](http://go.microsoft.com/fwlink/?LinkId=99546)  
 [<span data-ttu-id="8bbcf-115">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="8bbcf-115">MQMarkMessageRejected</span></span>](http://go.microsoft.com/fwlink/?LinkId=99548)
