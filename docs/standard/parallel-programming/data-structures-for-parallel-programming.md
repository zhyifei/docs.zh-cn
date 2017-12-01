---
title: "用于并行编程的数据结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>用于并行编程的数据结构
.NET Framework 版本 4 引入了几种新类型，可在并行编程中，包括一套并发集合类、 轻量同步基元，以及对延迟初始化的类型。 你可以使用任何多线程应用程序代码，包括任务并行库和 PLINQ 中使用这些类型。  
  
## <a name="concurrent-collection-classes"></a>并发集合类  
 中的集合类<xref:System.Collections.Concurrent?displayProperty=nameWithType>命名空间提供线程安全添加和删除尽可能避免锁的操作以及使用锁必需的细粒度锁定。 与不同的在.NET framework 1.0 和 2.0 版中引入的集合，并发集合类不需要用户代码时要执行的任何锁它访问项。 并发集合类可以显著提高性能类型如<xref:System.Collections.ArrayList?displayProperty=nameWithType>和<xref:System.Collections.Generic.List%601?displayProperty=nameWithType>（与用户实现锁定） 方案，其中多个线程中添加和删除项集合中。  
  
 下表列出了新的并发集合类：  
  
|类型|描述|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|为实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> 的线程安全集合提供阻塞和限制功能。 制造者线程阻止如果没有槽可用，或如果集合已满。 如果该集合为空，将阻止使用者线程。 此类型还支持通过使用者和制造非阻止访问。 <xref:System.Collections.Concurrent.BlockingCollection%601>可以使用作为基类或后备存储，以提供阻塞和限制为支持任何集合类<xref:System.Collections.Generic.IEnumerable%601>。|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|提供可缩放的线程安全包实现添加和获取操作。|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|一种并发且可伸缩的字典类型。|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|并发和可缩放的先进先出队列。|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|并发和可缩放的后进先出堆栈。|  
  
 有关详细信息，请参阅[线程安全集合](../../../docs/standard/collections/thread-safe/index.md)。  
  
## <a name="synchronization-primitives"></a>同步基元  
 中的新同步基元<xref:System.Threading?displayProperty=nameWithType>命名空间通过避免开销在旧的多线程处理代码中找到的锁定机制启用细化的并发性和更快的性能。 某些新类型，如<xref:System.Threading.Barrier?displayProperty=nameWithType>和<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>早期版本的.NET Framework 中具有不对应。  
  
 下表列出的新同步类型：  
  
|类型|描述|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|使多个线程能够通过提供每个任务可以指示其到达并且某些或所有任务均已到达，然后等到点处理并行算法。 有关详细信息，请参阅 [Barrier](../../../docs/standard/threading/barrier.md)。|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|通过提供简单会合机制简化分叉和联接的方案。 有关详细信息，请参阅[CountdownEvent](../../../docs/standard/threading/countdownevent.md)。|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|类似于一个同步基元<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>。 <xref:System.Threading.ManualResetEventSlim>轻量但仅用于内部进程通信。 有关详细信息，请参阅[ManualResetEvent 和 ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)。|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|一个同步基元，限制可以同时访问资源的线程数或资源池。 有关详细信息，请参阅[Semaphore 和 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)。|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|一个相互排斥锁基元，导致线程尝试获取锁后，在循环中等待或*数值调节钮*，生成其量程之前的时间段内。 在方案中等待的锁的地方短，<xref:System.Threading.SpinLock>提供更好的性能比其他形式的锁定。 有关详细信息，请参阅[旋转锁](../../../docs/standard/threading/spinlock.md)。|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|指定的时间，并最终将旋转的小的轻型类型将线程置于等待状态，如果超过重试次数。  有关详细信息，请参阅[SpinWait](../../../docs/standard/threading/spinwait.md)。|  
  
 有关详细信息，请参见:  
  
-   [如何：使用 SpinLock 进行低级别同步](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [如何： 使并发操作保持同步使用屏障](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)。  
  
## <a name="lazy-initialization-classes"></a>延迟初始化类  
 对于迟缓初始化，直到需要它时不分配对象的内存。 通过在程序的生存期之间均匀分配对象分配，延迟初始化可以提高性能。 你可以通过包装类型启用任何自定义类型的延迟初始化<xref:System.Lazy%601>。  
  
 下表列出的延迟初始化类型：  
  
|类型|描述|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|提供轻量、 线程安全迟缓初始化。|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|与延迟调用的初始化函数的每个线程上为每个线程运行，提供延迟初始化值。|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|提供无需分配的专用、 延迟初始化的实例的静态方法。 相反，它们使用引用以确保目标已初始化为这些表进行访问。|  
  
 若要了解详细信息，请参阅[迟缓初始化](../../../docs/framework/performance/lazy-initialization.md)  
  
## <a name="aggregate-exceptions"></a>聚合异常  
 <xref:System.AggregateException?displayProperty=nameWithType>类型可以用于捕获多个异常单独线程上同时引发，并且将它们返回到为单个异常的联接线程。 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>和<xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>类型和 PLINQ 使用<xref:System.AggregateException>广泛用于此目的。 有关详细信息，请参阅[NIB： 如何： 处理由任务引发异常](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d)和[如何： 处理 PLINQ 查询中的异常](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [并行编程](../../../docs/standard/parallel-programming/index.md)
