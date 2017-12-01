---
title: SpinWait
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
helpviewer_keywords: synchronization primitives, SpinWait
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfaf85c0fe1de3be89618ae540e9c183b66a11eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="spinwait"></a>SpinWait
<xref:System.Threading.SpinWait?displayProperty=nameWithType>是可以在低级别方案中使用，以避免昂贵的上下文切换和内核转换所需的内核事件的轻量同步类型。 在多核计算机上时资源不需要容纳较长时间，它可以是时间的正在等待的线程几个装入数十或几个几百个周期，在用户模式下启动，然后重试获取该资源对于更加高效。 如果资源在旋转后变为可用，则可以节省数千个周期。 如果资源是仍不可用，然后你所用仅几个周期，并仍然可以输入基于内核的等待。 此旋转然后等待组合有时称为*两阶段等待操作*。  
  
 <xref:System.Threading.SpinWait>旨在与.NET Framework 类型，如简单包装内核事件结合使用<xref:System.Threading.ManualResetEvent>。 <xref:System.Threading.SpinWait>此外可通过本身只在一个程序中的基本旋转功能。  
  
 <xref:System.Threading.SpinWait>远不止一个空的循环。 仔细实现以提供的一般情况下，正确的旋转行为，而且会本身执行上下文切换在旋转足够长的时间 （大约内核转换所需的时间长度）。 例如，在单核计算机<xref:System.Threading.SpinWait>产生线程的时间片立即因为旋转块转发所有线程上的进度。 <xref:System.Threading.SpinWait>此外会产生甚至在多核计算机，以防止阻止更高优先级的线程或垃圾回收器正在等待的线程上。 因此，如果你使用<xref:System.Threading.SpinWait>在两阶段等待操作中，我们建议调用之前在内核等待<xref:System.Threading.SpinWait>本身启动的上下文切换。 <xref:System.Threading.SpinWait>提供<xref:System.Threading.SpinWait.NextSpinWillYield%2A>属性，可以在每次调用之前检查<xref:System.Threading.SpinWait.SpinOnce%2A>。 当该属性返回`true`，启动你自己的等待操作。 有关示例，请参阅[如何： 使用 SpinWait 实现两阶段等待操作](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md)。  
  
 如果你不执行两阶段等待操作，但只旋转直到某些条件为 true，则可以启用<xref:System.Threading.SpinWait>执行其上下文切换，以便它是在 Windows 操作系统环境中的一个好公民。 下面的基本示例演示<xref:System.Threading.SpinWait>无锁堆栈中。 如果你需要高性能、 线程安全的堆栈，请考虑使用<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>。  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Thread.SpinWait%2A>  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)
