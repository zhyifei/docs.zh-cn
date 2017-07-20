---
title: "How to: Add Trace Statements to Application Code | Microsoft Docs"
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
  - "tracing [.NET Framework], conditional writes based on switches"
  - "trace statements"
  - "WriteLineIf method"
  - "tracing [.NET Framework], adding trace statements"
  - "Assert method, tracing code"
  - "trace switches, conditional writes based on switches"
  - "WriteIf method"
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Add Trace Statements to Application Code
最常用于跟踪的方法是用于将输出写入侦听器的以下方法：**Write**、**WriteIf**、**WriteLine**、**WriteLineIf**、**Assert** 和 **Fail**。  这些方法可以分为两类：**Write**、**WriteLine** 和 **Fail** 都无条件地发出输出，而 **WriteIf**、**WriteLineIf** 和 **Assert** 则测试 Boolean 条件并根据条件的值来写入或不写入。  **WriteIf** 和 **WriteLineIf** 在条件为 `true` 时发出输出，而 **Assert** 在条件为 `false` 时发出输出。  
  
 当设计跟踪和调试策略时，应考虑所需的输出形式。  填充不相关信息的多个 **Write** 语句将创建难以阅读的日志。  另一方面，如果使用 **WriteLine** 将相关语句放置在单独的行上，可能会难以区分哪些信息应该在一起。  通常，当需要将来自多个源的信息组合起来创建单个信息性消息时，使用多个 **Write**；当需要创建单个完整消息时，使用 **WriteLine** 语句。  
  
### 写入完整的行  
  
1.  调用 <xref:System.Diagnostics.Trace.WriteLine%2A> 或 <xref:System.Diagnostics.Trace.WriteLineIf%2A> 方法。  
  
     一个回车符将追加到此方法返回的消息末尾，使 **Write**、**WriteIf**、**WriteLine** 或 **WriteLineIf** 返回的下一则消息将以如下行开始：  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,   
       "Error in AppendData procedure.");  
  
    ```  
  
### 写入部分行  
  
1.  调用 <xref:System.Diagnostics.Trace.Write%2A> 或 <xref:System.Diagnostics.Trace.WriteIf%2A> 方法。  
  
     由 **Write**、**WriteIf**、**WriteLine** 或 **WriteLineIf** 生成的下一条消息将会在由 **Write** 或 **WriteIf** 语句生成的消息所在的同一行上开始：  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,   
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
  
    ```  
  
### 验证特定条件在执行方法之前或之后存在  
  
1.  调用 <xref:System.Diagnostics.Trace.Assert%2A> 方法。  
  
    ```vb  
    Dim I As Integer = 4  
    Trace.Assert(I = 5, "I is not equal to 5.")  
  
    ```  
  
    ```csharp  
    int I = 4;  
    System.Diagnostics.Trace.Assert(I == 5, "I is not equal to 5.");  
  
    ```  
  
    > [!NOTE]
    >  你可以讲 **Assert** 用于跟踪和调试。  此示例将调用堆栈输出到 **Listeners** 集合中的任意侦听器。  有关详细信息，请参阅[托管代码中的断言](../Topic/Assertions%20in%20Managed%20Code.md)和 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>。  
  
## 请参阅  
 <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=fullName>   
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)