---
title: "垃圾回收通知"
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
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="09627-102">垃圾回收通知</span><span class="sxs-lookup"><span data-stu-id="09627-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="09627-103">在有些情况下，公共语言运行时执行的完整垃圾回收（即第 2 代回收）可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="09627-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="09627-104">这可以是一个问题尤其是对于处理大量请求; 的服务器在这种情况下，长垃圾回收可能会导致请求超时。若要防止中重要的时间段期间发生的完整集合，你可以通知完整的垃圾回收正在接近和则采取措施以将工作负荷重定向到另一个服务器实例。</span><span class="sxs-lookup"><span data-stu-id="09627-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="09627-105">你可以还自己引发回收，前提是当前的服务器实例不需要处理请求。</span><span class="sxs-lookup"><span data-stu-id="09627-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="09627-106"><xref:System.GC.RegisterForFullGCNotification%2A>方法注册的通知，以便在运行时检测该接近完整垃圾回收时引发。</span><span class="sxs-lookup"><span data-stu-id="09627-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="09627-107">有两个部分： 此通知： 当接近完整垃圾回收和完整的垃圾回收完成时。</span><span class="sxs-lookup"><span data-stu-id="09627-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="09627-108">只有阻止垃圾回收会引发通知。</span><span class="sxs-lookup"><span data-stu-id="09627-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="09627-109">当[ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)配置元素启用时，背景垃圾回收不会引发通知。</span><span class="sxs-lookup"><span data-stu-id="09627-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="09627-110">若要确定已时发出通知，请使用<xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="09627-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="09627-111">通常情况下，使用这些方法中的`while`循环来持续获取<xref:System.GCNotificationStatus>显示通知的状态的枚举。</span><span class="sxs-lookup"><span data-stu-id="09627-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="09627-112">如果此值为<xref:System.GCNotificationStatus.Succeeded>，你可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09627-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="09627-113">响应使用获取通知<xref:System.GC.WaitForFullGCApproach%2A>方法，你可以重定向工作负荷并可能自己引发回收。</span><span class="sxs-lookup"><span data-stu-id="09627-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="09627-114">响应使用获取通知<xref:System.GC.WaitForFullGCComplete%2A>方法，可使可用要再次处理请求的当前服务器实例。</span><span class="sxs-lookup"><span data-stu-id="09627-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="09627-115">你还可以收集信息。</span><span class="sxs-lookup"><span data-stu-id="09627-115">You can also gather information.</span></span> <span data-ttu-id="09627-116">例如，你可以使用<xref:System.GC.CollectionCount%2A>方法来记录的集合的数量。</span><span class="sxs-lookup"><span data-stu-id="09627-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="09627-117"><xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法设计为协同工作。</span><span class="sxs-lookup"><span data-stu-id="09627-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="09627-118">使用其中一种可能产生不确定结果。</span><span class="sxs-lookup"><span data-stu-id="09627-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="09627-119">完整的垃圾回收</span><span class="sxs-lookup"><span data-stu-id="09627-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="09627-120">在以下方案中的任何一种情况时，运行时将导致完整垃圾回收：</span><span class="sxs-lookup"><span data-stu-id="09627-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="09627-121">足够的内存被提升到第 2 进行下一步的第 2 代回收代。</span><span class="sxs-lookup"><span data-stu-id="09627-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="09627-122">足够的内存被提升到大型对象堆进行下一步的第 2 代回收。</span><span class="sxs-lookup"><span data-stu-id="09627-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="09627-123">第 1 代集合升级到的其他因素由于第 2 代集合。</span><span class="sxs-lookup"><span data-stu-id="09627-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="09627-124">在指定的阈值<xref:System.GC.RegisterForFullGCNotification%2A>方法应用到的前两个方案。</span><span class="sxs-lookup"><span data-stu-id="09627-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="09627-125">但是，在第一个方案中你将不一定会收到通知在两个原因你指定的阈值值成正比的时间：</span><span class="sxs-lookup"><span data-stu-id="09627-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="09627-126">运行时不会检查每个小型对象分配 （出于性能原因）。</span><span class="sxs-lookup"><span data-stu-id="09627-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="09627-127">仅生成 1 的集合将内存提升到第 2 代。</span><span class="sxs-lookup"><span data-stu-id="09627-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="09627-128">第三个方案也增加了当你将收到通知的不确定性。</span><span class="sxs-lookup"><span data-stu-id="09627-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="09627-129">尽管这并不保证数据，但它未证实是有用的方法，以将请求重定向在此时间或集合自行引发时可以更好地容纳减轻不适当的完整垃圾回收的影响。</span><span class="sxs-lookup"><span data-stu-id="09627-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="09627-130">通知阈值参数</span><span class="sxs-lookup"><span data-stu-id="09627-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="09627-131"><xref:System.GC.RegisterForFullGCNotification%2A>方法具有两个参数指定的第 2 代对象和大型对象堆的阈值。</span><span class="sxs-lookup"><span data-stu-id="09627-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="09627-132">在满足这些值后，应引发垃圾回收通知。</span><span class="sxs-lookup"><span data-stu-id="09627-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="09627-133">下表介绍了这些参数。</span><span class="sxs-lookup"><span data-stu-id="09627-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="09627-134">参数</span><span class="sxs-lookup"><span data-stu-id="09627-134">Parameter</span></span>|<span data-ttu-id="09627-135">描述</span><span class="sxs-lookup"><span data-stu-id="09627-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="09627-136">一个介于 1 和 99 之间的数字，指定应何时引发通知根据在第 2 代提升的对象。</span><span class="sxs-lookup"><span data-stu-id="09627-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="09627-137">一个介于 1 和 99 之间的数字，指定应何时引发通知基于大型对象堆中分配的对象。</span><span class="sxs-lookup"><span data-stu-id="09627-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="09627-138">如果指定一个值，太高，则很可能你将收到一个通知，但可能太长的运行时就会导致回收之前要等待的时间。</span><span class="sxs-lookup"><span data-stu-id="09627-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="09627-139">如果你自己引发回收，你可能回收更多的对象不是如果运行时就会导致回收将回收。</span><span class="sxs-lookup"><span data-stu-id="09627-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="09627-140">如果指定一个值，太低，可能会导致运行时集合之前你有足够的时间，若要得到通知。</span><span class="sxs-lookup"><span data-stu-id="09627-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09627-141">示例</span><span class="sxs-lookup"><span data-stu-id="09627-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="09627-142">描述</span><span class="sxs-lookup"><span data-stu-id="09627-142">Description</span></span>  
 <span data-ttu-id="09627-143">在下面的示例中，一组服务器传入 Web 请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="09627-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="09627-144">若要模拟处理请求的工作负荷，字节数组添加到<xref:System.Collections.Generic.List%601>集合。</span><span class="sxs-lookup"><span data-stu-id="09627-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="09627-145">每个服务器垃圾回收通知的注册，然后启动上的线程`WaitForFullGCProc`用户方法来持续监视<xref:System.GCNotificationStatus>返回的枚举<xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="09627-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="09627-146"><xref:System.GC.WaitForFullGCApproach%2A>和<xref:System.GC.WaitForFullGCComplete%2A>方法调用其各自的事件处理用户方法时引发通知：</span><span class="sxs-lookup"><span data-stu-id="09627-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="09627-147">此方法调用`RedirectRequests`用户方法，指示请求队列服务器挂起发送请求到的服务器。</span><span class="sxs-lookup"><span data-stu-id="09627-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="09627-148">这由设置类级变量模拟`bAllocate`到`false`以便分配更多的对象。</span><span class="sxs-lookup"><span data-stu-id="09627-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="09627-149">接下来，`FinishExistingRequests`用户方法调用以完成处理挂起的服务器请求。</span><span class="sxs-lookup"><span data-stu-id="09627-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="09627-150">这由清除模拟<xref:System.Collections.Generic.List%601>集合。</span><span class="sxs-lookup"><span data-stu-id="09627-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="09627-151">最后，因为工作负载较轻，被引发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="09627-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="09627-152">此方法调用用户方法`AcceptRequests`继续接受请求，因为服务器无法再很容易受到完整垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="09627-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="09627-153">此操作由设置模拟`bAllocate`变量`true`，使对象可以添加到恢复<xref:System.Collections.Generic.List%601>集合。</span><span class="sxs-lookup"><span data-stu-id="09627-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="09627-154">下面的代码包含`Main`方法的示例。</span><span class="sxs-lookup"><span data-stu-id="09627-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="09627-155">下面的代码包含`WaitForFullGCProc`包含连续的 while 循环，以检查垃圾回收通知的用户方法。</span><span class="sxs-lookup"><span data-stu-id="09627-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="09627-156">下面的代码包含`OnFullGCApproachNotify`方法，如从调用</span><span class="sxs-lookup"><span data-stu-id="09627-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="09627-157">`WaitForFullGCProc` 方法。</span><span class="sxs-lookup"><span data-stu-id="09627-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="09627-158">下面的代码包含`OnFullGCApproachComplete`方法，如从调用</span><span class="sxs-lookup"><span data-stu-id="09627-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="09627-159">`WaitForFullGCProc` 方法。</span><span class="sxs-lookup"><span data-stu-id="09627-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="09627-160">下面的代码包含从调用的用户方法`OnFullGCApproachNotify`和`OnFullGCCompleteNotify`方法。</span><span class="sxs-lookup"><span data-stu-id="09627-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="09627-161">用户方法将请求重定向、 完成现有请求，以及完整的垃圾回收发生后再继续请求。</span><span class="sxs-lookup"><span data-stu-id="09627-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="09627-162">整个代码示例是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09627-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="09627-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09627-163">See Also</span></span>  
 [<span data-ttu-id="09627-164">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="09627-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
