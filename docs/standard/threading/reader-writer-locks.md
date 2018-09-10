---
title: 读取器/编写器锁
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275039"
---
# <a name="reader-writer-locks"></a><span data-ttu-id="358c1-102">读取器/编写器锁</span><span class="sxs-lookup"><span data-stu-id="358c1-102">Reader-Writer Locks</span></span>
<span data-ttu-id="358c1-103">借助 <xref:System.Threading.ReaderWriterLockSlim> 类，多个线程可以同时读取资源，但线程必须等待排他锁生成，才能对资源执行写入操作。</span><span class="sxs-lookup"><span data-stu-id="358c1-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="358c1-104">可以在应用中使用 <xref:System.Threading.ReaderWriterLockSlim>，以便在访问共享资源的线程之间进行协作同步。</span><span class="sxs-lookup"><span data-stu-id="358c1-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="358c1-105">锁应用于 <xref:System.Threading.ReaderWriterLockSlim> 本身。</span><span class="sxs-lookup"><span data-stu-id="358c1-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="358c1-106">与任何线程同步机制一样，必须确保没有线程规避 <xref:System.Threading.ReaderWriterLockSlim> 提供的锁定。</span><span class="sxs-lookup"><span data-stu-id="358c1-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="358c1-107">为了确保这一点，一种方法是设计一个类来封装共享资源。</span><span class="sxs-lookup"><span data-stu-id="358c1-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="358c1-108">此类的成员访问专用共享资源，并使用专用 <xref:System.Threading.ReaderWriterLockSlim> 执行同步。</span><span class="sxs-lookup"><span data-stu-id="358c1-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="358c1-109">有关示例，请参阅 <xref:System.Threading.ReaderWriterLockSlim> 类的代码示例。</span><span class="sxs-lookup"><span data-stu-id="358c1-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="358c1-110"><xref:System.Threading.ReaderWriterLockSlim> 非常高效，可用于同步各个对象。</span><span class="sxs-lookup"><span data-stu-id="358c1-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="358c1-111">请设计应用的结构，以最大限度地缩短读取和写入操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="358c1-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="358c1-112">长时间的写入操作会直接影响吞吐量，因为写锁是独占锁。</span><span class="sxs-lookup"><span data-stu-id="358c1-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="358c1-113">长时间的读取操作会阻止正在等待的编写器，并且如果至少有一个线程在等待写入访问，请求读取访问的线程也会受阻止。</span><span class="sxs-lookup"><span data-stu-id="358c1-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="358c1-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 有下面两个读取器-编写器锁：<xref:System.Threading.ReaderWriterLockSlim> 和 <xref:System.Threading.ReaderWriterLock>。</span><span class="sxs-lookup"><span data-stu-id="358c1-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="358c1-115">建议对所有新开发的项目使用 <xref:System.Threading.ReaderWriterLockSlim>。</span><span class="sxs-lookup"><span data-stu-id="358c1-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="358c1-116">虽然 <xref:System.Threading.ReaderWriterLockSlim> 类似于 <xref:System.Threading.ReaderWriterLock>，但不同之处在于，前者简化了递归规则以及锁状态的升级和降级规则。</span><span class="sxs-lookup"><span data-stu-id="358c1-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="358c1-117"><xref:System.Threading.ReaderWriterLockSlim> 避免了许多潜在的死锁情况。</span><span class="sxs-lookup"><span data-stu-id="358c1-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="358c1-118">另外，<xref:System.Threading.ReaderWriterLockSlim> 的性能显著优于 <xref:System.Threading.ReaderWriterLock>。</span><span class="sxs-lookup"><span data-stu-id="358c1-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358c1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="358c1-119">See also</span></span>

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [<span data-ttu-id="358c1-120">线程处理</span><span class="sxs-lookup"><span data-stu-id="358c1-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="358c1-121">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="358c1-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
