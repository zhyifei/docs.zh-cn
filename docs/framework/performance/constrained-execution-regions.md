---
title: "受约束的执行区域 | Microsoft Docs"
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
  - "CER"
  - "受约束的执行区域"
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 受约束的执行区域
受约束的执行区域 \(CER\) 是创作可靠托管代码的机制的一部分。  CER 定义一个区域，在该区域中公共语言运行时 \(CLR\) 会受到约束，不能引发可使区域中的代码无法完全执行的带外异常。  在该区域中，用户代码受到约束，不能执行会导致引发带外异常的代码。  <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法必须直接位于 `try` 块之前，并将 `catch`、`finally` 和 `fault` 块标记为受约束的执行区域。  标记为受约束的区域后，代码只能调用其他具有强可靠性约定的代码，而且代码不应分配或者对未准备好的或不可靠的方法进行虚调用，除非代码已经准备好处理错误。  CLR 为 CER 中正在执行的代码延迟线程中止。  
  
 除批注的 `try` 块外，受约束的执行区域还以其他形式用于 CLR 中，特别是在从 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 类派生的类中执行的关键终止程序和使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 方法执行的代码。  
  
## CER 事先准备  
 CLR 会事先准备 CER 以避免出现内存不足的情况。  进行事先准备的目的是为了避免 CLR 在实时编译或类型加载时发生内存不足的情况。  
  
 开发人员需要指定一个代码区域作为 CER：  
  
-   顶级 CER 区域和完整调用关系图中应用了 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 特性的方法是事先准备好的。  <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 只能声明 <xref:System.Runtime.ConstrainedExecution.Cer> 或 <xref:System.Runtime.ConstrainedExecution.Cer> 的保证。  
  
-   事先准备不能针对无法静态确定的调用（如虚调度）执行。  此时可使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> 方法。  使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 方法时，应该对清理代码应用 <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> 特性。  
  
## 约束  
 用户可在 CER 中写入的代码的类型受到限制。  代码不能导致带外异常，例如以下操作就可能导致此类异常：  
  
-   显式分配。  
  
-   装箱。  
  
-   获取锁。  
  
-   对未准备好的方法进行虚调用。  
  
-   调用具有弱可靠性约定或不具有可靠性约定的方法。  
  
 在 .NET Framework 2.0 版中，这些约束称为准则。  诊断通过代码分析工具提供。  
  
## 可靠性协定  
 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 是记录给定方法的可靠性保证和损坏状态的自定义特性。  
  
### 可靠性保证  
 可靠性保证由 <xref:System.Runtime.ConstrainedExecution.Cer> 枚举值表示，指示给定方法的可靠度：  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  在异常情况下，该方法可能会失败。  在这种情况下，该方法会向进行调用的方法报告是成功还是失败。  该方法必须包含在 CER 中，以确保它可以报告返回值。  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  方法、类型或程序集完全不知道 CER，如果不实质性地缓解状态损坏的情况，则在 CER 内进行调用很可能是不安全的。  它不利用 CER 保证。  这意味着：  
  
    1.  在异常情况下，该方法可能会失败。  
  
    2.  该方法可能报告失败，也可能不报告失败。  
  
    3.  最可能的情形是未编写该方法以使用 CER。  
  
    4.  如果方法、类型或程序集未显式标识为成功的，则会隐式标识为 <xref:System.Runtime.ConstrainedExecution.Cer>。  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  在异常情况下，保证该方法能够成功。  若要达到此可靠性级别，应始终在调用的方法周围构造 CER，即使是从非 CER 区域内进行调用。  如果一个方法完成了其任务，它就是成功的，虽然这种成功可能只是主观认为的成功。  例如，用 `ReliabilityContractAttribute(Cer.Success)` 标记 Count 意味着当它在 CER 下运行时，它始终返回 <xref:System.Collections.ArrayList> 中元素的数目的计数，并且它永远不能将内部字段保留为不确定状态。但是，<xref:System.Threading.Interlocked.CompareExchange%2A> 方法也标记为成功，这里的成功意味着该值不会因争用条件而替换为新值。关键在于该方法的行为方式与记录的行为方式相同，不需要在 CER 代码中处理除正确但不可靠代码的行为之外的任何非正常行为。  
  
### 损坏级别  
 损坏级别由 <xref:System.Runtime.ConstrainedExecution.Consistency> 枚举值表示，指示给定环境下状态的损坏程度：  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  在异常情况下，公共语言运行时 \(CLR\) 对当前应用程序域中的状态一致性不做任何保证。  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  在异常情况下，保证该方法的状态损坏仅限制于当前实例。  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>，在异常情况下，CLR 对状态一致性不做任何保证；即这种情况可能会损坏进程。  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  在异常情况下，保证该方法不会损坏状态。  
  
## 可靠性 try\/catch\/finally  
 可靠性 `try/catch/finally` 是一种异常处理机制，其可预知性保证的级别与非托管版本相同。  `catch/finally` 块为 CER。  块中的方法需要事先准备，并且必须是不可中断的。  
  
 在 .NET Framework 2.0 版中，代码通过紧接在 try 块之前调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 来通知运行时 try 操作是可靠的。  <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 是 <xref:System.Runtime.CompilerServices.RuntimeHelpers>（一个编译器支持类）的成员。  通过使用编译器暂停可用性，直接调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>。  
  
## 不可中断区域  
 不可中断区域可将一组指令分组到 CER 中。  
  
 在 .NET Framework 2.0 版中，通过使用编译器支持暂停可用性，用户代码创建不可中断的区域，其中具有包含前面是 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法调用的空 try\/catch 块的可靠 try\/catch\/finally。  
  
## 关键终结器对象  
 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 保证垃圾回收会执行终结器。  进行分配时，终结器及其调用关系图是事先准备好的。  终结器方法在 CER 中执行，并且必须服从所有有关 CER 和终结器的约束。  
  
 从 <xref:System.Runtime.InteropServices.SafeHandle> 和 <xref:System.Runtime.InteropServices.CriticalHandle> 继承的任何类型都保证在 CER 内执行其终结器。  在 <xref:System.Runtime.InteropServices.SafeHandle> 派生类中实现 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 可执行释放句柄所需的所有代码。  
  
## CER 中不允许的代码  
 CER 中不允许下面的操作：  
  
-   显式分配。  
  
-   获取锁。  
  
-   装箱。  
  
-   多维数组访问。  
  
-   通过反射进行的方法调用。  
  
-   <xref:System.Threading.Monitor.Enter%2A> 或 <xref:System.IO.FileStream.Lock%2A>。  
  
-   安全检查。  不执行命令，仅链接命令。  
  
-   COM 对象和代理的 <xref:System.Reflection.Emit.OpCodes.Isinst> 和 <xref:System.Reflection.Emit.OpCodes.Castclass>  
  
-   获取或设置透明代理上的字段。  
  
-   序列化。  
  
-   函数指针和委托。  
  
## 请参阅  
 [可靠性最佳做法](../../../docs/framework/performance/reliability-best-practices.md)