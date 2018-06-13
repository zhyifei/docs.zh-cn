---
title: 内置活动
ms.date: 03/30/2017
ms.assetid: 31e1b8c2-7f74-458a-b2e2-fddc5b10eac1
ms.openlocfilehash: f427788050da4de799c1908829020b10a0de6816
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519308"
---
# <a name="built-in-activities"></a><span data-ttu-id="a218e-102">内置活动</span><span class="sxs-lookup"><span data-stu-id="a218e-102">Built-in Activities</span></span>
<span data-ttu-id="a218e-103">本节包含演示内置的 Windows Workflow Foundation (WF) 活动的示例。</span><span class="sxs-lookup"><span data-stu-id="a218e-103">This section contains samples that demonstrate built-in Windows Workflow Foundation (WF) activities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a218e-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="a218e-104">In This Section</span></span>  
 [<span data-ttu-id="a218e-105">使用 TryCatch 在 Flowchart 活动中进行错误处理</span><span class="sxs-lookup"><span data-stu-id="a218e-105">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
 <span data-ttu-id="a218e-106">演示如何在复杂控制流活动中使用 <xref:System.Activities.Statements.TryCatch> 活动。</span><span class="sxs-lookup"><span data-stu-id="a218e-106">Demonstrates how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>  
  
 [<span data-ttu-id="a218e-107">在 While 活动中模拟中断</span><span class="sxs-lookup"><span data-stu-id="a218e-107">Emulating breaking in a While activity</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/emulating-breaking-in-a-while-activity.md)  
 <span data-ttu-id="a218e-108">演示如何中断下列活动的循环机制：<xref:System.Activities.Statements.DoWhile>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.While> 和 <xref:System.Activities.Statements.ParallelForEach%601>。</span><span class="sxs-lookup"><span data-stu-id="a218e-108">Demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 [<span data-ttu-id="a218e-109">DynamicActivity 创建</span><span class="sxs-lookup"><span data-stu-id="a218e-109">DynamicActivity Creation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)  
 <span data-ttu-id="a218e-110">演示在运行时使用 <xref:System.Activities.DynamicActivity> 活动来创建活动的两种不同方式。</span><span class="sxs-lookup"><span data-stu-id="a218e-110">Demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 [<span data-ttu-id="a218e-111">将变量用于 .NET Framework 3.5 规则集</span><span class="sxs-lookup"><span data-stu-id="a218e-111">Using Variables with a .NET Framework 3.5 Ruleset</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-variables-with-dotnet-ruleset.md)  
 <span data-ttu-id="a218e-112">演示如何创建一个工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 活动集成在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中编写的使用了策略和规则的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="a218e-112">Demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span>  
  
 [<span data-ttu-id="a218e-113">从 XAML 加载</span><span class="sxs-lookup"><span data-stu-id="a218e-113">Load From XAML</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/load-from-xaml.md)  
 <span data-ttu-id="a218e-114">演示如何在不运行 XamlBuildTask 工具的情况下动态加载 XAML 工作流。</span><span class="sxs-lookup"><span data-stu-id="a218e-114">Demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span>  
  
 [<span data-ttu-id="a218e-115">使用集合活动</span><span class="sxs-lookup"><span data-stu-id="a218e-115">Using Collection Activities</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-collection-activities.md)  
 <span data-ttu-id="a218e-116">演示如何将集合活动（<xref:System.Activities.Statements.AddToCollection%601>、<xref:System.Activities.Statements.ClearCollection%601>、<xref:System.Activities.Statements.ExistsInCollection%601> 和 <xref:System.Activities.Statements.RemoveFromCollection%601>）与实现 <xref:System.Collections.ICollection> 接口的类一起使用，以及如何创建一个自定义活动，该活动循环访问集合以输出集合中每个元素的内容。</span><span class="sxs-lookup"><span data-stu-id="a218e-116">Demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span>  
  
 [<span data-ttu-id="a218e-117">使用 InvokeMethod 活动</span><span class="sxs-lookup"><span data-stu-id="a218e-117">Using the InvokeMethod Activity</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-the-invokemethod-activity.md)  
 <span data-ttu-id="a218e-118">演示如何使用 <xref:System.Activities.Statements.InvokeMethod> 活动调用公共类中的公共方法。</span><span class="sxs-lookup"><span data-stu-id="a218e-118">Demonstrates how to use the <xref:System.Activities.Statements.InvokeMethod> activity to invoke public methods in public classes.</span></span>  
  
 [<span data-ttu-id="a218e-119">使用 Pick 活动</span><span class="sxs-lookup"><span data-stu-id="a218e-119">Using the Pick Activity</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)  
 <span data-ttu-id="a218e-120">演示如何使用 <xref:System.Activities.Statements.Pick> 活动。</span><span class="sxs-lookup"><span data-stu-id="a218e-120">Demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 [<span data-ttu-id="a218e-121">使用过程性活动</span><span class="sxs-lookup"><span data-stu-id="a218e-121">Using Procedural Activities</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
 <span data-ttu-id="a218e-122">演示如何使用 <xref:System.Activities.Statements.Sequence>、<xref:System.Activities.Statements.Assign>、<xref:System.Activities.Statements.If>、<xref:System.Activities.Statements.While>、<xref:System.Activities.Statements.Switch%601>、<xref:System.Activities.Statements.TryCatch> 和 <xref:System.Activities.Statements.WriteLine> 活动以实现猜谜游戏。</span><span class="sxs-lookup"><span data-stu-id="a218e-122">Demonstrates how to use the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span>  
  
 [<span data-ttu-id="a218e-123">使用 CancellationScope</span><span class="sxs-lookup"><span data-stu-id="a218e-123">Using CancellationScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/using-cancellationscope.md)  
 <span data-ttu-id="a218e-124">演示如何使用 <xref:System.Activities.Statements.CancellationScope> 活动取消应用程序中的工作。</span><span class="sxs-lookup"><span data-stu-id="a218e-124">Demonstrates how to use the <xref:System.Activities.Statements.CancellationScope> activity to cancel work in an application.</span></span>  
  
 [<span data-ttu-id="a218e-125">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="a218e-125">InvokeMethod</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
 <span data-ttu-id="a218e-126">演示使用 <xref:System.Activities.Statements.InvokeMethod> 活动调用类的方法的不同方式。</span><span class="sxs-lookup"><span data-stu-id="a218e-126">Demonstrates the different ways to use the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 [<span data-ttu-id="a218e-127">带自定义类型的切换活动的用法</span><span class="sxs-lookup"><span data-stu-id="a218e-127">Usage of the Switch Activity with Custom Types</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/usage-of-the-switch-activity-with-custom-types.md)  
 <span data-ttu-id="a218e-128">介绍如何使 <xref:System.Activities.Statements.Switch%601> 活动能够在运行时计算用户定义的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="a218e-128">Describes how to enable a <xref:System.Activities.Statements.Switch%601> activity to evaluate a user-defined complex type at runtime.</span></span>  
  
 [<span data-ttu-id="a218e-129">与 3.5 规则集交互</span><span class="sxs-lookup"><span data-stu-id="a218e-129">Interop with 3.5 Rule Set</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/interop-with-3-5-rule-set.md)  
 <span data-ttu-id="a218e-130">演示如何使用 <xref:System.Activities.Statements.Interop> 活动以便与 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中使用 <xref:System.Workflow.Activities.PolicyActivity> 和规则的自定义活动集成。</span><span class="sxs-lookup"><span data-stu-id="a218e-130">Demonstrates the use of the <xref:System.Activities.Statements.Interop> activity to integrate with a custom activity in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] using <xref:System.Workflow.Activities.PolicyActivity> and rules.</span></span>
