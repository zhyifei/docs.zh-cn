---
title: "如何：向集合添加限制和阻塞功能 | Microsoft Docs"
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
  - "线程安全集合，自定义阻塞集合"
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 如何：向集合添加限制和阻塞功能
本示例演示如何通过实现类中的 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> 接口，然后将类实例用作 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的内部存储机制，来向自定义集合类添加限制和阻塞功能。  有关限制和阻塞的更多信息，请参见 [BlockingCollection 概述](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)。  
  
## 示例  
 自定义集合类是一个基本优先级别队列，优先级别在其中表示为一个 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> 对象的数组。  在每个队列中不进行其他排序。  
  
 客户端代码中启动了三个任务。  第一个任务仅轮询键盘键击以便在执行过程中的任意时刻启用取消。  第二个任务是制造者线程，它会向阻塞集合添加新项并根据随机值为每个项分配一个优先级别。  第三个任务在项可用时将其从集合中移除。  
  
 可以通过使这些线程中的一个线程的运行速度快于另一个线程的运行速度来调整应用程序的行为。  如果制造者线程的运行速度更快，则当阻塞集合阻止添加项（如果该集合已包含构造函数中所指定的数目的项）时，您会注意到限制功能。  如果使用者线程的运行速度更快，则当使用者等待添加新项时，您会注意到阻塞功能。  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 默认情况下，<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的存储为 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>。  
  
## 请参阅  
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)