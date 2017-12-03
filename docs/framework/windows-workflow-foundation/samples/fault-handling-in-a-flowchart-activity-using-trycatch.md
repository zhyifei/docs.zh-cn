---
title: "使用 TryCatch 在 Flowchart 活动中进行错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d8bccc1b9505f685fd4e358216e76c22ec751e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="65152-102">使用 TryCatch 在 Flowchart 活动中进行错误处理</span><span class="sxs-lookup"><span data-stu-id="65152-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="65152-103">此示例演示如何在复杂控制流活动中使用 <xref:System.Activities.Statements.TryCatch> 活动。</span><span class="sxs-lookup"><span data-stu-id="65152-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>  
  
 <span data-ttu-id="65152-104">在此示例中，将促销代码和孩子数量作为变量传递到 <xref:System.Activities.Statements.Flowchart> 活动，该活动将根据与促销代码相对应的公式计算折扣。</span><span class="sxs-lookup"><span data-stu-id="65152-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="65152-105">此示例分为命令性代码版本和工作流设计器版本。 </span><span class="sxs-lookup"><span data-stu-id="65152-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>  
  
 <span data-ttu-id="65152-106">下表详细描述了 `CreateFlowchartWithFaults` 活动的变量。</span><span class="sxs-lookup"><span data-stu-id="65152-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>  
  
|<span data-ttu-id="65152-107">参数</span><span class="sxs-lookup"><span data-stu-id="65152-107">Parameters</span></span>|<span data-ttu-id="65152-108">描述</span><span class="sxs-lookup"><span data-stu-id="65152-108">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="65152-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="65152-109">promoCode</span></span>|<span data-ttu-id="65152-110">促销代码。</span><span class="sxs-lookup"><span data-stu-id="65152-110">The promotion code.</span></span> <span data-ttu-id="65152-111">类型：String</span><span class="sxs-lookup"><span data-stu-id="65152-111">Type: String</span></span><br /><br /> <span data-ttu-id="65152-112">可能的值，括号中带有说明：</span><span class="sxs-lookup"><span data-stu-id="65152-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="65152-113">-单 （单个）</span><span class="sxs-lookup"><span data-stu-id="65152-113">-   Single (Single)</span></span><br /><span data-ttu-id="65152-114">-MNK （已婚但没有孩子。）</span><span class="sxs-lookup"><span data-stu-id="65152-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="65152-115">-MWK （已婚并且有孩子）。</span><span class="sxs-lookup"><span data-stu-id="65152-115">-   MWK (Married with kids.)</span></span>|  
|<span data-ttu-id="65152-116">numKids</span><span class="sxs-lookup"><span data-stu-id="65152-116">numKids</span></span>|<span data-ttu-id="65152-117">孩子数量。</span><span class="sxs-lookup"><span data-stu-id="65152-117">The number of children.</span></span> <span data-ttu-id="65152-118">类型：int</span><span class="sxs-lookup"><span data-stu-id="65152-118">Type: int</span></span>|  
  
 <span data-ttu-id="65152-119">`CreateFlowchartWithFaults` 活动使用 <xref:System.Activities.Statements.FlowSwitch%601> 活动，后者根据 `promoCode` 参数进行切换并使用以下公式计算折扣。</span><span class="sxs-lookup"><span data-stu-id="65152-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>  
  
|<span data-ttu-id="65152-120">`promoCode` 的值</span><span class="sxs-lookup"><span data-stu-id="65152-120">Value of `promoCode`</span></span>|<span data-ttu-id="65152-121">折扣 (%)</span><span class="sxs-lookup"><span data-stu-id="65152-121">Discount (%)</span></span>|  
|--------------------------|--------------------|  
|<span data-ttu-id="65152-122">Single</span><span class="sxs-lookup"><span data-stu-id="65152-122">Single</span></span>|<span data-ttu-id="65152-123">10</span><span class="sxs-lookup"><span data-stu-id="65152-123">10</span></span>|  
|<span data-ttu-id="65152-124">MNK</span><span class="sxs-lookup"><span data-stu-id="65152-124">MNK</span></span>|<span data-ttu-id="65152-125">15</span><span class="sxs-lookup"><span data-stu-id="65152-125">15</span></span>|  
|<span data-ttu-id="65152-126">MWK</span><span class="sxs-lookup"><span data-stu-id="65152-126">MWK</span></span>|<span data-ttu-id="65152-127">15 + (1-1 /`numberOfKids`)\*10**注意：**可能，此计算可能会引发<xref:System.DivideByZeroException>。</span><span class="sxs-lookup"><span data-stu-id="65152-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="65152-128">因此，将折扣计算包装在 <xref:System.Activities.Statements.TryCatch> 活动中，该活动可捕获 <xref:System.DivideByZeroException> 异常并将折扣设置为零。</span><span class="sxs-lookup"><span data-stu-id="65152-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="65152-129">使用此示例</span><span class="sxs-lookup"><span data-stu-id="65152-129">To use this sample</span></span>  
  
1.  <span data-ttu-id="65152-130">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 FlowchartWithFaultHandling.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="65152-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the FlowchartWithFaultHandling.sln solution file.</span></span>  
  
2.  <span data-ttu-id="65152-131">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="65152-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="65152-132">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="65152-132">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65152-133">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="65152-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="65152-134">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="65152-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65152-135">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="65152-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65152-136">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="65152-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="65152-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65152-137">See Also</span></span>  
 [<span data-ttu-id="65152-138">流程图工作流</span><span class="sxs-lookup"><span data-stu-id="65152-138">Flowchart Workflows</span></span>](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [<span data-ttu-id="65152-139">异常</span><span class="sxs-lookup"><span data-stu-id="65152-139">Exceptions</span></span>](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
