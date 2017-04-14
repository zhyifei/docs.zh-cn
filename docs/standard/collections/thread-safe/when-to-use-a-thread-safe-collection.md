---
title: "何时使用线程安全集合 | Microsoft Docs"
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
  - "线程安全集合，何时升级"
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 何时使用线程安全集合
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]引入了五种新的集合类型，这些集合类型专用于为多线程的添加和移除操作提供支持。  为了实现线程安全性，这些新类型使用了各种有效的锁定和无锁同步机制。  同步会增加操作的开销。  开销的数量取决于所使用同步的类型、所执行操作的类型和其他因素（如正在尝试同时访问集合的线程的数目）。  
  
 在一些情况中，同步开销是可以忽略的，这使得多线程类型相对于其受外部锁保护的非线程安全等效类型，不仅在执行速度上快很多，而且在伸缩程度上也好很多。  但在其他情况中，同步开销会使得线程安全类型在执行速度和伸缩程度上与该类型的外部锁定的非线程安全版本大致相同甚至更差一些。  
  
 以下各节提供有关何时使用线程安全集合与其非线程安全等效项（其读取和写入操作受用户提供的锁保护）的一般性指导原则。  由于性能会随多个因素而变化，因此本指导原则并不是针对具体情况的，不一定适用于所有环境。  如果性能非常重要，确定要使用的集合类型的最佳方式是：根据有代表性的计算机配置和负载来测量性能。  本文档中使用了以下术语：  
  
 *纯制造者\-使用者情况*  
 任何给定线程只添加元素或移除元素，而不是同时执行这两个操作。  
  
 *混合制造者\-使用者情况*  
 任何给定线程既添加元素也移除元素。  
  
 *加速*  
 在同一情况中，算法性能相对于另一个类型较快。  
  
 *可伸缩性*  
 与计算机上的内核数成比例的性能改进。  一种可伸缩的算法在八核计算机上的执行速度比在双核计算机上快。  
  
## ConcurrentQueue\(T\) vs. Queue\(T\)  
 在纯制造者\-使用者情况中，每个元素的处理时间非常少（几条指令），<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> 相对于带有外部锁的 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 能够提供稍好一些的性能。  在此情况中，当一个专用线程正在排队，而另一个专用线程正在取消排队时，<xref:System.Collections.Concurrent.ConcurrentQueue%601> 的性能最佳。  如果不实施此规则，则在多核计算机上，<xref:System.Collections.Generic.Queue%601> 的执行速度可能会稍快于 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 的执行速度。  
  
 当处理时间约为或超过 500 FLOPS（浮点运算）时，双线程规则不应用于 <xref:System.Collections.Concurrent.ConcurrentQueue%601>，这样做将具有良好的伸缩性。  在此情况中，<xref:System.Collections.Generic.Queue%601> 无法很好地伸缩。  
  
 在混合制造者\-使用者情况中，当处理时间非常少时，带有外部锁的 <xref:System.Collections.Generic.Queue%601> 能够比 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 更好地进行伸缩。  但是，当处理时间约为或超过 500 FLOPS 时，<xref:System.Collections.Concurrent.ConcurrentQueue%601> 的伸缩性较好。  
  
## 并发栈 vs .栈  
 在纯制造者\-使用者情况中，当处理时间非常少时，<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName> 和具有外部锁的 <xref:System.Collections.Generic.Stack%601?displayProperty=fullName> 在使用一个专用推送线程和一个专用弹出线程时的执行性能大致相同。  但是，随着线程数目的增加，两种类型都会因为争用加剧而导致性能下降，并且 <xref:System.Collections.Generic.Stack%601> 的性能可能会好于 <xref:System.Collections.Concurrent.ConcurrentStack%601> 的性能。  当处理时间约为或超过 500 FLOPS 时，这两个类型将以相同的速率进行伸缩。  
  
 在混合制造者\-使用者情况中，无论是在少量工作负荷还是在大量工作负荷的情况下，<xref:System.Collections.Concurrent.ConcurrentStack%601> 的速率都要更快一些。  
  
 使用 <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> 可以大大加快访问速度。  
  
## 并行字典与.字典  
 通常，在从多个线程中同时添加和更新键或值的情况中，请使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>。  在涉及频繁的更新操作和相对较少的读取操作的情况中，<xref:System.Collections.Concurrent.ConcurrentDictionary%602> 通常会具有一些优势。  在涉及很多读取和更新操作的情况中，在具有任意数目的内核的计算机上，<xref:System.Collections.Concurrent.ConcurrentDictionary%602> 的执行速度通常会较快。  
  
 在涉及频繁的更新操作的情况中，可以增大 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 中并发的程度，然后进行测量以查看性能在具有更多内核的计算机上是否得到提高。  如果更改了并发级别，请尽可能避免全局操作。  
  
 如果只读取键或值，则 <xref:System.Collections.Generic.Dictionary%602> 会更快，因为在任何线程均未修改字典的情况下不需要进行同步。  
  
## ConcurrentBag  
 在纯制造者\-使用者情况中，<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> 的执行速度可能会比其他并发集合类型的执行速度慢得多。  
  
 在混合制造者\-使用者情况中，无论是在少量工作负荷还是在大量工作负荷的情况下，<xref:System.Collections.Concurrent.ConcurrentBag%601> 通常不仅在执行速度上会比任何其他并发集合类型更快，而且在可伸缩性上会比后者更好。  
  
## BlockingCollection  
 在需要限制和阻塞语义时，<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的执行速度可能会比任何自定义实现的执行速度都快。  它还支持各种取消、枚举和异常处理。  
  
## 请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)