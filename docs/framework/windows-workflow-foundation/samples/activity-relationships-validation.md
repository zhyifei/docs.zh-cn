---
title: 活动关系验证
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: 50f08118fb5ad4d9b8fe809e7ab3cc5d57f28149
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784807"
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="10b67-102">活动关系验证</span><span class="sxs-lookup"><span data-stu-id="10b67-102">Activity Relationships Validation</span></span>
<span data-ttu-id="10b67-103">此示例由以下三个活动组成：`CreateCity`、`CreateState` 和 `CreateCountry`。</span><span class="sxs-lookup"><span data-stu-id="10b67-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="10b67-104">`CreateCity` 必须在 `CreateState` 活动内，并且`CreateState` 必须在 `CreateCountry` 活动内。 </span><span class="sxs-lookup"><span data-stu-id="10b67-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="10b67-105">此示例出于演示的需要，对 `CreateState` 活动使用代码形式的验证逻辑，而对 `CreateCity` 活动使用 XAML 形式的验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="10b67-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="10b67-106">这两个约束具有相同的行为。</span><span class="sxs-lookup"><span data-stu-id="10b67-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="10b67-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 提供了以下三个帮助器活动，开发人员可使用它们验证各活动之间的关系：</span><span class="sxs-lookup"><span data-stu-id="10b67-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="10b67-108">提供属于当前节点的父级的所有活动的集合</span><span class="sxs-lookup"><span data-stu-id="10b67-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="10b67-109">提供属于当前节点的子树（不包括当前节点）的所有活动的集合</span><span class="sxs-lookup"><span data-stu-id="10b67-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="10b67-110">提供当前节点所在的同一树中的所有活动的集合</span><span class="sxs-lookup"><span data-stu-id="10b67-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="10b67-111">在此示例中，<xref:System.Activities.Statements.ForEach%601> 活动用于遍历 <xref:System.Activities.Validation.GetParentChain> 返回的集合。</span><span class="sxs-lookup"><span data-stu-id="10b67-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="10b67-112">对于集合中的每个元素，都会将其类型与 `CreateCountry` 进行比较（如果验证的是 `CreateState`，则与 `CreateCity` 进行比较），并且在发现匹配项时，会将结果标志设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="10b67-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="10b67-113">最后，<xref:System.Activities.Validation.AssertValidation> 用于在结果标志设置为 `false` 时生成验证错误。</span><span class="sxs-lookup"><span data-stu-id="10b67-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="10b67-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="10b67-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="10b67-115">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ContainmentValidation.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="10b67-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="10b67-116">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="10b67-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="10b67-117">按 CTRL + F5 启动程序。</span><span class="sxs-lookup"><span data-stu-id="10b67-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10b67-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="10b67-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="10b67-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="10b67-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="10b67-120">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="10b67-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10b67-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="10b67-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
