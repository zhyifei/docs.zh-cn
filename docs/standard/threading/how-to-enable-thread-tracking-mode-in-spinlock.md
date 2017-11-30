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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="cc837-102">如何：在 SpinLock 中启用线程跟踪模式</span><span class="sxs-lookup"><span data-stu-id="cc837-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="cc837-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>是一个可用于具有等待时间非常短的方案的低级别的相互排斥锁。</span><span class="sxs-lookup"><span data-stu-id="cc837-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="cc837-104"><xref:System.Threading.SpinLock>不是可重入的。</span><span class="sxs-lookup"><span data-stu-id="cc837-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="cc837-105">线程进入锁定后，它必须之前可以重新输入正确退出锁。</span><span class="sxs-lookup"><span data-stu-id="cc837-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="cc837-106">通常情况下，重新进入锁定状态的任何尝试都会导致死锁，并且死锁可以很难进行调试。</span><span class="sxs-lookup"><span data-stu-id="cc837-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="cc837-107">作为辅助手段开发，<xref:System.Threading.SpinLock?displayProperty=nameWithType>支持一个线程尝试重新输入已持有的锁时引发异常的线程跟踪模式。</span><span class="sxs-lookup"><span data-stu-id="cc837-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="cc837-108">这样可以更易于定位的锁未正确退出点。</span><span class="sxs-lookup"><span data-stu-id="cc837-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="cc837-109">你可以通过启用线程跟踪模式<xref:System.Threading.SpinLock>构造函数采用一个布尔值输入参数，并传入的自变量`true`。</span><span class="sxs-lookup"><span data-stu-id="cc837-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="cc837-110">开发和测试阶段完成后，关闭线程跟踪模式以更好的性能。</span><span class="sxs-lookup"><span data-stu-id="cc837-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc837-111">示例</span><span class="sxs-lookup"><span data-stu-id="cc837-111">Example</span></span>  
 <span data-ttu-id="cc837-112">下面的示例演示线程跟踪模式。</span><span class="sxs-lookup"><span data-stu-id="cc837-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="cc837-113">正确退出锁的行注释掉，以模拟导致以下结果之一的编码错误：</span><span class="sxs-lookup"><span data-stu-id="cc837-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="cc837-114">如果引发异常<xref:System.Threading.SpinLock>通过使用的自变量创建`true`(`True`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="cc837-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="cc837-115">如果发生死锁<xref:System.Threading.SpinLock>通过使用的自变量创建`false`(`False`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="cc837-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="cc837-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc837-116">See Also</span></span>  
 [<span data-ttu-id="cc837-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="cc837-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
