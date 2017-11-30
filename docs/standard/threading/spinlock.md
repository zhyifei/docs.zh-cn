---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a><span data-ttu-id="8e8f3-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="8e8f3-102">SpinLock</span></span>
<span data-ttu-id="8e8f3-103"><xref:System.Threading.SpinLock>结构是低级别、 互斥的同步基元，会旋转并同时等待获取锁。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="8e8f3-104">在多核计算机上，当等待时间预计较短且出现争用情况时最小，<xref:System.Threading.SpinLock>可以比其他类型的锁的更好地执行。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="8e8f3-105">但是，我们建议你使用<xref:System.Threading.SpinLock>仅当你确定通过分析时，才<xref:System.Threading.Monitor?displayProperty=nameWithType>方法或<xref:System.Threading.Interlocked>方法显著降低了你程序的性能。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="8e8f3-106"><xref:System.Threading.SpinLock>即使它已不获取锁，则可能会产生的线程的时间片。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="8e8f3-107">这一点，以避免线程优先级别反转，以及启用垃圾回收器来进行。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="8e8f3-108">当你使用<xref:System.Threading.SpinLock>，确保没有线程可以持有锁的多个非常短的时间跨度内，并且在它持有锁时，可以阻止任何线程。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="8e8f3-109">旋转锁是值类型，因为你必须显式将其传递由引用如果你想以引用同一个锁的两个副本。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="8e8f3-110">有关如何使用此类型的详细信息，请参阅<xref:System.Threading.SpinLock?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8e8f3-111">有关示例，请参阅[如何： 使用 SpinLock 进行低级别同步](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="8e8f3-112"><xref:System.Threading.SpinLock>支持*线程*-*跟踪*可以在开发阶段中使用，来帮助跟踪在特定时间持有锁的线程的模式。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="8e8f3-113">线程跟踪模式是非常有用的调试，但我们建议，你将其关闭程序的发行版中因为它可能会降低性能。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="8e8f3-114">有关详细信息，请参阅[如何： 在 SpinLock 中启用线程跟踪模式](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md)。</span><span class="sxs-lookup"><span data-stu-id="8e8f3-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8f3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e8f3-115">See Also</span></span>  
 [<span data-ttu-id="8e8f3-116">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="8e8f3-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
