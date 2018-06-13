---
title: 如何：使用 SpinLock 进行低级别同步
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7795b25ca8e9337a53fc67ebc6f56130237d0764
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582751"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="b43a3-102">如何：使用 SpinLock 进行低级别同步</span><span class="sxs-lookup"><span data-stu-id="b43a3-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="b43a3-103">下面的示例展示了如何使用 <xref:System.Threading.SpinLock>。</span><span class="sxs-lookup"><span data-stu-id="b43a3-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b43a3-104">示例</span><span class="sxs-lookup"><span data-stu-id="b43a3-104">Example</span></span>  
 <span data-ttu-id="b43a3-105">在此示例中，关键部分执行的工作量最少，因而非常适合执行 <xref:System.Threading.SpinLock>。</span><span class="sxs-lookup"><span data-stu-id="b43a3-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="b43a3-106">与标准锁相比，增加一点工作量即可提升 <xref:System.Threading.SpinLock> 的性能。</span><span class="sxs-lookup"><span data-stu-id="b43a3-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="b43a3-107">但是，超过某个点时 SpinLock 将比标准锁开销更大。</span><span class="sxs-lookup"><span data-stu-id="b43a3-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="b43a3-108">可以使用分析工具中的并发分析功能，查看哪种类型的锁可以在程序中提供更好的性能。</span><span class="sxs-lookup"><span data-stu-id="b43a3-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="b43a3-109">有关详细信息，请参阅[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)。</span><span class="sxs-lookup"><span data-stu-id="b43a3-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="b43a3-110">如果共享资源上的锁不会保留太长时间，<xref:System.Threading.SpinLock> 可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="b43a3-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="b43a3-111">在这种情况下，多核计算机上的阻止线程可高效旋转几个周期，直到锁被释放。</span><span class="sxs-lookup"><span data-stu-id="b43a3-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="b43a3-112">通过旋转，线程不会受到阻止，这是一个占用大量 CPU 资源的进程。</span><span class="sxs-lookup"><span data-stu-id="b43a3-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="b43a3-113">在某些情况下，<xref:System.Threading.SpinLock> 会停止旋转，以防出现逻辑处理器资源不足或超线程系统上优先级反转的情况。</span><span class="sxs-lookup"><span data-stu-id="b43a3-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="b43a3-114">此示例使用 <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> 类，要求必须有用户同步，才能执行多线程访问。</span><span class="sxs-lookup"><span data-stu-id="b43a3-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="b43a3-115">在定目标到 .NET Framework 版本 4 的应用中，另一种选择是使用不需要任何用户锁的 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b43a3-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="b43a3-116">请注意，在 <xref:System.Threading.SpinLock.Exit%2A> 调用中使用 `false`（Visual Basic 中的 `False`）。</span><span class="sxs-lookup"><span data-stu-id="b43a3-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="b43a3-117">这可提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b43a3-117">This provides the best performance.</span></span> <span data-ttu-id="b43a3-118">在 IA64 架构上指定 `true` (`True`) 可使用内存界定，这会刷新写入缓冲区以确保锁现在可供其他线程退出。</span><span class="sxs-lookup"><span data-stu-id="b43a3-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43a3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b43a3-119">See Also</span></span>  
 [<span data-ttu-id="b43a3-120">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="b43a3-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
