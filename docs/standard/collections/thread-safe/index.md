---
title: "线程安全集合 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "线程安全集合，概述"
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
caps.latest.revision: 24
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 24
---
# 线程安全集合
[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 引入了 <xref:System.Collections.Concurrent?displayProperty=fullName> 命名空间，此命名空间包含多个线程安全且可伸缩的集合类。  多个线程可以在这些集合中安全高效地添加或移除项，而无需在用户代码中执行其他同步。  在编写新代码时，只要将集合同时写入多个线程中，就请使用并发集合类。  如果仅从共享集合进行读取，则可使用 <xref:System.Collections.Generic?displayProperty=fullName> 命名空间中的类。  建议您不要使用 1.0 集合类，除非您需要以 .NET Framework 1.1 或早期版本的运行时为目标。  
  
## .NET Framework 1.0 和 2.0 集合中的线程同步  
 可以在 <xref:System.Collections?displayProperty=fullName> 命名空间中找到 .NET Framework 1.0 中引入的集合。  这些集合（包括常用的 <xref:System.Collections.ArrayList> 和 <xref:System.Collections.Hashtable>）通过 `Synchronized` 属性（此属性返回与集合有关的线程安全包装）提供某种线程安全性。  该包装的工作原理是：对每个添加或移除操作锁定整个集合。  因此，每个尝试访问集合的线程必须一直等待，直到轮到它来获取锁。  这是无法进行伸缩的，并且对于大型集合而言，将会导致性能显著降低。  此外，这一设计并不能完全防止出现争用情况。  有关更多信息，请参见MSDN网站上的以下页面：[Synchronization in Generic Collections](http://go.microsoft.com/fwlink/?LinkID=161130)  
  
 可以在 <xref:System.Collections.Generic?displayProperty=fullName> 命名空间中找到 .NET Framework 2.0 中引入的集合类。  这些集合类包括 <xref:System.Collections.Generic.List%601>、<xref:System.Collections.Generic.Dictionary%602> 等。  与 .NET Framework 1.0 类相比，这些类提供的类型安全性和性能会更高。  不过，.NET Framework 2.0 集合类不提供任何线程同步；当同时在多个线程上添加或移除项时，用户代码必须提供所有同步。  
  
 建议您使用 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 中的并发集合类，因为这些类不仅提供了 .NET Framework 2.0 集合类的类型安全性，而且还提供了比 [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)] 集合所提供的线程安全性更高效且更完整的线程安全性。  
  
## 细粒度锁定和无锁机制  
 一些并发集合类型使用的是轻量同步机制，如 <xref:System.Threading.SpinLock>、<xref:System.Threading.SpinWait>、<xref:System.Threading.SemaphoreSlim> 和 <xref:System.Threading.CountdownEvent>，这些同步机制是 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 中的新增功能。  通常，上述同步类型在将线程置于实际等待状态之前会在短时间内使用“繁忙旋转”。  如果预计等待时间会非常短，则旋转所消耗的计算资源将比等待所消耗的计算资源少得多，因为后者涉及将消耗大量资源的内核转换。  对于使用旋转的集合类，这种效率意味着多个线程能够以非常快的速率添加和移除项。  有关限制和阻塞的更多信息，请参见[SpinLock](../../../../docs/standard/threading/spinlock.md) and [SpinWait](../../../../docs/standard/threading/spinwait.md) 。  
  
 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601> 类根本不使用锁定。  相反，它们依赖 <xref:System.Threading.Interlocked> 操作来实现线程安全性。  
  
> [!NOTE]
>  由于并发集合类支持 <xref:System.Collections.ICollection>，因此它们可提供针对 <xref:System.Collections.ICollection.IsSynchronized%2A> 和 <xref:System.Collections.ICollection.SyncRoot%2A> 属性的实现，即使这些属性是不相关的。  `IsSynchronized` 始终返回 `false`，而 `SyncRoot` 始终为 `null`（在 Visual Basic 中为 `Nothing`）。  
  
 下表列出了 <xref:System.Collections.Concurrent?displayProperty=fullName> 命名空间中的集合类型。  
  
|类型|描述|  
|--------|--------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|提供针对实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 的任何类型的限制和阻塞功能。  有关详细信息，请参阅[BlockingCollection 概述](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)。|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|键\/值对字典的线程安全实现。|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|FIFO（先进先出）队列的线程安全实现。|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|LIFO（后进先出）堆栈的线程安全实现。|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|无序的元素集合的线程安全实现。|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|类型必须实现以在 `BlockingCollection` 中使用的接口。|  
  
## 相关主题  
  
|标题|描述|  
|--------|--------|  
|[BlockingCollection 概述](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|描述 <xref:System.Collections.Concurrent.BlockingCollection%601> 类型提供的功能。|  
|[如何：在 ConcurrentDictionary 中添加和移除项](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|描述如何从 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 添加和移除元素。|  
|[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|描述如何在不使用只读枚举器的情况下从阻塞集合添加和检索项。|  
|[如何：向集合添加限制和阻塞功能](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|描述如何将任一集合类用作 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 集合的基础存储机制。|  
|[如何：使用 ForEach 移除 BlockingCollection 中的项](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|描述如何使用 `foreach`（在 Visual Basic 中为 `For Each`）移除阻塞集合中的所有项。|  
|[如何：在管道中使用阻塞集合的数组](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|描述如何同时使用多个阻塞集合来实现一个管道。|  
|[如何：使用 ConcurrentBag 创建目标池](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|演示如何使用并发包在可重用对象（而不是继续创建新对象）的情况下改进性能。|  
  
## 引用  
 <xref:System.Collections.Concurrent?displayProperty=fullName>