---
title: 线程处理对象和功能
ms.date: 08/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d56d962279120a03a6e4b89154ac1429ea5479e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44039324"
---
# <a name="threading-objects-and-features"></a>线程处理对象和功能

.NET 与 <xref:System.Threading.Thread?displayProperty=nameWithType> 类一起提供了许多可帮助开发多线程应用程序的类。 以下文章是对这些类的概述：

|标题|描述|  
|-----------|-----------------|  
|[托管线程池](the-managed-thread-pool.md)|描述 <xref:System.Threading.ThreadPool?displayProperty=nameWithType> 类，它提供由 .NET 托管的工作线程池。|  
|[计时器](timers.md)|介绍可在多线程环境中使用的计时器。|
|[同步基元概述](overview-of-synchronization-primitives.md)|描述可用于同步对数据的访问或控制线程交互的类。|
|[EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|描述用于通过发送和等待信号同步线程活动的托管事件等待句柄。|
|[Mutex](mutexes.md)|描述如何使用 <xref:System.Threading.Mutex?displayProperty=nameWithType> 同步访问对象或生成自己的同步机制。|
|[互锁操作](interlocked-operations.md)|描述 <xref:System.Threading.Interlocked?displayProperty=nameWithType> 类，它为多个线程共享的变量提供原子操作。|
|[读取器-编写器锁](reader-writer-locks.md)|描述 <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> 类，它提供单编写器/多读取器语义。|
|[Semaphore 和 SemaphoreSlim](semaphore-and-semaphoreslim.md)|描述 <xref:System.Threading.Semaphore?displayProperty=nameWithType> 类并说明如何使用它控制对有限资源的访问权限。|
|[Barrier](barrier.md)|描述 <xref:System.Threading.Barrier?displayProperty=nameWithType> 类，它可实现分阶段操作中的线程协调屏障模式。|
|[SpinLock](spinlock.md)|描述 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 类，它是某些低级别方案的 <xref:System.Threading.Monitor?displayProperty=nameWithType> 类的轻型替代项。|
|[SpinWait](spinwait.md)|描述 <xref:System.Threading.SpinWait?displayProperty=nameWithType> 类，它是一个级别较低的同步基元，可在启动基于内核的等待之前执行忙碌的旋转。|

## <a name="see-also"></a>请参阅

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [使用线程和线程处理](using-threads-and-threading.md)
- [异步文件 I/O](../io/asynchronous-file-i-o.md)
- [并行编程](../parallel-programming/index.md)
- [任务并行库 (TPL)](../parallel-programming/task-parallel-library-tpl.md)
