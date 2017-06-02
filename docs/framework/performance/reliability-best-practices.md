---
title: "可靠性最佳做法 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "异步异常处理"
  - "退出代码"
  - "块, 可靠性"
  - "捕捉块"
  - "CER"
  - "清理操作"
  - "受约束的执行区域"
  - "跨应用程序域共享状态"
  - "拒绝服务攻击"
  - "纤程"
  - "终结器, 可靠性"
  - "finally 语句"
  - "GC.KeepAlive 方法"
  - "识别锁"
  - "模拟"
  - "泄漏资源 [.NET Framework]"
  - "锁定, 可靠性"
  - "托管线程处理"
  - "标记锁"
  - "内存, 可靠性"
  - "进程范围的域共享状态"
  - "重新启动数据库"
  - "可靠性 [.NET Framework]"
  - "可靠性协定 [.NET Framework]"
  - "SafeHandle 类, 可靠性"
  - "共享状态"
  - "单线程 COM 组件"
  - "缓慢泄漏"
  - "SQL Server [.NET Framework], 可靠性"
  - "依赖 STA 的功能"
  - "挂起线程"
  - "同步, 可靠性"
  - "线程处理 [.NET Framework], 可靠性"
  - "非托管内存"
  - "编写可靠代码"
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# 可靠性最佳做法
下列可靠性规则是面向 SQL Server 的；但它们也适用于任何基于宿主的服务器应用程序。  对于 SQL Server 这类服务器而言，不泄漏资源且不降低性能极其重要。但是，并不能通过为每个更改对象状态的方法编写退出代码来实现这两个目标。我们的目标不是编写 100％ 可靠并能够通过退出代码从任意位置的任何错误中进行恢复的托管代码。那样做的话任务过于艰巨，且成功的可能性微乎其微。公共语言运行时 \(CLR\) 难以为托管代码提供足够强的保证，因此要编写完美的代码很不现实。注意，与 ASP.NET 不同，SQL Server 仅使用一个进程，且只有将数据库关闭一段时间后才能回收该进程，而且这段时间长得不可接受。  
  
 由于这些保证较弱且又以单进程运行，因此要实现可靠性，则需要在必要时终止线程或回收应用程序域，并且采取预防措施来确保不泄漏操作系统资源（如句柄或内存）。即使在这样较为简单的可靠性约束下，仍然存在一个非常重要的可靠性要求：  
  
-   任何情况下都不要泄漏操作系统资源。  
  
-   向 CLR 标识所有形式的所有托管锁。  
  
-   任何情况下都不要破坏跨应用程序域共享状态，以便使 <xref:System.AppDomain> 回收顺利进行。  
  
 尽管理论上可以编写托管代码来处理 <xref:System.Threading.ThreadAbortException>、<xref:System.StackOverflowException> 和 <xref:System.OutOfMemoryException> 异常，但希望开发人员在整个应用程序范围内编写这样可靠的代码则很不切实际。因此，带外异常会导致执行线程终止；如果被终止的线程正在编辑共享状态（可由该线程是否持有锁来确定），则 <xref:System.AppDomain> 会被卸载。正在编辑共享状态的方法终止时，共享状态会被损坏，因为无法编写可靠的退出代码来更新共享状态。  
  
 在 .NET Framework 2.0 版中，SQL Server 是唯一有可靠性要求的宿主。如果程序集将在 SQL Server 上运行，那么即使某些特定功能在数据库中运行时是禁用的，也应对该程序集的每个部分进行可靠性处理。之所以必须这样做，是因为代码分析引擎在程序集级别检查代码，无法区分出禁用的代码。  进行 SQL Server 编程时还有一点需要注意，即 SQL Server 是在一个进程中运行所有内容，并使用 <xref:System.AppDomain> 回收清理所有资源（如内存和操作系统句柄）。  
  
 不能依赖于终结器、析构函数或 `try/finally` 块作为退出代码。  它们可能会被中断或不被调用。  
  
 异步异常可在意外的位置引发，并且可能由每个计算机指令引发：<xref:System.Threading.ThreadAbortException>、<xref:System.StackOverflowException> 和 <xref:System.OutOfMemoryException>。  
  
 托管线程不一定是 SQL 中的 Win32 线程；也可能是纤程。  
  
 很难安全更改进程范围或跨应用程序域的可变共享状态，因此应尽可能避免此类操作。  
  
 内存不足的情况在 SQL Server 中并不少见。  
  
 如果寄宿在 SQL Server 中的库没有正确地更新其共享状态，代码就很可能不会在数据库重新启动前恢复。此外，在某些极端情况下，还可能导致 SQL Server 进程失败，使数据库重新启动。重新启动数据库可使网站关闭或影响公司运营，从而影响可用性。操作系统资源（如内存或句柄）的缓慢泄漏可能导致服务器最终无法分配句柄并且无法恢复，也可能导致服务器的性能缓慢下降并使客户应用程序可用性降低。很显然我们要避免这类情况。  
  
## 最佳做法规则  
 要重点介绍的是，为了提高框架的稳定性和可靠性，在对服务器中运行的托管代码进行代码检查时必须捕捉什么。  所有这些检查通常都是良好的做法，而且绝对必须在服务器上进行。  
  
 遇到死锁或资源约束时，SQL Server 将中止线程或拆开 <xref:System.AppDomain>。发生这种情况时，仅保证运行受约束执行区域 \(CER\) 中的退出代码。  
  
### 使用 SafeHandle 避免资源泄漏  
 <xref:System.AppDomain> 被卸载的情况下，不能依赖 `finally` 块或终结器的执行，因此，通过 <xref:System.Runtime.InteropServices.SafeHandle> 类而不是 <xref:System.IntPtr>、<xref:System.Runtime.InteropServices.HandleRef> 或类似的类来抽象所有操作系统资源访问就很重要。  这样可使 CLR 跟踪和关闭您使用的句柄，甚至是在 <xref:System.AppDomain> 拆分的情况下，<xref:System.Runtime.InteropServices.SafeHandle> 将使用 CLR 始终运行的关键终结器。  
  
 操作系统句柄从创建时起至释放前都存储在安全句柄中。任何窗口中都不会出现引发句柄泄漏的 <xref:System.Threading.ThreadAbortException>。此外，平台调用将对句柄进行引用计数（这样可密切跟踪句柄的生存期），通过 `Dispose` 与当前使用该句柄的方法之间的争用条件来防止安全性问题的出现。  
  
 当前仅使用终结器清理操作系统句柄的大多数类将不再需要终结器。  <xref:System.Runtime.InteropServices.SafeHandle> 派生类才使用终结器。  
  
 注意，<xref:System.Runtime.InteropServices.SafeHandle> 并不替换 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>。显式释放操作系统资源还可能具有处理资源争用和提高性能的优点。注意，显式释放资源的 `finally` 块可能不会完全执行。  
  
 <xref:System.Runtime.InteropServices.SafeHandle> 允许实现您自己的 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法来执行释放句柄的工作，如将状态传递给释放例程的操作系统句柄或释放循环中的一组句柄。CLR 保证此方法的运行。确保句柄在任何情况下都能得到释放是实现 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 的创作者的责任。  如果不这样做，则会导致句柄泄漏，通常也会因此导致与句柄关联的本机资源泄漏。  因此，构造 <xref:System.Runtime.InteropServices.SafeHandle> 派生类使 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 实现不要求分配任何在调用时不可用的资源是非常重要的。  注意，可以在 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 的实现中调用可能失败的方法，但要求您自己的代码能够处理此类失败并完成释放本机句柄的约定。  为了进行调试，<xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 具有一个 <xref:System.Boolean> 返回值，如果遇到阻止资源释放的灾难性错误，该值会被设置为 `false`。  这样可激活 [releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md) MDA（如果启用）以协助确定问题。  它不以任何其他方式影响运行时；对于同一资源将不再调用 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>，因此会导致句柄泄漏。  
  
 <xref:System.Runtime.InteropServices.SafeHandle> 不适用于某些上下文。由于 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法可以在 <xref:System.GC> 终结器线程上使用，因此，任何需要在特定线程上释放的句柄都不应包装在 <xref:System.Runtime.InteropServices.SafeHandle> 中。  
  
 运行时可调用包装 \(RCW\) 无需其他代码即可由 CLR 清理。对于使用平台调用并将 COM 对象作为 `IUnknown*` 或 <xref:System.IntPtr>处理的代码，应重新编写代码以使用 RCW。<xref:System.Runtime.InteropServices.SafeHandle> 可能不能满足此方案，由于回调入托管代码的非托管释放方法的可能性。  
  
#### 代码分析规则  
 使用 <xref:System.Runtime.InteropServices.SafeHandle> 封装操作系统资源。  不要使用 <xref:System.Runtime.InteropServices.HandleRef> 或 <xref:System.IntPtr> 类型的字段。  
  
### 确保不必运行终结器防也可防止操作系统资源泄漏  
 仔细检查终结器，确保即使不运行这些它们也不会泄漏重要的操作系统资源。与应用程序在稳定状态下执行时或 SQL Server 等服务器关闭时的正常 <xref:System.AppDomain> 卸载不同，突然的 <xref:System.AppDomain> 卸载期间对象不会终结。要确保资源在突然卸载的情况下不会泄漏，因为不能保证应用程序的正确性，但却必须通过不泄漏资源来维持服务器的完整性。可使用 <xref:System.Runtime.InteropServices.SafeHandle> 释放所有操作系统资源。  
  
### 确保不必运行 finally 子句也可防止操作系统资源泄漏  
 `finally` 子句不能保证在 CER 之外也能运行，这要求库开发人员不要依赖 `finally` 块中的代码来释放非托管资源。建议的解决方案是使用 <xref:System.Runtime.InteropServices.SafeHandle>。  
  
#### 代码分析规则  
 使用 <xref:System.Runtime.InteropServices.SafeHandle> 而不要使用 `Finalize` 来清理操作系统资源。  不要使用 <xref:System.IntPtr>；应使用 <xref:System.Runtime.InteropServices.SafeHandle> 封装资源。  如果必须运行 finally 子句，请将其放置在 CER 中。  
  
### 所有的锁应遍历现有托管锁定代码  
 CLR 必须知道代码何时锁定，这样才会知道停止 <xref:System.AppDomain> 而不仅仅是中止线程。中止线程可能会有危险，因为线程操作的数据所保留的状态可能不一致。  因此，必须回收整个 <xref:System.AppDomain>。未能识别锁可能造成死锁或错误的结果。  使用 <xref:System.Threading.Thread.BeginCriticalRegion%2A> 和 <xref:System.Threading.Thread.EndCriticalRegion%2A> 方法可识别锁区域。这两个方法是 <xref:System.Threading.Thread> 类的静态方法，仅应用于当前线程，有助于防止线程编辑其他线程的锁计数。  
  
 <xref:System.Threading.Monitor.Enter%2A> 和 <xref:System.Threading.Monitor.Exit%2A> 内置此 CLR 通知，因此建议使用这些方法和 [“锁定”语句](../Topic/lock%20Statement%20\(C%23%20Reference\).md)（该语句使用这些方法）。  
  
 其他锁定机制（如数值调节锁和 <xref:System.Threading.AutoResetEvent>）必须调用这些方法来通知 CLR 已进入临界区。这些方法不使用任何锁；它们通知 CLR 代码正在临界区中执行，中止线程可能会使共享状态不一致。如果定义了自己的锁类型，如自定义 <xref:System.Threading.ReaderWriterLock> 类，请使用这些锁计数方法。  
  
#### 代码分析规则  
 使用 <xref:System.Threading.Thread.BeginCriticalRegion%2A> 和 <xref:System.Threading.Thread.EndCriticalRegion%2A> 标记和识别所有锁。  不要在循环中使用 <xref:System.Threading.Interlocked.CompareExchange%2A>、<xref:System.Threading.Interlocked.Increment%2A> 和 <xref:System.Threading.Interlocked.Decrement%2A>。不要对这些方法的 Win32 变量执行平台调用。不要在循环中使用 <xref:System.Threading.Thread.Sleep%2A>。不要使用可变字段。  
  
### 清除代码必须位处于 finally 或 catch 块中，不能处于 catch 之后  
 任何情况下清除代码都不应在 `catch` 块后；而应在 `finally` 或 `catch` 块中。这应该成为标准的良好做法。通常首选使用 `finally` 块，因为它在异常引发和正常到达 `try` 块末尾时运行相同的代码。如果引发了意外的异常，如 <xref:System.Threading.ThreadAbortException>，清除代码将不会运行。要防止泄漏，最好将所有要在 `finally` 中清理的非托管资源包装在 <xref:System.Runtime.InteropServices.SafeHandle> 中。注意，C\# `using` 关键字可用来有效地释放对象（包括句柄）。  
  
 尽管 <xref:System.AppDomain> 回收可以清理终结器线程的资源，将清除代码位置在正确的位置仍很重要。注意，如果线程接收到异步异常但没有锁，则 CLR 尝试自行结束线程，而不回收 <xref:System.AppDomain>。确保尽早清理资源可使更多资源可用，也能更好地管理生存期。如果不在某一错误代码路径中显式关闭文件的句柄，然后等待 <xref:System.Runtime.InteropServices.SafeHandle> 终结器将其清理，则下次代码运行时，如果终结器尚未运行，访问该文件的尝试就可能失败。因此，即使不是严格必要的，确保清理代码存在并能正确工作也有助于更加快速顺利地从故障中恢复。  
  
#### 代码分析规则  
 `catch` 后的清理代码应在 `finally` 块中。  在最后一个块放置一个调用来处理，`catch` 块应以引发或再次引发结束。可能存在异常时，例如检测是否可以建立网络连接的代码（这种情况下可能会出现大量异常中的任一个），任何需要在正常情况下捕捉异常的代码都应该给出指示，说明应对代码进行测试以验证其是否能成功执行。  
  
### 应用程序域之间的进程范围的可变共享状态应被清除，或使用受约束执行区域  
 如介绍所述，要以可靠的方式编写托管代码来监视应用程序域之间进程范围的共享状态是很困难的。进程范围共享状态是应用程序域之间共享的任意数据结构，可以在 Win32 代码中、CLR 中，也可以在使用远程处理的托管代码中。任何可变共享状态都很难在托管代码中正确编写，任何静态共享状态也只能极小心地进行处理。如果具有进程范围或计算机范围的共享状态，请找出某种方法来将其清除或使用受约束执行区域 \(CER\) 保护该共享状态。注意，如果库具有未被识别和纠正的共享状态，则可能使需要清理 <xref:System.AppDomain> 卸载的宿主（如 SQL Server）崩溃。  
  
 如果代码使用 COM 对象，请避免在应用程序域之间共享该 COM 对象。  
  
### 锁在进程范围或应用程序域之间不起作用。  
 过去，<xref:System.Threading.Monitor.Enter%2A> 和 [“锁定”语句](../Topic/lock%20Statement%20\(C%23%20Reference\).md) 用于创建全局进程锁。例如，在 <xref:System.AppDomain> 灵活类（例如，非共享程序集的 <xref:System.Type> 实例、<xref:System.Threading.Thread> 对象、暂留的字符串，以及一些使用远程处理在应用程序域之间共享的字符串）上锁定时则会这样做。这些锁不再是进程范围的。若要知道是否存在进程范围跨应用程序域锁，请确定锁中的代码是否使用了任何持久性外部资源，如磁盘上的文件或数据库。  
  
 注意，如果受保护的代码使用了外部资源，在 <xref:System.AppDomain> 中采用锁则可能引起问题，因为该代码可能跨多个应用程序域同时运行。向一个日志文件写入或绑定到整个进程的套接字时，这可能是个问题。这些更改意味着通过使用托管代码而不是使用命名的 <xref:System.Threading.Mutex> 或 <xref:System.Threading.Semaphore> 实例获取进程全局锁没有简单的方法。请创建不在两个应用程序域中同步运行的代码，或使用 <xref:System.Threading.Mutex> 或 <xref:System.Threading.Semaphore> 类。如果不能更改现有代码，请不要使用 Win32 命名 Mutex 来实现此同步，因为在纤程模式中运行意味着无法保证同一操作系统线程会获取和释放一个 Mutex。必须使用托管 <xref:System.Threading.Mutex> 类或命名的 <xref:System.Threading.ManualResetEvent>、<xref:System.Threading.AutoResetEvent> 或 <xref:System.Threading.Semaphore> 以 CLR 能识别的方式来同步代码锁，而不是使用非托管代码同步锁。  
  
#### 避免 lock\(typeof\(MyType\)\)  
 共享程序集中仅具有一份跨所有应用程序域的共享代码副本的私有和公共 <xref:System.Type> 对象也会出现问题。对于共享程序集，每个进程只有一个 <xref:System.Type> 实例，这意味着多个应用程序域共享完全相同的 <xref:System.Type> 实例。对 <xref:System.Type> 实例采用锁则会采用影响整个进程的锁，而不仅仅影响 <xref:System.AppDomain>。如果一个 <xref:System.AppDomain> 对 <xref:System.Type> 对象采用锁，然后该线程突然中止，则锁不会被释放。此锁因此可能导致其他应用程序域死锁。  
  
 要较好地在静态方法中采用锁，需要向代码添加静态内部同步对象。如果该对象已存在，则可在类构造函数中初始化，如果不存在，则可按如下方式初始化：  
  
```  
private static Object s_InternalSyncObject;  
private static Object InternalSyncObject   
{  
    get   
    {  
        if (s_InternalSyncObject == null)   
        {  
            Object o = new Object();  
            Interlocked.CompareExchange(  
                ref s_InternalSyncObject, o, null);  
        }  
        return s_InternalSyncObject;  
    }  
}  
```  
  
 然后，在采用锁时，使用 `InternalSyncObject` 属性获取要锁定的对象。如果已在类构造函数中初始化内部同步对象，则无需使用该属性。检查锁初始化代码应类似下面的示例：  
  
```  
public static MyClass SingletonProperty   
{  
    get   
    {  
        if (s_SingletonProperty == null)   
        {  
            lock(InternalSyncObject)   
            {  
                // Do not use lock(typeof(MyClass))   
                if (s_SingletonProperty == null)   
                {  
                    MyClass tmp = new MyClass(…);     
                    // Do all initialization before publishing  
                    s_SingletonProperty = tmp;  
                }  
            }  
        }  
        return s_SingletonProperty;  
    }  
}  
```  
  
#### Lock\(this\) 说明  
 通常都可对公共可访问的单个对象采用锁。但是，如果对象是可能导致整个子系统死锁的单一实例对象，请考虑使用上面的设计模式。例如，对 <xref:System.Security.SecurityManager> 对象使用锁可能导致 <xref:System.AppDomain> 中发生死锁，从而使整个 <xref:System.AppDomain> 不可用。  最好不要对此类型的公共可访问的对象采用锁。但是，单个集合或数组的锁通常不会出现问题。  
  
#### 代码分析规则  
 不要对可能跨应用程序域使用或不能明确识别的类型采用锁。  不要对 <xref:System.Type>、<xref:System.Reflection.MethodInfo>、<xref:System.Reflection.PropertyInfo>、<xref:System.String>、<xref:System.ValueType>、<xref:System.Threading.Thread> 或任何从 <xref:System.MarshalByRefObject> 派生的对象调用 <xref:System.Threading.Monitor.Enter%2A>。  
  
### 移除 GC.KeepAlive 调用  
 大量现有代码要么在应使用 <xref:System.GC.KeepAlive%2A> 时不使用，要么在不应使用时使用。转换为 <xref:System.Runtime.InteropServices.SafeHandle> 后，假定类没有终结器而是依赖 <xref:System.Runtime.InteropServices.SafeHandle> 来终结操作系统句柄，则这些类无需调用 <xref:System.GC.KeepAlive%2A>。虽然保留对 <xref:System.GC.KeepAlive%2A> 的调用的性能开销可以忽略，但如果认为对 <xref:System.GC.KeepAlive%2A> 的调用是解决可能不再存在的生存期问题所必需的，或仅此即可解决这一问题，将使得代码的维护更加困难。但是，使用 COM 互操作 CLR 可调用包装 \(RCW\) 时，代码仍需要 <xref:System.GC.KeepAlive%2A>。  
  
#### 代码分析规则  
 移除 <xref:System.GC.KeepAlive%2A>。  
  
### 使用宿主保护特性  
 <xref:System.Security.Permissions.HostProtectionAttribute> \(HPA\) 提供声明性安全操作来确定宿主保护要求，从而允许宿主阻止（即使是完全受信任代码）调用不适用于给定宿主的特定方法，如 <xref:System.Environment.Exit%2A> 或 <xref:System.Windows.Forms.MessageBox.Show%2A>（对于 SQL Server）。  
  
 HPA 只影响承载公共语言运行时和实施宿主保护的非托管应用程序，例如 SQL Server。  应用后，安全操作会要求创建基于类或方法所公开的宿主资源的链接。  如果在客户端应用程序中或未实施宿主保护的服务器上运行代码，该特性就会“蒸发”，该特性既不会被检测到，因为也不会被应用到。  
  
> [!IMPORTANT]
>  此特性的目的在于强制实施特定宿主的编程模型准则，而非安全行为。尽管链接要求是用于检查与编程模型要求的一致性，但 <xref:System.Security.Permissions.HostProtectionAttribute> 并不是一个安全权限。  
  
 如果宿主没有编程模型要求，链接要求就不会发生。  
  
 此特性标识下面的内容：  
  
-   方法或类，它们不适合宿主编程模型，但在其他方面性能良好。  
  
-   方法或类，它们不适合宿主编程模型，并可能导致服务器托管的用户代码不稳定。  
  
-   方法或类，它们不适合宿主编程模型，并可能导致服务器进程本身不稳定。  
  
> [!NOTE]
>  如果正创建的类库将由可能在宿主保护环境中执行的应用程序调用，应对公开 <xref:System.Security.Permissions.HostProtectionResource> 资源类别的成员应用此特性。  具有此特性的 .NET Framework 类库成员导致只检查直接调用方。您的库成员必须也以同样的方式使其直接调用方得到检查。  
  
 请在 <xref:System.Security.Permissions.HostProtectionAttribute> 中查找有关 HPA 的更多信息。  
  
#### 代码分析规则  
 对于 SQL Server，所有用于引入同步或线程处理的方法都必须以 HPA 标识。  这些方法包括共享状态、被同步或管理外部进程的方法。  影响 SQL Server 的 <xref:System.Security.Permissions.HostProtectionResource> 值是 <xref:System.Security.Permissions.HostProtectionResource>、<xref:System.Security.Permissions.HostProtectionResource> 和 <xref:System.Security.Permissions.HostProtectionResource>。  但是，公开任何 <xref:System.Security.Permissions.HostProtectionResource> 的任何方法都应由 HPA 标识，而不仅是使用影响 SQL 的资源的方法。  
  
### 不要在非托管代码中无限期阻止  
 由于 CLR 不能中止线程，因此在非托管代码而不是托管代码中阻止可导致拒绝服务攻击。阻止的线程可防止 CLR 卸载 <xref:System.AppDomain>，至少不会执行某些非常不安全的操作。使用 Win32 同步基元进行阻止是不被允许的。应尽可能避免在调用套接字 `ReadFile` 时阻止 — Win32 API 最好为类似操作提供超时机制。  
  
 任何进行本机调用的方法都最好使用具有合理有限超时的 Win32 调用。如果允许用户指定超时，则不应允许用户在没有某种特定安全性权限限制的条件下指定无限超时。一般原则是，如果方法将阻止 ~10 秒以上，则需要使用支持超时的版本或更多 CLR 支持。  
  
 下面是一些存在问题的 API 示例。可以创建具有超时值的管道（匿名管道和命名管道）；但代码必须确保该管道在任何情况下都不会使用 NMPWAIT\_WAIT\_FOREVER 调用 `CreateNamedPipe` 或 `WaitNamedPipe`。此外，即使指定了超时值，仍可能存在意外阻止。调用匿名管道的 `WriteFile` 将阻止，直到写入所有字节为止，这意味着缓冲区中只要存在未读数据，`WriteFile` 调用就会阻止，直到读取器释放管道缓冲区的空间为止。套接字应始终使用一些采用超时机制的 API。  
  
#### 代码分析规则  
 在非托管代码中没有超时的阻止即是拒绝服务攻击。  不要对 `WaitForSingleObject`、`WaitForSingleObjectEx`、`WaitForMultipleObjects`、`MsgWaitForMultipleObjects` 和 `MsgWaitForMultipleObjectsEx` 执行平台调用。不要使用 NMPWAIT\_WAIT\_FOREVER。  
  
### 识别所有依赖 STA 的功能。  
 识别任何使用 COM 单线程单元 \(STA\) 的代码。在 SQL Server 进程禁用 STA。依赖 `CoInitialize` 的功能（如性能计数器或剪贴板）必须在 SQL Server 中禁用。  
  
### 确保终结器没有同步问题  
 在 .NET Framework 的未来版本中，多个终结器线程可以并存，这意味着相同类型的不同实例的终结器可以同时运行。它们不必完全是线程安全的；垃圾回收器会保证仅有一个线程运行给定对象实例的终结器。但是，必须编写终结器代码以避免多个不同对象实例同时运行时出现争用条件和死锁。在终结器中使用任何外部状态时，如向日志文件写入，必须处理线程处理问题。不要依赖终止来提供线程安全。  不要使用线程本地存储区（托管或本机）来存储终结器线程的状态。  
  
#### 代码分析规则  
 终结器必须没有同步问题。  不要在终结器中使用静态可变状态。  
  
### 尽量避免使用非托管内存  
 与操作系统句柄一样，非托管内存可能泄漏。尽量通过 [stackalloc](../Topic/stackalloc%20\(C%23%20Reference\).md) 使用堆栈内存或通过 byte\[\] 使用 [fixed 语句](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) 或 <xref:System.Runtime.InteropServices.GCHandle> 等固定托管对象。<xref:System.GC> 最后清理这些内容。但是，如果必须分配非托管内存，请考虑使用从 <xref:System.Runtime.InteropServices.SafeHandle> 派生的类来包装内存分配。  
  
 注意，至少在一种情况下 <xref:System.Runtime.InteropServices.SafeHandle> 不能满足要求。对于分配或释放内存的 COM 方法调用，通常是由一个 DLL 通过 `CoTaskMemAlloc` 分配内存，由另一个 DLL 使用 `CoTaskMemFree` 释放该内存。在这些位置使用 <xref:System.Runtime.InteropServices.SafeHandle> 可能不合适，因为它会尝试把非托管内存的生存期绑定到 <xref:System.Runtime.InteropServices.SafeHandle> 的生存期，而不是允许另一个 DLL 控制内存的生存期。  
  
### 查看 Catch\(Exception\) 的所有用法  
 捕捉所有异常而不是一个特定异常的 Catch 块现在也可捕捉异步异常。检查每个 catch\(Exception\) 块，确保释放所有重要的资源，并且不会跳过退出代码，而且 catch 块本身也不会在处理 <xref:System.Threading.ThreadAbortException>、<xref:System.StackOverflowException> 或 <xref:System.OutOfMemoryException> 时存在不正确的行为。注意，此代码可能会记录和假定只能发现某些异常，或者每当发生异常时，失败都是某个特定原因引起的。这些假定可能需要更新，以便包含 <xref:System.Threading.ThreadAbortException>。  
  
 请考虑将所有捕捉全部异常的位置更改为捕捉预计会引发的特定类型异常，如字符串格式设置方法引发的 <xref:System.FormatException>。这样可防止在遇到意外异常时运行 catch 块，通过捕捉意外异常，有助于确保代码不会隐藏 bug。一般原则是，任何情况下都不要处理库代码中的异常（要求捕捉异常的代码可能指示要调用的代码中存在设计缺陷）。在某些情况下，可能需要通过捕捉一种异常来引发其他异常类型，以便提供更多数据。在这种情况下，请使用嵌套异常，将故障的实际原因存储在新异常的 <xref:System.Exception.InnerException%2A> 属性中。  
  
#### 代码分析规则  
 检查托管代码中捕捉所有对象或捕捉所有异常的所有 catch 块。在 C\# 中，这意味着设置 `catch` {} 和 `catch(Exception)` {} 标志。请考虑使异常类型非常具体，或检查代码以确保其在捕捉意外异常类型时不会以糟糕的方式进行。  
  
### 不要假定托管线程是 Win32 线程 – 它是纤程  
 可以使用托管线程本地存储区，但不能使用非托管线程本地存储区，也不能假定代码将在当前操作系统线程中再次运行。不要更改线程区域设置之类的设置。不要通过平台调用来调用 `InitializeCriticalSection` 或 `CreateMutex`，因为它们要求进入锁的操作系统线程也退出锁。由于使用纤程时情况并不是这样，因此，Win32 临界区和 Mutex 不能直接在 SQL 中使用。注意，托管 <xref:System.Threading.Mutex> 类不处理这些线程关联问题。  
  
 可以安全地使用托管 <xref:System.Threading.Thread> 对象的大部分状态，包括托管线程本地存储区和线程的当前用户界面区域性。还可以使用 <xref:System.ThreadStaticAttribute>，这使得现有静态变量的值只能由当前托管线程访问（这是在 CLR 中处理纤程本地存储区的另一个方法）。由于编程模型的原因，在 SQL 中运行时不能更改线程的当前区域性。  
  
#### 代码分析规则  
 SQL Server 以纤程模式运行；不要使用线程本地存储区。  避免对 `TlsAlloc`、`TlsFree`、`TlsGetValue` 和 `TlsSetValue.` 进行平台调用  
  
### 用 SQL Server 处理模拟  
 由于模拟在线程级别运行，而 SQL 可以在纤程模式下运行，因此托管代码不应模拟用户，也不应调用 `RevertToSelf`。  
  
#### 代码分析规则  
 让 SQL Server 处理模拟。  不要使用 `RevertToSelf`、`ImpersonateAnonymousToken`、`DdeImpersonateClient`、`ImpersonateDdeClientWindow`、`ImpersonateLoggedOnUser`、`ImpersonateNamedPipeClient`、`ImpersonateSelf`、`RpcImpersonateClient`、`RpcRevertToSelf`、`RpcRevertToSelfEx` 或 `SetThreadToken`。  
  
### 不要调用 Thread::Suspend  
 挂起线程的功能看起来是简单操作，但可引起死锁。如果持有锁的线程由另一个线程挂起，然后第二个线程又尝试获取相同的锁，则会发生死锁。<xref:System.Threading.Thread.Suspend%2A> 可以影响当前安全性、类加载、远程处理和反射。  
  
#### 代码分析规则  
 不要调用 <xref:System.Threading.Thread.Suspend%2A>。  请考虑使用真正的同步基元，如 <xref:System.Threading.Semaphore> 或 <xref:System.Threading.ManualResetEvent>。  
  
### 用受约束执行区域和可靠性协定来保护关键型操作  
 执行更新共享状态或需要明确完全成功或完全失败的复杂操作时，请确保由约束执行区域 \(CER\) 进行保护。  这样可保证代码在每种情况下都能运行，即使突然线程中止或突然 <xref:System.AppDomain> 卸载。  
  
 CER 是紧跟对 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 的调用的特定 `try/finally` 块。  
  
 这样做可指示实时编译器在运行 `try` 块之前在 finally 块中准备所有代码。  这样可保证生成 finally 块中的代码并在任何情况下都会运行。  CER 中具有空 `try` 块并不少见。  使用 CER 可防止异步线程中止和内存不足异常。  有关进一步处理极深代码的堆栈溢出的 CER 形式，请参见 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>。  
  
## 请参阅  
 <xref:System.Runtime.ConstrainedExecution>   
 [SQL Server 编程和宿主保护特性](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)