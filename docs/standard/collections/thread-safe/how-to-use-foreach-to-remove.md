---
title: "如何：使用 ForEach 移除 BlockingCollection 中的项 | Microsoft Docs"
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
  - "线程安全集合，如何枚举阻塞集合"
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 如何：使用 ForEach 移除 BlockingCollection 中的项
除了使用 <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法从 <xref:System.Collections.Concurrent.BlockingCollection%601> 中提取项之外，还可以使用 [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md)（在 Visual Basic 中为 [For Each](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)）移除项，直至添加完成并且集合为空。  由于与典型的 `foreach` \(`For Each`\) 循环不同，此枚举器通过移除项来修改源集合，因此将其称作“转变枚举”或“使用枚举”。  
  
## 示例  
 下面的示例演示如何通过使用 `foreach` \(`For Each`\) 循环来移除 <xref:System.Collections.Concurrent.BlockingCollection%601> 中的所有项。  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 此示例将 `foreach` 循环与使用线程中的 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> 方法结合使用，这会导致在枚举每个项时将其从集合中移除。  <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 可限制集合中任意时间所包含的最大项数。  按照此方式枚举集合会在没有项可用或集合为空时阻塞使用者线程。  在此示例中，由于制造者线程添加项的速度快于使用项的速度，因此不需要考虑阻塞问题。  
  
 不能保证按照制造者线程添加项的顺序来枚举这些项。  
  
 若要枚举集合而不对其进行修改，只需使用 `foreach` \(`For Each`\) 即可，而无需使用 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法。  但是，一定要了解，此类枚举表示某个准确时间点的集合快照。  如果其他线程在您执行循环时同时添加或移除项，则循环可能不会表示集合的实际状态。  
  
## 请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)