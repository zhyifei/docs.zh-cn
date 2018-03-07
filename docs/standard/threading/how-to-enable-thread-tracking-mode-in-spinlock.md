---
title: "如何：在 SpinLock 中启用线程跟踪模式"
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
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f3d5b40f1f7b4b7534a44f4f7ab542d33d373702
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="d1252-102">如何：在 SpinLock 中启用线程跟踪模式</span><span class="sxs-lookup"><span data-stu-id="d1252-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="d1252-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> 是一种低级互斥锁，可用于等待时间非常短的方案。</span><span class="sxs-lookup"><span data-stu-id="d1252-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="d1252-104"><xref:System.Threading.SpinLock> 不可重入。</span><span class="sxs-lookup"><span data-stu-id="d1252-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="d1252-105">进入锁后，线程必须先正确退出锁定，然后才能再次进入。</span><span class="sxs-lookup"><span data-stu-id="d1252-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="d1252-106">通常，只要尝试重入锁，就会导致死锁发生，且死锁的调试难度可能非常大。</span><span class="sxs-lookup"><span data-stu-id="d1252-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="d1252-107">作为开发的辅助手段，<xref:System.Threading.SpinLock?displayProperty=nameWithType> 支持线程跟踪模式。也就是说，如果线程尝试重入已保留的锁，就会导致异常抛出。</span><span class="sxs-lookup"><span data-stu-id="d1252-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="d1252-108">这样一来，可以更轻松地定位未正确退出锁的点。</span><span class="sxs-lookup"><span data-stu-id="d1252-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="d1252-109">线程跟踪模式的启用方法为，使用需要使用布尔输入参数的 <xref:System.Threading.SpinLock> 构造函数，并传入参数 `true`。</span><span class="sxs-lookup"><span data-stu-id="d1252-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="d1252-110">完成开发和测试阶段后，禁用线程跟踪模式，以提升性能。</span><span class="sxs-lookup"><span data-stu-id="d1252-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1252-111">示例</span><span class="sxs-lookup"><span data-stu-id="d1252-111">Example</span></span>  
 <span data-ttu-id="d1252-112">下面的示例展示了线程跟踪模式。</span><span class="sxs-lookup"><span data-stu-id="d1252-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="d1252-113">正确退出锁的代码行被注释掉，以模拟导致以下结果之一的编码错误：</span><span class="sxs-lookup"><span data-stu-id="d1252-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="d1252-114">如果 <xref:System.Threading.SpinLock> 是通过使用参数 `true`（Visual Basic 中的 `True`）创建而成，异常就会抛出。</span><span class="sxs-lookup"><span data-stu-id="d1252-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="d1252-115">如果 <xref:System.Threading.SpinLock> 是通过使用参数 `false`（Visual Basic 中的 `False`）创建而成，死锁就会发生。</span><span class="sxs-lookup"><span data-stu-id="d1252-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="d1252-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1252-116">See Also</span></span>  
 [<span data-ttu-id="d1252-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="d1252-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
