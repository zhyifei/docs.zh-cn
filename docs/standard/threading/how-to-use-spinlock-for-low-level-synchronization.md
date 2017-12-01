---
title: "如何：使用 SpinLock 进行低级别同步"
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>如何：使用 SpinLock 进行低级别同步
下面的示例演示如何使用<xref:System.Threading.SpinLock>。  
  
## <a name="example"></a>示例  
 在此示例中，关键部分执行最少量的工作，则会使的良好候选<xref:System.Threading.SpinLock>。 增加工作一小部分会增加的性能<xref:System.Threading.SpinLock>相比标准锁。 但是，超过某个点时 SpinLock 将比标准锁开销更大。 可以使用分析工具中的并发分析功能，查看哪种类型的锁可以在程序中提供更好的性能。 有关详细信息，请参阅[并发可视化工具](/visualstudio/profiling/concurrency-visualizer)。  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>可能会很有用，当共享资源的锁不要保留时间很长。 在这种情况下，多核计算机上的阻止线程可高效旋转几个周期，直到锁被释放。 通过旋转，线程不会受到阻止，这是一个占用大量 CPU 资源的进程。 <xref:System.Threading.SpinLock>将会停止在某些条件且要阻止的逻辑处理器或优先级数据倒排在具有超线程系统上的资源不足的旋转。  
  
 此示例使用<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>类，这就需要为多线程访问的用户同步。 在面向.NET Framework 版本 4 的应用程序，另一个选项是使用<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>，从而无需任何用户锁。  
  
 请注意，使用`false`(`False`在 Visual Basic 中) 的调用中<xref:System.Threading.SpinLock.Exit%2A>。 这可提供最佳性能。 在 IA64 架构上指定 `true` (`True`) 可使用内存界定，这会刷新写入缓冲区以确保锁现在可供其他线程退出。  
  
## <a name="see-also"></a>另请参阅  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
