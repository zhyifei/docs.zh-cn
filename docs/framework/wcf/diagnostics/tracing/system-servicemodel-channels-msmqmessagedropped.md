---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 07bef8b391a03f2c011e1d1a7c7fb4fad908e022
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405326"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="5033f-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="5033f-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="5033f-103">MSMQ 已删除该消息。</span><span class="sxs-lookup"><span data-stu-id="5033f-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5033f-104">描述</span><span class="sxs-lookup"><span data-stu-id="5033f-104">Description</span></span>  
 <span data-ttu-id="5033f-105">该跟踪指示已丢弃 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="5033f-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="5033f-106">当 Windows Communication Foundation (WCF) （与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用） 无法处理它们时，可以删除 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="5033f-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="5033f-107">这些消息称为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="5033f-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="5033f-108">当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Drop` 时，将丢弃病毒消息。</span><span class="sxs-lookup"><span data-stu-id="5033f-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="5033f-109">丢弃的消息会从队列中移除而不再可恢复。</span><span class="sxs-lookup"><span data-stu-id="5033f-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="5033f-110">请参阅[病毒消息处理](https://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒和如何将服务配置为适当地处理更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5033f-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5033f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5033f-111">See Also</span></span>  
 [<span data-ttu-id="5033f-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="5033f-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="5033f-113">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="5033f-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="5033f-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="5033f-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [<span data-ttu-id="5033f-115">病毒消息处理</span><span class="sxs-lookup"><span data-stu-id="5033f-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
