---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486771"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="2eacd-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="2eacd-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="2eacd-103">WS-AT 协议服务从不响应 Prepare 的持久参与者接收到重播消息。</span><span class="sxs-lookup"><span data-stu-id="2eacd-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="2eacd-104">因此，中止了事务。</span><span class="sxs-lookup"><span data-stu-id="2eacd-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2eacd-105">描述</span><span class="sxs-lookup"><span data-stu-id="2eacd-105">Description</span></span>  
 <span data-ttu-id="2eacd-106">如果持久参与者仍然在准备时接收到重播消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="2eacd-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="2eacd-107">这是此状态的非法消息，将中止事务。</span><span class="sxs-lookup"><span data-stu-id="2eacd-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2eacd-108">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2eacd-108">Troubleshooting</span></span>

<span data-ttu-id="2eacd-109">收到此错误可能表示持久参与者 （包括从属事务管理器） 已从故障; 恢复但是，它不确定事务结果，并请求其状态。</span><span class="sxs-lookup"><span data-stu-id="2eacd-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eacd-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eacd-110">See also</span></span>

- [<span data-ttu-id="2eacd-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="2eacd-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2eacd-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="2eacd-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2eacd-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="2eacd-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
