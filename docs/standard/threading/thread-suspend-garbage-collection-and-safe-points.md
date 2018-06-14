---
title: Thread.Suspend、垃圾回收和安全点
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ded5c057b1c257e8bcf3c8427f5810720eaf0947
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582156"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend、垃圾回收和安全点
如果对线程调用 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>，系统就会注意到线程暂停请求已发出，并允许线程在实际暂停前一直执行到安全点。 线程的安全点是可以执行垃圾回收的执行点。  
  
 一旦达到安全点，运行时就会确保暂停的线程在托管代码中不会进一步取得任何进展。 在托管代码外部执行的线程始终都可以安全执行垃圾回收，并继续执行到尝试恢复执行托管代码。  
  
> [!NOTE]
>  为了执行垃圾回收，运行时必须暂停所有线程（执行回收的线程除外）。 每个线程必须先到达安全点，然后才能暂停。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [自动内存管理](../../../docs/standard/automatic-memory-management.md)
