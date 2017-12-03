---
title: "Windows 工作流体系结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1b58456fe99331a47871fbf4b1ad86cd43c53c2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="windows-workflow-architecture"></a><span data-ttu-id="d4531-102">Windows 工作流体系结构</span><span class="sxs-lookup"><span data-stu-id="d4531-102">Windows Workflow Architecture</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="d4531-103"> 提升了开发长时间运行的交互式应用程序的抽象级别。</span><span class="sxs-lookup"><span data-stu-id="d4531-103"> raises the abstraction level for developing interactive long-running applications.</span></span> <span data-ttu-id="d4531-104">工作单元封装为活动。</span><span class="sxs-lookup"><span data-stu-id="d4531-104">Units of work are encapsulated as activities.</span></span> <span data-ttu-id="d4531-105">活动运行环境提供用于流控制、异常处理、错误传播、状态数据保存、从内存加载和卸载正在进行的工作流、跟踪以及事务流的功能。</span><span class="sxs-lookup"><span data-stu-id="d4531-105">Activities run in an environment that provides facilities for flow control, exception handling, fault propagation, persistence of state data, loading and unloading of in-progress workflows from memory, tracking, and transaction flow.</span></span>  
  
## <a name="activity-architecture"></a><span data-ttu-id="d4531-106">活动体系结构</span><span class="sxs-lookup"><span data-stu-id="d4531-106">Activity Architecture</span></span>  
 <span data-ttu-id="d4531-107">活动作为 CLR 类型开发，这些类型或者派生自 <xref:System.Activities.Activity>、<xref:System.Activities.CodeActivity>、<xref:System.Activities.AsyncCodeActivity> 或 <xref:System.Activities.NativeActivity>，或者派生自返回某个值的对应 <xref:System.Activities.Activity%601>、<xref:System.Activities.CodeActivity%601>、<xref:System.Activities.AsyncCodeActivity%601> 或 <xref:System.Activities.NativeActivity%601> 变体。</span><span class="sxs-lookup"><span data-stu-id="d4531-107">Activities are developed as CLR types that derive from either <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>, or their variants that return a value, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, or <xref:System.Activities.NativeActivity%601>.</span></span> <span data-ttu-id="d4531-108">通过开发派生自 <xref:System.Activities.Activity> 的活动，用户可以组合预先存在的活动，以便快速创建在工作流环境中执行的工作单元。</span><span class="sxs-lookup"><span data-stu-id="d4531-108">Developing activities that derive from <xref:System.Activities.Activity> allows the user to assemble pre-existing activities to quickly create units of work that execute in the workflow environment.</span></span> <span data-ttu-id="d4531-109">另一方面，<xref:System.Activities.CodeActivity> 支持通过将 <xref:System.Activities.CodeActivityContext> 主要用于访问活动参数，在托管代码中创作执行逻辑。</span><span class="sxs-lookup"><span data-stu-id="d4531-109"><xref:System.Activities.CodeActivity>, on the other hand, enables execution logic to be authored in managed code using <xref:System.Activities.CodeActivityContext> primarily for access to activity arguments.</span></span> <span data-ttu-id="d4531-110"><xref:System.Activities.AsyncCodeActivity> 类似于 <xref:System.Activities.CodeActivity>，只不过它可以用于实现异步任务。</span><span class="sxs-lookup"><span data-stu-id="d4531-110"><xref:System.Activities.AsyncCodeActivity> is similar to <xref:System.Activities.CodeActivity> except that it can be used to implement asynchronous tasks.</span></span> <span data-ttu-id="d4531-111">通过开发派生自 <xref:System.Activities.NativeActivity> 的活动，用户可以通过 <xref:System.Activities.NativeActivityContext> 访问运行时，以实现安排子级、创建书签、调用异步工作、注册事务等功能。</span><span class="sxs-lookup"><span data-stu-id="d4531-111">Developing activities that derive from <xref:System.Activities.NativeActivity> allows users to access the runtime through the <xref:System.Activities.NativeActivityContext> for functionality like scheduling children, creating bookmarks, invoking asynchronous work, registering transactions, and more.</span></span>  
  
 <span data-ttu-id="d4531-112">创作派生自 <xref:System.Activities.Activity> 的活动是声明性的，可以在 XAML 中创作这些活动。</span><span class="sxs-lookup"><span data-stu-id="d4531-112">Authoring activities that derive from <xref:System.Activities.Activity> is declarative and these activities can be authored in XAML.</span></span> <span data-ttu-id="d4531-113">下面的示例使用其他活动作为执行体来创建一个名为 `Prompt` 的活动。</span><span class="sxs-lookup"><span data-stu-id="d4531-113">In the following example, an activity called `Prompt` is created using other activities for the execution body.</span></span>  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a><span data-ttu-id="d4531-114">活动上下文</span><span class="sxs-lookup"><span data-stu-id="d4531-114">Activity Context</span></span>  
 <span data-ttu-id="d4531-115"><xref:System.Activities.ActivityContext> 是活动作者的工作流运行时接口，提供对诸多运行时功能的访问。</span><span class="sxs-lookup"><span data-stu-id="d4531-115">The <xref:System.Activities.ActivityContext> is the activity author's interface to the workflow runtime and provides access to the runtime's wealth of features.</span></span> <span data-ttu-id="d4531-116">下面的示例定义一个使用执行上下文创建书签（一种机制，允许活动在其执行中注册一个延续点，该延续点可由将数据传入活动的主机恢复）的活动。</span><span class="sxs-lookup"><span data-stu-id="d4531-116">In the following example, an activity is defined that uses the execution context to create a bookmark (the mechanism that allows an activity to register a continuation point in its execution that can be resumed by a host passing data into the activity).</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a><span data-ttu-id="d4531-117">活动生命周期</span><span class="sxs-lookup"><span data-stu-id="d4531-117">Activity Life Cycle</span></span>  
 <span data-ttu-id="d4531-118">活动实例启动时处于 <xref:System.Activities.ActivityInstanceState.Executing> 状态。</span><span class="sxs-lookup"><span data-stu-id="d4531-118">An instance of an activity starts out in the <xref:System.Activities.ActivityInstanceState.Executing> state.</span></span> <span data-ttu-id="d4531-119">除非发生异常，否则活动将保持此状态，直到已完成执行所有子活动和所有其他挂起的工作（如 <xref:System.Activities.Bookmark> 对象），此时，该活动将转换为 <xref:System.Activities.ActivityInstanceState.Closed> 状态。</span><span class="sxs-lookup"><span data-stu-id="d4531-119">Unless exceptions are encountered, it remains in this state until all child activities are finished executing and any other pending work (<xref:System.Activities.Bookmark> objects, for instance) is completed, at which point it transitions to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="d4531-120">活动实例的父级可以请求取消子级；如果可以取消子级，该子级则在完成时处于 <xref:System.Activities.ActivityInstanceState.Canceled> 状态。</span><span class="sxs-lookup"><span data-stu-id="d4531-120">The parent of an activity instance can request a child to cancel; if the child is able to be canceled it completes in the <xref:System.Activities.ActivityInstanceState.Canceled> state.</span></span> <span data-ttu-id="d4531-121">如果在执行期间引发异常，运行时会使活动进入 <xref:System.Activities.ActivityInstanceState.Faulted> 状态，并将此异常向上传播到活动父链。</span><span class="sxs-lookup"><span data-stu-id="d4531-121">If an exception is thrown during execution, the runtime puts the activity into the <xref:System.Activities.ActivityInstanceState.Faulted> state and propagates the exception up the parent chain of activities.</span></span> <span data-ttu-id="d4531-122">下面列出了活动的三个完成状态：</span><span class="sxs-lookup"><span data-stu-id="d4531-122">Following are the three completion states of an activity:</span></span>  
  
-   <span data-ttu-id="d4531-123">**关闭：**活动已完成其工作并退出。</span><span class="sxs-lookup"><span data-stu-id="d4531-123">**Closed:** The activity has completed its work and exited.</span></span>  
  
-   <span data-ttu-id="d4531-124">**取消：**活动已正常放弃其工作并退出。</span><span class="sxs-lookup"><span data-stu-id="d4531-124">**Canceled:** The activity has gracefully abandoned its work and exited.</span></span> <span data-ttu-id="d4531-125">当进入此状态时，不会显式回滚工作。</span><span class="sxs-lookup"><span data-stu-id="d4531-125">Work is not explicitly rolled back when this state is entered.</span></span>  
  
-   <span data-ttu-id="d4531-126">**出错：**活动已遇到错误，并且具有未完成其工作的情况下退出。</span><span class="sxs-lookup"><span data-stu-id="d4531-126">**Faulted:** The activity has encountered an error and has exited without completing its work.</span></span>  
  
 <span data-ttu-id="d4531-127">当保存或卸载活动时，活动会保持 <xref:System.Activities.ActivityInstanceState.Executing> 状态。</span><span class="sxs-lookup"><span data-stu-id="d4531-127">Activities remain in the <xref:System.Activities.ActivityInstanceState.Executing> state when they are persisted or unloaded.</span></span>
