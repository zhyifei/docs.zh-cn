---
title: 异步编程模式
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 42298bc8e3101b03f6c3e03fec453b72cd959efb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="62fc9-102">异步编程模式</span><span class="sxs-lookup"><span data-stu-id="62fc9-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="62fc9-103">.NET Framework 提供了执行异步操作的三种模式：</span><span class="sxs-lookup"><span data-stu-id="62fc9-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="62fc9-104">异步编程模型 (APM) 模式（也称 <xref:System.IAsyncResult> 模式），在此模式中异步操作需要 `Begin` 和 `End` 方法（比如用于异步写入操作的 `BeginWrite` 和 `EndWrite`）。</span><span class="sxs-lookup"><span data-stu-id="62fc9-104">Asynchronous Programming Model (APM) pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="62fc9-105">不建议新的开发使用此模式。</span><span class="sxs-lookup"><span data-stu-id="62fc9-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="62fc9-106">有关详细信息，请参阅[异步编程模型 (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc9-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="62fc9-107">基于事件的异步模式 (EAP)，这种模式需要 `Async` 后缀，也需要一个或多个事件、事件处理程序委托类型和 `EventArg` 派生类型。</span><span class="sxs-lookup"><span data-stu-id="62fc9-107">Event-based Asynchronous Pattern (EAP), which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="62fc9-108">EAP 是在 .NET Framework 2.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="62fc9-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="62fc9-109">不建议新的开发使用这种模式。</span><span class="sxs-lookup"><span data-stu-id="62fc9-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="62fc9-110">有关详细信息，请参阅[基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc9-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="62fc9-111">基于任务的异步模式 (TAP) 使用一种方法来表示异步操作的启动和完成。</span><span class="sxs-lookup"><span data-stu-id="62fc9-111">Task-based Asynchronous Pattern (TAP), which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="62fc9-112">TAP 是在 .NET Framework 4 中引入的，并且它是在 .NET Framework 中进行异步编程的推荐使用方法。</span><span class="sxs-lookup"><span data-stu-id="62fc9-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="62fc9-113">C# 中的 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 关键词以及 Visual Basic 语言中的 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 运算符为 TAP 添加了语言支持。</span><span class="sxs-lookup"><span data-stu-id="62fc9-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="62fc9-114">有关详细信息，请参阅[基于任务的异步模式 (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc9-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="62fc9-115">比较模式</span><span class="sxs-lookup"><span data-stu-id="62fc9-115">Comparing Patterns</span></span>  

<span data-ttu-id="62fc9-116">为了快速比较这三种模式的异步操作方式，请考虑使用从指定偏移量处起将指定量数据读取到提供的缓冲区中的`Read`方法：</span><span class="sxs-lookup"><span data-stu-id="62fc9-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="62fc9-117">此方法对应的 APM 将公开 `BeginRead` 和 `EndRead` 方法：</span><span class="sxs-lookup"><span data-stu-id="62fc9-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="62fc9-118">对应的 EAP 将公开以下类型和成员的集：</span><span class="sxs-lookup"><span data-stu-id="62fc9-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="62fc9-119">对应的 TAP 将公开以下单个 `ReadAsync` 方法：</span><span class="sxs-lookup"><span data-stu-id="62fc9-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="62fc9-120">为了全面讨论 TAP、APM 和 EAP，请参阅下一节中提供的链接。</span><span class="sxs-lookup"><span data-stu-id="62fc9-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="62fc9-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="62fc9-121">Related topics</span></span>

| <span data-ttu-id="62fc9-122">标题</span><span class="sxs-lookup"><span data-stu-id="62fc9-122">Title</span></span> | <span data-ttu-id="62fc9-123">描述</span><span class="sxs-lookup"><span data-stu-id="62fc9-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="62fc9-124">异步编程模型 (APM)</span><span class="sxs-lookup"><span data-stu-id="62fc9-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="62fc9-125">描述使用 <xref:System.IAsyncResult> 接口提供异步行为的旧模型。</span><span class="sxs-lookup"><span data-stu-id="62fc9-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="62fc9-126">不建议新的开发使用此模型。</span><span class="sxs-lookup"><span data-stu-id="62fc9-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="62fc9-127">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="62fc9-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="62fc9-128">描述提供异步行为的基于事件的旧模型。</span><span class="sxs-lookup"><span data-stu-id="62fc9-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="62fc9-129">不建议新的开发使用此模型。</span><span class="sxs-lookup"><span data-stu-id="62fc9-129">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="62fc9-130">基于任务的异步模式 (TAP)</span><span class="sxs-lookup"><span data-stu-id="62fc9-130">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) | <span data-ttu-id="62fc9-131">描述基于 <xref:System.Threading.Tasks> 命名空间的新异步模式。</span><span class="sxs-lookup"><span data-stu-id="62fc9-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="62fc9-132">此模型是在 .NET Framework 4 及更高版本中进行异步编程的推荐使用方法。</span><span class="sxs-lookup"><span data-stu-id="62fc9-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="62fc9-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="62fc9-133">See also</span></span>

<span data-ttu-id="62fc9-134">[C# 中的异步编程](~/docs/csharp/async.md) </span><span class="sxs-lookup"><span data-stu-id="62fc9-134">[Asynchronous programming in C#](~/docs/csharp/async.md) </span></span>  
<span data-ttu-id="62fc9-135">[F# 中的异步编程](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span><span class="sxs-lookup"><span data-stu-id="62fc9-135">[Async Programming in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md) </span></span>  
[<span data-ttu-id="62fc9-136">使用 Async 和 Await 的异步编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62fc9-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
