---
title: 线程处理对象和功能
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02f88faab6ddbaa026e73ad61bc63fbe8e5e00ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="threading-objects-and-features"></a>线程处理对象和功能
.NET Framework 提供许多对象，有助于你创建和管理多线程应用程序。 托管线程通过 <xref:System.Threading.Thread> 类表示。 <xref:System.Threading.ThreadPool> 类可以轻松创建和管理多线程后台任务。 <xref:System.ComponentModel.BackgroundWorker> 类执行的任务和与用户界面交互的任务相同。 <xref:System.Threading.Timer> 类可在指定的时间间隔内执行后台任务。  
  
 此外，还有许多类可同步激活线程，包括 .NET Framework 2.0 版中引入的 <xref:System.Threading.Semaphore> 和 <xref:System.Threading.EventWaitHandle> 类。 [同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)中对这些类的功能进行了比较。  
  
## <a name="in-this-section"></a>本节内容  
 [托管线程池](../../../docs/standard/threading/the-managed-thread-pool.md)  
 介绍 **ThreadPool** 类，可以通过该类请求线程执行任务，而无须自行执行任何线程管理。  
  
 [计时器](../../../docs/standard/threading/timers.md)  
 介绍如何使用**计时器**指定在指定的时间调用委派。  
  
 [监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 介绍如何使用**监视器**类同步访问成员或创建自己的线程管理类型。  
  
 [等待句柄](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 描述 <xref:System.Threading.WaitHandle> 类、事件等待句柄的抽象基类、互斥体和可以等待多个同步事件的信号量。  
  
 [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 描述用于通过发送和等待信号同步线程活动的托管事件等待句柄。  
  
 [Mutex](../../../docs/standard/threading/mutexes.md)  
 介绍了如何使用 <xref:System.Threading.Mutex> 同步访问对象或生成自己的同步机制。  
  
 [互锁操作](../../../docs/standard/threading/interlocked-operations.md)  
 说明如何使用 <xref:System.Threading.Interlocked> 类递增或递减值和以单原子操作存储值。  
  
 [读取器-编写器锁](../../../docs/standard/threading/reader-writer-locks.md)  
 定义可实现单个编写器/多个读取器语义的锁。  
  
 [Semaphore 和 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 描述 <xref:System.Threading.Semaphore> 对象并说明如何使用这些对象控制对有限资源的访问权限。  
  
 [同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 比较提供用于锁定和同步托管线程的 .NET Framework 类的功能。  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 描述 <xref:System.Threading.Barrier> 对象，这些对象可实现分阶段操作中的线程协调屏障模式。  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 描述 <xref:System.Threading.SpinLock>，某些低级别方案的监视器类的轻型替代项。  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 描述 <xref:System.Threading.SpinWait>，一个级别较低的同步基元，可在启动基于内核的等待之前执行忙碌的旋转。  
  
## <a name="reference"></a>参考  
 <xref:System.Threading.Thread>  
 提供**线程**类的参考文档，无论该类是来自托管代码还是在托管应用程序中创建的，它都表示一个托管线程。  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 启用与用户界面交互的后台任务，通过用户界面线程上引发的事件进行通信。  
  
## <a name="related-sections"></a>相关章节  
 [异步文件 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 描述 I/O 异步完成端口如何使用线程池处理（仅在输入/输出操作完成时，才需要）。  
  
 [任务并行库 (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 描述 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 及更高版本中建议的多线程编程的方法。
