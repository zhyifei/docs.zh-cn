---
title: 程序工作流
description: 在 Workflow Foundation 中，过程工作流使用类似于在过程语言中找到的流控制方法。
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 97664c1352928e7d05c2ed15fc118dd21474cfc3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421431"
---
# <a name="procedural-workflows"></a><span data-ttu-id="c3ac6-103">程序工作流</span><span class="sxs-lookup"><span data-stu-id="c3ac6-103">Procedural Workflows</span></span>
<span data-ttu-id="c3ac6-104">程序工作流使用的流控制方法与程序语言中使用的流控制方法类似。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-104">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="c3ac6-105">这些构造包括 `While` 和 `If`。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-105">These constructs include `While` and `If`.</span></span> <span data-ttu-id="c3ac6-106">使用 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Sequence> 等其他流控制活动，可以随意组合这些工作流。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-106">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="c3ac6-107">控制执行流</span><span class="sxs-lookup"><span data-stu-id="c3ac6-107">Controlling Execution Flow</span></span>  
 <span data-ttu-id="c3ac6-108">工作流活动库包含的活动可用于对程序语言中使用的大多数流控制方法进行建模，</span><span class="sxs-lookup"><span data-stu-id="c3ac6-108">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="c3ac6-109">其中包括：</span><span class="sxs-lookup"><span data-stu-id="c3ac6-109">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="c3ac6-110">若要使用流控制活动，请将**活动**工具箱中的这些活动拖放到设计器窗口内的复合活动。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-110">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3ac6-111">如果使用 Windows Server AppFabric 的承载功能在 Web 场上托管工作流，则 AppFabric 将在不同的 AppFabric 服务器之间移动实例。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-111">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="c3ac6-112">这就需要资源在所有节点之间可以共享。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-112">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="c3ac6-113">默认 NET 4 工作流活动不包含访问本地资源的任何操作。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-113">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="c3ac6-114">由于 AppFabric 没有提供将工作流标记为可移动的机制，所以开发人员不能在移动工作流时创建自定义活动。</span><span class="sxs-lookup"><span data-stu-id="c3ac6-114">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ac6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3ac6-115">See also</span></span>

- [<span data-ttu-id="c3ac6-116">流程图工作流</span><span class="sxs-lookup"><span data-stu-id="c3ac6-116">Flowchart Workflows</span></span>](flowchart-workflows.md)
