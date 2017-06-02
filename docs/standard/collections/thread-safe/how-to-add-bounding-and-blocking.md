---
title: "如何：向集合添加控制和锁定功能 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: df159b1ab3f7c16564ce493a585246c4c461a8f9
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>如何：向集合添加限制和阻塞功能
本示例展示了如何在类中实现 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> 接口，然后将类实例用作 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的内部存储机制，从而向自定义集合类添加控制和锁定功能。 有关限制和阻塞的详细信息，请参阅 [BlockingCollection 概述](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)。  
  
## <a name="example"></a>示例  
 自定义集合类是基本的优先级队列，其中的优先级表示为一组 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> 对象。 在每个队列中不进行其他排序。  
  
 客户端代码中启动了三个任务。 第一个任务仅轮询键盘键击以便在执行过程中的任意时刻启用取消。 第二个任务是制造者线程；它会向阻塞集合添加新项并根据随机值为每个项分配一个优先级。 第三个任务在项可用时将其从集合中移除。  
  
 可以通过使其中一个线程运行速度快于另一个线程来调整应用程序的行为。 如果制造者运行速度更快，则在阻塞集合阻止添加项（如果该集合已包含构造函数中所指定的项数）时，你会注意到限制功能。 如果使用者运行速度更快，则在使用者等待添加新项时，你会注意到阻塞功能。  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 默认情况下，<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 的存储是 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>。  
  
## <a name="see-also"></a>另请参阅  
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)
