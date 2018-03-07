---
title: "计时器"
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
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 80b4cee03e934d3aec98ca323aac43f934c56455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="timers"></a><span data-ttu-id="3bbb7-102">计时器</span><span class="sxs-lookup"><span data-stu-id="3bbb7-102">Timers</span></span>
<span data-ttu-id="3bbb7-103">计时器是一种轻型对象，可便于指定要在指定时间调用的委托。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="3bbb7-104">线程池中的线程执行等待操作。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="3bbb7-105"><xref:System.Threading.Timer?displayProperty=nameWithType> 类使用起来非常简单。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="3bbb7-106">创建 Timer 的同时，向回调方法传递 <xref:System.Threading.TimerCallback> 委托、表示传递给回调的状态的对象、初始抛出时间和表示回调调用时间间隔的时间。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="3bbb7-107">若要取消挂起的计时器，请调用 Timer.Dispose 函数。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bbb7-108">还有其他两个计时器类。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-108">There are two other timer classes.</span></span> <span data-ttu-id="3bbb7-109"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 类是与可视化设计器结合使用的控件，适用于用户界面上下文，在用户界面线程上抛出事件。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="3bbb7-110">由于 <xref:System.Timers.Timer?displayProperty=nameWithType> 类派生自 <xref:System.ComponentModel.Component>，因此可以与可视化设计器结合使用；它还会抛出事件，但是在 <xref:System.Threading.ThreadPool> 线程上抛出这些事件。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="3bbb7-111"><xref:System.Threading.Timer?displayProperty=nameWithType> 类在 <xref:System.Threading.ThreadPool> 线程上执行回调，完全不使用事件模型。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="3bbb7-112">它还向回调方法提供状态对象，而其他计时器则不会。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="3bbb7-113">它是极度轻型类。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="3bbb7-114">下面的代码示例启动计时器，此计时器在一秒（1000 毫秒）后启动，且每秒都会计时，直到按下 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="3bbb7-115">为了确保计时器在运行的同时不受垃圾回收影响，包含对计时器的引用的变量是类级别字段。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="3bbb7-116">若要详细了解积极垃圾回收，请参阅 <xref:System.GC.KeepAlive%2A>。</span><span class="sxs-lookup"><span data-stu-id="3bbb7-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3bbb7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bbb7-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="3bbb7-118">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="3bbb7-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
