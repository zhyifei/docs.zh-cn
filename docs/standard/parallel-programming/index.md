---
title: "Parallel Programming in the .NET Framework | Microsoft Docs"
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
  - "parallel programming"
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Parallel Programming in the .NET Framework
许多个人计算机和工作站都有两个或四个内核（即 CPU），使多个线程能够同时执行。  在不久的将来，计算机预期会有更多的内核。  为了利用当今和未来的硬件，您可以对代码进行并行化，以将工作分摊在多个处理器上。  过去，并行化需要线程和锁的低级操作。  [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 和 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 提供了新的运行时、新的类库类型以及新的诊断工具，从而增强了对并行编程的支持。  这些功能简化了并行开发，使您能够通过固有方法编写高效、细化且可伸缩的并行代码，而不必直接处理线程或线程池。  下图从较高层面上概述了 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中的并行编程体系结构。  
  
 ![.NET 并行编程体系结构](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL\_Architecture")  
  
## 相关主题  
  
|技术|描述|  
|--------|--------|  
|[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|提供针对 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 类的文档（包括 `For` 和 `ForEach` 循环的并行版本），还提供了针对 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 类的文档（描绘了表示异步操作的首选方式）。|  
|[Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|LINQ to Objects 的并行实现，该实现显著提高了许多情况下的性能。|  
|[Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|提供一些链接，这些链接指向有关线程安全集合类、轻量同步类型以及延迟初始化类型的文档。|  
|[Parallel Diagnostic Tools](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|提供一些链接，这些链接指向有关 Visual Studio 任务和并行堆栈调试器窗口以及[并发可视化工具](../Topic/Concurrency%20Visualizer.md)的文档，其中包含 [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] 探查器中的一组视图，你可以使用这些视图来调试和调整并行代码的性能。|  
|[Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|描述分区程序的工作方式，以及如何配置默认分区程序或创建新的分区程序。|  
|[Task Schedulers](../Topic/Task%20Schedulers.md)|描述计划程序的工作方式，以及如何配置默认计划程序。|  
|[Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|简要概述 C\# 和 Visual Basic 中的 lambda 表达式，并演示如何在 PLINQ 和任务并行库中使用这些表达式。|  
|[For Further Reading](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|提供一些链接，这些链接指向其他文档以及在 .NET Framework 中进行并行编程的示例资源。|  
  
## 请参阅  
 [并行编程模式：了解和应用 .NET Framework 4 的并行模式](http://go.microsoft.com/fwlink/?LinkID=185142)   
 [使用 .NET Framework 的并行编程示例](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)