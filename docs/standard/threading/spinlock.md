---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
<xref:System.Threading.SpinLock>结构是低级别、 互斥的同步基元，会旋转并同时等待获取锁。 在多核计算机上，当等待时间预计较短且出现争用情况时最小，<xref:System.Threading.SpinLock>可以比其他类型的锁的更好地执行。 但是，我们建议你使用<xref:System.Threading.SpinLock>仅当你确定通过分析时，才<xref:System.Threading.Monitor?displayProperty=nameWithType>方法或<xref:System.Threading.Interlocked>方法显著降低了你程序的性能。  
  
 <xref:System.Threading.SpinLock>即使它已不获取锁，则可能会产生的线程的时间片。 这一点，以避免线程优先级别反转，以及启用垃圾回收器来进行。 当你使用<xref:System.Threading.SpinLock>，确保没有线程可以持有锁的多个非常短的时间跨度内，并且在它持有锁时，可以阻止任何线程。  
  
 旋转锁是值类型，因为你必须显式将其传递由引用如果你想以引用同一个锁的两个副本。  
  
 有关如何使用此类型的详细信息，请参阅<xref:System.Threading.SpinLock?displayProperty=nameWithType>。 有关示例，请参阅[如何： 使用 SpinLock 进行低级别同步](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)。  
  
 <xref:System.Threading.SpinLock>支持*线程*-*跟踪*可以在开发阶段中使用，来帮助跟踪在特定时间持有锁的线程的模式。 线程跟踪模式是非常有用的调试，但我们建议，你将其关闭程序的发行版中因为它可能会降低性能。 有关详细信息，请参阅[如何： 在 SpinLock 中启用线程跟踪模式](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md)。  
  
## <a name="see-also"></a>另请参阅  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
