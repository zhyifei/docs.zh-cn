---
title: "约束类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f78337ebc643b584b89f26ca39e400fb8e6e9c26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="constraint-types"></a><span data-ttu-id="fe9da-102">约束类型</span><span class="sxs-lookup"><span data-stu-id="fe9da-102">Constraint Types</span></span>
<span data-ttu-id="fe9da-103">本实例演示将约束应用于工作流的两种不同方法：一种方法是从活动内部应用（生成），另一种方法是从活动外部应用（策略）。</span><span class="sxs-lookup"><span data-stu-id="fe9da-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="fe9da-104">在此方案中，某个活动作者（来自于第三方软件公司）想要验证两个参数之间的关系。</span><span class="sxs-lookup"><span data-stu-id="fe9da-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="fe9da-105">在此例中，成本应小于或等于价格。</span><span class="sxs-lookup"><span data-stu-id="fe9da-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="fe9da-106">这是一个常规的验证生成约束。</span><span class="sxs-lookup"><span data-stu-id="fe9da-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="fe9da-107">然后，一个店主想要为此常规活动中添加一些验证。</span><span class="sxs-lookup"><span data-stu-id="fe9da-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="fe9da-108">对于他而言，他想要让大多数产品的价格为 9.99 美元或者更少。</span><span class="sxs-lookup"><span data-stu-id="fe9da-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="fe9da-109">因此，他在 `CreateProduct` 活动之上使用一个策略约束。</span><span class="sxs-lookup"><span data-stu-id="fe9da-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="fe9da-110">在此示例中：</span><span class="sxs-lookup"><span data-stu-id="fe9da-110">In the sample:</span></span>  
  
 <span data-ttu-id="fe9da-111">活动作者（生成）必须：</span><span class="sxs-lookup"><span data-stu-id="fe9da-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="fe9da-112">创建一个约束 (`PriceGreaterThanCost`)。</span><span class="sxs-lookup"><span data-stu-id="fe9da-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="fe9da-113">这是存放全部验证逻辑的位置。</span><span class="sxs-lookup"><span data-stu-id="fe9da-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="fe9da-114">重写 `System.Activities.CodeActivity.OnGetConstraints()` 并将约束 (`PriceGreaterThanCost`) 添加到约束集 <xref:System.Collections.IList> 中。</span><span class="sxs-lookup"><span data-stu-id="fe9da-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="fe9da-115">工作流作者（策略）必须：</span><span class="sxs-lookup"><span data-stu-id="fe9da-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="fe9da-116">使用要验证的活动实例来创建一个工作流 (`CreateProduct`)。</span><span class="sxs-lookup"><span data-stu-id="fe9da-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="fe9da-117">创建一个约束 (`MaxPrice`)。</span><span class="sxs-lookup"><span data-stu-id="fe9da-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="fe9da-118">创建一个 <xref:System.Activities.Validation.ValidationSettings> 实例 (`validationSettings`)，并将约束 (`MaxPrice`) 添加到集合 `AdditionalConstraints` 中。</span><span class="sxs-lookup"><span data-stu-id="fe9da-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="fe9da-119">在此处，工作流作者可以将策略约束添加到任何活动，例如一个序列或并行活动。</span><span class="sxs-lookup"><span data-stu-id="fe9da-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="fe9da-120">调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回 <xref:System.Activities.Validation.ValidationResults> 对象的 <xref:System.Activities.Validation.ValidationError> 的集合。</span><span class="sxs-lookup"><span data-stu-id="fe9da-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="fe9da-121">（可选）输出 <xref:System.Activities.Validation.ValidationError> 对象。</span><span class="sxs-lookup"><span data-stu-id="fe9da-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fe9da-122">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="fe9da-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fe9da-123">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ConstraintTypes.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="fe9da-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe9da-124">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="fe9da-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe9da-125">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="fe9da-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe9da-126">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="fe9da-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe9da-127">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="fe9da-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe9da-128">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="fe9da-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`  
  
## <a name="see-also"></a><span data-ttu-id="fe9da-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe9da-129">See Also</span></span>
