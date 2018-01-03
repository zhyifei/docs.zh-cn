---
title: "垃圾回收"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "36"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c8288473b25b3f3cd75666e1da0611dec37c3127
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="garbage-collection"></a><span data-ttu-id="03e81-102">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="03e81-102">Garbage Collection</span></span>
<span data-ttu-id="03e81-103">.NET 的垃圾回收器管理应用程序的内存分配和释放。</span><span class="sxs-lookup"><span data-stu-id="03e81-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="03e81-104">每当有对象新建时，公共语言运行时都会从托管堆为对象分配内存。</span><span class="sxs-lookup"><span data-stu-id="03e81-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="03e81-105">只要托管堆中有地址空间，运行时就会继续为新对象分配空间。</span><span class="sxs-lookup"><span data-stu-id="03e81-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="03e81-106">不过，内存并不是无限的。</span><span class="sxs-lookup"><span data-stu-id="03e81-106">However, memory is not infinite.</span></span> <span data-ttu-id="03e81-107">垃圾回收器最终必须执行垃圾回收来释放一些内存。</span><span class="sxs-lookup"><span data-stu-id="03e81-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="03e81-108">垃圾回收器的优化引擎会根据所执行的分配来确定执行回收的最佳时机。</span><span class="sxs-lookup"><span data-stu-id="03e81-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="03e81-109">执行回收时，垃圾回收器会在托管堆中检查应用程序不再使用的对象，然后执行必要的操作来回收其内存。</span><span class="sxs-lookup"><span data-stu-id="03e81-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="03e81-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="03e81-110">Related Topics</span></span>  
  
|<span data-ttu-id="03e81-111">标题</span><span class="sxs-lookup"><span data-stu-id="03e81-111">Title</span></span>|<span data-ttu-id="03e81-112">描述</span><span class="sxs-lookup"><span data-stu-id="03e81-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="03e81-113">垃圾回收的基础知识</span><span class="sxs-lookup"><span data-stu-id="03e81-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="03e81-114">描述垃圾回收的工作原理、如何在托管堆上分配对象，以及其他核心概念。</span><span class="sxs-lookup"><span data-stu-id="03e81-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="03e81-115">垃圾回收和性能</span><span class="sxs-lookup"><span data-stu-id="03e81-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="03e81-116">介绍了可用来诊断垃圾回收和性能问题的性能检查。</span><span class="sxs-lookup"><span data-stu-id="03e81-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="03e81-117">已引发回收</span><span class="sxs-lookup"><span data-stu-id="03e81-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="03e81-118">描述如何完成垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="03e81-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="03e81-119">延迟模式</span><span class="sxs-lookup"><span data-stu-id="03e81-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="03e81-120">描述确定垃圾回收侵入性的模式。</span><span class="sxs-lookup"><span data-stu-id="03e81-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="03e81-121">针对共享 Web 托管进行优化</span><span class="sxs-lookup"><span data-stu-id="03e81-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="03e81-122">介绍了如何在多个小网站共用的服务器上优化垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="03e81-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="03e81-123">垃圾回收通知</span><span class="sxs-lookup"><span data-stu-id="03e81-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="03e81-124">介绍了如何确定全面垃圾回收的开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="03e81-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="03e81-125">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="03e81-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="03e81-126">介绍了如何监视应用程序域的 CPU 和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="03e81-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="03e81-127">弱引用</span><span class="sxs-lookup"><span data-stu-id="03e81-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="03e81-128">描述允许应用程序访问对象的同时也允许垃圾回收器收集相应对象的功能。</span><span class="sxs-lookup"><span data-stu-id="03e81-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="03e81-129">参考</span><span class="sxs-lookup"><span data-stu-id="03e81-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="03e81-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="03e81-130">See Also</span></span>  
 <span data-ttu-id="03e81-131">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)（清理未托管资源）</span><span class="sxs-lookup"><span data-stu-id="03e81-131">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)</span></span>
