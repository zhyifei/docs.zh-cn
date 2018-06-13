---
title: 'How to: Create a Workflow'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 98235eac9309ecb0229281160f210079e712b755
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513258"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="d5399-102">How to: Create a Workflow</span><span class="sxs-lookup"><span data-stu-id="d5399-102">How to: Create a Workflow</span></span>
<span data-ttu-id="d5399-103">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="d5399-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="d5399-104">在此部分步骤中通过创建工作流使用这两个内置的活动，如本主题<xref:System.Activities.Statements.Flowchart>活动和自定义活动与上一[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d5399-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="d5399-105">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="d5399-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="d5399-106">本节中只有一个主题是完成本教程所必需的；您应该选择感兴趣的样式并按照该步骤执行。</span><span class="sxs-lookup"><span data-stu-id="d5399-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="d5399-107">但是，您可以完成所有主题（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="d5399-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5399-108">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="d5399-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="d5399-109">若要完成本主题，必须先完成[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="d5399-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5399-110">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="d5399-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5399-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="d5399-111">In This Section</span></span>  
 [<span data-ttu-id="d5399-112">如何：创建顺序工作流</span><span class="sxs-lookup"><span data-stu-id="d5399-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="d5399-113">介绍如何使用 <xref:System.Activities.Statements.Sequence> 活动创建顺序工作流。</span><span class="sxs-lookup"><span data-stu-id="d5399-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="d5399-114">如何：创建流程图工作流</span><span class="sxs-lookup"><span data-stu-id="d5399-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="d5399-115">介绍如何使用 <xref:System.Activities.Statements.Flowchart> 活动创建流程图工作流。</span><span class="sxs-lookup"><span data-stu-id="d5399-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="d5399-116">如何：创建状态机工作流</span><span class="sxs-lookup"><span data-stu-id="d5399-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="d5399-117">介绍如何使用 <xref:System.Activities.Statements.StateMachine> 活动创建状态机工作流。</span><span class="sxs-lookup"><span data-stu-id="d5399-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5399-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5399-118">See Also</span></span>  
 [<span data-ttu-id="d5399-119">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="d5399-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
