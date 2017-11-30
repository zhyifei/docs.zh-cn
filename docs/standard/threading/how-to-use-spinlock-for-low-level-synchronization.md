---
title: "如何：使用 SpinLock 进行低级别同步"
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="4e706-102">如何：使用 SpinLock 进行低级别同步</span><span class="sxs-lookup"><span data-stu-id="4e706-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="4e706-103">下面的示例演示如何使用<xref:System.Threading.SpinLock>。</span><span class="sxs-lookup"><span data-stu-id="4e706-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e706-104">示例</span><span class="sxs-lookup"><span data-stu-id="4e706-104">Example</span></span>  
 <span data-ttu-id="4e706-105">在此示例中，关键部分执行最少量的工作，则会使的良好候选<xref:System.Threading.SpinLock>。</span><span class="sxs-lookup"><span data-stu-id="4e706-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="4e706-106">增加工作一小部分会增加的性能<xref:System.Threading.SpinLock>相比标准锁。</span><span class="sxs-lookup"><span data-stu-id="4e706-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="4e706-107">但是，超过某个点时 SpinLock 将比标准锁开销更大。</span><span class="sxs-lookup"><span data-stu-id="4e706-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="4e706-108">可以使用分析工具中的并发分析功能，查看哪种类型的锁可以在程序中提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="4e706-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="4e706-109">有关详细信息，请参阅[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)。</span><span class="sxs-lookup"><span data-stu-id="4e706-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="4e706-110"><xref:System.Threading.SpinLock>可能会很有用，当共享资源的锁不要保留时间很长。</span><span class="sxs-lookup"><span data-stu-id="4e706-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="4e706-111">在这种情况下，多核计算机上的阻止线程可高效旋转几个周期，直到锁被释放。</span><span class="sxs-lookup"><span data-stu-id="4e706-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="4e706-112">通过旋转，线程不会受到阻止，这是一个占用大量 CPU 资源的进程。</span><span class="sxs-lookup"><span data-stu-id="4e706-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="4e706-113"><xref:System.Threading.SpinLock>将会停止在某些条件且要阻止的逻辑处理器或优先级数据倒排在具有超线程系统上的资源不足的旋转。</span><span class="sxs-lookup"><span data-stu-id="4e706-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="4e706-114">此示例使用<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>类，这就需要为多线程访问的用户同步。</span><span class="sxs-lookup"><span data-stu-id="4e706-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="4e706-115">在面向.NET Framework 版本 4 的应用程序，另一个选项是使用<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>，从而无需任何用户锁。</span><span class="sxs-lookup"><span data-stu-id="4e706-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="4e706-116">请注意，使用`false`(`False`在 Visual Basic 中) 的调用中<xref:System.Threading.SpinLock.Exit%2A>。</span><span class="sxs-lookup"><span data-stu-id="4e706-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="4e706-117">这可提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="4e706-117">This provides the best performance.</span></span> <span data-ttu-id="4e706-118">在 IA64 架构上指定 `true` (`True`) 可使用内存界定，这会刷新写入缓冲区以确保锁现在可供其他线程退出。</span><span class="sxs-lookup"><span data-stu-id="4e706-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e706-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e706-119">See Also</span></span>  
 [<span data-ttu-id="4e706-120">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="4e706-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
