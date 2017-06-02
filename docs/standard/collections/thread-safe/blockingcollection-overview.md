---
title: "BlockingCollection 概述 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BlockingCollection, overview
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f920d8327a536184c71ad2feb68624cee6bd8ffa
ms.lasthandoff: 04/18/2017

---
# <a name="blockingcollection-overview"></a>BlockingCollection 概述
<xref:System.Collections.Concurrent.BlockingCollection%601> 是线程安全集合类，可提供以下功能：  
  
-   实现制造者-使用者模式。  
  
-   通过多线程并发添加和获取项。  
  
-   可选最大容量。  
  
-   集合为空或已满时通过插入和移除操作进行阻塞。  
  
-   插入和移除“尝试”操作不发生阻塞，或在指定时间段内发生阻塞。  
  
-   封装任何实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 的集合类型  
  
-   使用取消标记执行取消操作。  
  
-   支持使用 `foreach`（在 Visual Basic 中，使用 `For Each`）的两种枚举：  
  
    1.  只读枚举。  
  
    2.  在枚举项时将项移除的枚举。  
  
## <a name="bounding-and-blocking-support"></a>限制和阻塞支持  
 <xref:System.Collections.Concurrent.BlockingCollection%601> 支持控制和锁定。 限制意味着可以设置集合的最大容量。 限制在某些情况中很重要，因为它使你能够控制内存中的集合的最大大小，并可阻止制造线程移动到离使用线程前方太远的位置。  
  
 多个线程或任务可同时向集合添加项，如果集合达到其指定最大容量，则制造线程将发生阻塞，直到移除集合中的某个项。 多个使用者可以同时移除项，如果集合变空，则使用线程将发生阻塞，直到制造者添加某个项。 生成的线程可以通过调用 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> 来指明不会再添加任何项。 使用者通过监视 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 属性来确定集合何时为空以及何时不会再添加任何项。 下面的示例展示了容量上限为 100 的简单 BlockingCollection。 只要某些外部条件为 true，生成方任务就会将项添加到集合中，然后调用 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>。 在 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 属性为 true 前，使用者任务获取项。  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 有关完整示例，请参阅[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)。  
  
## <a name="timed-blocking-operations"></a>计时阻塞操作  
 在对受控集合执行的限时锁定 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 操作中，方法尝试添加或获取项。 如果项可用，项会被置于通过引用传入的变量中，然后方法返回 true。 如果在指定的超时期限过后未检索到任何项，方法返回 false。 相应线程可以任意执行一些其他有用的工作，然后再重新尝试访问该集合。 有关计时阻塞访问的示例，请参阅[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)中的第二个示例。  
  
## <a name="cancelling-add-and-take-operations"></a>取消添加和取出操作  
 添加和取出操作通常会在一个循环内执行。 可以将 <xref:System.Threading.CancellationToken> 传入 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 或 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法，然后对每次迭代检查令牌的 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 属性值，从而取消循环。 如果值为 true，由你自行决定是否通过清理所有资源并退出循环来响应取消请求。 下面的示例展示了获取取消令牌的 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 重载，以及使用它的代码：  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 有关如何添加取消支持的示例，请参阅[如何：在 BlockingCollection 中逐个添加和获取项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)中的第二个示例。  
  
## <a name="specifying-the-collection-type"></a>指定集合类型  
 创建 <xref:System.Collections.Concurrent.BlockingCollection%601> 时，不仅可以指定容量上限，还可以指定要使用的集合类型。 例如，可以为先进先出 (FIFO) 行为指定 <xref:System.Collections.Concurrent.ConcurrentQueue%601>，也可以为后进先出 (LIFO) 行为指定 <xref:System.Collections.Concurrent.ConcurrentStack%601>。 可以使用任何实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 接口的集合类。 <xref:System.Collections.Concurrent.BlockingCollection%601> 的默认集合类型是 <xref:System.Collections.Concurrent.ConcurrentQueue%601>。 下面的代码示例展示了如何创建容量上限为 1000 且使用 <xref:System.Collections.Concurrent.ConcurrentBag%601> 的字符串 <xref:System.Collections.Concurrent.BlockingCollection%601>：  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 有关详细信息，请参阅[如何：向集合添加控制和锁定功能](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)。  
  
## <a name="ienumerable-support"></a>IEnumerable 支持  
 <xref:System.Collections.Concurrent.BlockingCollection%601> 提供 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法，以便使用者可以在集合完成（也就是说，集合为空且不能再添加其他任何项）前使用 `foreach`（在 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 中，使用 `For Each`）删除项。 有关详细信息，请参阅[如何：使用 ForEach 移除 BlockingCollection 中的项](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)。  
  
## <a name="using-many-blockingcollections-as-one"></a>将多个 BlockingCollection 作为整体使用  
 如果使用者需要同时从多个集合获取项，可以创建 <xref:System.Collections.Concurrent.BlockingCollection%601> 的数组，然后使用在数组的任意集合中添加或获取项的静态方法，如 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A>。 如果一个集合发生阻塞，此方法会立即尝试其他集合，直到找到能够执行该操作的集合。 有关详细信息，请参阅[如何：在管道中使用阻塞集合的数组](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [集合和数据结构](../../../../docs/standard/collections/index.md)   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)
