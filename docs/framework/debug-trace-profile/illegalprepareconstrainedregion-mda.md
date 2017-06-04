---
title: "illegalPrepareConstrainedRegion MDA | Microsoft Docs"
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
  - "PrepareConstrainedRegions method"
  - "managed debugging assistants (MDAs), illegal PrepareConstrainedRegions"
  - "try/catch exception handling, managed debugging assistants"
  - "IllegalPrepareConstrainedRegions MDA"
  - "MDAs (managed debugging assistants), illegal PrepareConstrainedRegions"
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# illegalPrepareConstrainedRegion MDA
如果异常处理程序的 `try` 语句没有紧随在 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=fullName> 方法调用之后，则将激活 `illegalPrepareConstrainedRegion` 托管调试助手 \(MDA\)。  此限制处于 MSIL 级别，因此在该调用和 `try` 之间允许存在非代码生成源，例如注释。  
  
## 症状  
 受约束的执行区域 \(CER\) 从来不被名符其实地视为受约束的执行区域，而是被视为一个简单的异常处理块（`finally` 或 `catch`）。  结果，在内存不足或线程中止时不会运行该区域。  
  
## 原因  
 没有正确遵循 CER 的准备模式。这是一个错误事件。  `try` 语句必须紧随在向 `catch`\/`finally`\/`fault`\/`filter` 块中引入 CER 时用于标记异常处理程序的 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法之后。  
  
## 解决方法  
 确保紧接在 `try` `` 语句之前调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## Output  
 此 MDA 显示调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法的方法的名称、MSIL 偏移量和一条指示 try 块没有紧随在该调用之后的消息。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 下面的代码示例演示了导致激活此 MDA 的模式。  
  
```  
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)