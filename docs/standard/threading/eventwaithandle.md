---
title: EventWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bd248133bd95ff05246eb36a8e250247fd7ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle"></a>EventWaitHandle
<xref:System.Threading.EventWaitHandle>类允许通过发送信号和等待信号相互通信的线程。 事件等待句柄 （也简称为事件） 是可以指示实时编码器以释放一个或多个正在等待的线程的等待句柄。 处于有信号状态后，手动或自动将重置事件等待句柄。 <xref:System.Threading.EventWaitHandle>类可以表示任一本地事件等待句柄 （本地事件） 或已命名的系统事件等待句柄 （名为事件或系统事件，对所有进程可见）。  
  
> [!NOTE]
>  事件等待句柄不是在通常是由.NET Framework 中的该单词的意义上的事件。 没有任何委托或事件处理程序所涉及。 Word"事件"用于描述它们，因为具有传统上已称其为操作系统事件，并且正在等待的线程的信号等待句柄 act 指示已发生事件。  
  
 这两个本地和命名事件等待句柄使用系统同步对象，因为它们受<xref:Microsoft.Win32.SafeHandles.SafeWaitHandle>包装器来确保释放资源。 你可以使用<xref:System.Threading.WaitHandle.Dispose%2A>方法以立即你完成使用对象时释放资源。  
  
## <a name="event-wait-handles-that-reset-automatically"></a>自动重置的事件等待句柄  
 通过指定创建的自动重置事件<xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType>创建时<xref:System.Threading.EventWaitHandle>对象。 顾名思义，此同步事件会自动重置时收到信号后释放单个正在等待的线程。 发出事件信号通过调用其<xref:System.Threading.EventWaitHandle.Set%2A>方法。  
  
 自动重置事件通常用于一次提供单个线程对资源的独占访问权。 线程通过调用请求资源<xref:System.Threading.WaitHandle.WaitOne%2A>方法。 如果没有其他线程持有等待句柄，该方法返回`true`和调用线程已对资源的控制。  
  
> [!IMPORTANT]
>  与所有的同步机制，必须确保，所有代码路径上的正确的都等待句柄之前都等待访问受保护的资源。 线程同步是协作性。  
  
 如果任何线程在不等待时收到信号的自动重置事件，它将一直终止线程尝试在其上等待。 该事件释放线程，并立即重置，阻止后面的线程。  
  
## <a name="event-wait-handles-that-reset-manually"></a>手动重置的事件等待句柄  
 通过指定创建手动重置事件<xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType>创建时<xref:System.Threading.EventWaitHandle>对象。 顾名思义，此同步事件必须是后手动重置已终止。 它被重置之前，通过调用其<xref:System.Threading.EventWaitHandle.Reset%2A>方法，等待的事件句柄的线程会立即继续而不阻止。  
  
 手动重置事件就像入口马棚。 当事件不处于终止状态时，阻止在其等待的线程，如同在马棚让马。 该事件已终止时，通过调用其<xref:System.Threading.EventWaitHandle.Set%2A>方法中，所有正在等待的线程都可以继续。 在事件未终止状态，直到其<xref:System.Threading.EventWaitHandle.Reset%2A>调用方法。 这使得手动重置事件理想的方式，可以保存最多需要等待，直到一个线程完成任务的线程。  
  
 如同让马离开马棚一样，则需要花时间的已发布的线程，以计划由操作系统并继续执行。 如果<xref:System.Threading.EventWaitHandle.Reset%2A>所有线程具有都继续执行之前调用方法，则其余的线程再次进行阻止。 哪些线程恢复和线程阻止取决于随机因素，如在系统上，线程数负载正在等待计划程序，等等。 如果发出事件信号的线程结束信号之后, 它是最常见的使用情况模式，则不出现问题。 如果你想终止的事件，别忘了开始新任务正在等待线程已恢复的线程，您必须具有在恢复所有正在等待的线程之前阻止它。 否则为有争用条件，并且你的代码的行为是不可预知。  
  
## <a name="features-common-to-automatic-and-manual-events"></a>对自动和手动事件都通用的功能  
 通常情况下，一个或多个线程阻止<xref:System.Threading.EventWaitHandle>直到取消阻止的线程调用<xref:System.Threading.EventWaitHandle.Set%2A>方法，该释放一个 （如果为自动重置事件） 正在等待的线程或所有这些方法 （如果是手动重置事件）。 线程都可以发送<xref:System.Threading.EventWaitHandle>，然后阻止它，以原子操作，通过调用静态<xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType>方法。  
  
 <xref:System.Threading.EventWaitHandle>对象可以用于静态<xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType>和<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>方法。 因为<xref:System.Threading.EventWaitHandle>和<xref:System.Threading.Mutex>类都派生自<xref:System.Threading.WaitHandle>，你可以使用这些方法使用这两个类。  
  
### <a name="named-events"></a>命名的事件  
 Windows 操作系统允许事件等待句柄可以具有的名称。 命名的事件是系统范围。 即，已命名的事件创建后，是可见的所有进程中的所有线程。 因此，命名的事件可用于同步进程以及线程的活动。  
  
 你可以创建<xref:System.Threading.EventWaitHandle>通过使用指定的事件名称的构造函数之一表示已命名的系统事件的对象。  
  
> [!NOTE]
>  因为命名的事件是系统范围，就可以有多个<xref:System.Threading.EventWaitHandle>表示相同的对象名为事件。 每次调用构造函数，或<xref:System.Threading.EventWaitHandle.OpenExisting%2A>方法时，新<xref:System.Threading.EventWaitHandle>创建对象。 反复指定相同的名称创建多个表示同一命名的事件的对象。  
  
 警告： 建议在使用名为事件。 因为它们是系统范围，则使用相同的名称的另一个进程可以意外阻止您的线程。 同一台计算机上的恶意代码执行可将此作为拒绝服务攻击的基础。  
  
 使用访问控制安全性来保护<xref:System.Threading.EventWaitHandle>表示命名的事件，最好是通过使用指定的构造函数的对象<xref:System.Security.AccessControl.EventWaitHandleSecurity>对象。 你还可以应用访问控件安全性使用<xref:System.Threading.EventWaitHandle.SetAccessControl%2A>方法，但这留出创建事件等待句柄的时间和受保护的时间之间的安全漏洞的一段。 保护事件使用访问控制安全性帮助阻止恶意攻击，但它不能解决的意外的名称冲突问题。  
  
> [!NOTE]
>  与不同<xref:System.Threading.EventWaitHandle>类，派生的类<xref:System.Threading.AutoResetEvent>和<xref:System.Threading.ManualResetEvent>可以表示仅为本地等待句柄。 它们不能表示已命名的系统事件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [EventWaitHandle、AutoResetEvent、CountdownEvent、ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
