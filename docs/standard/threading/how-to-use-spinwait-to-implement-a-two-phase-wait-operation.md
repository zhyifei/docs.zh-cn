---
title: "如何：使用 SpinWait 实现两阶段等待操作"
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>如何：使用 SpinWait 实现两阶段等待操作
下面的示例演示如何使用<xref:System.Threading.SpinWait?displayProperty=nameWithType>对象来实现两阶段等待操作。 在第一个阶段，同步对象， `Latch`，旋转几个周期，同时检查是否该锁变为可用。 在第二个阶段，如果该锁变为可用，则`Wait`方法返回时不使用<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>执行其等待; 否则为`Wait`执行等待。  
  
## <a name="example"></a>示例  
 此示例演示非常基本的实现的闩锁同步基元。 当等待时间预计很短，你可以使用此数据结构。 此示例是仅用于演示目的。 如果在程序中需要闩锁类型功能，请考虑使用<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>。  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 闩锁使用<xref:System.Threading.SpinWait>对象仅在下一个调用就地旋转`SpinOnce`导致<xref:System.Threading.SpinWait>以生成线程的时间片。 此时，闩锁将导致通过调用其自己的上下文切换<xref:System.Threading.WaitHandle.WaitOne%2A>上<xref:System.Threading.ManualResetEvent>并传递的超时值的其余部分中。  
  
 日志记录输出显示频率闩锁是能够提高性能，通过获取锁，而无需使用<xref:System.Threading.ManualResetEvent>。  
  
## <a name="see-also"></a>另请参阅  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
