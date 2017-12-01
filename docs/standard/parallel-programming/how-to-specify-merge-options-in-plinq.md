---
title: "如何：在 PLINQ 中指定合并选项"
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a>如何：在 PLINQ 中指定合并选项
此示例演示如何指定将应用于 PLINQ 查询中的所有后续运算符的合并选项。 不需要显式设置合并选项，但这样做可能会提高性能。 有关合并选项的详细信息，请参阅[在 PLINQ 中的合并选项](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)。  
  
> [!WARNING]
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示具有不受未经排序的源，并将高开销函数应用于每个元素的基本方案中的合并选项的行为。  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 在情况下其中<xref:System.Linq.ParallelMergeOptions.AutoBuffered>选项会产生意外的延迟，生成的第一个元素之前，请尝试<xref:System.Linq.ParallelMergeOptions.NotBuffered>地更快、 更平稳地生成结果元素的选项。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq.ParallelMergeOptions>  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
