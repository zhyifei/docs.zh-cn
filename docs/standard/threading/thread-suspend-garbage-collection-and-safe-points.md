---
title: "Thread.Suspend、垃圾回收和安全点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend、垃圾回收和安全点
当调用<xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>在线程上，系统会注意的线程挂起已请求，并允许以执行，直到它已达到某一安全点之前实际上挂起线程的线程。 线程的安全点是在可执行回收垃圾其执行中的点。  
  
 一旦达到某一安全点，运行时就会确保挂起的线程将不在托管代码中执行任何进一步的操作。 托管代码之外执行的线程始终是安全的垃圾回收，并且其执行会继续，直到它将尝试继续执行托管代码。  
  
> [!NOTE]
>  若要执行垃圾回收，运行时必须挂起执行回收的线程以外的所有线程。 在可以挂起之前，每个线程必须转到某一安全点。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [自动内存管理](../../../docs/standard/automatic-memory-management.md)
