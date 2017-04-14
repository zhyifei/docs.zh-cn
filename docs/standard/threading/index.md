---
title: "Managed Threading | Microsoft Docs"
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
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading
无论您是为具有单个处理器的计算机还是为具有多个处理器的计算机进行开发，您都希望应用程序为用户提供最好的响应性能，即使应用程序当前正在完成其他工作。  要使应用程序能够快速响应用户操作，同时在用户事件之间或者甚至在用户事件期间利用处理器，最强大的方式之一是使用多个执行线程。  尽管本节只是介绍线程处理的基本概念，但它集中讨论了托管线程处理的概念以及如何使用托管线程处理。  
  
> [!NOTE]
>  从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，通过 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 和 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 类、<xref:System.Collections.Concurrent?displayProperty=fullName> 命名空间中新的并发集合类 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) 以及基于任务（而不是线程）概念的新编程模型，多线程编程得到了极大简化。  有关更多信息，请参见[Parallel Programming](../../../docs/standard/parallel-programming/index.md)。  
  
## 本节内容  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)  
 概述托管线程处理并讨论何时使用多个线程。  
  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 解释如何创建、启动、暂停、继续和中止线程。  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 讨论同步的级别，如何避免死锁和争用条件，并讨论单处理器和多处理器计算机以及其他线程处理问题。  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)  
 描述一些托管类，这些类可用来同步线程的活动以及由不同线程访问的对象的数据，并概述了线程池线程。  
  
## 参考  
 <xref:System.Threading>  
 包含用于使用和同步托管线程的类。  
  
 <xref:System.Collections.Concurrent>  
 包含安全用于多个线程的集合类。  
  
 <xref:System.Threading.Tasks>  
 包含用于创建和计划并发处理任务的类。  
  
## 相关章节  
 [应用程序域](../../../docs/framework/app-domains/application-domains.md)  
 概述应用程序域及 Common Language Infrastructure 对它们的使用。  
  
 [异步文件 I\/O](../../../docs/standard/io/异步文件-i-o.md)  
 描述异步 I\/O 的性能优势和基本操作。  
  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 提供异步编程的概述。  
  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 说明如何使用委托的内置功能对线程池线程调用方法。  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 描述并行编程库，这些库简化了多个线程在应用程序中的使用。  
  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 描述并行运行查询以充分利用多个处理器的系统。