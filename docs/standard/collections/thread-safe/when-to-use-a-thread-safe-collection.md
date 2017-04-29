---
title: "何时使用线程安全集合 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, when to upgrade
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 87898a4a6ba3d3ef4c53fd1c6b8f94ff353f10e4
ms.lasthandoff: 04/18/2017

---
# <a name="when-to-use-a-thread-safe-collection"></a>何时使用线程安全集合
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 新引入了五个专为支持多线程添加和删除操作而设计的集合类型。 为了实现线程安全性，这些新类型使用多种高效的锁定和免锁定同步机制。 同步会增加操作的开销。 开销数取决于所用的同步类型、执行的操作类型和其他因素，例如尝试并行访问该集合的线程数。  
  
 在某些方案中，同步开销可忽略不计，使多线程类型的执行速度和缩放水平远远超过其受外部锁保护的非线程安全同等类型。 在其他方案中，开销可能会导致线程安全类型的执行速度和缩放水平与该类型外部锁定的非线程安全版本相同，甚至更差。  
  
 以下部分提供有关何时使用线程安全集合与其非线程安全同等集合（其读写操作受用户提供的锁定保护）的通用指南。 由于性能可能因多种因素而异，所以本指南并不针对某特定情况且不一定对所有情况都有效。 如果性能非常重要，那么确定要使用的集合类型的最佳方式是基于典型计算机配置和负载衡量性能。 本文档使用以下术语：  
  
 *纯生成方-使用者方案*  
 任何给定线程要么添加元素，要么删除元素，两种操作不能同时执行。  
  
 *混合生成方-使用者方案*  
 任何给定线程可同时添加和删除元素。  
  
 *加速*  
 相对于同一方案中其他类型更快速的算法性能。  
  
 *可缩放性*  
 与计算机内核数相称的性能提升。 一种可伸缩的算法，相比两个内核，八个内核上的执行速度更快。  
  
## <a name="concurrentqueuet-vs-queuet"></a>ConcurrentQueue (T) 与 Queue(T)  
 在纯生成方-使用者方案中，每个元素的处理时间都非常短（几条指令），<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> 相比含外部锁的 <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> 具有细微的性能优势。 在此方案中，当一个专用线程正在排队，另一个专用线程正在取消排队时，<xref:System.Collections.Concurrent.ConcurrentQueue%601> 的性能最佳。 如果不强制使用此规则，在具有多个内核的计算机上，<xref:System.Collections.Generic.Queue%601> 的执行速度甚至可能稍快于 <xref:System.Collections.Concurrent.ConcurrentQueue%601>。  
  
 当处理时间大约为 500 FLOPS（浮点运算）或更长时间时，双线程规则不适用于 <xref:System.Collections.Concurrent.ConcurrentQueue%601>，因此有很高的可缩放性。 在此方案中，<xref:System.Collections.Generic.Queue%601> 的可缩放性不高。  
  
 在混合生成方-使用者方案中，当处理时间非常短时，含外部锁的 <xref:System.Collections.Generic.Queue%601> 的可缩放性要高于 <xref:System.Collections.Concurrent.ConcurrentQueue%601>。 不过，当处理时间大约为 500 FLOPS 或更长时间时，<xref:System.Collections.Concurrent.ConcurrentQueue%601> 的可缩放性更高。  
  
## <a name="concurrentstack-vs-stack"></a>ConcurrentStack 与堆栈  
 在纯生成方-使用者方案中，当处理时间非常短时，<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName> 和含外部锁的 <xref:System.Collections.Generic.Stack%601?displayProperty=fullName> 在使用一个专用推送线程和一个专用弹出线程时的执行性能可能大致相同。 然而，随着线程数量的增多，这两种类型由于争用增多速度会变慢，并且 <xref:System.Collections.Generic.Stack%601> 的性能可能优于 <xref:System.Collections.Concurrent.ConcurrentStack%601>。 处理时间大约为 500 FLOPS 或更长时，这两种类型的伸缩速率大致相同。  
  
 在混合生成方-使用者方案中，对于小型和大型工作负载，<xref:System.Collections.Concurrent.ConcurrentStack%601> 的执行速度更快。  
  
 使用 <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> 可能会大大缩短访问时间。  
  
## <a name="concurrentdictionary-vs-dictionary"></a>ConcurrentDictionary 与词典  
 通常，在任何通过多线程同时添加和更新键或值的方案中，使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>。 在涉及频繁更新和相对较少读取操作的方案中，<xref:System.Collections.Concurrent.ConcurrentDictionary%602> 通常具有细微优势。 在涉及许多读取和更新操作的方案中，<xref:System.Collections.Concurrent.ConcurrentDictionary%602> 通常在具备任意数量内核的计算机上的运行速度更快得多。  
  
 在涉及频繁更新的方案中，可以在 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 中提高并发度，然后进行衡量，以确定在具有更多内核的计算机上性能是否有所提升。 如果更改并发级别，请尽可能避免全局操作。  
  
 如果仅读取键或值，<xref:System.Collections.Generic.Dictionary%602> 的速度更快，因为如果字典未被任何线程修改，则无需同步。  
  
## <a name="concurrentbag"></a>ConcurrentBag  
 在纯生成方-使用者方案中，<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> 的执行速度可能慢于其他并发集合类型。  
  
 在混合生成方-使用者方案中，对于大型和小型工作负载，<xref:System.Collections.Concurrent.ConcurrentBag%601> 的执行速度和可缩放性往往比其他任何并发集合类型更快更高。  
  
## <a name="blockingcollection"></a>BlockingCollection  
 需要控制和锁定语义时，<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的执行速度可能快于任何自定义实现代码。 它还支持诸多取消、枚举和异常处理操作。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)   
 [并行编程](../../../../docs/standard/parallel-programming/index.md)
