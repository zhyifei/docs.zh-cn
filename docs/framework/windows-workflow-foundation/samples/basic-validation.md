---
title: "基本验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dd6f85dc7961a7c3fd51e67b9fd6e16de9faa41d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="basic-validation"></a><span data-ttu-id="681e3-102">基本验证</span><span class="sxs-lookup"><span data-stu-id="681e3-102">Basic Validation</span></span>
<span data-ttu-id="681e3-103">此示例包含 `CreateProduct` 活动，该活动验证它的 `Cost` 参数是否小于或等于它的 `Price` 参数。</span><span class="sxs-lookup"><span data-stu-id="681e3-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="681e3-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="681e3-104">Sample Details</span></span>  
 <span data-ttu-id="681e3-105">有两个使用验证的作者：活动作者（创建活动的验证逻辑）和工作流作者（对特定工作流调用验证服务）。</span><span class="sxs-lookup"><span data-stu-id="681e3-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="681e3-106">在此方案中，活动作者想要强制其活动的每个实例的成本都必须小于或等于价格。</span><span class="sxs-lookup"><span data-stu-id="681e3-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="681e3-107">活动作者（活动内部）必须：</span><span class="sxs-lookup"><span data-stu-id="681e3-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="681e3-108">创建一个约束 (`PriceGreaterThanCost`)。</span><span class="sxs-lookup"><span data-stu-id="681e3-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="681e3-109">这是存放全部验证逻辑的位置。</span><span class="sxs-lookup"><span data-stu-id="681e3-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="681e3-110">重写 `System.Activities.CodeActivity.OnGetConstraints()` 并将约束 (`PriceGreaterThanCost`) 添加到约束集 <xref:System.Collections.IList> 中。</span><span class="sxs-lookup"><span data-stu-id="681e3-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="681e3-111">工作流作者（主程序）必须：</span><span class="sxs-lookup"><span data-stu-id="681e3-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="681e3-112">使用要验证的活动实例来创建一个工作流 (`CreateProduct`)。</span><span class="sxs-lookup"><span data-stu-id="681e3-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="681e3-113">调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回<xref:System.Activities.Validation.ValidationResults> 的 <xref:System.Activities.Validation.ValidationError> 集合。</span><span class="sxs-lookup"><span data-stu-id="681e3-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="681e3-114">（可选）输出 <xref:System.Activities.Validation.ValidationError> 对象。</span><span class="sxs-lookup"><span data-stu-id="681e3-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="681e3-115">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="681e3-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="681e3-116">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 BasicValidation.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="681e3-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="681e3-117">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="681e3-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="681e3-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="681e3-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="681e3-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="681e3-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="681e3-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="681e3-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="681e3-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="681e3-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`