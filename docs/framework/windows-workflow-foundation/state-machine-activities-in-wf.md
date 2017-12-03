---
title: "WF 中的状态机活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed2b5ace499af3c050529e9f0f2cdd3634c247fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="cc9d4-102">WF 中的状态机活动</span><span class="sxs-lookup"><span data-stu-id="cc9d4-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="cc9d4-103"> 提供几个系统提供的活动和用于创建状态机工作流的活动设计器。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-103"> provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="cc9d4-104">使用熟悉的状态机范例执行包含的活动。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="cc9d4-105">代表状态机中的状态。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="cc9d4-106">表示状态机中的终止状态。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="cc9d4-107"><xref:System.Activities.Core.Presentation.FinalState> 是在创建预配置为终止状态的 <xref:System.Activities.Statements.State> 时所使用的活动设计器。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="cc9d4-108">有关详细信息，请参阅[FinalState 活动设计器](/visualstudio/workflow-designer/finalstate-activity-designer)。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="cc9d4-109">表示两个状态间的转换。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-109">Represents the transition between two states.</span></span> <span data-ttu-id="cc9d4-110">没有任何**工具箱**项<xref:System.Activities.Statements.Transition>; 在工作流设计器上通过拖放线条，两个状态之间创建转换或通过将一个状态时出现的三角形上一个状态悬停在另一个.</span><span class="sxs-lookup"><span data-stu-id="cc9d4-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="cc9d4-111">有关详细信息，请参阅[Transition 活动设计器](/visualstudio/workflow-designer/transition-activity-designer)。</span><span class="sxs-lookup"><span data-stu-id="cc9d4-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc9d4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc9d4-112">See Also</span></span>  
 [<span data-ttu-id="cc9d4-113">入门教程</span><span class="sxs-lookup"><span data-stu-id="cc9d4-113">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
