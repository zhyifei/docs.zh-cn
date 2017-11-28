---
title: "如何：向应用程序代码添加跟踪语句"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5dd46da24c379a7900dff0dc482577195f5f4c23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-trace-statements-to-application-code"></a>如何：向应用程序代码添加跟踪语句
最常用于跟踪的方法是用于将输出写入侦听器的以下方法：Write、WriteIf、WriteLine、WriteLineIf、Assert 和 Fail。 这些方法可以分为两类：Write、WriteLine 和 Fail 都无条件地发出输出，而 WriteIf、WriteLineIf 和 Assert 则测试 Boolean 条件并根据条件的值来写入或不写入。 WriteIf 和 WriteLineIf 在条件为 `true` 时发出输出，而 Assert 在条件为 `false` 时发出输出。  
  
 当设计跟踪和调试策略时，应考虑所需的输出形式。 填充不相关信息的多个 Write 语句将创建难以读取的日志。 另一方面，如果使用 WriteLine 将相关语句放置在单独的行上，可能会难以区分哪些信息应该在一起。 通常，当需要将来自多个源的信息组合起来创建单个信息性消息时，使用多个 Write；当需要创建单个完整消息时，则使用 WriteLine 语句。  
  
### <a name="to-write-a-complete-line"></a>写入完整的行  
  
1.  调用 <xref:System.Diagnostics.Trace.WriteLine%2A> 或 <xref:System.Diagnostics.Trace.WriteLineIf%2A> 方法。  
  
     一个回车符会被追加到此方法返回的消息末尾，使 Write、WriteIf、WriteLine 或 WriteLineIf 返回的下一条消息将从以下行开始：  
  
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
  
### <a name="to-write-a-partial-line"></a>写入部分行  
  
1.  调用 <xref:System.Diagnostics.Trace.Write%2A> 或 <xref:System.Diagnostics.Trace.WriteIf%2A> 方法。  
  
     由 Write、WriteIf、WriteLine 或 WriteLineIf 生成的下一条消息将从由 Write 或 WriteIf 语句生成的消息所在的同一行上开始：  
  
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
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a>验证特定条件在执行方法之前或之后存在  
  
1.  调用 <xref:System.Diagnostics.Trace.Assert%2A> 方法。  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    >  可以将 Assert 用于跟踪和调试。 此示例将调用堆栈输出到 Listeners 集合中的任意侦听器。 有关详细信息，请参阅[托管代码中的断言<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>和 ](/visualstudio/debugger/assertions-in-managed-code)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>  
 [跟踪应用程序和在应用程序中插入检测点](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [如何： 创建、 初始化和配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)  
 [跟踪开关](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [跟踪侦听器](../../../docs/framework/debug-trace-profile/trace-listeners.md)
