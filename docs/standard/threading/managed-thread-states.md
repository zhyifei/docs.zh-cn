---
title: 托管线程状态
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55409cd2c3bed2bc09db10622de1cceab934112
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45624562"
---
# <a name="managed-thread-states"></a><span data-ttu-id="d12c6-102">托管线程状态</span><span class="sxs-lookup"><span data-stu-id="d12c6-102">Managed Thread States</span></span>
<span data-ttu-id="d12c6-103"><xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> 属性提供了位掩码，以指明线程的当前状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-103">The property <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> provides a bit mask that indicates the thread's current state.</span></span> <span data-ttu-id="d12c6-104">一个线程始终处于 <xref:System.Threading.ThreadState> 枚举中的至少一个可能状态，并且可以同时处于多个状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-104">A thread is always in at least one of the possible states in the <xref:System.Threading.ThreadState> enumeration, and can be in multiple states at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d12c6-105">线程状态仅涉及几个调试方案。</span><span class="sxs-lookup"><span data-stu-id="d12c6-105">Thread state is only of interest in a few debugging scenarios.</span></span> <span data-ttu-id="d12c6-106">因此，始终不应在代码中使用线程状态来同步线程活动。</span><span class="sxs-lookup"><span data-stu-id="d12c6-106">Your code should never use thread state to synchronize the activities of threads.</span></span>  
  
 <span data-ttu-id="d12c6-107">创建托管线程时，该线程处于 <xref:System.Threading.ThreadState.Unstarted> 状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-107">When you create a managed thread, it is in the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="d12c6-108">线程会一直保持 <xref:System.Threading.ThreadState.Unstarted> 状态，直到操作系统将其转移到已启动状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-108">The thread remains in the <xref:System.Threading.ThreadState.Unstarted> state until it is moved into the started state by the operating system.</span></span> <span data-ttu-id="d12c6-109">调用 <xref:System.Threading.Thread.Start%2A> 使操作系统知道该线程可启动；它不会更改线程的状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-109">Calling <xref:System.Threading.Thread.Start%2A> lets the operating system know that the thread can be started; it does not change the state of the thread.</span></span>  
  
 <span data-ttu-id="d12c6-110">进入托管环境的非托管线程已处于已启动状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-110">Unmanaged threads that enter the managed environment are already in the started state.</span></span> <span data-ttu-id="d12c6-111">线程处于已启动状态后，可以执行许多操作来使线程更改状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-111">Once a thread is in the started state, a number of actions can cause it to change states.</span></span> <span data-ttu-id="d12c6-112">下表列出了使状态发生更改的操作和相应的新状态</span><span class="sxs-lookup"><span data-stu-id="d12c6-112">The following table lists the actions that cause a change of state, along with the corresponding new state.</span></span>  
  
|<span data-ttu-id="d12c6-113">操作</span><span class="sxs-lookup"><span data-stu-id="d12c6-113">Action</span></span>|<span data-ttu-id="d12c6-114">所得到的新状态</span><span class="sxs-lookup"><span data-stu-id="d12c6-114">Resulting new state</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="d12c6-115">调用 <xref:System.Threading.Thread> 类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="d12c6-115">The constructor for the <xref:System.Threading.Thread> class is called.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="d12c6-116">另一个线程调用 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-116">Another thread calls <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Unstarted>|  
|<span data-ttu-id="d12c6-117">线程响应 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> 并开始运行。</span><span class="sxs-lookup"><span data-stu-id="d12c6-117">The thread responds to <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> and starts running.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="d12c6-118">线程调用 <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-118">The thread calls <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="d12c6-119">线程对另一个对象调用 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-119">The thread calls <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> on another object.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="d12c6-120">线程对另一个线程调用 <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-120">The thread calls <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> on another thread.</span></span>|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|<span data-ttu-id="d12c6-121">另一个线程调用 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-121">Another thread calls <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.SuspendRequested>|  
|<span data-ttu-id="d12c6-122">线程响应 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 请求。</span><span class="sxs-lookup"><span data-stu-id="d12c6-122">The thread responds to a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> request.</span></span>|<xref:System.Threading.ThreadState.Suspended>|  
|<span data-ttu-id="d12c6-123">另一个线程调用 <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-123">Another thread calls <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.Running>|  
|<span data-ttu-id="d12c6-124">另一个线程调用 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-124">Another thread calls <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<xref:System.Threading.ThreadState.AbortRequested>|  
|<span data-ttu-id="d12c6-125">线程响应 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-125">The thread responds to an <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>|<span data-ttu-id="d12c6-126"><xref:System.Threading.ThreadState.Aborted>，然后 <xref:System.Threading.ThreadState.Stopped></span><span class="sxs-lookup"><span data-stu-id="d12c6-126"><xref:System.Threading.ThreadState.Aborted>, then <xref:System.Threading.ThreadState.Stopped></span></span>|  
  
 <span data-ttu-id="d12c6-127">由于 <xref:System.Threading.ThreadState.Running> 状态具有值 0，因此它不能执行位测试来发现此状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-127">Because the <xref:System.Threading.ThreadState.Running> state has a value of 0, it is not possible to perform a bit test to discover this state.</span></span> <span data-ttu-id="d12c6-128">相反，可以使用以下测试（以伪代码表示）：</span><span class="sxs-lookup"><span data-stu-id="d12c6-128">Instead, the following test (in pseudo-code) can be used:</span></span>  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 <span data-ttu-id="d12c6-129">在任何给定时间，线程通常处于多个状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-129">Threads are often in more than one state at any given time.</span></span> <span data-ttu-id="d12c6-130">例如，如果线程在 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 调用中受阻止，并且另一个线程对相同的线程调用 <xref:System.Threading.Thread.Abort%2A>，那么线程就会同时处于 <xref:System.Threading.ThreadState.WaitSleepJoin> 和 <xref:System.Threading.ThreadState.AbortRequested> 状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-130">For example, if a thread is blocked on a <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> call and another thread calls <xref:System.Threading.Thread.Abort%2A> on that same thread, the thread will be in both the <xref:System.Threading.ThreadState.WaitSleepJoin> and the <xref:System.Threading.ThreadState.AbortRequested> states at the same time.</span></span> <span data-ttu-id="d12c6-131">在这种情况下，一旦该线程从对 <xref:System.Threading.Monitor.Wait%2A> 的调用返回或该线程中断，它就会收到 <xref:System.Threading.ThreadAbortException>。</span><span class="sxs-lookup"><span data-stu-id="d12c6-131">In that case, as soon as the thread returns from the call to <xref:System.Threading.Monitor.Wait%2A> or is interrupted, it will receive the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 <span data-ttu-id="d12c6-132">线程由于调用 <xref:System.Threading.ThreadState.Unstarted> 而离开 <xref:System.Threading.Thread.Start%2A>状态后，它将无法再返回到 <xref:System.Threading.ThreadState.Unstarted> 状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-132">Once a thread leaves the <xref:System.Threading.ThreadState.Unstarted> state as the result of a call to <xref:System.Threading.Thread.Start%2A>, it can never return to the <xref:System.Threading.ThreadState.Unstarted> state.</span></span> <span data-ttu-id="d12c6-133">同样，线程也永远无法离开 <xref:System.Threading.ThreadState.Stopped> 状态。</span><span class="sxs-lookup"><span data-stu-id="d12c6-133">A thread can never leave the <xref:System.Threading.ThreadState.Stopped> state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12c6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d12c6-134">See also</span></span>

- <xref:System.Threading.ThreadAbortException>  
- <xref:System.Threading.Thread>  
- <xref:System.Threading.ThreadState>  
- [<span data-ttu-id="d12c6-135">线程处理</span><span class="sxs-lookup"><span data-stu-id="d12c6-135">Threading</span></span>](../../../docs/standard/threading/index.md)
