---
title: "处理和引发异常 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "公共语言运行时, 异常"
  - "错误 [.NET Framework], 异常"
  - "异常 [.NET Framework]"
  - "异常 [.NET Framework], 处理"
  - "异常 [.NET Framework], 引发"
  - "筛选异常"
  - "运行时, 异常"
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# 处理和引发异常
<a name="top"></a> 应用程序必须能够以一致的方式处理执行期间发生的错误。 公共语言运行时提供一个模型，用于以统一的方式向应用程序通知错误。 所有 .NET Framework 操作通过引发异常来指示失败。  
  
 本主题包含以下各节：  
  
-   [.NET Framework 中的异常](#exceptions_in_the_net_framework)  
  
-   [异常与传统的错误处理方法](#exceptions_vs_traditional_errorhandling_methods)  
  
-   [运行时如何管理异常](#how_the_runtime_manages_exceptions)  
  
-   [筛选运行时异常](#filtering_runtime_exceptions)  
  
-   [相关主题](#related_topics)  
  
-   [参考](#reference)  
  
<a name="exceptions_in_the_net_framework"></a>   
## .NET Framework 中的异常  
 异常是执行程序遇到的所有错误条件或意外行为。 异常可能由你的代码或调用的代码（如共享库）中的错误、不可用的操作系统资源、公共语言运行时遇到的意外情况（如无法验证的代码）等引发。 应用程序可从这些情况中的一些中恢复，但无法从其他情况中恢复。 尽管可以从大多数应用程序异常中恢复，但不能从大多数运行时异常中恢复。  
  
 在 .NET Framework 中，异常是从 <xref:System.Exception?displayProperty=fullName> 类继承的对象。 异常引发自发生问题的代码区域。 异常在堆栈中向上传递，直到应用程序对其进行处理或者程序终止。  
  
 [返回页首](#top)  
  
<a name="exceptions_vs_traditional_errorhandling_methods"></a>   
## 异常与传统的错误处理方法  
 传统上，语言的错误处理模型依赖语言检测错误和针对错误查找其处理程序的独特方式，或者依赖操作系统提供的错误处理机制。 运行时实现具有以下特点的异常处理：  
  
-   处理异常，而不考虑生成异常的语言或处理异常的语言。  
  
-   处理异常不需要任何特定的语言语法，但允许每种语言定义自己的语法。  
  
-   允许跨进程，甚至跨计算机边界引发异常。  
  
 异常相较于其他错误通知方法（如返回代码）具有多种优势。 失败不会被忽略。 无效值不会持续在整个系统传播。 无需检查返回代码。 可轻松添加异常处理代码以提高程序的可靠性。 最后，运行时的异常处理的速度快于基于 Windows 的 C\+\+ 错误处理。  
  
 由于执行线程定期遍历托管和非托管代码块，因此运行时可在托管或非托管代码中引发或捕捉异常。 非托管代码可以包括 C\+\+ 样式 SEH 异常和基于 COM 的 HRESULT。  
  
<a name="how_the_runtime_manages_exceptions"></a>   
## 运行时如何管理异常  
 运行时使用基于异常对象和受保护的代码块的异常处理模型。 创建 <xref:System.Exception> 对象以在异常发生时表示异常。  
  
 运行时为每个可执行文件创建异常信息表。 可执行文件的每种方法在异常信息表中都有一组异常处理信息的关联数组（可以为空）。 数组中的每个条目描述受保护的代码块、与该代码关联的所有异常筛选器以及所有异常处理程序（`catch` 语句）。 此异常表效率极高，且在不发生异常时，不会导致处理器时间或内存使用中产生任何性能损失。 仅当发生异常时使用资源。  
  
 异常信息表表示受保护块的四种类型的异常处理程序：  
  
-   `finally` 处理程序，只要块存在即执行，无论由正常控制流还是未处理的异常引发。  
  
-   错误处理程序，如果异常发生则必须执行，但不会在正常控制流完成时执行。  
  
-   类型筛选处理程序，处理指定类或其任何派生类的所有异常。  
  
-   用户筛选的处理程序，运行用户指定的代码，以确定应由关联的处理程序处理异常还是应将异常传递到下一个受保护的块。  
  
 每种语言根据各自规范实现这些异常处理程序。 例如，Visual Basic 通过 `catch` 语句中的变量比较（使用 `When` 关键字）提供对用户筛选的处理程序的访问；C\# 不实现用户筛选的处理程序。  
  
 发生异常后，运行时开始一个两步过程：  
  
1.  运行时搜索数组以找到第一个执行以下内容的受保护块：  
  
    -   保护包含当前执行的指令的区域。  
  
    -   包含异常处理程序或包含处理异常的筛选器。  
  
2.  如果出现匹配项，则运行时创建描述异常的 <xref:System.Exception> 对象。 然后，运行时执行所有 `finally` 或执行发生异常的语句和处理异常的语句之间的错误语句。 请注意异常处理程序的顺序很重要；首先计算最里面的异常处理程序。 此外注意异常处理程序可以访问捕获异常的例程的本地变量和本地内存，但引发异常时的任何中间值将会丢失。  
  
     如果没有匹配项出现在当前方法中，运行时会搜索当前方法的每个调用方，并在堆栈中向上继续此路径。 如果没有调用方具有匹配项，则运行时允许调试器访问异常。 如果调试器未附加到异常，则运行时引发 <xref:System.AppDomain.UnhandledException?displayProperty=fullName> 事件。 如果此事件没有侦听器，则运行时转储堆栈跟踪并结束应用程序。  
  
 [返回页首](#top)  
  
<a name="filtering_runtime_exceptions"></a>   
## 筛选运行时异常  
 可以筛选捕获的异常，并按类型或按某些用户定义的条件进行处理。  
  
 类型筛选处理程序管理特定类型的异常（或从其派生的类）。 以下示例显示旨在捕获特定异常的类型筛选处理程序，在此例中则为 <xref:System.IO.FileNotFoundException>。  
  
 [!code-cpp[CatchException#5](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception3.cpp#5)]
 [!code-csharp[CatchException#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception3.cs#5)]
 [!code-vb[CatchException#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception3.vb#5)]  
  
 用户筛选的异常处理程序基于定义的异常要求来捕获和处理异常。 有关采用这种方式筛选异常的详细信息，请参阅[在 Catch 块中使用特定异常](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)。  
  
 [返回页首](#top)  
  
<a name="related_topics"></a>   
## 相关主题  
  
|标题|说明|  
|--------|--------|  
|[异常类和属性](../../../docs/standard/exceptions/exception-class-and-properties.md)|介绍异常对象的元素。|  
|[异常层次结构](../../../docs/standard/exceptions/exception-hierarchy.md)|介绍大多数异常派生自的异常。|  
|[异常处理基础知识](../../../docs/standard/exceptions/exception-handling-fundamentals.md)|说明如何使用 catch、throw 和 finally 语句处理异常。|  
|[异常的最佳做法](../../../docs/standard/exceptions/best-practices-for-exceptions.md)|介绍用于处理异常的建议方法。|  
|[处理 COM 互操作异常](../../../docs/standard/exceptions/handling-com-interop-exceptions.md)|描述如何处理非托管代码中引发和捕获的异常。|  
|[如何：映射 HRESULT 和异常](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|描述托管和非托管代码之间异常的映射。|  
  
<a name="reference"></a>   
## 参考  
 <xref:System.Exception?displayProperty=fullName>  
  
 <xref:System.ApplicationException?displayProperty=fullName>  
  
 <xref:System.SystemException?displayProperty=fullName>