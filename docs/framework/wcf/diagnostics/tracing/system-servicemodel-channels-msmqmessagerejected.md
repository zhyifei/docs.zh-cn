---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 0addf987eac62c750a3c418e1b1c431d3f9bc1b0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195599"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="9c69f-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9c69f-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="9c69f-103">MSMQ 已拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9c69f-104">描述</span><span class="sxs-lookup"><span data-stu-id="9c69f-104">Description</span></span>  
 <span data-ttu-id="9c69f-105">此跟踪指示已拒绝 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="9c69f-106">当 Windows Communication Foundation (WCF) （与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用） 无法处理它们时，可以拒绝 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="9c69f-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="9c69f-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将拒绝病毒消息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="9c69f-109">将被拒绝的消息传递回发件人[死信队列](https://go.microsoft.com/fwlink/?LinkID=99544)。</span><span class="sxs-lookup"><span data-stu-id="9c69f-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://go.microsoft.com/fwlink/?LinkID=99544).</span></span>  
  
 <span data-ttu-id="9c69f-110">请参阅[病毒消息处理](https://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒和如何将服务配置为适当地处理更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
 <span data-ttu-id="9c69f-111">请参阅[MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548)有关被拒绝的消息在 MSMQ 中的含义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c69f-111">See [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) for more details on what a rejected message means in MSMQ.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c69f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c69f-112">See Also</span></span>  
 [<span data-ttu-id="9c69f-113">跟踪</span><span class="sxs-lookup"><span data-stu-id="9c69f-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="9c69f-114">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="9c69f-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="9c69f-115">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="9c69f-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="9c69f-116">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="9c69f-116">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)  
 [<span data-ttu-id="9c69f-117">MQMarkMessageRejected</span><span class="sxs-lookup"><span data-stu-id="9c69f-117">MQMarkMessageRejected</span></span>](https://go.microsoft.com/fwlink/?LinkID=99548)
