---
title: Mutexes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>Mutexes
你可以使用<xref:System.Threading.Mutex>来提供对资源的独占访问的对象。 <xref:System.Threading.Mutex>类使用的详细的系统资源比<xref:System.Threading.Monitor>类，但它可以封送跨应用程序域边界，它可以用于多个等待，并且它可以用于同步不同的进程中的线程。 有关托管同步机制的比较，请参阅[同步基元概述](../../../docs/standard/threading/overview-of-synchronization-primitives.md)。  
  
 有关代码示例，请参阅的参考文档<xref:System.Threading.Mutex.%23ctor%2A>构造函数。  
  
## <a name="using-mutexes"></a>使用 Mutex  
 线程调用<xref:System.Threading.WaitHandle.WaitOne%2A>请求所有权互斥体的方法。 在 mutex 可用或可选超时间隔结束前，该调用会一直处于阻止状态。 如果没有任何线程拥有它，则 mutex 将处于已发出信号状态。  
  
 一个线程释放互斥体通过调用其<xref:System.Threading.Mutex.ReleaseMutex%2A>方法。 Mutex 具有线程关联；即 mutex 只能由拥有它的线程释放。 如果一个线程释放互斥体不拥有，<xref:System.ApplicationException>线程中引发。  
  
 因为<xref:System.Threading.Mutex>类派生自<xref:System.Threading.WaitHandle>，你还可以调用静态<xref:System.Threading.WaitHandle.WaitAll%2A>或<xref:System.Threading.WaitHandle.WaitAny%2A>方法<xref:System.Threading.WaitHandle>请求所有权的<xref:System.Threading.Mutex>与其他结合使用等待句柄。  
  
 如果一个线程拥有<xref:System.Threading.Mutex>，线程可以指定相同<xref:System.Threading.Mutex>中重复的等待请求在调用而不会阻止其执行; 但是，它必须释放<xref:System.Threading.Mutex>尽可能多的次数，以释放所有权。  
  
## <a name="abandoned-mutexes"></a>放弃的 mutex  
 如果某个线程终止而不释放<xref:System.Threading.Mutex>，则认为该 mutex 来放弃。 这通常指示存在严重的编程错误，因为该 mutex 正在保护的资源可能会处于不一致状态。 在.NET Framework 2.0 版中，<xref:System.Threading.AbandonedMutexException>获取互斥体的下一个线程中引发。  
  
> [!NOTE]
>  在.NET framework 1.0 和 1.1 中，放弃的<xref:System.Threading.Mutex>正在设置为终止的状态和下一个等待线程获取所有权。 如果任何线程在不等待，<xref:System.Threading.Mutex>仍保留在发送信号状态。 不引发异常。  
  
 对于系统范围的 mutex，放弃的 mutex 可能指示应用程序已突然终止（例如，通过使用 Windows 任务管理器终止）。  
  
## <a name="local-and-system-mutexes"></a>本地 mutex 和系统 mutex  
 Mutex 有两种类型：本地 mutex 和命名系统 mutex。 如果你创建<xref:System.Threading.Mutex>对象使用构造函数接受一个名称，它是与该名称的操作系统对象相关联。 命名系统 mutex 在整个操作系统中都可见，并且可用于同步进程活动。 你可以创建多个<xref:System.Threading.Mutex>对象来表示同一个已命名系统互斥体，并且你可以使用<xref:System.Threading.Mutex.OpenExisting%2A>方法以打开一个现有的已命名系统互斥体。  
  
 本地 mutex 仅存在于进程中。 它可供你具有到本地的引用的过程中的任何线程<xref:System.Threading.Mutex>对象。 每个<xref:System.Threading.Mutex>对象是单独的局部互斥体。  
  
### <a name="access-control-security-for-system-mutexes"></a>系统 mutex 的访问控制安全性  
 .NET Framework 2.0 版提供查询和设置命名系统对象的 Windows 访问控制安全性的能力。 建议从创建起立刻开始保护系统 mutex，因为系统对象是全局对象，因此可能被不是你自己的代码锁定。  
  
 互斥体的访问控制安全性的信息，请参阅<xref:System.Security.AccessControl.MutexSecurity>和<xref:System.Security.AccessControl.MutexAccessRule>类，<xref:System.Security.AccessControl.MutexRights>枚举， <xref:System.Threading.Mutex.GetAccessControl%2A>， <xref:System.Threading.Mutex.SetAccessControl%2A>，和<xref:System.Threading.Mutex.OpenExisting%2A>方法<xref:System.Threading.Mutex>类，并且<xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>构造函数。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [线程处理](../../../docs/standard/threading/index.md)  
 [线程处理对象和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [监视器](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [线程与线程处理](../../../docs/standard/threading/threads-and-threading.md)
