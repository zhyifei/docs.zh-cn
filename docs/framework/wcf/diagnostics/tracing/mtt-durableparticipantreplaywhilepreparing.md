---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 830a55a9f82c38b0a58783c49d3f58f64d5afdb4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="39d1c-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="39d1c-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="39d1c-103">WS-AT 协议服务从不响应 Prepare 的持久参与者接收到重播消息。</span><span class="sxs-lookup"><span data-stu-id="39d1c-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="39d1c-104">因此，中止了事务。</span><span class="sxs-lookup"><span data-stu-id="39d1c-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="39d1c-105">描述</span><span class="sxs-lookup"><span data-stu-id="39d1c-105">Description</span></span>  
 <span data-ttu-id="39d1c-106">如果持久参与者仍然在准备时接收到重播消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="39d1c-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="39d1c-107">这是此状态的非法消息，将中止事务。</span><span class="sxs-lookup"><span data-stu-id="39d1c-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="39d1c-108">疑难解答</span><span class="sxs-lookup"><span data-stu-id="39d1c-108">Troubleshooting</span></span>  
 <span data-ttu-id="39d1c-109">收到此错误表示持久参与者（包括从属事务管理器）已从故障中恢复，但不确定事务结果，因此请求提供其状态。</span><span class="sxs-lookup"><span data-stu-id="39d1c-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d1c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39d1c-110">See Also</span></span>  
 [<span data-ttu-id="39d1c-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="39d1c-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="39d1c-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="39d1c-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="39d1c-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="39d1c-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
