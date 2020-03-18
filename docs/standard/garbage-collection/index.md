---
title: 垃圾回收
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 846df5ecb1e681e8d0440e627586a681bf071efa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160139"
---
# <a name="garbage-collection"></a><span data-ttu-id="abc2a-102">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="abc2a-102">Garbage Collection</span></span>
<span data-ttu-id="abc2a-103">.NET 的垃圾回收器管理应用程序的内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="abc2a-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="abc2a-104">每当有对象新建时，公共语言运行时都会从托管堆为对象分配内存。</span><span class="sxs-lookup"><span data-stu-id="abc2a-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="abc2a-105">只要托管堆中有地址空间，运行时就会继续为新对象分配空间。</span><span class="sxs-lookup"><span data-stu-id="abc2a-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="abc2a-106">不过，内存并不是无限的。</span><span class="sxs-lookup"><span data-stu-id="abc2a-106">However, memory is not infinite.</span></span> <span data-ttu-id="abc2a-107">垃圾回收器最终必须执行垃圾回收来释放一些内存。</span><span class="sxs-lookup"><span data-stu-id="abc2a-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="abc2a-108">垃圾回收器的优化引擎会根据所执行的分配来确定执行回收的最佳时机。</span><span class="sxs-lookup"><span data-stu-id="abc2a-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="abc2a-109">执行回收时，垃圾回收器会在托管堆中检查应用程序不再使用的对象，然后执行必要的操作来回收其内存。</span><span class="sxs-lookup"><span data-stu-id="abc2a-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="abc2a-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="abc2a-110">Related Topics</span></span>  
  
|<span data-ttu-id="abc2a-111">标题</span><span class="sxs-lookup"><span data-stu-id="abc2a-111">Title</span></span>|<span data-ttu-id="abc2a-112">说明</span><span class="sxs-lookup"><span data-stu-id="abc2a-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="abc2a-113">垃圾回收的基础知识</span><span class="sxs-lookup"><span data-stu-id="abc2a-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="abc2a-114">描述垃圾回收的工作原理、如何在托管堆上分配对象，以及其他核心概念。</span><span class="sxs-lookup"><span data-stu-id="abc2a-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="abc2a-115">垃圾回收和性能</span><span class="sxs-lookup"><span data-stu-id="abc2a-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="abc2a-116">介绍了可用来诊断垃圾回收和性能问题的性能检查。</span><span class="sxs-lookup"><span data-stu-id="abc2a-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="abc2a-117">已引发回收</span><span class="sxs-lookup"><span data-stu-id="abc2a-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="abc2a-118">描述如何完成垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="abc2a-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="abc2a-119">延迟模式</span><span class="sxs-lookup"><span data-stu-id="abc2a-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="abc2a-120">描述确定垃圾回收侵入性的模式。</span><span class="sxs-lookup"><span data-stu-id="abc2a-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="abc2a-121">针对共享 Web 托管进行优化</span><span class="sxs-lookup"><span data-stu-id="abc2a-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="abc2a-122">介绍了如何在多个小网站共用的服务器上优化垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="abc2a-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="abc2a-123">垃圾回收通知</span><span class="sxs-lookup"><span data-stu-id="abc2a-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="abc2a-124">介绍了如何确定全面垃圾回收的开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="abc2a-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="abc2a-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="abc2a-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="abc2a-126">介绍了如何监视应用程序域的 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="abc2a-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="abc2a-127">弱引用</span><span class="sxs-lookup"><span data-stu-id="abc2a-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="abc2a-128">描述允许应用程序访问对象的同时也允许垃圾回收器收集相应对象的功能。</span><span class="sxs-lookup"><span data-stu-id="abc2a-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="abc2a-129">引用</span><span class="sxs-lookup"><span data-stu-id="abc2a-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="abc2a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abc2a-130">See also</span></span>

- <span data-ttu-id="abc2a-131">[清理未托管资源](../../../docs/standard/garbage-collection/unmanaged.md)（清理未托管资源）</span><span class="sxs-lookup"><span data-stu-id="abc2a-131">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)</span></span>
