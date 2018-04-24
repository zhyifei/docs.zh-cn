---
title: 基于事件的异步模式 (EAP)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fecd71355d53f1e3937d3724569b10fa0c8e50da
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="55832-102">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="55832-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="55832-103">有多种方式可向客户端代码公开异步功能。</span><span class="sxs-lookup"><span data-stu-id="55832-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="55832-104">基于事件的异步模式规定了类呈现异步行为的一种方式。</span><span class="sxs-lookup"><span data-stu-id="55832-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55832-105">从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 开始，任务并行库为异步和并行编程提供了一种新模型。</span><span class="sxs-lookup"><span data-stu-id="55832-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="55832-106">有关详细信息，请参阅[并行编程](../../../docs/standard/parallel-programming/index.md)。</span><span class="sxs-lookup"><span data-stu-id="55832-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55832-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="55832-107">In This Section</span></span>  
 [<span data-ttu-id="55832-108">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="55832-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="55832-109">描述基于事件的异步模式如何在隐藏多线程设计中固有的许多复杂问题的同时，提供多线程应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="55832-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="55832-110">实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="55832-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="55832-111">描述打包具有异步功能的类的标准方式。</span><span class="sxs-lookup"><span data-stu-id="55832-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="55832-112">实现基于事件的异步模式的最佳做法</span><span class="sxs-lookup"><span data-stu-id="55832-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="55832-113">描述根据基于事件的异步模式公开异步功能的需求。</span><span class="sxs-lookup"><span data-stu-id="55832-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="55832-114">确定何时实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="55832-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="55832-115">描述如何确定何时应选择实现基于事件的异步模式而不是 <xref:System.IAsyncResult> 模式。</span><span class="sxs-lookup"><span data-stu-id="55832-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="55832-116">演练：实现支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="55832-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="55832-117">演示如何创建实现基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="55832-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="55832-118">它是使用 <xref:System.ComponentModel?displayProperty=nameWithType> 命名空间的帮助器类实现的，这可确保该组件在任何应用程序模型下均可正常工作。</span><span class="sxs-lookup"><span data-stu-id="55832-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="55832-119">如何：使用支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="55832-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="55832-120">描述如何使用支持基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="55832-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="55832-121">参考</span><span class="sxs-lookup"><span data-stu-id="55832-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="55832-122">描述 <xref:System.ComponentModel.AsyncOperation> 类并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="55832-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="55832-123">描述 <xref:System.ComponentModel.AsyncOperationManager> 类并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="55832-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="55832-124">描述 <xref:System.ComponentModel.BackgroundWorker> 组件并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="55832-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55832-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="55832-125">Related Sections</span></span>  
 [<span data-ttu-id="55832-126">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="55832-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="55832-127">描述用于异步和并行操作的编程模型。</span><span class="sxs-lookup"><span data-stu-id="55832-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="55832-128">线程处理</span><span class="sxs-lookup"><span data-stu-id="55832-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="55832-129">描述 .NET Framework 中的多线程处理功能。</span><span class="sxs-lookup"><span data-stu-id="55832-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="55832-130">线程处理</span><span class="sxs-lookup"><span data-stu-id="55832-130">Threading</span></span>](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="55832-131">描述 C# 和 Visual Basic 语言中的多线程处理功能。</span><span class="sxs-lookup"><span data-stu-id="55832-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55832-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="55832-132">See Also</span></span>  
 [<span data-ttu-id="55832-133">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="55832-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="55832-134">事件</span><span class="sxs-lookup"><span data-stu-id="55832-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="55832-135">组件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="55832-135">Multithreading in Components</span></span>](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="55832-136">异步编程设计模式</span><span class="sxs-lookup"><span data-stu-id="55832-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
