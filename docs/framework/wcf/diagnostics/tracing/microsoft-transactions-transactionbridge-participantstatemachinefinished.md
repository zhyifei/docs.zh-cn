---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 56eb40d4e8b2580ba094e67552872cf558c8a617
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642290"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="9853a-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="9853a-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="9853a-103">参与者列入的状态机进入已完成状态。</span><span class="sxs-lookup"><span data-stu-id="9853a-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9853a-104">描述</span><span class="sxs-lookup"><span data-stu-id="9853a-104">Description</span></span>  
 <span data-ttu-id="9853a-105">从属参与者列入已完成 2pc 处理时跟踪。</span><span class="sxs-lookup"><span data-stu-id="9853a-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="9853a-106">列入的结果可以是“已提交”或“已中止”。</span><span class="sxs-lookup"><span data-stu-id="9853a-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="9853a-107">此外，还会跟踪是否有参与者在“准备”过程中投票“只读”。</span><span class="sxs-lookup"><span data-stu-id="9853a-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9853a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="9853a-108">See also</span></span>
- [<span data-ttu-id="9853a-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="9853a-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9853a-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="9853a-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9853a-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="9853a-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
