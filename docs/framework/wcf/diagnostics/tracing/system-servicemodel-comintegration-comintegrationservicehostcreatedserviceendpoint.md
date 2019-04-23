---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: d56bbf145c85902d8e5f1fd21f760633121da6da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115279"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="5bb11-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="5bb11-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="5bb11-103">无法移动或删除消息。</span><span class="sxs-lookup"><span data-stu-id="5bb11-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5bb11-104">描述</span><span class="sxs-lookup"><span data-stu-id="5bb11-104">Description</span></span>  
 <span data-ttu-id="5bb11-105">跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。</span><span class="sxs-lookup"><span data-stu-id="5bb11-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="5bb11-106">使用 MSMQ 消息时由 Windows Communication Foundation (WCF) （当与 NetMsmqBinding 或 msmqintegrationbinding 一起使用）。此跟踪与所选的值的`ReceiveErrorHandling`NetMsmqBinding 或 MsmqIntegrationBinding 上的属性。</span><span class="sxs-lookup"><span data-stu-id="5bb11-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="5bb11-107">此跟踪不会指示出全部的系统失败。</span><span class="sxs-lookup"><span data-stu-id="5bb11-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="5bb11-108">但是，它会指示某条消息的选定病毒消息处理失败。</span><span class="sxs-lookup"><span data-stu-id="5bb11-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="5bb11-109">请参阅[病毒消息处理](https://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒和如何将服务配置为适当地处理更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bb11-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb11-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bb11-110">See also</span></span>

- [<span data-ttu-id="5bb11-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="5bb11-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="5bb11-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="5bb11-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="5bb11-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="5bb11-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
