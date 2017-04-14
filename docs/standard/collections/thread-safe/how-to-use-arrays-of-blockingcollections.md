---
title: "如何：在管道中使用阻塞集合的数组 | Microsoft Docs"
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
  - "线程安全集合，管道中的阻塞集合"
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# 如何：在管道中使用阻塞集合的数组
下面的示例演示如何将 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 对象的数组与静态方法（如 <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>）一起使用以便在组件之间实现快速而灵活的数据传输。  
  
## 示例  
 下面的示例演示一个基本管道实现，在此实现中，所有对象同时获取输入集合中的数据、转换该数据并将该数据传递到输出集合。  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## 请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)