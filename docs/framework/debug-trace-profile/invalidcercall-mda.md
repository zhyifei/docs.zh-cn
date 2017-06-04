---
title: "invalidCERCall MDA | Microsoft Docs"
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
  - "invalid CER calls"
  - "InvalidCERCall MDA"
  - "MDAs (managed debugging assistants), CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidCERCall MDA
当受约束的执行区域 \(CER\) 关系图中存在对某个没有可靠性协定或具有过弱协定的方法的调用时，将激活 `invalidCERCall` 托管调试助手 \(MDA\)。  弱协定是声明最坏情况下的状态损坏的范围超出传递给调用的实例的协定，即 <xref:System.AppDomain> 或进程状态可能被损坏，或者在 CER 中调用时，其结果并不总是明确地可计算。  
  
## 症状  
 在 CER 中执行代码时得到意外结果。  这些症状并不明确。  它们可能是在调入不可靠的方法时发生的意外 <xref:System.OutOfMemoryException>、<xref:System.Threading.ThreadAbortException> 或其他异常（因为运行时没有预先准备该方法或提供相应的保护以使它在运行时不引发 <xref:System.Threading.ThreadAbortException> 异常）。  更大的威胁在于，该方法在运行时产生的任何异常可能将 <xref:System.AppDomain> 或进程置于不稳定状态，这违背了 CER 的目标。  创建 CER 的目的就是避免这样的状态损坏。  损坏的状态的症状特定于应用程序，因为一致状态的定义在应用程序之间是不同的。  
  
## 原因  
 CER 中的代码调用没有 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 或具有弱 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 的函数，该函数不适合在 CER 中运行。  
  
 根据可靠性协定语法，弱协定是未指定 <xref:System.Runtime.ConstrainedExecution.Consistency> 枚举值或指定 <xref:System.Runtime.ConstrainedExecution.Consistency>、<xref:System.Runtime.ConstrainedExecution.Consistency> 或 <xref:System.Runtime.ConstrainedExecution.Cer> 的 <xref:System.Runtime.ConstrainedExecution.Consistency> 值的协定。  这其中任何条件均指示被调用的代码可能妨碍 CER 中的其他代码维护一致状态的努力。CER 允许代码以非常明确的方式处理错误，维护对应用程序很重要的内部不变量并允许它在面对诸如内存不足异常之类的瞬态错误时继续运行。  
  
 此 MDA 的激活指示 CER 中正在调用的方法会以调用方未预期或导致 <xref:System.AppDomain> 进程状态损坏或不可恢复的方式失败的可能性。  当然，被调用的代码可能正确执行，并且问题只是缺少协定。  但是，编写可靠代码所涉及的问题很微妙，缺少协定是代码可能无法正确执行的一个很好的指示器。  协定是程序员已可靠地编写代码并承诺这些保证不会在将来的代码修订中改变的指示器。也就是说，协定是意图声明而不只是实现细节。  
  
 由于具有弱协定或不具有协定的任何方法都有可能以多种不可预测的方式失败，运行时并不尝试从惰性 JIT 编译、泛型字典填充或线程中止（举例而言）所引入的方法中移除它自己的任何不可预测的失败。  也就是说，当此 MDA 被激活时，它指示运行时不在所定义的 CER 中包括被调用的方法；调用关系图在此节点终止，因为继续准备此子树将有助于掩蔽潜在的错误。  
  
## 解决方法  
 向该函数添加有效的可靠性协定，或避免使用该函数调用。  
  
## 对运行时的影响  
 从 CER 调用弱协定的影响可能是 CER 未能完成其操作。  这可能导致 <xref:System.AppDomain> 进程状态的损坏。  
  
## Output  
 下面是来自此 MDA 的示例输出。  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)