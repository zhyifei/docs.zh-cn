---
title: "调度线程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a><span data-ttu-id="e03b6-102">调度线程</span><span class="sxs-lookup"><span data-stu-id="e03b6-102">Scheduling Threads</span></span>
<span data-ttu-id="e03b6-103">每个线程都有分配给它的线程优先级。</span><span class="sxs-lookup"><span data-stu-id="e03b6-103">Every thread has a thread priority assigned to it.</span></span> <span data-ttu-id="e03b6-104">公共语言运行时内创建的线程最初分配的优先级**ThreadPriority.Normal**。</span><span class="sxs-lookup"><span data-stu-id="e03b6-104">Threads created within the common language runtime are initially assigned the priority of **ThreadPriority.Normal**.</span></span> <span data-ttu-id="e03b6-105">在运行时以外创建的线程会保留它们进入托管的环境之前所具有的优先级。</span><span class="sxs-lookup"><span data-stu-id="e03b6-105">Threads created outside the runtime retain the priority they had before they entered the managed environment.</span></span> <span data-ttu-id="e03b6-106">你可以获取或设置与任何线程的优先级**Thread.Priority**属性。</span><span class="sxs-lookup"><span data-stu-id="e03b6-106">You can get or set the priority of any thread with the **Thread.Priority** property.</span></span>  
  
 <span data-ttu-id="e03b6-107">线程都计划进行执行基于它们的优先级别。</span><span class="sxs-lookup"><span data-stu-id="e03b6-107">Threads are scheduled for execution based on their priority.</span></span> <span data-ttu-id="e03b6-108">即使在运行时执行线程，所有线程都是由操作系统都分配处理器时间段。</span><span class="sxs-lookup"><span data-stu-id="e03b6-108">Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.</span></span> <span data-ttu-id="e03b6-109">用于确定线程的执行顺序的计划算法的详细信息因每个操作系统而异。</span><span class="sxs-lookup"><span data-stu-id="e03b6-109">The details of the scheduling algorithm used to determine the order in which threads are executed varies with each operating system.</span></span> <span data-ttu-id="e03b6-110">在某些操作系统下 （的这些可执行的线程） 的最高优先级的线程始终计划要首先运行。</span><span class="sxs-lookup"><span data-stu-id="e03b6-110">Under some operating systems, the thread with the highest priority (of those threads that can be executed) is always scheduled to run first.</span></span> <span data-ttu-id="e03b6-111">如果具有相同优先级的多个线程都可用，通过以该优先级，提供在其执行中的固定的时间片的每个线程的线程的计划程序周期。</span><span class="sxs-lookup"><span data-stu-id="e03b6-111">If multiple threads with the same priority are all available, the scheduler cycles through the threads at that priority, giving each thread a fixed time slice in which to execute.</span></span> <span data-ttu-id="e03b6-112">只要可用来运行具有较高优先级的线程，就不会较低优先级的线程执行。</span><span class="sxs-lookup"><span data-stu-id="e03b6-112">As long as a thread with a higher priority is available to run, lower priority threads do not get to execute.</span></span> <span data-ttu-id="e03b6-113">当在给定的优先级存在没有其他可运行的线程时，计划程序将移动到下一步的较低优先级，并计划在执行该优先级的线程。</span><span class="sxs-lookup"><span data-stu-id="e03b6-113">When there are no more runnable threads at a given priority, the scheduler moves to the next lower priority and schedules the threads at that priority for execution.</span></span> <span data-ttu-id="e03b6-114">如果较高的优先级线程变得可运行的占用较低优先级的线程和更高优先级的线程可以再次执行。</span><span class="sxs-lookup"><span data-stu-id="e03b6-114">If a higher priority thread becomes runnable, the lower priority thread is preempted and the higher priority thread is allowed to execute once again.</span></span> <span data-ttu-id="e03b6-115">除此之外，系统还可以调整线程优先级动态间前景色和背景移动应用程序的用户界面为。</span><span class="sxs-lookup"><span data-stu-id="e03b6-115">On top of all that, the operating system can also adjust thread priorities dynamically as an application's user interface is moved between foreground and background.</span></span> <span data-ttu-id="e03b6-116">其他操作系统可能选择使用不同的计划算法。</span><span class="sxs-lookup"><span data-stu-id="e03b6-116">Other operating systems might choose to use a different scheduling algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03b6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e03b6-117">See Also</span></span>  
 [<span data-ttu-id="e03b6-118">使用线程和线程处理</span><span class="sxs-lookup"><span data-stu-id="e03b6-118">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="e03b6-119">Windows 中的托管和非托管线程</span><span class="sxs-lookup"><span data-stu-id="e03b6-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
