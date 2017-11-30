---
title: "线程与线程处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a>线程与线程处理
操作系统使用进程分隔一起执行的不同应用程序。 线程是操作系统向其分配处理器时间的基本单元和多个线程可执行该过程内的代码。 每个线程都维持异常处理程序、 计划的优先级别和一组系统使用保存的线程上下文，直到为计划的结构。 线程上下文包括线程需要无缝地继续执行，包括 CPU 寄存器和堆栈的线程的一组线程的主机进程的地址空间中的所有信息。  
  
 .NET Framework 进一步细分为轻量的托管子进程，调用应用程序域，由表示的操作系统进程<xref:System.AppDomain?displayProperty=nameWithType>。 一个或多个托管的线程 (由表示<xref:System.Threading.Thread?displayProperty=nameWithType>) 可以在任何数目的相同的托管进程内的应用程序域中运行。 尽管每个应用程序域开始使用单线程，该应用程序域中的代码可以创建其他应用程序域和其他线程。 结果是一个托管的线程可以自由移动在相同的托管过程; 的应用程序域之间你可能必须只有一个线程在多个应用程序域之间切换。  
  
 支持强占式多任务操作系统从多个进程创建的多个线程同时执行的效果。 此，它会将需要它在线程之间的可用的处理器时间、 依次分配到每个线程的处理器时间切片。 其时间片结束，而另一个线程继续运行时挂起当前正在执行的线程。 当系统从一个线程切换到另一个时，它将保存已抢占线程的线程上下文，并重新加载线程队列中的下一个线程的已保存的线程上下文。  
  
 时间段的长度取决于操作系统和处理器。 因为每个时间段很小，多个线程看起来似乎相同次执行即使只有一个处理器。 这是实际在多处理器系统中，这种情况在可用的处理器之间分发可执行的线程的位置。  
  
## <a name="when-to-use-multiple-threads"></a>何时使用多个线程  
 需要用户交互的软件必须尽可能提供丰富的用户体验最快响应用户的活动。 在同一时间，但是，它必须执行必要的计算来向用户尽可能快地显示数据。 如果你的应用程序使用只有一个线程的执行，你可以组合[异步编程](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)与[.NET Framework 远程处理](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)或[XML Web services](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)使用 ASP 创建若要使用的其他计算机的处理时间此外于给用户，并减少你的应用程序的数据处理时间你自己以提高响应能力的.NET。 如果你正在密集型的输入/输出工作，你可以使用 I/O 完成端口以提高应用程序的响应能力。  
  
### <a name="advantages-of-multiple-threads"></a>多个线程的优点  
 使用多个线程，但是，是最强大的技术可用于增加对用户的响应能力和处理几乎同时完成工作所必需的数据。 具有一个处理器的计算机，在多个线程可以创建此效果，请利用很小的用户事件，以处理在后台的数据之间的时间段。 例如，用户可以编辑电子表格，而另一个线程正在重新计算同一个应用程序中的电子表格的其他部分。  
  
 而不进行修改，同一个应用程序任务会急剧增加用户满意度当在具有多个处理器的计算机上运行。 单个应用程序域可以使用多个线程来完成以下任务：  
  
-   通过网络，到 Web 服务器和数据库进行通信。  
  
-   执行需要大量的时间的操作。  
  
-   区分具有不同优先级的任务。 例如，优先级较高的线程管理时间关键任务，而低优先级的线程执行其他任务。  
  
-   允许用户界面以保持响应度，分配到的后台任务的时间时。  
  
### <a name="disadvantages-of-multiple-threads"></a>多个线程的缺点  
 建议你使用尽可能少的线程，从而最小化操作系统资源的使用和提高性能。 线程处理还具有要设计你的应用程序时考虑的资源要求和潜在的冲突。 资源要求如下所示：  
  
-   系统使用的内存的进程，所需的上下文信息**AppDomain**对象和线程。 因此，进程，数**AppDomain**对象和可以创建的线程受可用内存的限制。  
  
-   跟踪的大量的线程将占用大量的处理器时间。 如果有线程过多，其中大多数都不会明显的进度。 如果当前线程的大多数都在一个进程，其他进程中的线程计划频率较低。  
  
-   控制使用多线程代码执行复杂，并且可以是多个 bug 的源。  
  
-   销毁线程需要了解可能发生和处理这些问题。  
  
 提供对资源的共享访问权限会造成冲突。 若要避免冲突，你必须同步，或控制对共享资源的访问。 正确 （在相同或不同的应用程序域中） 的访问进行同步的失败可能导致问题，例如死锁 （中的两个线程停止响应每个等待另一个用于完成时） 和 （异常结果发生时争用条件意外严重依赖于两个事件的计时）。 系统提供了可用于协调多个线程间共享的资源的同步对象。 减少的线程数，使更轻松地将资源同步。  
  
 需要同步的资源包括：  
  
-   系统资源 （如通信的端口）。  
  
-   由 （如文件句柄） 的多个进程共享的资源。  
  
-   单个应用程序域的资源 (如全局、 静态和实例字段) 多个线程访问。  
  
### <a name="threading-and-application-design"></a>线程处理和应用程序设计  
 一般情况下，使用<xref:System.Threading.ThreadPool>类是最简单的方法来处理多个线程相对较短的任务不会阻止其他线程，并且当你不期待的任务的任何特定的计划。 但是，有多种原因需要创建您自己的线程：  
  
-   如果你需要具有特定优先级的任务。  
  
-   如果你有一个任务，它可能运行较长时间 （并因此阻止其他任务）。  
  
-   如果你需要将线程放入单线程单元 (所有**线程池**线程处于多线程单元)。  
  
-   如果你需要与线程关联的稳定标识。 例如，应使用的专用的线程中止该线程，挂起，或按名称发现它。  
  
-   如果你需要运行与用户界面交互的后台线程，.NET Framework 2.0 版提供了<xref:System.ComponentModel.BackgroundWorker>与跨线程封送到的用户界面线程中使用事件，进行通信的组件。  
  
### <a name="threading-and-exceptions"></a>线程处理和异常  
 不要处理线程中的异常。 中的线程，甚至是后台线程中未经处理的异常通常会终止进程。 以下为此规则的三种例外情况：  
  
-   A<xref:System.Threading.ThreadAbortException>线程中引发，因为<xref:System.Threading.Thread.Abort%2A>调用。  
  
-   <xref:System.AppDomainUnloadedException>线程中引发，因为应用程序域是否正在卸载。  
  
-   公共语言运行时或主机进程将终止该线程。  
  
 有关详细信息，请参阅[托管线程中的异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)。  
  
> [!NOTE]
>  在.NET framework 1.0 和 1.1 版中，公共语言运行时将以无提示方式捕获一些例外情况，例如在线程池线程。 这可能会损坏应用程序状态并最终导致应用程序挂起，这可能是很难进行调试。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [为多线程处理同步数据](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [托管线程池](../../../docs/standard/threading/the-managed-thread-pool.md)
