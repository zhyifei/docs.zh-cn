---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a><span data-ttu-id="d43c1-102">SpinWait</span><span class="sxs-lookup"><span data-stu-id="d43c1-102">SpinWait</span></span>
<span data-ttu-id="d43c1-103"><xref:System.Threading.SpinWait?displayProperty=nameWithType>是可以在低级别方案中使用，以避免昂贵的上下文切换和内核转换所需的内核事件的轻量同步类型。</span><span class="sxs-lookup"><span data-stu-id="d43c1-103"><xref:System.Threading.SpinWait?displayProperty=nameWithType> is a lightweight synchronization type that you can use in low-level scenarios to avoid the expensive context switches and kernel transitions that are required for kernel events.</span></span> <span data-ttu-id="d43c1-104">在多核计算机上时资源不需要容纳较长时间，它可以是时间的正在等待的线程几个装入数十或几个几百个周期，在用户模式下启动，然后重试获取该资源对于更加高效。</span><span class="sxs-lookup"><span data-stu-id="d43c1-104">On multicore computers, when a resource is not expected to be held for long periods of time, it can be more efficient for a waiting thread to spin in user mode for a few dozen or a few hundred cycles, and then retry to acquire the resource.</span></span> <span data-ttu-id="d43c1-105">如果资源在旋转后变为可用，则可以节省数千个周期。</span><span class="sxs-lookup"><span data-stu-id="d43c1-105">If the resource is available after spinning, then you have saved several thousand cycles.</span></span> <span data-ttu-id="d43c1-106">如果资源是仍不可用，然后你所用仅几个周期，并仍然可以输入基于内核的等待。</span><span class="sxs-lookup"><span data-stu-id="d43c1-106">If the resource is still not available, then you have spent only a few cycles and can still enter a kernel-based wait.</span></span> <span data-ttu-id="d43c1-107">此旋转然后等待组合有时称为*两阶段等待操作*。</span><span class="sxs-lookup"><span data-stu-id="d43c1-107">This spinning-then-waiting combination is sometimes referred to as a *two-phase wait operation*.</span></span>  
  
 <span data-ttu-id="d43c1-108"><xref:System.Threading.SpinWait>旨在与.NET Framework 类型，如简单包装内核事件结合使用<xref:System.Threading.ManualResetEvent>。</span><span class="sxs-lookup"><span data-stu-id="d43c1-108"><xref:System.Threading.SpinWait> is designed to be used in conjunction with the .NET Framework types that wrap kernel events such as <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="d43c1-109"><xref:System.Threading.SpinWait>此外可通过本身只在一个程序中的基本旋转功能。</span><span class="sxs-lookup"><span data-stu-id="d43c1-109"><xref:System.Threading.SpinWait> can also be used by itself for basic spinning functionality in just one program.</span></span>  
  
 <span data-ttu-id="d43c1-110"><xref:System.Threading.SpinWait>远不止一个空的循环。</span><span class="sxs-lookup"><span data-stu-id="d43c1-110"><xref:System.Threading.SpinWait> is more than just an empty loop.</span></span> <span data-ttu-id="d43c1-111">仔细实现以提供的一般情况下，正确的旋转行为，而且会本身执行上下文切换在旋转足够长的时间 （大约内核转换所需的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="d43c1-111">It is carefully implemented to provide correct spinning behavior for the general case, and will itself initiate context switches if it spins long enough (roughly the length of time required for a kernel transition).</span></span> <span data-ttu-id="d43c1-112">例如，在单核计算机<xref:System.Threading.SpinWait>产生线程的时间片立即因为旋转块转发所有线程上的进度。</span><span class="sxs-lookup"><span data-stu-id="d43c1-112">For example, on single-core computers, <xref:System.Threading.SpinWait> yields the time slice of the thread immediately because spinning blocks forward progress on all threads.</span></span> <span data-ttu-id="d43c1-113"><xref:System.Threading.SpinWait>此外会产生甚至在多核计算机，以防止阻止更高优先级的线程或垃圾回收器正在等待的线程上。</span><span class="sxs-lookup"><span data-stu-id="d43c1-113"><xref:System.Threading.SpinWait> also yields even on multi-core machines to prevent the waiting thread from blocking higher-priority threads or the garbage collector.</span></span> <span data-ttu-id="d43c1-114">因此，如果你使用<xref:System.Threading.SpinWait>在两阶段等待操作中，我们建议调用之前在内核等待<xref:System.Threading.SpinWait>本身启动的上下文切换。</span><span class="sxs-lookup"><span data-stu-id="d43c1-114">Therefore, if you are using a <xref:System.Threading.SpinWait> in a two-phase wait operation, we recommend that you invoke the kernel wait before the <xref:System.Threading.SpinWait> itself initiates a context switch.</span></span> <span data-ttu-id="d43c1-115"><xref:System.Threading.SpinWait>提供<xref:System.Threading.SpinWait.NextSpinWillYield%2A>属性，可以在每次调用之前检查<xref:System.Threading.SpinWait.SpinOnce%2A>。</span><span class="sxs-lookup"><span data-stu-id="d43c1-115"><xref:System.Threading.SpinWait> provides the <xref:System.Threading.SpinWait.NextSpinWillYield%2A> property, which you can check before every call to <xref:System.Threading.SpinWait.SpinOnce%2A>.</span></span> <span data-ttu-id="d43c1-116">当该属性返回`true`，启动你自己的等待操作。</span><span class="sxs-lookup"><span data-stu-id="d43c1-116">When the property returns `true`, initiate your own Wait operation.</span></span> <span data-ttu-id="d43c1-117">有关示例，请参阅[如何： 使用 SpinWait 实现两阶段等待操作](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="d43c1-117">For an example, see [How to: Use SpinWait to Implement a Two-Phase Wait Operation](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).</span></span>  
  
 <span data-ttu-id="d43c1-118">如果你不执行两阶段等待操作，但只旋转直到某些条件为 true，则可以启用<xref:System.Threading.SpinWait>执行其上下文切换，以便它是在 Windows 操作系统环境中的一个好公民。</span><span class="sxs-lookup"><span data-stu-id="d43c1-118">If you are not performing a two-phase wait operation but are just spinning until some condition is true, you can enable <xref:System.Threading.SpinWait> to perform its context switches so that it is a good citizen in the Windows operating system environment.</span></span> <span data-ttu-id="d43c1-119">下面的基本示例演示<xref:System.Threading.SpinWait>无锁堆栈中。</span><span class="sxs-lookup"><span data-stu-id="d43c1-119">The following basic example shows a <xref:System.Threading.SpinWait> in a lock-free stack.</span></span> <span data-ttu-id="d43c1-120">如果你需要高性能、 线程安全的堆栈，请考虑使用<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d43c1-120">If you require a high-performance, thread-safe stack, consider using <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a><span data-ttu-id="d43c1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d43c1-121">See Also</span></span>  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [<span data-ttu-id="d43c1-122">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="d43c1-122">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
