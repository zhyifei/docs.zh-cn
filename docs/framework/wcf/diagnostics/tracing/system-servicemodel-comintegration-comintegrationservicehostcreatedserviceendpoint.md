---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674779"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="1f047-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="1f047-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="1f047-103">无法移动或删除消息。</span><span class="sxs-lookup"><span data-stu-id="1f047-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f047-104">说明</span><span class="sxs-lookup"><span data-stu-id="1f047-104">Description</span></span>  
 <span data-ttu-id="1f047-105">跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。</span><span class="sxs-lookup"><span data-stu-id="1f047-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="1f047-106">MSMQ 消息受雇于 Windows 通信基金会 （WCF）（当与 NetMmq 绑定或 Msmq 集成绑定一起使用时）。此跟踪与 NetMmqBinding`ReceiveErrorHandling`或 Msmq集成绑定上属性的选定值相关。</span><span class="sxs-lookup"><span data-stu-id="1f047-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="1f047-107">此跟踪不会指示出全部的系统失败。</span><span class="sxs-lookup"><span data-stu-id="1f047-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="1f047-108">但是，它会指示某条消息的选定病毒消息处理失败。</span><span class="sxs-lookup"><span data-stu-id="1f047-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="1f047-109">有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="1f047-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f047-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f047-110">See also</span></span>

- [<span data-ttu-id="1f047-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="1f047-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1f047-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="1f047-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1f047-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="1f047-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
