---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 8cc32e7b38bfd1bdafd2377ad759f98b248d722e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710451"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="6f4b5-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="6f4b5-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="6f4b5-103">用于协调器登记的状态机已进入已完成状态。</span><span class="sxs-lookup"><span data-stu-id="6f4b5-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f4b5-104">描述</span><span class="sxs-lookup"><span data-stu-id="6f4b5-104">Description</span></span>  
 <span data-ttu-id="6f4b5-105">本地事务管理器认为高级协调器登记已完成 2pc 处理时跟踪。</span><span class="sxs-lookup"><span data-stu-id="6f4b5-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="6f4b5-106">登记的结果可以是“已提交”、“已中止”或“已忘记”。</span><span class="sxs-lookup"><span data-stu-id="6f4b5-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="6f4b5-107">本地事务管理器在“准备”过程中对“只读”投票时也会进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="6f4b5-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4b5-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f4b5-108">See also</span></span>
- [<span data-ttu-id="6f4b5-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="6f4b5-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="6f4b5-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="6f4b5-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6f4b5-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="6f4b5-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
