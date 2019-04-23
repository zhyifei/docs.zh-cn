---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 7f37cb5d9ee3d2d9d56519f785388f278b3333b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170721"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="ca129-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="ca129-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="ca129-103">参与者列入的状态机进入已完成状态。</span><span class="sxs-lookup"><span data-stu-id="ca129-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ca129-104">描述</span><span class="sxs-lookup"><span data-stu-id="ca129-104">Description</span></span>  
 <span data-ttu-id="ca129-105">从属参与者列入已完成 2pc 处理时跟踪。</span><span class="sxs-lookup"><span data-stu-id="ca129-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="ca129-106">列入的结果可以是“已提交”或“已中止”。</span><span class="sxs-lookup"><span data-stu-id="ca129-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="ca129-107">此外，还会跟踪是否有参与者在“准备”过程中投票“只读”。</span><span class="sxs-lookup"><span data-stu-id="ca129-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca129-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca129-108">See also</span></span>

- [<span data-ttu-id="ca129-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="ca129-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ca129-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="ca129-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ca129-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="ca129-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
