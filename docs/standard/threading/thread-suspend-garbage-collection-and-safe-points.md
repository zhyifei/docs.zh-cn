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
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="62ce2-102">Thread.Suspend、垃圾回收和安全点</span><span class="sxs-lookup"><span data-stu-id="62ce2-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="62ce2-103">当调用<xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>在线程上，系统会注意的线程挂起已请求，并允许以执行，直到它已达到某一安全点之前实际上挂起线程的线程。</span><span class="sxs-lookup"><span data-stu-id="62ce2-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="62ce2-104">线程的安全点是在可执行回收垃圾其执行中的点。</span><span class="sxs-lookup"><span data-stu-id="62ce2-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="62ce2-105">一旦达到某一安全点，运行时就会确保挂起的线程将不在托管代码中执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="62ce2-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="62ce2-106">托管代码之外执行的线程始终是安全的垃圾回收，并且其执行会继续，直到它将尝试继续执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="62ce2-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62ce2-107">若要执行垃圾回收，运行时必须挂起执行回收的线程以外的所有线程。</span><span class="sxs-lookup"><span data-stu-id="62ce2-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="62ce2-108">在可以挂起之前，每个线程必须转到某一安全点。</span><span class="sxs-lookup"><span data-stu-id="62ce2-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ce2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62ce2-109">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [<span data-ttu-id="62ce2-110">线程处理</span><span class="sxs-lookup"><span data-stu-id="62ce2-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="62ce2-111">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="62ce2-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
