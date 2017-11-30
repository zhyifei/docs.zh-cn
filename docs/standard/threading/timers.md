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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a><span data-ttu-id="2955f-102">计时器</span><span class="sxs-lookup"><span data-stu-id="2955f-102">Timers</span></span>
<span data-ttu-id="2955f-103">计时器是使您能够指定要在指定的时间调用的委托的轻型对象。</span><span class="sxs-lookup"><span data-stu-id="2955f-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="2955f-104">在线程池中的线程执行等待操作。</span><span class="sxs-lookup"><span data-stu-id="2955f-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="2955f-105">使用<xref:System.Threading.Timer?displayProperty=nameWithType>类非常简单。</span><span class="sxs-lookup"><span data-stu-id="2955f-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="2955f-106">你创建**计时器**，并传递<xref:System.Threading.TimerCallback>到回调方法中，将传递的状态表示为回调，初始引发时间，表示回调调用之间的时间段时间的对象的委托。</span><span class="sxs-lookup"><span data-stu-id="2955f-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="2955f-107">若要取消的挂起计时器，请调用**Timer.Dispose**函数。</span><span class="sxs-lookup"><span data-stu-id="2955f-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2955f-108">有两个其他计时器类。</span><span class="sxs-lookup"><span data-stu-id="2955f-108">There are two other timer classes.</span></span> <span data-ttu-id="2955f-109"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>类是使用可视化设计器，并旨在在用户界面上下文中使用的控件; 它会引发用户界面线程上的事件。</span><span class="sxs-lookup"><span data-stu-id="2955f-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="2955f-110"><xref:System.Timers.Timer?displayProperty=nameWithType>类派生自<xref:System.ComponentModel.Component>，因此可与可视化设计器使用; 它还会引发事件，但它会发出它们上<xref:System.Threading.ThreadPool>线程。</span><span class="sxs-lookup"><span data-stu-id="2955f-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="2955f-111"><xref:System.Threading.Timer?displayProperty=nameWithType>类上，使回调<xref:System.Threading.ThreadPool>线程和根本不使用的事件模型。</span><span class="sxs-lookup"><span data-stu-id="2955f-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="2955f-112">它还提供给回调方法，其他计时器不这样做的状态对象。</span><span class="sxs-lookup"><span data-stu-id="2955f-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="2955f-113">它是非常轻量。</span><span class="sxs-lookup"><span data-stu-id="2955f-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="2955f-114">下面的代码示例将启动一个秒 （1000年毫秒） 计时周期后启动每秒，直到您按下一个计时器**Enter**密钥。</span><span class="sxs-lookup"><span data-stu-id="2955f-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="2955f-115">包含对计时器的引用的变量是类级字段，以确保计时器不是进行垃圾回收它仍在运行时。</span><span class="sxs-lookup"><span data-stu-id="2955f-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="2955f-116">频繁垃圾收集的详细信息，请参阅<xref:System.GC.KeepAlive%2A>。</span><span class="sxs-lookup"><span data-stu-id="2955f-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2955f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2955f-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="2955f-118">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="2955f-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
