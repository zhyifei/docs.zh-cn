---
title: WF 中的状态机活动
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120908"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="3f2b4-102">WF 中的状态机活动</span><span class="sxs-lookup"><span data-stu-id="3f2b4-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="3f2b4-103">提供用于创建状态机工作流的多个系统提供的活动和活动设计器。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="3f2b4-104">使用熟悉的状态机范例执行包含的活动。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="3f2b4-105">代表状态机中的状态。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="3f2b4-106">表示状态机中的终止状态。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-106">Represents a terminating state in a state machine.</span></span> <xref:System.Activities.Core.Presentation.FinalState> <span data-ttu-id="3f2b4-107">为活动设计器，当使用创建<xref:System.Activities.Statements.State>预配置为终止状态。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-107">is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="3f2b4-108">有关详细信息，请参阅[FinalState 活动设计器](/visualstudio/workflow-designer/finalstate-activity-designer)。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="3f2b4-109">表示两个状态间的转换。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-109">Represents the transition between two states.</span></span> <span data-ttu-id="3f2b4-110">没有任何**工具箱**项<xref:System.Activities.Statements.Transition>; 通过拖放两个状态之间的一条线方式在工作流设计器上创建转换或通过删除状态时出现的三角形上一个状态悬停在另一个.</span><span class="sxs-lookup"><span data-stu-id="3f2b4-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="3f2b4-111">有关详细信息，请参阅[Transition 活动设计器](/visualstudio/workflow-designer/transition-activity-designer)。</span><span class="sxs-lookup"><span data-stu-id="3f2b4-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f2b4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f2b4-112">See also</span></span>

- [<span data-ttu-id="3f2b4-113">入门教程</span><span class="sxs-lookup"><span data-stu-id="3f2b4-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
