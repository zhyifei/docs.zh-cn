---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90989d6b83ea5b54d5ed476d58a5d7f6e32f1fed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="72a06-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="72a06-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="72a06-103">参与者列入的状态机进入已完成状态。</span><span class="sxs-lookup"><span data-stu-id="72a06-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="72a06-104">描述</span><span class="sxs-lookup"><span data-stu-id="72a06-104">Description</span></span>  
 <span data-ttu-id="72a06-105">从属参与者列入已完成 2pc 处理时跟踪。</span><span class="sxs-lookup"><span data-stu-id="72a06-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="72a06-106">列入的结果可以是“已提交”或“已中止”。</span><span class="sxs-lookup"><span data-stu-id="72a06-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="72a06-107">此外，还会跟踪是否有参与者在“准备”过程中投票“只读”。</span><span class="sxs-lookup"><span data-stu-id="72a06-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72a06-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="72a06-108">See Also</span></span>  
 [<span data-ttu-id="72a06-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="72a06-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="72a06-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="72a06-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="72a06-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="72a06-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
