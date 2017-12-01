---
title: "如何：实现动态分区"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a>如何：实现动态分区
下面的示例演示如何实现一个自定义<xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>，实现动态分区，并可以从特定重载使用<xref:System.Threading.Tasks.Parallel.ForEach%2A>和从 PLINQ。  
  
## <a name="example"></a>示例  
 每次分区调用<xref:System.Collections.IEnumerator.MoveNext%2A>对枚举器，枚举数为分区提供一个列表元素。 在 PLINQ 和<xref:System.Threading.Tasks.Parallel.ForEach%2A>，分区是<xref:System.Threading.Tasks.Task>实例。 请求的多个线程同时发生，因为对当前索引的访问被同步。  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 这是一个示例的分区，其中包含一个元素的每个区块的块区。 通过一次提供多个元素，你可以通过锁减少争用并理论上实现更快的性能。 但是，在某些时候，更大的区块可能需要其他负载平衡的逻辑才能使所有线程处于繁忙状态，直到完成所有工作。  
  
## <a name="see-also"></a>另请参阅  
 [PLINQ 和 TPL 的自定义分区程序](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [如何：实现静态分区程序](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
