---
title: 针对 .NET Framework 4.5 的 Windows Workflow Foundation 词汇表
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], glossary
- WF [WF], glossary
ms.assetid: ab682b2f-3779-45ca-b831-b7c03d7dbb3a
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54a0cc6d9a0c922e57bf00b649894f26b42a64f4
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="windows-workflow-foundation-glossary-for-net-framework-45"></a><span data-ttu-id="2841a-102">针对 .NET Framework 4.5 的 Windows Workflow Foundation 词汇表</span><span class="sxs-lookup"><span data-stu-id="2841a-102">Windows Workflow Foundation Glossary for .NET Framework 4.5</span></span>
<span data-ttu-id="2841a-103">Windows Workflow Foundation 文档中使用了以下术语。</span><span class="sxs-lookup"><span data-stu-id="2841a-103">The following terms are used in the Windows Workflow Foundation documentation.</span></span>  
  
## <a name="terms"></a><span data-ttu-id="2841a-104">术语</span><span class="sxs-lookup"><span data-stu-id="2841a-104">Terms</span></span>  
  
|<span data-ttu-id="2841a-105">术语</span><span class="sxs-lookup"><span data-stu-id="2841a-105">Term</span></span>|<span data-ttu-id="2841a-106">定义</span><span class="sxs-lookup"><span data-stu-id="2841a-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2841a-107">活动</span><span class="sxs-lookup"><span data-stu-id="2841a-107">activity</span></span>|<span data-ttu-id="2841a-108">Windows Workflow Foundation 中的程序行为单元。</span><span class="sxs-lookup"><span data-stu-id="2841a-108">A unit of program behavior in Windows Workflow Foundation.</span></span> <span data-ttu-id="2841a-109">可将单个活动组合在一起，形成更复杂的活动。</span><span class="sxs-lookup"><span data-stu-id="2841a-109">Single activities can be composed together into more complex activities.</span></span>|  
|<span data-ttu-id="2841a-110">activity action（活动操作）</span><span class="sxs-lookup"><span data-stu-id="2841a-110">activity action</span></span>|<span data-ttu-id="2841a-111">用于公开工作流和活动执行的回调的数据结构。</span><span class="sxs-lookup"><span data-stu-id="2841a-111">A data structure used to expose callbacks for workflow and activity execution.</span></span>|  
|<span data-ttu-id="2841a-112">argument（参数）</span><span class="sxs-lookup"><span data-stu-id="2841a-112">argument</span></span>|<span data-ttu-id="2841a-113">定义流入和流出活动的数据。</span><span class="sxs-lookup"><span data-stu-id="2841a-113">Defines the data flow into and out of an activity.</span></span> <span data-ttu-id="2841a-114">每个参数都有特定的方向：in、out 或 in/out。这些表示活动的输入参数、输出参数或输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="2841a-114">Each argument has a specified direction: in, out, or in/out. These represent the input, output, and input/output parameters of the activity.</span></span>|  
|<span data-ttu-id="2841a-115">bookmark（书签）</span><span class="sxs-lookup"><span data-stu-id="2841a-115">bookmark</span></span>|<span data-ttu-id="2841a-116">活动可以暂停并等待继续的时间点。</span><span class="sxs-lookup"><span data-stu-id="2841a-116">The point at which an activity can pause and wait to be resumed.</span></span>|  
|<span data-ttu-id="2841a-117">compensation（补偿）</span><span class="sxs-lookup"><span data-stu-id="2841a-117">compensation</span></span>|<span data-ttu-id="2841a-118">一组旨在撤消或减轻先前所完成工作的效果的操作。</span><span class="sxs-lookup"><span data-stu-id="2841a-118">A group of actions designed to undo or mitigate the effect of previously completed work.</span></span>|  
|<span data-ttu-id="2841a-119">关联</span><span class="sxs-lookup"><span data-stu-id="2841a-119">correlation</span></span>|<span data-ttu-id="2841a-120">将消息路由至工作流或服务实例的机制。</span><span class="sxs-lookup"><span data-stu-id="2841a-120">The mechanism for routing messages to a workflow or service instance.</span></span>|  
|<span data-ttu-id="2841a-121">表达式</span><span class="sxs-lookup"><span data-stu-id="2841a-121">expression</span></span>|<span data-ttu-id="2841a-122">一个构造，它采用一个或多个参数，对参数执行运算，并返回一个值。</span><span class="sxs-lookup"><span data-stu-id="2841a-122">A construct that takes in one or more arguments, performs an operation on the arguments and returns a single value.</span></span> <span data-ttu-id="2841a-123">可以在可使用活动的任意位置使用表达式。</span><span class="sxs-lookup"><span data-stu-id="2841a-123">Expressions can be used anywhere an activity can be used.</span></span>|  
|<span data-ttu-id="2841a-124">flowchart（流程图）</span><span class="sxs-lookup"><span data-stu-id="2841a-124">flowchart</span></span>|<span data-ttu-id="2841a-125">一个众所周知的建模范例，它将程序组件表示为用方向箭头链接在一起的符号。</span><span class="sxs-lookup"><span data-stu-id="2841a-125">A well-known modeling paradigm that represents program components as symbols linked together with directional arrows.</span></span>  <span data-ttu-id="2841a-126">在 .NET Framework 4 中，可以使用 Flowchart 活动将工作流作为流程图来建模。</span><span class="sxs-lookup"><span data-stu-id="2841a-126">In the .NET Framework 4, workflows can be modeled as flowcharts using the Flowchart activity.</span></span>|  
|<span data-ttu-id="2841a-127">long-running process（长时间运行的进程）</span><span class="sxs-lookup"><span data-stu-id="2841a-127">long-running process</span></span>|<span data-ttu-id="2841a-128">不立即返回并且可跨系统重新启动的程序执行单元。</span><span class="sxs-lookup"><span data-stu-id="2841a-128">A unit of program execution that does not return immediately and may span system restarts.</span></span>|  
|<span data-ttu-id="2841a-129">持久性</span><span class="sxs-lookup"><span data-stu-id="2841a-129">persistence</span></span>|<span data-ttu-id="2841a-130">将工作流或服务的状态保存到持久性介质中，以便其可以从内存中卸载，或在系统出现故障后恢复。</span><span class="sxs-lookup"><span data-stu-id="2841a-130">Saving the state of a workflow or service to a durable medium, so that it can be unloaded from memory or recovered after a system failure.</span></span>|  
|<span data-ttu-id="2841a-131">状态机</span><span class="sxs-lookup"><span data-stu-id="2841a-131">state machine</span></span>|<span data-ttu-id="2841a-132">一个众所周知的建模范例，它将程序组件表示为用事件驱动状态转换链接在一起的单个状态。</span><span class="sxs-lookup"><span data-stu-id="2841a-132">A well-known modeling paradigm that represents program components as individual states linked together with event-driven state transitions.</span></span>  <span data-ttu-id="2841a-133">可以使用 StateMachine 活动将工作流作为状态机来建模。</span><span class="sxs-lookup"><span data-stu-id="2841a-133">Workflows can be modeled as state machines using the StateMachine activity.</span></span>|  
|<span data-ttu-id="2841a-134">substance（实体）</span><span class="sxs-lookup"><span data-stu-id="2841a-134">substance</span></span>|<span data-ttu-id="2841a-135">表示公共标识符下的一组相关书签，允许运行时做出有关特定书签恢复是有效还是会变为有效的决定。</span><span class="sxs-lookup"><span data-stu-id="2841a-135">Represents a group of related bookmarks under a common identifier and allows the runtime to make decisions about whether a particular bookmark resumption is valid or may become valid.</span></span>|  
|<span data-ttu-id="2841a-136">type converter（类型转换器）</span><span class="sxs-lookup"><span data-stu-id="2841a-136">type converter</span></span>|<span data-ttu-id="2841a-137">CLR 类型可以与一个或多个 System.ComponentModel.TypeConverter 派生类型关联，这些派生类型使 CLR 类型的实例与其他类型的实例之间能够互相转换。</span><span class="sxs-lookup"><span data-stu-id="2841a-137">A CLR type can be associated with one or more System.ComponentModel.TypeConverter derived types that enable converting instances of the CLR type to and from instances of other types.</span></span> <span data-ttu-id="2841a-138">类型转换器使用 System.ComponentModel.TypeConverterAttribute 特性与 CLR 类型相关联。</span><span class="sxs-lookup"><span data-stu-id="2841a-138">A type converterr is associated with a CLR type using the System.ComponentModel.TypeConverterAttribute attribute.</span></span>  <span data-ttu-id="2841a-139">可以在 CLR 类型或属性上直接指定 TypeConverterAttribute。</span><span class="sxs-lookup"><span data-stu-id="2841a-139">A TypeConverterAttribute can be specified directly on the CLR type or on a property.</span></span> <span data-ttu-id="2841a-140">在属性上指定的类型转换器始终优先于在属性的 CLR 类型上指定的类型转换器。</span><span class="sxs-lookup"><span data-stu-id="2841a-140">A type converter specified on a property always takes precedence over a type converter specified on the CLR type of the property.</span></span>|  
|<span data-ttu-id="2841a-141">变量</span><span class="sxs-lookup"><span data-stu-id="2841a-141">variable</span></span>|<span data-ttu-id="2841a-142">表示必须保存并稍后访问的某些数据的存储。</span><span class="sxs-lookup"><span data-stu-id="2841a-142">Represents the storage of some data that must be saved and accessed later.</span></span>|  
|<span data-ttu-id="2841a-143">工作流</span><span class="sxs-lookup"><span data-stu-id="2841a-143">workflow</span></span>|<span data-ttu-id="2841a-144">由宿主进程调用的一个活动或活动树。</span><span class="sxs-lookup"><span data-stu-id="2841a-144">A single activity or tree of activities invoked by a host process.</span></span>|  
|<span data-ttu-id="2841a-145">XAML</span><span class="sxs-lookup"><span data-stu-id="2841a-145">XAML</span></span>|<span data-ttu-id="2841a-146">可扩展应用程序标记语言</span><span class="sxs-lookup"><span data-stu-id="2841a-146">eXtensible Application Markup Language</span></span>|
