---
title: ".NET 性能提示 | Microsoft Docs"
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
  - "C# 语言, 性能"
  - "性能 [C#]"
  - "性能 [Visual Basic]"
  - "Visual Basic, 性能"
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
caps.handback.revision: 36
---
# .NET 性能提示
术语“性能”通常指程序的执行速度。  有时候，通过遵循源代码中的一些基本规则便可以提高执行速度。  在某些程序中，仔细检查代码并使用探查器确保程序可以尽可能快地运行非常重要。  在另一些程序中，由于在编写时代码运行得足够快，因此不必进行此类优化。  本文列出了性能可能受损的常见区域，并提供了改进方法以及其他性能主题的链接。  有关性能的计划和衡量的详细信息，请参阅 [Performance](../../../docs/framework/performance/index.md)  
  
## 装箱和取消装箱  
 如果必须频繁地将值类型装箱，则最好避免使用值类型，例如在非泛型集合类（如 <xref:System.Collections.ArrayList?displayProperty=fullName>）中。  可以通过使用泛型集合（例如 <xref:System.Collections.Generic.List%601?displayProperty=fullName>）来避免将值类型装箱。  装箱和取消装箱都是需要大量运算的过程。  对值类型进行装箱时，必须创建一个全新的对象。  此操作所需时间可比简单的引用赋值操作长 20 倍。  取消装箱时，强制转换过程所需时间可达赋值操作的四倍。  有关更多信息，请参见[装箱和取消装箱](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md)。  
  
## Strings  
 在连接大量字符串变量时，例如在紧凑循环中，请使用 <xref:System.Text.StringBuilder?displayProperty=fullName> 而不是 C\# [\+ 运算符](../Topic/+%20Operator%20\(C%23%20Reference\).md)或 Visual Basic [串联运算符](../Topic/Concatenation%20Operators%20\(Visual%20Basic\).md)。  有关更多信息，请参见[如何：串联多个字符串](../Topic/How%20to:%20Concatenate%20Multiple%20Strings%20\(C%23%20Programming%20Guide\).md)和[串联运算符 \(Visual Basic\)](../Topic/Concatenation%20Operators%20in%20Visual%20Basic.md)。  
  
## 析构函数  
 不应使用空析构函数。  如果类包含析构函数，Finalize 队列中则会创建一个项。  调用析构函数时，将调用垃圾回收器来处理该队列。  如果析构函数为空，只会导致性能降低。  有关更多信息，请参见[析构函数](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md)和[对象生存期：如何创建和销毁对象](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)。  
  
## 其他资源  
  
-   [编写更快的托管代码：了解开销](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [编写高性能托管应用程序：入门](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [垃圾回收器基础知识和性能提示](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [.NET 应用程序的性能提示和技巧](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [.NET 的内部诊断工具](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Rico Mariani 关于性能问题的见解](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## 请参阅  
 [Performance](../../../docs/framework/performance/index.md)   
 [编程概念](../Topic/Programming%20Concepts.md)   
 [Visual Basic 编程指南](../Topic/Visual%20Basic%20Programming%20Guide.md)   
 [C\# 编程指南](../Topic/C%23%20Programming%20Guide.md)