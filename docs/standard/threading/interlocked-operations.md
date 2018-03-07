---
title: "互锁操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c10c1188820b7a270baa0c51696974f93a8a2990
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="interlocked-operations"></a><span data-ttu-id="acc6c-102">互锁操作</span><span class="sxs-lookup"><span data-stu-id="acc6c-102">Interlocked Operations</span></span>
<span data-ttu-id="acc6c-103"><xref:System.Threading.Interlocked> 类中的方法可用于同步对多个线程共享的变量的访问。</span><span class="sxs-lookup"><span data-stu-id="acc6c-103">The <xref:System.Threading.Interlocked> class provides methods that synchronize access to a variable that is shared by multiple threads.</span></span> <span data-ttu-id="acc6c-104">如果该变量位于共享内存中，则不同进程的线程都可以使用此机制。</span><span class="sxs-lookup"><span data-stu-id="acc6c-104">The threads of different processes can use this mechanism if the variable is in shared memory.</span></span> <span data-ttu-id="acc6c-105">互锁操作是原子的 - 即整个操作是不能由相同变量上的另一个互锁操作中断的单元。</span><span class="sxs-lookup"><span data-stu-id="acc6c-105">Interlocked operations are atomic — that is, the entire operation is a unit that cannot be interrupted by another interlocked operation on the same variable.</span></span> <span data-ttu-id="acc6c-106">这在抢占式多线程处理操作系统中非常重要，在此类操作系统中，可在从内存地址加载值之后但有机会更改和存储该值之前将线程挂起。</span><span class="sxs-lookup"><span data-stu-id="acc6c-106">This is important in operating systems with preemptive multithreading, where a thread can be suspended after loading a value from a memory address, but before having the chance to alter it and store it.</span></span>  
  
 <span data-ttu-id="acc6c-107"><xref:System.Threading.Interlocked> 类提供以下操作：</span><span class="sxs-lookup"><span data-stu-id="acc6c-107">The <xref:System.Threading.Interlocked> class provides the following operations:</span></span>  
  
-   <span data-ttu-id="acc6c-108">在 .NET Framework 版本 2.0 中，<xref:System.Threading.Interlocked.Add%2A> 方法向变量添加整数值，并返回此变量的新值。</span><span class="sxs-lookup"><span data-stu-id="acc6c-108">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Add%2A> method adds an integer value to a variable and returns the new value of the variable.</span></span>  
  
-   <span data-ttu-id="acc6c-109">在 .NET Framework 版本 2.0 中，<xref:System.Threading.Interlocked.Read%2A> 方法以原子操作的形式读取 64 位整数值。</span><span class="sxs-lookup"><span data-stu-id="acc6c-109">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Read%2A> method reads a 64-bit integer value as an atomic operation.</span></span> <span data-ttu-id="acc6c-110">这在 32 位操作系统上很有用，在此类操作系统上，读取一个 64 位整数通常不是原子操作。</span><span class="sxs-lookup"><span data-stu-id="acc6c-110">This is useful on 32-bit operating systems, where reading a 64-bit integer is not ordinarily an atomic operation.</span></span>  
  
-   <span data-ttu-id="acc6c-111"><xref:System.Threading.Interlocked.Increment%2A> 和 <xref:System.Threading.Interlocked.Decrement%2A> 方法递增或递减变量，并返回生成值。</span><span class="sxs-lookup"><span data-stu-id="acc6c-111">The <xref:System.Threading.Interlocked.Increment%2A> and <xref:System.Threading.Interlocked.Decrement%2A> methods increment or decrement a variable and return the resulting value.</span></span>  
  
-   <span data-ttu-id="acc6c-112"><xref:System.Threading.Interlocked.Exchange%2A> 方法在指定变量中以原子操作的形式交换值，同时返回此值并将它替换为新值。</span><span class="sxs-lookup"><span data-stu-id="acc6c-112">The <xref:System.Threading.Interlocked.Exchange%2A> method performs an atomic exchange of the value in a specified variable, returning that value and replacing it with a new value.</span></span> <span data-ttu-id="acc6c-113">在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="acc6c-113">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="acc6c-114">请参阅 <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>。</span><span class="sxs-lookup"><span data-stu-id="acc6c-114">See <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.</span></span>  
  
-   <span data-ttu-id="acc6c-115"><xref:System.Threading.Interlocked.CompareExchange%2A> 方法也交换两个值，但具体视比较结果而定。</span><span class="sxs-lookup"><span data-stu-id="acc6c-115">The <xref:System.Threading.Interlocked.CompareExchange%2A> method also exchanges two values, but contingent on the result of a comparison.</span></span> <span data-ttu-id="acc6c-116">在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="acc6c-116">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="acc6c-117">请参阅 <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>。</span><span class="sxs-lookup"><span data-stu-id="acc6c-117">See <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.</span></span>  
  
 <span data-ttu-id="acc6c-118">在新式处理器中，通常使用一个指令即可实现 <xref:System.Threading.Interlocked> 类的方法。</span><span class="sxs-lookup"><span data-stu-id="acc6c-118">On modern processors, the methods of the <xref:System.Threading.Interlocked> class can often be implemented by a single instruction.</span></span> <span data-ttu-id="acc6c-119">因此，它们提供性能非常高的同步，并且可用于生成更高级的同步机制，例如自旋锁。</span><span class="sxs-lookup"><span data-stu-id="acc6c-119">Thus, they provide very high-performance synchronization and can be used to build higher-level synchronization mechanisms, like spin locks.</span></span>  
  
 <span data-ttu-id="acc6c-120">有关组合使用 <xref:System.Threading.Monitor> 和 <xref:System.Threading.Interlocked> 类的示例，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。</span><span class="sxs-lookup"><span data-stu-id="acc6c-120">For an example that uses the <xref:System.Threading.Monitor> and <xref:System.Threading.Interlocked> classes in combination, see [Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="compareexchange-example"></a><span data-ttu-id="acc6c-121">CompareExchange示例</span><span class="sxs-lookup"><span data-stu-id="acc6c-121">CompareExchange Example</span></span>  
 <span data-ttu-id="acc6c-122"><xref:System.Threading.Interlocked.CompareExchange%2A> 方法可用于保护比简单的递增和递减更为复杂的计算。</span><span class="sxs-lookup"><span data-stu-id="acc6c-122">The <xref:System.Threading.Interlocked.CompareExchange%2A> method can be used to protect computations that are more complicated than simple increment and decrement.</span></span> <span data-ttu-id="acc6c-123">以下示例演示一个线程安全的方法，该方法向存储为浮点数的累计值执行加运算。</span><span class="sxs-lookup"><span data-stu-id="acc6c-123">The following example demonstrates a thread-safe method that adds to a running total stored as a floating point number.</span></span> <span data-ttu-id="acc6c-124">（对于整数，<xref:System.Threading.Interlocked.Add%2A> 方法是更简单的解决方案。）有关完整的代码示例，请参阅需要使用单精度和双精度浮点参数的 <xref:System.Threading.Interlocked.CompareExchange%2A> 重载（<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> 和 <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>）。</span><span class="sxs-lookup"><span data-stu-id="acc6c-124">(For integers, the <xref:System.Threading.Interlocked.Add%2A> method is a simpler solution.) For complete code examples, see the overloads of <xref:System.Threading.Interlocked.CompareExchange%2A> that take single-precision and double-precision floating-point arguments (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> and <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a><span data-ttu-id="acc6c-125">Exchange 和 CompareExchange 的非类型化重载</span><span class="sxs-lookup"><span data-stu-id="acc6c-125">Untyped Overloads of Exchange and CompareExchange</span></span>  
 <span data-ttu-id="acc6c-126"><xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法包含需要使用 <xref:System.Object> 类型参数的重载。</span><span class="sxs-lookup"><span data-stu-id="acc6c-126">The <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods have overloads that take arguments of type <xref:System.Object>.</span></span> <span data-ttu-id="acc6c-127">其中每个重载的第一个参数都是 `ref Object`（Visual Basic 中的 `ByRef … As Object`），根据类型安全性要求，必须将传递给此参数的变量严格类型化为 <xref:System.Object>；不能在调用这些方法时，直接将第一个参数强制转换为 <xref:System.Object> 类型。</span><span class="sxs-lookup"><span data-stu-id="acc6c-127">The first argument of each of these overloads is `ref Object` (`ByRef … As Object` in Visual Basic), and type safety requires the variable passed to this argument to be typed strictly as <xref:System.Object>; you cannot simply cast the first argument to type <xref:System.Object> when calling these methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acc6c-128">在 .NET Framework 版本 2.0 中，使用 <xref:System.Threading.Interlocked.Exchange%2A> 和 <xref:System.Threading.Interlocked.CompareExchange%2A> 方法的泛型重载来交换强类型变量。</span><span class="sxs-lookup"><span data-stu-id="acc6c-128">In the .NET Framework version 2.0, use the generic overloads of the <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods to exchange strongly typed variables.</span></span>  
  
 <span data-ttu-id="acc6c-129">以下代码示例演示只能设置一次的 `ClassA` 类型的属性，正如它在 .NET Framework 1.0 或 1.1 版中实现的那样。</span><span class="sxs-lookup"><span data-stu-id="acc6c-129">The following code example shows a property of type `ClassA` that can be set only once, as it might be implemented in the .NET Framework version 1.0 or 1.1.</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="acc6c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="acc6c-130">See Also</span></span>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="acc6c-131">线程处理</span><span class="sxs-lookup"><span data-stu-id="acc6c-131">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="acc6c-132">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="acc6c-132">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
