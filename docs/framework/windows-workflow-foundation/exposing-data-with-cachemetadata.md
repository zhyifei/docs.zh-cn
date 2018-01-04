---
title: "使用 CacheMetadata 公开数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25e658d512cf0575a4e3902a9a951099675e29a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="bcb20-102">使用 CacheMetadata 公开数据</span><span class="sxs-lookup"><span data-stu-id="bcb20-102">Exposing data with CacheMetadata</span></span>
<span data-ttu-id="bcb20-103">在执行某活动之前，工作流运行时会获取所需的所有活动信息以保持活动的执行。</span><span class="sxs-lookup"><span data-stu-id="bcb20-103">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="bcb20-104">工作流运行时在 <xref:System.Activities.Activity.CacheMetadata%2A> 方法执行期间获取这些信息。</span><span class="sxs-lookup"><span data-stu-id="bcb20-104">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="bcb20-105">在执行此方法的时候，此方法的默认实现为运行时提供活动公开的所有公共参数、变量和子活动；如果活动需要向运行时提供比这更多的信息（如私有成员或将由该活动安排的活动），可以重写此方法以进行提供。</span><span class="sxs-lookup"><span data-stu-id="bcb20-105">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>  
  
## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="bcb20-106">默认 CacheMetadata 行为</span><span class="sxs-lookup"><span data-stu-id="bcb20-106">Default CacheMetadata behavior</span></span>  
 <span data-ttu-id="bcb20-107"><xref:System.Activities.NativeActivity.CacheMetadata%2A> 所派生活动的 <xref:System.Activities.NativeActivity> 的默认实现将通过以下方式来处理以下方法类型：</span><span class="sxs-lookup"><span data-stu-id="bcb20-107">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>  
  
-   <span data-ttu-id="bcb20-108"><xref:System.Activities.InArgument%601>、<xref:System.Activities.OutArgument%601> 或 <xref:System.Activities.InOutArgument%601>（泛型参数）：这些参数作为参数公开给运行时，具有与公开的属性名称和类型相等的名称和类型、相应的参数方向和某些验证数据。</span><span class="sxs-lookup"><span data-stu-id="bcb20-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>  
  
-   <span data-ttu-id="bcb20-109"><xref:System.Activities.Variable> 或其中的任何子类：这些成员作为公共变量公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-109"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="bcb20-110"><xref:System.Activities.Activity> 或其中的任何子类：这些成员作为公共子活动公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-110"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="bcb20-111">可以通过调用 <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>、传入子活动来显式实现默认行为。</span><span class="sxs-lookup"><span data-stu-id="bcb20-111">The default behavior can be implemented explicity by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>  
  
-   <span data-ttu-id="bcb20-112"><xref:System.Activities.ActivityDelegate> 或其中的任何子类：这些成员作为公共委托公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-112"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>  
  
-   <span data-ttu-id="bcb20-113"><xref:System.Collections.ICollection> 类型的 <xref:System.Activities.Variable>：集合中的所有元素都作为公共变量公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-113"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>  
  
-   <span data-ttu-id="bcb20-114"><xref:System.Collections.ICollection> 类型的 <xref:System.Activities.Activity>：集合中的所有元素都作为公共子活动公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>  
  
-   <span data-ttu-id="bcb20-115"><xref:System.Collections.ICollection> 类型的 <xref:System.Activities.ActivityDelegate>：集合中的所有元素都作为公共委托公开给运行时。</span><span class="sxs-lookup"><span data-stu-id="bcb20-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>  
  
 <span data-ttu-id="bcb20-116">从 <xref:System.Activities.Activity.CacheMetadata%2A>、<xref:System.Activities.Activity> 和 <xref:System.Workflow.Activities.CodeActivity> 派生的活动 <xref:System.Activities.AsyncCodeActivity> 也能起到以上的作用，但有以下差异：</span><span class="sxs-lookup"><span data-stu-id="bcb20-116">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>  
  
-   <span data-ttu-id="bcb20-117">从 <xref:System.Activities.Activity> 派生的类不能安排子活动或委托，所以此类成员作为导入的子活动或委托公开。</span><span class="sxs-lookup"><span data-stu-id="bcb20-117">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>  
  
-   <span data-ttu-id="bcb20-118">从 <xref:System.Activities.CodeActivity> 和 <xref:System.Activities.AsyncCodeActivity> 派生的类不支持变量、子活动或委托，所以将只公开参数。</span><span class="sxs-lookup"><span data-stu-id="bcb20-118">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>  
  
## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="bcb20-119">重写 CacheMetadata 以向运行时提供信息</span><span class="sxs-lookup"><span data-stu-id="bcb20-119">Overriding CacheMetadata to provide information to the runtime</span></span>  
 <span data-ttu-id="bcb20-120">以下代码段演示如何在 <xref:System.Activities.Activity.CacheMetadata%2A> 方法执行期间向活动的元数据添加有关成员的信息。</span><span class="sxs-lookup"><span data-stu-id="bcb20-120">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="bcb20-121">注意，调用了该方法的基类以缓存有关活动的所有公共数据。</span><span class="sxs-lookup"><span data-stu-id="bcb20-121">Note that the base of the method is called to cache all public data about the activity.</span></span>  
  
```  
protected override void CacheMetadata(NativeActivityMetadata metadata)  
{      
    base.CacheMetadata(metadata);  
    metadata.AddImplementationChild(this._writeLine);  
    metadata.AddVariable(this._myVariable);  
    metadata.AddImplementationVariable(this._myImplementationVariable);  
  
    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));  
    metadata.Bind(argument, this.SomeName);  
    metadata.AddArgument(argument);  
}  
```  
  
## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="bcb20-122">使用 CacheMetadata 公开实现子活动</span><span class="sxs-lookup"><span data-stu-id="bcb20-122">Using CacheMetadata to expose implementation children</span></span>  
 <span data-ttu-id="bcb20-123">为了使用变量将数据传递给将由活动安排的子活动，有必要将变量添加为实现变量；不能用这种方式设置公共变量的值。</span><span class="sxs-lookup"><span data-stu-id="bcb20-123">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="bcb20-124">原因在于，活动将更有可能作为功能的实现（有参数）执行，而不是作为封装类（有属性）执行。</span><span class="sxs-lookup"><span data-stu-id="bcb20-124">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="bcb20-125">但是，在有些情况下，必须显式设置参数，如使用 <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> 时，因为安排的活动不能像子活动那样访问父活动的参数。</span><span class="sxs-lookup"><span data-stu-id="bcb20-125">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>  
  
 <span data-ttu-id="bcb20-126">下面的代码段演示如何使用 <xref:System.Activities.Activity.CacheMetadata%2A> 将参数从本机活动传入一个安排的活动。</span><span class="sxs-lookup"><span data-stu-id="bcb20-126">The following code snippet demonstrates how to pass an argument form a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>  
  
```  
public sealed class ChildActivity : NativeActivity  
{  
    public WriteLine _writeLine;  
    public InArgument<string> Message { get; set; }  
    private Variable<string> MessageVariable { get; set; }  
    public ChildActivity()  
    {  
        MessageVariable = new Variable<string>();  
        _writeLine = new WriteLine  
        {  
            Text = new InArgument<string>(MessageVariable),  
        };  
    }  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        metadata.AddImplementationVariable(this.MessageVariable);  
        metadata.AddImplementationChild(this._writeLine);  
    }  
    protected override void Execute(NativeActivityContext context)  
    {  
        string configuredMessage = context.GetValue(Message);  
        context.SetValue(MessageVariable, configuredMessage);  
        context.ScheduleActivity(this._writeLine);  
    }  
}  
```
