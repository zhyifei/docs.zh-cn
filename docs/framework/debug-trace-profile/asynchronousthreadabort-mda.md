---
title: "asynchronousThreadAbort MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "asynchronous thread aborts"
  - "AsynchronousThreadAbort MDA"
  - "managed debugging assistants (MDAs), asynchronous thread aborts"
  - "threading [.NET Framework], managed debugging assistants"
  - "MDAs (managed debugging assistants), asynchronous thread aborts"
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# asynchronousThreadAbort MDA
如果一个线程尝试向另一个线程引入一个异步中止，则将激活 `asynchronousThreadAbort` 托管调试助手 \(MDA\)。  同步线程中止不会激活 `asynchronousThreadAbort` MDA。  
  
## 症状  
 主应用程序线程中止时，应用程序崩溃，同时会有一个未处理的 <xref:System.Threading.ThreadAbortException>。  如果该应用程序继续执行，结果可能比应用程序崩溃还要坏，可能会导致进一步的数据损坏。  
  
 被设计为原子操作的操作可能在完成一部分后中断了，从而使应用程序数据处在一种不可预知的状态。  从代码执行中表面上的随机点（往往是那些本不应该引发异常的位置）可能会生成 <xref:System.Threading.ThreadAbortException>。  该代码可能无法处理这样的异常，从而导致损坏状态。  
  
 由于问题固有的随机性，具体症状可能会大不相同。  
  
## 原因  
 一个线程中的代码对目标线程调用 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> 方法以引入一个异步线程中止。  该线程中止是异步操作，因为对 <xref:System.Threading.Thread.Abort%2A> 发出调用的代码运行在与中止操作的目标线程不同的线程上。  同步线程中止不会导致问题发生，因为执行 <xref:System.Threading.Thread.Abort%2A> 的线程只会在应用程序状态一致的安全检查点执行此操作。  
  
 异步线程中止会引发问题，因为它们在目标线程执行中的不可预知的点处理的。  为避免发生此情况，对于编写的要在可能以此方式中止的线程上运行的代码，几乎每一行都需要处理一个 <xref:System.Threading.ThreadAbortException>，确保让应用程序数据恢复一致的状态。  希望在编写代码时考虑到此问题或编写可避免所有可能发生的问题的代码并不现实。  
  
 向非托管代码和 `finally` 块发出的调用将不会异步中止，但会在从这些类别之一退出时立即终止。  
  
 由于问题固有的随机性，原因可能很难确定。  
  
## 解决方法  
 避免需要使用异步线程中止的代码设计。  有几种更适用于中断目标线程的方法，这几种方法不需要对 <xref:System.Threading.Thread.Abort%2A> 发出调用。  最安全的方法就是引入一种机制（例如一个公共属性）来向目标线程发出信号，让目标线程请求中断。  目标线程在某个安全检查点检查该信号。  如果它注意到已请求中断，则会正常关闭。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  它只报告有关异步线程中止的数据。  
  
## Output  
 此 MDA 报告执行中止的线程的 ID 和作为中止目标的线程的 ID。  这两个 ID 永远都不会相同，因为这局限于异步中止。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <asynchronousThreadAbort />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 激活 `asynchronousThreadAbort` MDA 只需在另一运行线程上对 <xref:System.Threading.Thread.Abort%2A> 发出调用即可。  试考虑在线程启动函数的内容是一组更复杂的操作（该操作可能会在任意点因发生中止而中断）时的结果。  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Abort();   
    t.Join();  
}  
```  
  
## 请参阅  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)