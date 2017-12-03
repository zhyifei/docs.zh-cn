---
title: "高级策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9752b5779f4fbb525488e88f2f11c98de7b4ba8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="advanced-policy"></a><span data-ttu-id="726d3-102">高级策略</span><span class="sxs-lookup"><span data-stu-id="726d3-102">Advanced Policy</span></span>
<span data-ttu-id="726d3-103">此示例扩展了简单策略示例。</span><span class="sxs-lookup"><span data-stu-id="726d3-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="726d3-104">除了简单策略示例中的住户折扣和企业折扣规则外，还添加了若干新规则。</span><span class="sxs-lookup"><span data-stu-id="726d3-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="726d3-105">添加了一条高价值规则，可为高价值订单提供更大的折扣。</span><span class="sxs-lookup"><span data-stu-id="726d3-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="726d3-106">该规则被赋予了比前两条规则更小的优先级值，因此它将覆盖折扣字段，并优先于住户折扣和企业折扣规则。</span><span class="sxs-lookup"><span data-stu-id="726d3-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="726d3-107">另外还添加了一条计算总计规则，可基于折扣级别计算出总计。</span><span class="sxs-lookup"><span data-stu-id="726d3-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="726d3-108">它显示了如何引用工作流活动上定义的方法，以及如何使用其他操作。</span><span class="sxs-lookup"><span data-stu-id="726d3-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="726d3-109">此规则还演示了链接行为，因为任何时候当折扣字段发生更改时都会计算该规则。</span><span class="sxs-lookup"><span data-stu-id="726d3-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="726d3-110">而且，还通过 CalculateTotal 方法上的 RuleWriteAttribute 显示了方法属性设置。</span><span class="sxs-lookup"><span data-stu-id="726d3-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="726d3-111">这样，无论何时在执行方法时，都会重新计算受影响的规则 (ErrorTotalRule)。</span><span class="sxs-lookup"><span data-stu-id="726d3-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="726d3-112">添加的最后一条规则是用于检测错误（本例中为总计小于 0）的规则。</span><span class="sxs-lookup"><span data-stu-id="726d3-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="726d3-113">如果出现这种错误，策略执行将停止。</span><span class="sxs-lookup"><span data-stu-id="726d3-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="726d3-114">最后，还以操作的形式向每条规则中添加了 `Console.Writeline` 调用，以使规则执行的可见性更高，同时还显示它可能访问所引用类型上的静态方法。</span><span class="sxs-lookup"><span data-stu-id="726d3-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="726d3-115">您还可以使用跟踪来查看所执行的规则。</span><span class="sxs-lookup"><span data-stu-id="726d3-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="726d3-116">此示例中使用的规则包括：</span><span class="sxs-lookup"><span data-stu-id="726d3-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="726d3-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="726d3-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="726d3-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="726d3-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="726d3-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="726d3-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="726d3-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="726d3-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="726d3-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="726d3-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="726d3-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="726d3-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="726d3-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="726d3-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="726d3-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="726d3-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="726d3-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="726d3-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="726d3-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="726d3-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="726d3-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="726d3-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="726d3-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="726d3-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="726d3-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="726d3-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="726d3-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="726d3-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="726d3-131">如果总\<0</span><span class="sxs-lookup"><span data-stu-id="726d3-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="726d3-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="726d3-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="726d3-133">也可以通过追踪和跟踪看到规则的计算和执行过程。</span><span class="sxs-lookup"><span data-stu-id="726d3-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="726d3-134">生成示例</span><span class="sxs-lookup"><span data-stu-id="726d3-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="726d3-135">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="726d3-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="726d3-136">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="726d3-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="726d3-137">按 Ctrl+F5 运行解决方案而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="726d3-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="726d3-138">运行示例</span><span class="sxs-lookup"><span data-stu-id="726d3-138">To run the sample</span></span>  
  
-   <span data-ttu-id="726d3-139">在 SDK 命令提示窗口中，运行 AdvancedPolicy\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 AdvancedPolicy \bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。</span><span class="sxs-lookup"><span data-stu-id="726d3-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="726d3-140">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="726d3-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="726d3-141">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="726d3-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="726d3-142">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="726d3-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="726d3-143">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="726d3-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="726d3-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="726d3-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="726d3-145">简单策略</span><span class="sxs-lookup"><span data-stu-id="726d3-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
