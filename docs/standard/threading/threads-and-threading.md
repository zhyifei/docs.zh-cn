---
title: 线程与线程处理
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5049ed1b44155f3c21c53bef24a13006fe97a3fa
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452581"
---
# <a name="threads-and-threading"></a>线程与线程处理
操作系统使用进程隔开正在执行的不同应用。 线程是操作系统向其分配处理器时间的基本单位，在相应进程内多个线程可以同时执行代码。 每个线程负责维护异常处理程序、计划优先级，以及系统用来保存被排入计划前线程上下文的一组结构。 线程上下文包含线程在其主机进程地址空间中顺畅继续执行所需的全部信息，包括线程的一组 CPU 寄存器和堆栈。  
  
 .NET Framework 将操作系统进程进一步细分为轻型托管子进程，称为“应用域”（由 <xref:System.AppDomain?displayProperty=nameWithType> 表示）。 一个或多个托管线程（由 <xref:System.Threading.Thread?displayProperty=nameWithType> 表示）可以在同一个托管进程内的一个或任意多个应用域中运行。 尽管每个应用域一开始都只有一个线程，但相应应用域中的代码可能会创建其他应用域和其他线程。 因此，托管线程可以在同一个托管进程内的不同应用域之间自由移动；可能只有一个线程在多个应用域之间移动。  
  
 支持强占式多任务的操作系统造成的效应是，同时执行多个进程中的多个线程。 为此，它在有需求的线程之间分配可用处理器时间，相继向每个线程分配处理器时间片。 当前正在执行的线程在时间片结束后暂停，另一个线程继续运行。 如果系统从一个线程切换到另一个线程，它会保存强占线程的线程上下文，并重载线程队列中下一个线程的已保存线程上下文。  
  
 时间片长度具体视操作系统和处理器而定。 由于每个时间片都很小，因此即使只有一个处理器，多个线程也可能同时执行。 多处理器系统实际上正是如此，可执行线程在可用处理器之间进行分配。  
  
## <a name="when-to-use-multiple-threads"></a>何时使用多个线程  
 如果软件需要用户交互，必须尽可能快地回应用户活动，以便于提供丰富的用户体验。 然而，与此同时，它还必须执行必要的计算，以尽可能快地向用户呈现数据。 如果应用仅使用一个执行线程，可以结合使用[异步编程](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)和 [.NET Framework 远程处理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))或使用 ASP.NET 创建的 [XML Web 服务](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))，这样不仅可以使用自己计算机的处理时间，还能使用其他计算机的处理时间，以提高响应用户的速度，并减少应用的数据处理时间。 若要执行大量输入/输出工作，还可以使用 I/O 完成端口，以提高应用的响应速度。  
  
### <a name="advantages-of-multiple-threads"></a>多个线程的优势  
 不过，使用多个线程是目前功能最强大的方法，不仅可以提高响应用户的速度，还能在几乎同时处理必要数据来完成工作。 在具有一个处理器的计算机上，多个线程可以造成这样的效应，具体是通过利用用户事件之间的短时间段在后台处理数据。 例如，用户可以编辑电子表格，同时另一个线程正在重新计算同一应用中此电子表格的其他部分。  
  
 无需修改，同一应用会在具有多个处理器的计算机上运行时，显著提高用户满意度。 一个应用域可以使用多个线程来完成下列任务：  
  
-   通过网络与 Web 服务器和数据库通信。  
  
-   执行耗时很长的操作。  
  
-   区分不同优先级的任务。 例如，高优先级线程管理时间要求严格的任务，低优先级线程执行其他任务。  
  
-   让用户界面能够一直响应用户，同时为后台任务分配时间。  
  
### <a name="disadvantages-of-multiple-threads"></a>多个线程的缺点  
 建议尽量少使用线程，这样可以最大限度地减少使用操作系统资源，并提升性能。 线程处理也有资源要求和潜在冲突，需要在设计应用时纳入考虑范围。 资源要求如下：  
  
-   系统使用内存来保存进程、AppDomain 对象和线程所需的上下文信息。 因此，可以创建的进程数、AppDomain 对象数和线程数受可用内存限制。  
  
-   跟踪大量线程会消耗非常多的处理器时间。 如果线程太多，其中大多数都不会取得重大进展。 如果当前大多数线程都位于同一个进程中，那么其他进程中的线程被排入计划的频率会变低。  
  
-   控制包含多个线程的代码执行非常复杂，可能会导致许多 bug 出现。  
  
-   若要销毁线程，必须了解可能会发生的情况，并处理这些问题。  
  
 提供对资源的共享访问权限可能会产生冲突。 为避免冲突，必须同步或控制对共享资源的访问。 如果无法正确同步访问（在相同或不同的应用域中），可能会导致问题发生，如死锁（在一个线程等待另一个线程完成时，两个线程停止响应）和争用条件（由于意外严重依赖两个事件的时间而导致的异常后果）。 系统提供同步对象，可用于协调多个线程之间的资源共享。 减少线程数量可以简化资源同步。  
  
 需要同步的资源包括：  
  
-   系统资源（如通信端口）。  
  
-   多个进程共享的资源（如文件句柄）。  
  
-   多个线程访问的一个应用域的资源（如全局字段、静态字段和实例字段）。  
  
### <a name="threading-and-application-design"></a>线程处理和应用设计  
 一般来说，若要处理多个线程，以完成耗时相对较短且不会阻止其他线程的任务，且无需对任务有任何特定的计划，使用 <xref:System.Threading.ThreadPool> 类是最简单的方法。 不过，鉴于多种原因，也可以创建自己的线程：  
  
-   如果需要任务有特定的优先级。  
  
-   如果有运行时间可能很长（因此可能会阻止其他任务）的任务。  
  
-   如果需要将线程添加到单线程单元（所有 ThreadPool 线程都位于多线程单元中）。  
  
-   如果需要与线程相关联的稳定标识。 例如，应使用专用线程，以中止相应线程、暂停它或按名称发现它。  
  
-   如果需要运行与用户界面交互的后台线程，.NET Framework 版本 2.0 提供了 <xref:System.ComponentModel.BackgroundWorker> 组件，以使用事件和跨线程封送与用户界面线程进行通信。  
  
### <a name="threading-and-exceptions"></a>线程处理和异常  
 请务必处理线程异常。 未经处理的线程（甚至后台线程）异常通常会终止进程。 以下为此规则的三种例外情况：  
  
-   由于 <xref:System.Threading.Thread.Abort%2A> 得到调用，因此 <xref:System.Threading.ThreadAbortException> 在线程中抛出。  
  
-   由于正在卸载应用域，因此线程抛出 <xref:System.AppDomainUnloadedException>。  
  
-   公共语言运行时或主机进程将终止该线程。  
  
 有关详细信息，请参阅[托管线程异常](../../../docs/standard/threading/exceptions-in-managed-threads.md)。  
  
> [!NOTE]
>  在 .NET framework 版本 1.0 和 1.1 中，公共语言运行时以无提示方式捕获一些异常，例如线程池中的线程异常。 这可能会损坏应用状态，并最终导致应用挂起，此问题的调试难度非常大。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Threading.ThreadPool>  
- <xref:System.ComponentModel.BackgroundWorker>  
- [为多线程处理同步数据](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
- [托管线程池](../../../docs/standard/threading/the-managed-thread-pool.md)
