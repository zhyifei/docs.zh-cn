---
title: 如何：创建工作流
description: 完成此部分中三个选项中的一个，以在此 Workflow Foundation 教程中创建工作流。
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 7e4575436405e74b7575e55bea37a1a99d879a3e
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419559"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="e5d73-103">如何：创建工作流</span><span class="sxs-lookup"><span data-stu-id="e5d73-103">How to: Create a Workflow</span></span>
<span data-ttu-id="e5d73-104">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="e5d73-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="e5d73-105">本节中的主题介绍如何创建一个工作流，该工作流使用内置活动（如 <xref:System.Activities.Statements.Flowchart> 活动）和前面的[如何：创建活动](how-to-create-an-activity.md)主题中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="e5d73-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="e5d73-106">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="e5d73-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="e5d73-107">本节中只有一个主题是完成本教程所必需的；您应该选择感兴趣的样式并按照该步骤执行。</span><span class="sxs-lookup"><span data-stu-id="e5d73-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="e5d73-108">但是，您可以完成所有主题（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="e5d73-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5d73-109">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="e5d73-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="e5d73-110">若要完成本主题，必须先完成[操作方法：创建活动](how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d73-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5d73-111">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="e5d73-111">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5d73-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="e5d73-112">In This Section</span></span>  
 [<span data-ttu-id="e5d73-113">如何：创建顺序工作流</span><span class="sxs-lookup"><span data-stu-id="e5d73-113">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="e5d73-114">介绍如何使用 <xref:System.Activities.Statements.Sequence> 活动创建顺序工作流。</span><span class="sxs-lookup"><span data-stu-id="e5d73-114">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="e5d73-115">如何：创建 Flowchart 工作流</span><span class="sxs-lookup"><span data-stu-id="e5d73-115">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="e5d73-116">介绍如何使用 <xref:System.Activities.Statements.Flowchart> 活动创建流程图工作流。</span><span class="sxs-lookup"><span data-stu-id="e5d73-116">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="e5d73-117">如何：创建状态机工作流</span><span class="sxs-lookup"><span data-stu-id="e5d73-117">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="e5d73-118">介绍如何使用 <xref:System.Activities.Statements.StateMachine> 活动创建状态机工作流。</span><span class="sxs-lookup"><span data-stu-id="e5d73-118">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d73-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d73-119">See also</span></span>

- [<span data-ttu-id="e5d73-120">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="e5d73-120">Windows Workflow Foundation Programming</span></span>](programming.md)
