---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fe88e70ab4955305d78baa1158cd73a93ba2ed2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476315"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="97d33-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="97d33-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="97d33-103">WS-AT 协议服务从不响应 Prepare 的持久参与者接收到重播消息。</span><span class="sxs-lookup"><span data-stu-id="97d33-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="97d33-104">因此，中止了事务。</span><span class="sxs-lookup"><span data-stu-id="97d33-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="97d33-105">描述</span><span class="sxs-lookup"><span data-stu-id="97d33-105">Description</span></span>  
 <span data-ttu-id="97d33-106">如果持久参与者仍然在准备时接收到重播消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="97d33-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="97d33-107">这是此状态的非法消息，将中止事务。</span><span class="sxs-lookup"><span data-stu-id="97d33-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="97d33-108">疑难解答</span><span class="sxs-lookup"><span data-stu-id="97d33-108">Troubleshooting</span></span>  
 <span data-ttu-id="97d33-109">收到此错误表示持久参与者（包括从属事务管理器）已从故障中恢复，但不确定事务结果，因此请求提供其状态。</span><span class="sxs-lookup"><span data-stu-id="97d33-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d33-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="97d33-110">See Also</span></span>  
 [<span data-ttu-id="97d33-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="97d33-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="97d33-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="97d33-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="97d33-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="97d33-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
