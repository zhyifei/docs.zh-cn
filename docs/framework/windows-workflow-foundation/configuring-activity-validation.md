---
title: "配置活动验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 440f3ee85fe24707c6bb433736bf6104d9e0dfc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="3e543-102">配置活动验证</span><span class="sxs-lookup"><span data-stu-id="3e543-102">Configuring Activity Validation</span></span>
<span data-ttu-id="3e543-103">通过活动验证，活动作者和用户可以在执行活动配置之前标识和报告此配置中的错误。</span><span class="sxs-lookup"><span data-stu-id="3e543-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="3e543-104"> 提供以下三种类型的活动验证：</span><span class="sxs-lookup"><span data-stu-id="3e543-104"> provides the following three types of activity validation:</span></span>  
  
-   <span data-ttu-id="3e543-105">`RequiredArgument` 和 `OverloadGroup` 特性。</span><span class="sxs-lookup"><span data-stu-id="3e543-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
-   <span data-ttu-id="3e543-106">基于命令性代码的验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-106">Imperative code-based validation.</span></span>  
  
-   <span data-ttu-id="3e543-107">声明性约束。</span><span class="sxs-lookup"><span data-stu-id="3e543-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="3e543-108">`RequiredArgument` 和 `OverloadGroup` 特性指示活动中的特定参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3e543-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="3e543-109">基于命令性代码的验证为活动提供围绕其自身进行验证的简单方法，声明性约束支持围绕活动及其与包含工作流之间的关系进行验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="3e543-110">如果未根据验证要求正确配置活动，将返回验证错误和警告。</span><span class="sxs-lookup"><span data-stu-id="3e543-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="3e543-111">如果包含工作流是使用工作流设计器创建的，则会在设计器中显示所有验证错误和警告。</span><span class="sxs-lookup"><span data-stu-id="3e543-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="3e543-112">如果工作流不是使用工作流设计器创建的，则会在调用工作流时返回任何验证错误。</span><span class="sxs-lookup"><span data-stu-id="3e543-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="3e543-113">不管工作流的创建方式如何，绝不允许执行带有验证错误的工作流。</span><span class="sxs-lookup"><span data-stu-id="3e543-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="3e543-114">本节概述了这些活动验证类型及其调用方法。</span><span class="sxs-lookup"><span data-stu-id="3e543-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e543-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="3e543-115">In This Section</span></span>  
 [<span data-ttu-id="3e543-116">必需自变量和重载组</span><span class="sxs-lookup"><span data-stu-id="3e543-116">Required Arguments and Overload Groups</span></span>](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 <span data-ttu-id="3e543-117">介绍如何使用 `RequiredArgument` 和 `OverloadGroup` 特性提供验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="3e543-118">基于强制性代码的验证</span><span class="sxs-lookup"><span data-stu-id="3e543-118">Imperative Code-Based Validation</span></span>](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 <span data-ttu-id="3e543-119">介绍如何对基于 <xref:System.Activities.CodeActivity> 和 <xref:System.Activities.NativeActivity> 的活动使用基于代码的验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="3e543-120">声明性约束</span><span class="sxs-lookup"><span data-stu-id="3e543-120">Declarative Constraints</span></span>](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 <span data-ttu-id="3e543-121">介绍如何使用声明性约束提供复杂活动验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="3e543-122">调用活动验证</span><span class="sxs-lookup"><span data-stu-id="3e543-122">Invoking Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 <span data-ttu-id="3e543-123">讨论何时自动调用活动验证以及如何显式调用验证。</span><span class="sxs-lookup"><span data-stu-id="3e543-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3e543-124">参考</span><span class="sxs-lookup"><span data-stu-id="3e543-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3e543-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="3e543-125">Related Sections</span></span>
