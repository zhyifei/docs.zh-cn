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
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a><span data-ttu-id="bc1fc-102">互锁操作</span><span class="sxs-lookup"><span data-stu-id="bc1fc-102">Interlocked Operations</span></span>
<span data-ttu-id="bc1fc-103"><xref:System.Threading.Interlocked>类提供同步访问多个线程共享的变量的方法。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-103">The <xref:System.Threading.Interlocked> class provides methods that synchronize access to a variable that is shared by multiple threads.</span></span> <span data-ttu-id="bc1fc-104">如果该变量位于共享内存中，则不同进程的线程都可以使用此机制。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-104">The threads of different processes can use this mechanism if the variable is in shared memory.</span></span> <span data-ttu-id="bc1fc-105">互锁操作是原子的 - 即整个操作是不能由相同变量上的另一个互锁操作中断的单元。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-105">Interlocked operations are atomic — that is, the entire operation is a unit that cannot be interrupted by another interlocked operation on the same variable.</span></span> <span data-ttu-id="bc1fc-106">这在抢占式多线程处理操作系统中非常重要，在此类操作系统中，可在从内存地址加载值之后但有机会更改和存储该值之前将线程挂起。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-106">This is important in operating systems with preemptive multithreading, where a thread can be suspended after loading a value from a memory address, but before having the chance to alter it and store it.</span></span>  
  
 <span data-ttu-id="bc1fc-107"><xref:System.Threading.Interlocked>类提供了以下操作：</span><span class="sxs-lookup"><span data-stu-id="bc1fc-107">The <xref:System.Threading.Interlocked> class provides the following operations:</span></span>  
  
-   <span data-ttu-id="bc1fc-108">在.NET Framework 2.0 版中，<xref:System.Threading.Interlocked.Add%2A>方法将一个整数值添加到一个变量并返回该变量的新值。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-108">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Add%2A> method adds an integer value to a variable and returns the new value of the variable.</span></span>  
  
-   <span data-ttu-id="bc1fc-109">在.NET Framework 2.0 版中，<xref:System.Threading.Interlocked.Read%2A>方法读取一个 64 位整数值作为原子操作。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-109">In the .NET Framework version 2.0, the <xref:System.Threading.Interlocked.Read%2A> method reads a 64-bit integer value as an atomic operation.</span></span> <span data-ttu-id="bc1fc-110">这在 32 位操作系统上很有用，在此类操作系统上，读取一个 64 位整数通常不是原子操作。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-110">This is useful on 32-bit operating systems, where reading a 64-bit integer is not ordinarily an atomic operation.</span></span>  
  
-   <span data-ttu-id="bc1fc-111"><xref:System.Threading.Interlocked.Increment%2A>和<xref:System.Threading.Interlocked.Decrement%2A>方法递增或递减的变量并返回的结果值。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-111">The <xref:System.Threading.Interlocked.Increment%2A> and <xref:System.Threading.Interlocked.Decrement%2A> methods increment or decrement a variable and return the resulting value.</span></span>  
  
-   <span data-ttu-id="bc1fc-112"><xref:System.Threading.Interlocked.Exchange%2A>方法在指定变量中，返回该值并将它替换为新值执行原子交换的值。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-112">The <xref:System.Threading.Interlocked.Exchange%2A> method performs an atomic exchange of the value in a specified variable, returning that value and replacing it with a new value.</span></span> <span data-ttu-id="bc1fc-113">在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-113">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="bc1fc-114">请参阅<xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-114">See <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.</span></span>  
  
-   <span data-ttu-id="bc1fc-115"><xref:System.Threading.Interlocked.CompareExchange%2A>方法还交换两个值，但取决于比较的结果。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-115">The <xref:System.Threading.Interlocked.CompareExchange%2A> method also exchanges two values, but contingent on the result of a comparison.</span></span> <span data-ttu-id="bc1fc-116">在 .NET Framework 2.0 版中，可使用此方法的泛型重载在任何引用类型的变量上执行此交换。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-116">In the .NET Framework version 2.0, a generic overload of this method can be used to perform this exchange on a variable of any reference type.</span></span> <span data-ttu-id="bc1fc-117">请参阅<xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-117">See <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.</span></span>  
  
 <span data-ttu-id="bc1fc-118">在现代处理器中的方法<xref:System.Threading.Interlocked>类通常可以通过一条指令。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-118">On modern processors, the methods of the <xref:System.Threading.Interlocked> class can often be implemented by a single instruction.</span></span> <span data-ttu-id="bc1fc-119">因此，它们提供性能非常高的同步，并且可用于生成更高级的同步机制，例如自旋锁。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-119">Thus, they provide very high-performance synchronization and can be used to build higher-level synchronization mechanisms, like spin locks.</span></span>  
  
 <span data-ttu-id="bc1fc-120">有关示例，使用<xref:System.Threading.Monitor>和<xref:System.Threading.Interlocked>类结合使用，请参阅[监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-120">For an example that uses the <xref:System.Threading.Monitor> and <xref:System.Threading.Interlocked> classes in combination, see [Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="compareexchange-example"></a><span data-ttu-id="bc1fc-121">CompareExchange示例</span><span class="sxs-lookup"><span data-stu-id="bc1fc-121">CompareExchange Example</span></span>  
 <span data-ttu-id="bc1fc-122"><xref:System.Threading.Interlocked.CompareExchange%2A>方法可以用于保护比简单递增和递减更复杂的计算。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-122">The <xref:System.Threading.Interlocked.CompareExchange%2A> method can be used to protect computations that are more complicated than simple increment and decrement.</span></span> <span data-ttu-id="bc1fc-123">以下示例演示一个线程安全的方法，该方法向存储为浮点数的累计值执行加运算。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-123">The following example demonstrates a thread-safe method that adds to a running total stored as a floating point number.</span></span> <span data-ttu-id="bc1fc-124">(为整数，<xref:System.Threading.Interlocked.Add%2A>方法是更简单的解决方案。)有关完整的代码示例，请参阅的重载<xref:System.Threading.Interlocked.CompareExchange%2A>它们采用单精度和双精度浮点自变量 (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29>和<xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>)。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-124">(For integers, the <xref:System.Threading.Interlocked.Add%2A> method is a simpler solution.) For complete code examples, see the overloads of <xref:System.Threading.Interlocked.CompareExchange%2A> that take single-precision and double-precision floating-point arguments (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> and <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a><span data-ttu-id="bc1fc-125">Exchange 和 CompareExchange 的非类型化重载</span><span class="sxs-lookup"><span data-stu-id="bc1fc-125">Untyped Overloads of Exchange and CompareExchange</span></span>  
 <span data-ttu-id="bc1fc-126"><xref:System.Threading.Interlocked.Exchange%2A>和<xref:System.Threading.Interlocked.CompareExchange%2A>方法具有采用的类型自变量的重载<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-126">The <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods have overloads that take arguments of type <xref:System.Object>.</span></span> <span data-ttu-id="bc1fc-127">这些重载的第一个参数是`ref Object`(`ByRef … As Object`在 Visual Basic 中)，和类型安全要求传递给此参数以严格类型化为变量<xref:System.Object>; 只需不能强制转换为类型的第一个参数<xref:System.Object>调用这些方法时。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-127">The first argument of each of these overloads is `ref Object` (`ByRef … As Object` in Visual Basic), and type safety requires the variable passed to this argument to be typed strictly as <xref:System.Object>; you cannot simply cast the first argument to type <xref:System.Object> when calling these methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc1fc-128">在.NET Framework 2.0 版中，使用的泛型重载<xref:System.Threading.Interlocked.Exchange%2A>和<xref:System.Threading.Interlocked.CompareExchange%2A>方法来交换强类型化变量。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-128">In the .NET Framework version 2.0, use the generic overloads of the <xref:System.Threading.Interlocked.Exchange%2A> and <xref:System.Threading.Interlocked.CompareExchange%2A> methods to exchange strongly typed variables.</span></span>  
  
 <span data-ttu-id="bc1fc-129">以下代码示例演示只能设置一次的 `ClassA` 类型的属性，正如它在 .NET Framework 1.0 或 1.1 版中实现的那样。</span><span class="sxs-lookup"><span data-stu-id="bc1fc-129">The following code example shows a property of type `ClassA` that can be set only once, as it might be implemented in the .NET Framework version 1.0 or 1.1.</span></span>  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bc1fc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc1fc-130">See Also</span></span>  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="bc1fc-131">线程处理</span><span class="sxs-lookup"><span data-stu-id="bc1fc-131">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="bc1fc-132">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="bc1fc-132">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
