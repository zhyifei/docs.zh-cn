---
title: "读取器/编写器锁"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="a5477-102">读取器/编写器锁</span><span class="sxs-lookup"><span data-stu-id="a5477-102">Reader-Writer Locks</span></span>
<span data-ttu-id="a5477-103"><xref:System.Threading.ReaderWriterLockSlim>类使多个线程能够同时读取的资源，但需要一个线程等待的排他锁，若要写入的资源。</span><span class="sxs-lookup"><span data-stu-id="a5477-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="a5477-104">你可以使用<xref:System.Threading.ReaderWriterLockSlim>中你的应用程序，以提供访问共享的资源的线程间的协作同步。</span><span class="sxs-lookup"><span data-stu-id="a5477-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="a5477-105">锁占用<xref:System.Threading.ReaderWriterLockSlim>本身。</span><span class="sxs-lookup"><span data-stu-id="a5477-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="a5477-106">因为任何线程的同步机制，你必须确保没有线程绕过提供的锁定<xref:System.Threading.ReaderWriterLockSlim>。</span><span class="sxs-lookup"><span data-stu-id="a5477-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="a5477-107">确保这一点的一种方法是设计一个封装共享的资源的类。</span><span class="sxs-lookup"><span data-stu-id="a5477-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="a5477-108">此类将提供访问私有共享的资源和使用私有成员<xref:System.Threading.ReaderWriterLockSlim>同步。</span><span class="sxs-lookup"><span data-stu-id="a5477-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="a5477-109">有关示例，请参阅的代码示例<xref:System.Threading.ReaderWriterLockSlim>类。</span><span class="sxs-lookup"><span data-stu-id="a5477-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="a5477-110"><xref:System.Threading.ReaderWriterLockSlim>是高效到可用于同步单个对象。</span><span class="sxs-lookup"><span data-stu-id="a5477-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="a5477-111">构建你的应用程序，以最小化的持续时间的读取和写入操作。</span><span class="sxs-lookup"><span data-stu-id="a5477-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="a5477-112">长时间的写入操作直接影响吞吐量，因为写入锁是排他。</span><span class="sxs-lookup"><span data-stu-id="a5477-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="a5477-113">长时间的读取操作块等待编写器，并且，如果至少一个线程在等待以进行写访问，将以及阻止请求读取访问权限的线程。</span><span class="sxs-lookup"><span data-stu-id="a5477-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5477-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]具有两个读取器 / 编写器锁，<xref:System.Threading.ReaderWriterLockSlim>和<xref:System.Threading.ReaderWriterLock>。</span><span class="sxs-lookup"><span data-stu-id="a5477-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="a5477-115"><xref:System.Threading.ReaderWriterLockSlim>建议对于所有新的开发。</span><span class="sxs-lookup"><span data-stu-id="a5477-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="a5477-116"><xref:System.Threading.ReaderWriterLockSlim>类似于<xref:System.Threading.ReaderWriterLock>，但它已简化为递归以及升级或降级锁定状态的规则。</span><span class="sxs-lookup"><span data-stu-id="a5477-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="a5477-117"><xref:System.Threading.ReaderWriterLockSlim>可避免潜在的死锁的很多情况。</span><span class="sxs-lookup"><span data-stu-id="a5477-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="a5477-118">此外的性能<xref:System.Threading.ReaderWriterLockSlim>明显优于<xref:System.Threading.ReaderWriterLock>。</span><span class="sxs-lookup"><span data-stu-id="a5477-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5477-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5477-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="a5477-120">线程处理</span><span class="sxs-lookup"><span data-stu-id="a5477-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="a5477-121">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="a5477-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
