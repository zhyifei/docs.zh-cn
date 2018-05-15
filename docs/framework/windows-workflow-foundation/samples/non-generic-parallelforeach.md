---
title: 非泛型 ParallelForEach
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bb74af3763e21b0f3529319a1c0fdbd7145632e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="20c92-102">非泛型 ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="20c92-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="20c92-103"> 工具箱中附带的控制流活动，包括一组<xref:System.Activities.Statements.ParallelForEach%601>，这可用来循环访问<!--zz <xref:System.Collections.IEnumerable%601> -->`System.Collections.IEnumerable`集合。</span><span class="sxs-lookup"><span data-stu-id="20c92-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="20c92-104"><xref:System.Activities.Statements.ParallelForEach%601> 需要其<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>属性类型<!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="20c92-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="20c92-105">这将阻止从遍历数据结构实现用户<!--zz <xref:System.Collections.IEnumerable%601> -->`System.Collections.IEnumerable`接口 (例如， <xref:System.Collections.ArrayList>)。</span><span class="sxs-lookup"><span data-stu-id="20c92-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="20c92-106">非泛型版本的 <xref:System.Activities.Statements.ParallelForEach%601> 没有这一要求，不过与此对应的代价是，需要更复杂的运行时来确保集合中的值类型的兼容性。</span><span class="sxs-lookup"><span data-stu-id="20c92-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="20c92-107">此示例演示如何实现非泛型的 <xref:System.Activities.Statements.ParallelForEach%601> 活动及其设计器。</span><span class="sxs-lookup"><span data-stu-id="20c92-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="20c92-108">此活动可用于循环访问 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="20c92-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="20c92-109">ParallelForEach 活动</span><span class="sxs-lookup"><span data-stu-id="20c92-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="20c92-110">C#/VB `foreach` 语句枚举集合的元素，对集合中的每个元素执行嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="20c92-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="20c92-111">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 等效活动为 <xref:System.Activities.Statements.ForEach%601> 和 <xref:System.Activities.Statements.ParallelForEach%601>。</span><span class="sxs-lookup"><span data-stu-id="20c92-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="20c92-112"><xref:System.Activities.Statements.ForEach%601> 活动包含一个值列表和一个主体。</span><span class="sxs-lookup"><span data-stu-id="20c92-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="20c92-113">在运行时，将循环访问此列表，并对列表中的每个值执行主体。</span><span class="sxs-lookup"><span data-stu-id="20c92-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="20c92-114"><xref:System.Activities.Statements.ParallelForEach%601> 具有一个 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>，以便在 <xref:System.Activities.Statements.ParallelForEach%601> 的计算返回 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 的情况下，`true` 活动能够及早完成。</span><span class="sxs-lookup"><span data-stu-id="20c92-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="20c92-115">在每次迭代完成之后，将计算 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>。</span><span class="sxs-lookup"><span data-stu-id="20c92-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="20c92-116">对于大多数情况，此活动的泛型版本应为首选解决方案，因为它涵盖了应使用此活动的大多数方案，并且提供编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="20c92-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="20c92-117">非泛型版本可用于循环访问实现非泛型 <xref:System.Collections.IEnumerable> 接口的类型。</span><span class="sxs-lookup"><span data-stu-id="20c92-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="20c92-118">类定义</span><span class="sxs-lookup"><span data-stu-id="20c92-118">Class Definition</span></span>  
 <span data-ttu-id="20c92-119">下面的代码示例显示非泛型 `ParallelForEach` 活动的定义。</span><span class="sxs-lookup"><span data-stu-id="20c92-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ParallelForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    public Activity<bool> CompletionCondition  
    [DefaultValue(null)]  
    [DependsOn("CompletionCondition")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="20c92-120">Body（可选）</span><span class="sxs-lookup"><span data-stu-id="20c92-120">Body (optional)</span></span>  
 <span data-ttu-id="20c92-121"><xref:System.Activities.ActivityAction> 类型的 <xref:System.Object>，将对集合中的每个元素执行它。</span><span class="sxs-lookup"><span data-stu-id="20c92-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="20c92-122">通过单个元素的 Argument 属性将其传递到 Body。</span><span class="sxs-lookup"><span data-stu-id="20c92-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="20c92-123">Values（可选）</span><span class="sxs-lookup"><span data-stu-id="20c92-123">Values (optional)</span></span>  
 <span data-ttu-id="20c92-124">循环访问的元素集合。</span><span class="sxs-lookup"><span data-stu-id="20c92-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="20c92-125">在运行时确保所有集合元素为兼容类型。</span><span class="sxs-lookup"><span data-stu-id="20c92-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="20c92-126">CompletionCondition（可选）</span><span class="sxs-lookup"><span data-stu-id="20c92-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="20c92-127">在任何迭代完成之后，将计算 <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="20c92-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="20c92-128">如果其计算结果为 `true`，则取消已安排的挂起的迭代。</span><span class="sxs-lookup"><span data-stu-id="20c92-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="20c92-129">如果未设置此属性，则 Branches 集合中的所有活动都将执行，直至完成为止。</span><span class="sxs-lookup"><span data-stu-id="20c92-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="20c92-130">使用 ParallelForEach 的示例</span><span class="sxs-lookup"><span data-stu-id="20c92-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="20c92-131">下面的代码演示如何在应用程序中使用 ParallelForEach 活动。</span><span class="sxs-lookup"><span data-stu-id="20c92-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ParallelForEach  
    {  
       Values = new InArgument<IEnumerable>(c=> names),  
       Body = new ActivityAction<object>   
       {                          
           Argument = iterationVariable,  
           Handler = new WriteLine  
           {  
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))  
           }  
       }  
   };  
```  
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="20c92-132">ParallelForEach 设计器</span><span class="sxs-lookup"><span data-stu-id="20c92-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="20c92-133">此示例的活动设计器的外观与为内置 <xref:System.Activities.Statements.ParallelForEach%601> 活动提供的设计器的外观相似。</span><span class="sxs-lookup"><span data-stu-id="20c92-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="20c92-134">此设计器显示在工具箱**示例**，**非泛型活动**类别。</span><span class="sxs-lookup"><span data-stu-id="20c92-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="20c92-135">名为设计器**ParallelForEachWithBodyFactory**在工具箱中，因为活动会公开<xref:System.Activities.Presentation.IActivityTemplateFactory>创建使用正确配置活动工具箱中<xref:System.Activities.ActivityAction>。</span><span class="sxs-lookup"><span data-stu-id="20c92-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()  
        {  
            Body = new ActivityAction<object>()  
            {  
                Argument = new DelegateInArgument<object>()  
                {  
                    Name = "item"  
                }  
            }  
        };  
    }  
}  
```  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="20c92-136">运行示例</span><span class="sxs-lookup"><span data-stu-id="20c92-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="20c92-137">将您选择的项目设置为解决方案的启动项目。</span><span class="sxs-lookup"><span data-stu-id="20c92-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="20c92-138">**Codetestclient**演示如何使用活动使用代码。</span><span class="sxs-lookup"><span data-stu-id="20c92-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="20c92-139">**Designertestclient**演示如何使用设计器中的活动。</span><span class="sxs-lookup"><span data-stu-id="20c92-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="20c92-140">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="20c92-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20c92-141">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="20c92-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="20c92-142">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="20c92-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20c92-143">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="20c92-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20c92-144">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="20c92-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
