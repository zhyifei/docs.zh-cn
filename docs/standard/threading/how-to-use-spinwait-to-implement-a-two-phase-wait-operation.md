---
title: "如何：使用 SpinWait 实现两阶段等待操作"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="98aea-102">如何：使用 SpinWait 实现两阶段等待操作</span><span class="sxs-lookup"><span data-stu-id="98aea-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="98aea-103">下面的示例演示如何使用<xref:System.Threading.SpinWait?displayProperty=nameWithType>对象来实现两阶段等待操作。</span><span class="sxs-lookup"><span data-stu-id="98aea-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="98aea-104">在第一个阶段，同步对象， `Latch`，旋转几个周期，同时检查是否该锁变为可用。</span><span class="sxs-lookup"><span data-stu-id="98aea-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="98aea-105">在第二个阶段，如果该锁变为可用，则`Wait`方法返回时不使用<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>执行其等待; 否则为`Wait`执行等待。</span><span class="sxs-lookup"><span data-stu-id="98aea-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98aea-106">示例</span><span class="sxs-lookup"><span data-stu-id="98aea-106">Example</span></span>  
 <span data-ttu-id="98aea-107">此示例演示非常基本的实现的闩锁同步基元。</span><span class="sxs-lookup"><span data-stu-id="98aea-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="98aea-108">当等待时间预计很短，你可以使用此数据结构。</span><span class="sxs-lookup"><span data-stu-id="98aea-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="98aea-109">此示例是仅用于演示目的。</span><span class="sxs-lookup"><span data-stu-id="98aea-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="98aea-110">如果在程序中需要闩锁类型功能，请考虑使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="98aea-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="98aea-111">闩锁使用<xref:System.Threading.SpinWait>对象仅在下一个调用就地旋转`SpinOnce`导致<xref:System.Threading.SpinWait>以生成线程的时间片。</span><span class="sxs-lookup"><span data-stu-id="98aea-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="98aea-112">此时，闩锁将导致通过调用其自己的上下文切换<xref:System.Threading.WaitHandle.WaitOne%2A>上<xref:System.Threading.ManualResetEvent>并传递的超时值的其余部分中。</span><span class="sxs-lookup"><span data-stu-id="98aea-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="98aea-113">日志记录输出显示频率闩锁是能够提高性能，通过获取锁，而无需使用<xref:System.Threading.ManualResetEvent>。</span><span class="sxs-lookup"><span data-stu-id="98aea-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98aea-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98aea-114">See Also</span></span>  
 [<span data-ttu-id="98aea-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="98aea-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="98aea-116">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="98aea-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
