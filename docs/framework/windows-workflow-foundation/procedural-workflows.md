---
title: "程序工作流"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10cf83264fbdc2ed3dc088c11865c630c0b8f4f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="38f22-102">程序工作流</span><span class="sxs-lookup"><span data-stu-id="38f22-102">Procedural Workflows</span></span>
<span data-ttu-id="38f22-103">程序工作流使用的流控制方法与程序语言中使用的流控制方法类似。</span><span class="sxs-lookup"><span data-stu-id="38f22-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="38f22-104">这些构造包括 `While` 和 `If`。</span><span class="sxs-lookup"><span data-stu-id="38f22-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="38f22-105">使用 <xref:System.Activities.Statements.Flowchart> 和 <xref:System.Activities.Statements.Sequence> 等其他流控制活动，可以随意组合这些工作流。</span><span class="sxs-lookup"><span data-stu-id="38f22-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="38f22-106">控制执行流</span><span class="sxs-lookup"><span data-stu-id="38f22-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="38f22-107">工作流活动库包含的活动可用于对程序语言中使用的大多数流控制方法进行建模，</span><span class="sxs-lookup"><span data-stu-id="38f22-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="38f22-108">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="38f22-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="38f22-109">若要使用流控制活动，拖放从**活动**到设计器窗口内的复合活动的工具箱。</span><span class="sxs-lookup"><span data-stu-id="38f22-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38f22-110">如果使用 [!INCLUDE[dublin](../../../includes/dublin-md.md)] 在网络场上承载工作流，则 AppFabric 将在不同 AppFabric 服务器之间移动实例。</span><span class="sxs-lookup"><span data-stu-id="38f22-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="38f22-111">这就需要资源在所有节点之间可以共享。</span><span class="sxs-lookup"><span data-stu-id="38f22-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="38f22-112">默认 NET 4 工作流活动不包含访问本地资源的任何操作。</span><span class="sxs-lookup"><span data-stu-id="38f22-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="38f22-113">由于 AppFabric 没有提供将工作流标记为可移动的机制，所以开发人员不能在移动工作流时创建自定义活动。</span><span class="sxs-lookup"><span data-stu-id="38f22-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f22-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="38f22-114">See Also</span></span>  
 [<span data-ttu-id="38f22-115">流程图工作流</span><span class="sxs-lookup"><span data-stu-id="38f22-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
