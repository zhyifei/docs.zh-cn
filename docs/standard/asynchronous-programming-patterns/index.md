---
title: 异步编程模式
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50d76aef201fead37923a65cfeead16638b09842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031169"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="8ea9d-102">异步编程模式</span><span class="sxs-lookup"><span data-stu-id="8ea9d-102">Asynchronous programming patterns</span></span>

<span data-ttu-id="8ea9d-103">.NET 提供了执行异步操作的三种模式：</span><span class="sxs-lookup"><span data-stu-id="8ea9d-103">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="8ea9d-104">**基于任务的异步模式 (TAP)**，该模式使用单一方法表示异步操作的开始和完成。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-104">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="8ea9d-105">TAP 是在 .NET Framework 4 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-105">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="8ea9d-106">**这是在 .NET 中进行异步编程的推荐方法。**</span><span class="sxs-lookup"><span data-stu-id="8ea9d-106">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="8ea9d-107">C# 中的 [async](~/docs/csharp/language-reference/keywords/async.md) 和 [await](~/docs/csharp/language-reference/keywords/await.md) 关键词以及 Visual Basic 中的 [Async](~/docs/visual-basic/language-reference/modifiers/async.md) 和 [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) 运算符为 TAP 添加了语言支持。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-107">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="8ea9d-108">有关详细信息，请参阅[基于任务的异步模式 (TAP)](task-based-asynchronous-pattern-tap.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-108">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="8ea9d-109">基于事件的异步模式 (EAP)，是提供异步行为的基于事件的旧模型。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-109">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="8ea9d-110">这种模式需要后缀为 `Async` 的方法，以及一个或多个事件、事件处理程序委托类型和 `EventArg` 派生类型。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-110">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="8ea9d-111">EAP 是在 .NET Framework 2.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-111">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="8ea9d-112">建议新开发中不再使用这种模式。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-112">It's no longer recommended for new development.</span></span> <span data-ttu-id="8ea9d-113">有关详细信息，请参阅[基于事件的异步模式 (EAP)](event-based-asynchronous-pattern-eap.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-113">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="8ea9d-114">异步编程模型 (APM) 模式（也称为 <xref:System.IAsyncResult> 模式），这是使用 <xref:System.IAsyncResult> 接口提供异步行为的旧模型。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-114">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="8ea9d-115">在这种模式下，同步操作需要 `Begin` 和 `End` 方法（例如，`BeginWrite` 和 `EndWrite`以实现异步写入操作）。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-115">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="8ea9d-116">不建议新的开发使用此模式。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-116">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="8ea9d-117">有关详细信息，请参阅[异步编程模型 (APM)](asynchronous-programming-model-apm.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea9d-117">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="8ea9d-118">模式的比较</span><span class="sxs-lookup"><span data-stu-id="8ea9d-118">Comparison of patterns</span></span>

<span data-ttu-id="8ea9d-119">为了快速比较这三种模式的异步操作方式，请考虑使用从指定偏移量处起将指定量数据读取到提供的缓冲区中的`Read`方法：</span><span class="sxs-lookup"><span data-stu-id="8ea9d-119">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="8ea9d-120">此方法对应的 TAP 将公开以下单个 `ReadAsync` 方法：</span><span class="sxs-lookup"><span data-stu-id="8ea9d-120">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="8ea9d-121">对应的 EAP 将公开以下类型和成员的集：</span><span class="sxs-lookup"><span data-stu-id="8ea9d-121">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="8ea9d-122">对应的 APM 将公开 `BeginRead` 和 `EndRead` 方法：</span><span class="sxs-lookup"><span data-stu-id="8ea9d-122">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="8ea9d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ea9d-123">See also</span></span>

- [<span data-ttu-id="8ea9d-124">深入了解异步</span><span class="sxs-lookup"><span data-stu-id="8ea9d-124">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="8ea9d-125">C# 中的异步编程</span><span class="sxs-lookup"><span data-stu-id="8ea9d-125">Asynchronous programming in C#</span></span>](~/docs/csharp/async.md)
- [<span data-ttu-id="8ea9d-126">F# 中的异步编程</span><span class="sxs-lookup"><span data-stu-id="8ea9d-126">Async Programming in F#</span></span>](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="8ea9d-127">使用 Async 和 Await 的异步编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ea9d-127">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
