---
title: 非泛型 ForEach
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: c67f6e3c3afb893f7bb5713d64ce2f119eebc157
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519475"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="5db3f-102">非泛型 ForEach</span><span class="sxs-lookup"><span data-stu-id="5db3f-102">Non-Generic ForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="5db3f-103"> 工具箱中附带的控制流活动，包括一组<xref:System.Activities.Statements.ForEach%601>，这可用来循环访问<!--zz <xref:System.Collections.IEnumerable%601> -->`System.Collections.IEnumerable`集合。</span><span class="sxs-lookup"><span data-stu-id="5db3f-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="5db3f-104"><xref:System.Activities.Statements.ForEach%601> 需要其<xref:System.Activities.Statements.ForEach%601.Values%2A>属性类型<!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="5db3f-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="5db3f-105">这将阻止从遍历数据结构实现用户<!--zz <xref:System.Collections.IEnumerable%601> -->`System.Collections.IEnumerable`接口 (例如， <xref:System.Collections.ArrayList>)。</span><span class="sxs-lookup"><span data-stu-id="5db3f-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="5db3f-106">非泛型版本的 <xref:System.Activities.Statements.ForEach%601> 没有这一要求，不过与此对应的代价是，需要更复杂的运行时来确保集合中的值类型的兼容性。</span><span class="sxs-lookup"><span data-stu-id="5db3f-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="5db3f-107">此示例演示如何实现非泛型的 <xref:System.Activities.Statements.ForEach%601> 活动及其设计器。</span><span class="sxs-lookup"><span data-stu-id="5db3f-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="5db3f-108">此活动可用于循环访问 <xref:System.Collections.ArrayList>。</span><span class="sxs-lookup"><span data-stu-id="5db3f-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="5db3f-109">ForEach 活动</span><span class="sxs-lookup"><span data-stu-id="5db3f-109">ForEach Activity</span></span>  
 <span data-ttu-id="5db3f-110">C#/VB `foreach` 语句枚举集合的元素，对集合中的每个元素执行嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="5db3f-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="5db3f-111">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 的 `foreach` 等效活动为 <xref:System.Activities.Statements.ForEach%601> 和 <xref:System.Activities.Statements.ParallelForEach%601>。</span><span class="sxs-lookup"><span data-stu-id="5db3f-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="5db3f-112"><xref:System.Activities.Statements.ForEach%601> 活动包含一个值列表和一个主体。</span><span class="sxs-lookup"><span data-stu-id="5db3f-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="5db3f-113">在运行时，将循环访问此列表，并对列表中的每个值执行主体。</span><span class="sxs-lookup"><span data-stu-id="5db3f-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="5db3f-114">对于大多数情况，此活动的泛型版本应为首选解决方案，因为它涵盖了应使用此活动的大多数方案，并且提供编译时类型检查。</span><span class="sxs-lookup"><span data-stu-id="5db3f-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="5db3f-115">非泛型版本可用于循环访问实现非泛型 <xref:System.Collections.IEnumerable> 接口的类型。</span><span class="sxs-lookup"><span data-stu-id="5db3f-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="5db3f-116">类定义</span><span class="sxs-lookup"><span data-stu-id="5db3f-116">Class Definition</span></span>  
 <span data-ttu-id="5db3f-117">下面的代码示例显示非泛型 `ForEach` 活动的定义。</span><span class="sxs-lookup"><span data-stu-id="5db3f-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="5db3f-118">Body（可选）</span><span class="sxs-lookup"><span data-stu-id="5db3f-118">Body (optional)</span></span>  
 <span data-ttu-id="5db3f-119"><xref:System.Activities.ActivityAction> 类型的 <xref:System.Object>，将对集合中的每个元素执行它。</span><span class="sxs-lookup"><span data-stu-id="5db3f-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="5db3f-120">每个个体元素都通过其 `Argument` 属性传递到 Body。</span><span class="sxs-lookup"><span data-stu-id="5db3f-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="5db3f-121">Values（可选）</span><span class="sxs-lookup"><span data-stu-id="5db3f-121">Values (optional)</span></span>  
 <span data-ttu-id="5db3f-122">循环访问的元素集合。</span><span class="sxs-lookup"><span data-stu-id="5db3f-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="5db3f-123">在运行时确保所有集合元素为兼容类型。</span><span class="sxs-lookup"><span data-stu-id="5db3f-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="5db3f-124">使用 ForEach 的示例</span><span class="sxs-lookup"><span data-stu-id="5db3f-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="5db3f-125">下面的代码演示如何在应用程序中使用 ForEach 活动。</span><span class="sxs-lookup"><span data-stu-id="5db3f-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
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
  
|<span data-ttu-id="5db3f-126">条件</span><span class="sxs-lookup"><span data-stu-id="5db3f-126">Condition</span></span>|<span data-ttu-id="5db3f-127">消息</span><span class="sxs-lookup"><span data-stu-id="5db3f-127">Message</span></span>|<span data-ttu-id="5db3f-128">严重级别</span><span class="sxs-lookup"><span data-stu-id="5db3f-128">Severity</span></span>|<span data-ttu-id="5db3f-129">异常类型</span><span class="sxs-lookup"><span data-stu-id="5db3f-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="5db3f-130">Values 为 `null`</span><span class="sxs-lookup"><span data-stu-id="5db3f-130">Values is `null`</span></span>|<span data-ttu-id="5db3f-131">未提供必需活动参数“Values”的值。</span><span class="sxs-lookup"><span data-stu-id="5db3f-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="5db3f-132">错误</span><span class="sxs-lookup"><span data-stu-id="5db3f-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="5db3f-133">ForEachT 设计器</span><span class="sxs-lookup"><span data-stu-id="5db3f-133">ForEach Designer</span></span>  
 <span data-ttu-id="5db3f-134">此示例的活动设计器的外观与为内置 <xref:System.Activities.Statements.ForEach%601> 活动提供的设计器的外观相似。</span><span class="sxs-lookup"><span data-stu-id="5db3f-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="5db3f-135">此设计器显示在工具箱**示例**，**非泛型活动**类别。</span><span class="sxs-lookup"><span data-stu-id="5db3f-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="5db3f-136">名为设计器**ForEachWithBodyFactory**在工具箱中，因为活动会公开<xref:System.Activities.Presentation.IActivityTemplateFactory>从而可以在工具箱中，来创建使用正确配置活动<xref:System.Activities.ActivityAction>。</span><span class="sxs-lookup"><span data-stu-id="5db3f-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="5db3f-137">运行此示例</span><span class="sxs-lookup"><span data-stu-id="5db3f-137">To run this sample</span></span>  
  
1.  <span data-ttu-id="5db3f-138">将您选择的项目设置为解决方案的启动项目：</span><span class="sxs-lookup"><span data-stu-id="5db3f-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1.  <span data-ttu-id="5db3f-139">**Codetestclient**演示如何使用活动使用代码。</span><span class="sxs-lookup"><span data-stu-id="5db3f-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="5db3f-140">**Designertestclient**演示如何使用设计器中的活动。</span><span class="sxs-lookup"><span data-stu-id="5db3f-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="5db3f-141">生成并运行该项目。</span><span class="sxs-lookup"><span data-stu-id="5db3f-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5db3f-142">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5db3f-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5db3f-143">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5db3f-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5db3f-144">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="5db3f-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5db3f-145">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5db3f-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
