---
title: 高级策略
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: becdc28affd877239474d6f0f007a480297bccb8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672835"
---
# <a name="advanced-policy"></a><span data-ttu-id="6d306-102">高级策略</span><span class="sxs-lookup"><span data-stu-id="6d306-102">Advanced Policy</span></span>
<span data-ttu-id="6d306-103">此示例扩展了简单策略示例。</span><span class="sxs-lookup"><span data-stu-id="6d306-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="6d306-104">除了简单策略示例中的住户折扣和企业折扣规则外，还添加了若干新规则。</span><span class="sxs-lookup"><span data-stu-id="6d306-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="6d306-105">添加了一条高价值规则，可为高价值订单提供更大的折扣。</span><span class="sxs-lookup"><span data-stu-id="6d306-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="6d306-106">该规则被赋予了比前两条规则更小的优先级值，因此它将覆盖折扣字段，并优先于住户折扣和企业折扣规则。</span><span class="sxs-lookup"><span data-stu-id="6d306-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="6d306-107">另外还添加了一条计算总计规则，可基于折扣级别计算出总计。</span><span class="sxs-lookup"><span data-stu-id="6d306-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="6d306-108">它显示了如何引用工作流活动上定义的方法，以及如何使用其他操作。</span><span class="sxs-lookup"><span data-stu-id="6d306-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="6d306-109">此规则还演示了链接行为，因为任何时候当折扣字段发生更改时都会计算该规则。</span><span class="sxs-lookup"><span data-stu-id="6d306-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="6d306-110">而且，还通过 CalculateTotal 方法上的 RuleWriteAttribute 显示了方法属性设置。</span><span class="sxs-lookup"><span data-stu-id="6d306-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="6d306-111">这样，无论何时在执行方法时，都会重新计算受影响的规则 (ErrorTotalRule)。</span><span class="sxs-lookup"><span data-stu-id="6d306-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="6d306-112">添加的最后一条规则是用于检测错误（本例中为总计小于 0）的规则。</span><span class="sxs-lookup"><span data-stu-id="6d306-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="6d306-113">如果出现这种错误，策略执行将停止。</span><span class="sxs-lookup"><span data-stu-id="6d306-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="6d306-114">最后，还以操作的形式向每条规则中添加了 `Console.Writeline` 调用，以使规则执行的可见性更高，同时还显示它可能访问所引用类型上的静态方法。</span><span class="sxs-lookup"><span data-stu-id="6d306-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="6d306-115">您还可以使用跟踪来查看所执行的规则。</span><span class="sxs-lookup"><span data-stu-id="6d306-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="6d306-116">此示例中使用的规则包括：</span><span class="sxs-lookup"><span data-stu-id="6d306-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="6d306-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="6d306-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="6d306-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="6d306-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="6d306-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="6d306-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="6d306-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="6d306-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="6d306-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="6d306-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="6d306-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="6d306-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="6d306-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="6d306-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="6d306-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="6d306-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="6d306-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="6d306-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="6d306-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="6d306-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="6d306-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="6d306-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="6d306-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="6d306-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="6d306-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="6d306-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="6d306-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="6d306-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="6d306-131">如果总\<0</span><span class="sxs-lookup"><span data-stu-id="6d306-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="6d306-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="6d306-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="6d306-133">也可以通过追踪和跟踪看到规则的计算和执行过程。</span><span class="sxs-lookup"><span data-stu-id="6d306-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="6d306-134">生成示例</span><span class="sxs-lookup"><span data-stu-id="6d306-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="6d306-135">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d306-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6d306-136">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d306-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6d306-137">按 Ctrl+F5 运行解决方案而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="6d306-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="6d306-138">运行示例</span><span class="sxs-lookup"><span data-stu-id="6d306-138">To run the sample</span></span>  
  
-   <span data-ttu-id="6d306-139">在 SDK 命令提示窗口中，运行 AdvancedPolicy\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 AdvancedPolicy \bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。</span><span class="sxs-lookup"><span data-stu-id="6d306-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d306-140">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6d306-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6d306-141">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6d306-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6d306-142">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="6d306-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6d306-143">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6d306-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="6d306-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d306-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="6d306-145">简单策略</span><span class="sxs-lookup"><span data-stu-id="6d306-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
