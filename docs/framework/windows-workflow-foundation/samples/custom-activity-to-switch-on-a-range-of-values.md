---
title: "要基于一系列值进行切换的自定义活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4dcaf023960aab1989493475fe4e5306623adf8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="c704c-102">要基于一系列值进行切换的自定义活动</span><span class="sxs-lookup"><span data-stu-id="c704c-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="c704c-103">此示例演示如何创建扩展对 <xref:System.Activities.Statements.Switch%601> 的使用的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="c704c-104">常规的 <xref:System.Activities.Statements.Switch%601> 语句允许基于单个值进行切换。</span><span class="sxs-lookup"><span data-stu-id="c704c-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="c704c-105">但在一些业务方案中，活动必须基于一系列值进行切换。</span><span class="sxs-lookup"><span data-stu-id="c704c-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="c704c-106">例如，活动可能在基于 1 和 5 之间切换值时执行一个操作，在基于 6 和 10 之间切换值时执行另一个操作，并为所有其他值执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="c704c-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="c704c-107">此自定义活动完全支持上述方案。</span><span class="sxs-lookup"><span data-stu-id="c704c-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="c704c-108">SwitchRange 活动</span><span class="sxs-lookup"><span data-stu-id="c704c-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="c704c-109">`SwitchRange` 活动将在其表达式的结果值包含在其某个 `Cases` 的范围内时计划一个子活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="c704c-110">下面的代码示例是一个基于一系列值进行切换的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="c704c-111">属性</span><span class="sxs-lookup"><span data-stu-id="c704c-111">Property</span></span>|<span data-ttu-id="c704c-112">描述</span><span class="sxs-lookup"><span data-stu-id="c704c-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="c704c-113">Expression</span><span class="sxs-lookup"><span data-stu-id="c704c-113">Expression</span></span>|<span data-ttu-id="c704c-114">这是要计算并与 Cases 列表中的范围进行比较的表达式。</span><span class="sxs-lookup"><span data-stu-id="c704c-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="c704c-115">该表达式的结果的类型为 T。</span><span class="sxs-lookup"><span data-stu-id="c704c-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="c704c-116">Cases</span><span class="sxs-lookup"><span data-stu-id="c704c-116">Cases</span></span>|<span data-ttu-id="c704c-117">每个示例包含一个范围（From 和 To）和一个活动 (Body)。</span><span class="sxs-lookup"><span data-stu-id="c704c-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="c704c-118">计算表达式并将其与范围进行比较。</span><span class="sxs-lookup"><span data-stu-id="c704c-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="c704c-119">如果表达式的结果位于某个示例的范围内，则执行对应的活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="c704c-120">默认</span><span class="sxs-lookup"><span data-stu-id="c704c-120">Default</span></span>|<span data-ttu-id="c704c-121">没有匹配的示例时所执行的活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="c704c-122">在设置为 `null` 时，不采用任何操作。</span><span class="sxs-lookup"><span data-stu-id="c704c-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="c704c-123">CaseRange 类</span><span class="sxs-lookup"><span data-stu-id="c704c-123">CaseRange Class</span></span>  
 <span data-ttu-id="c704c-124">`CaseRange` 类表示 `SwitchRange` 活动中的范围。</span><span class="sxs-lookup"><span data-stu-id="c704c-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="c704c-125">`CaseRange` 的每个实例均包含一个范围（由 `From` 和 `To` 构成）和一个 `Body` 活动，如果在范围内计算 `SwitchRange` 中的表达式，则将计划该活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="c704c-126">下面的代码示例是 `CaseRange` 类的定义。</span><span class="sxs-lookup"><span data-stu-id="c704c-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="c704c-127">示例中定义的 `SwitchRange` 和 `CaseRange` 类都是可使用实现 `IComparable` 的任何类型的泛型类（如 <xref:System.Activities.Statements.Switch%601> 类）。</span><span class="sxs-lookup"><span data-stu-id="c704c-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="c704c-128">示例用法</span><span class="sxs-lookup"><span data-stu-id="c704c-128">Sample Usage</span></span>  
 <span data-ttu-id="c704c-129">下面的代码示例演示如何使用 `SwitchRange` 活动。</span><span class="sxs-lookup"><span data-stu-id="c704c-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c704c-130">使用此示例</span><span class="sxs-lookup"><span data-stu-id="c704c-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="c704c-131">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 SwitchRange.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="c704c-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c704c-132">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="c704c-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c704c-133">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="c704c-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c704c-134">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c704c-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c704c-135">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c704c-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c704c-136">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="c704c-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c704c-137">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c704c-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`