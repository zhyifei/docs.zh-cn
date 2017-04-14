---
title: "BlockingCollection 概述 | Microsoft Docs"
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
  - "BlockingCollection，概述"
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# BlockingCollection 概述
<xref:System.Collections.Concurrent.BlockingCollection%601> 是一个线程安全集合类，可提供以下功能：  
  
-   实现制造者\-使用者模式。  
  
-   同时在多个线程中添加和取出项。  
  
-   可选的最大容量。  
  
-   可在集合为空或已满时发生阻塞的插入和移除操作。  
  
-   不会发生阻塞或只在指定的时间段内发生阻塞的“尝试”插入和移除操作。  
  
-   封装实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 的任何集合类型  
  
-   使用取消标记执行取消操作。  
  
-   使用 `foreach`（在 Visual Basic 中为 `For Each`）的两类枚举：  
  
    1.  只读枚举。  
  
    2.  在枚举项时将项移除的枚举。  
  
## 边界和阻塞支持  
 <xref:System.Collections.Concurrent.BlockingCollection%601> 支持限制和阻塞。  边界意味着您可以设置集合的最大容量。  边界对于某些情况很重要，原因是它使您能够控制内存中的集合的最大大小，并可阻止制造线程移动到离使用线程太远的前方位置。  
  
 多个线程或任务可同时向集合中添加项，如果集合达到其指定最大容量，则制造线程将发生阻塞，直到移除集合中的某个项。  多个使用者可以同时移除项，如果集合变为空，则使用线程将发生阻塞，直到制造者添加某个项。  制造线程可调用 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> 来指示将不再添加项。  使用者将监视 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 属性以了解集合何时为空且不再添加项。  下面的示例演示了一个简单的 BlockingCollection，其上限容量为 100。  只要满足某些外部条件，制造者任务就会向集合添加项，然后调用 <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>。  用户任务获取项，直至 <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> 属性为 true。  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 有关完整示例，请参见[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)。  
  
## 计时阻塞操作  
 在针对有限集合的计时阻塞 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 操作中，此方法将尝试添加或取出某个项。  如果某个项可用，则会将该项放置到通过引用传入的变量中，并且此方法返回 true。  如果在指定的超时时间已过后未检索到任何项，则此方法返回 false。  相应的线程可以任意执行一些其他有用的工作，然后再重新尝试访问该集合。  有关计时阻塞访问的示例，请参见[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)中的第二个示例。  
  
## 取消添加和取出操作  
 添加和取出操作通常会在一个循环内执行。  可以通过以下方法来取消循环：向 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 或 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法中传入 <xref:System.Threading.CancellationToken>，然后在每次迭代时检查该标记的 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 属性的值。  如果该值为 true，则需要您来响应取消请求，即，清理所有资源并退出循环。  下面的示例演示获取取消标记使用它 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> 和代码的重载:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 有关如何添加取消支持的示例，请参见[如何：在 BlockingCollection 中逐个添加和取出项](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)中的第二个示例。  
  
## 指定集合类型  
 在创建 <xref:System.Collections.Concurrent.BlockingCollection%601> 时，您不仅可以指定上限容量，而且可以指定要使用的集合的类型。  例如，您可以为先进先出 \(FIFO\) 行为指定 <xref:System.Collections.Concurrent.ConcurrentQueue%601>，也可以为后进先出 \(LIFO\) 行为指定 <xref:System.Collections.Concurrent.ConcurrentStack%601>。  可以使用实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 接口的任何集合类。  <xref:System.Collections.Concurrent.BlockingCollection%601> 的默认集合类型为 <xref:System.Collections.Concurrent.ConcurrentQueue%601>。  下面的代码示例演示如何创建字符串的 <xref:System.Collections.Concurrent.BlockingCollection%601>，其容量为 1000 并且将使用 <xref:System.Collections.Concurrent.ConcurrentBag%601>：  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 有关更多信息，请参见[如何：向集合添加限制和阻塞功能](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)。  
  
## IEnumerable 支持  
 <xref:System.Collections.Concurrent.BlockingCollection%601> 提供了一个 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法，该方法允许使用者使用 `foreach`（在 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 中为 `For Each`）移除项直到完成集合，也就是说，集合为空并且将不再添加项。  有关更多信息，请参见[如何：使用 ForEach 移除 BlockingCollection 中的项](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)。  
  
## 将多个 BlockingCollection 作为一个 BlockingCollection 使用  
 在使用者需要同时取出多个集合中的项的情况下，您可以创建 <xref:System.Collections.Concurrent.BlockingCollection%601> 的数组并使用静态方法，如 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> 方法，这两个方法可以在该数组中的任意集合中添加或取出项。  如果某个集合发生阻塞，则此方法会立即尝试另一个集合，直到它找到一个能够执行该操作的集合。  有关更多信息，请参见[如何：在管道中使用阻塞集合的数组](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)。  
  
## 请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [集合和数据结构](../../../../docs/standard/collections/index.md)   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)