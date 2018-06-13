---
title: 使用基于事件的异步模式进行多线程编程
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
ms.openlocfilehash: 26e555a158ced352c297952b56f7557cbd825cd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567297"
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="2f8a3-102">使用基于事件的异步模式进行多线程编程</span><span class="sxs-lookup"><span data-stu-id="2f8a3-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="2f8a3-103">有多种方式可向客户端代码公开异步功能。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="2f8a3-104">基于事件的异步模式为类规定了用于显示异步行为的建议方式。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f8a3-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2f8a3-105">In This Section</span></span>  
 [<span data-ttu-id="2f8a3-106">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="2f8a3-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="2f8a3-107">描述基于事件的异步模式如何在隐藏多线程设计中固有的许多复杂问题的同时，提供多线程应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="2f8a3-108">实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="2f8a3-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2f8a3-109">描述打包具有异步功能的类的标准方式。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="2f8a3-110">实现基于事件的异步模式的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2f8a3-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2f8a3-111">描述根据基于事件的异步模式公开异步功能的需求。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="2f8a3-112">确定何时实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="2f8a3-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2f8a3-113">描述如何确定何时应选择实现基于事件的异步模式而不是 <xref:System.IAsyncResult> 模式。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="2f8a3-114">演练：实现支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="2f8a3-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2f8a3-115">演示如何创建实现基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="2f8a3-116">它是使用 <xref:System.ComponentModel?displayProperty=nameWithType> 命名空间的帮助器类实现的，这可确保该组件在任何应用程序模型下均可正常工作。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="2f8a3-117">如何：使用支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="2f8a3-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2f8a3-118">描述如何使用支持基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2f8a3-119">参考</span><span class="sxs-lookup"><span data-stu-id="2f8a3-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="2f8a3-120">描述 <xref:System.ComponentModel.AsyncOperation> 类并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="2f8a3-121">描述 <xref:System.ComponentModel.AsyncOperationManager> 类并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="2f8a3-122">描述 <xref:System.ComponentModel.BackgroundWorker> 组件并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="2f8a3-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8a3-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f8a3-123">See Also</span></span>  
 [<span data-ttu-id="2f8a3-124">托管线程处理的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2f8a3-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="2f8a3-125">事件</span><span class="sxs-lookup"><span data-stu-id="2f8a3-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="2f8a3-126">组件中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="2f8a3-126">Multithreading in Components</span></span>](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="2f8a3-127">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="2f8a3-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
