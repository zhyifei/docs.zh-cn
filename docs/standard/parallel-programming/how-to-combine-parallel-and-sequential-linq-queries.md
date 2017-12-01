---
title: "如何：合并并行和顺序 LINQ 查询"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>如何：合并并行和顺序 LINQ 查询
此示例演示如何使用<xref:System.Linq.ParallelEnumerable.AsSequential%2A>方法来指示 PLINQ 查询中的所有后续运算符按顺序处理。 尽管顺序处理是通常比并行速度慢，但有时很必要生成正确的结果。  
  
> [!WARNING]
>  本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。 有关加速的详细信息，请参阅[了解 PLINQ 中的加速](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示一种情况，在其中<xref:System.Linq.ParallelEnumerable.AsSequential%2A>是必需的即到保留在查询的前一个子句中已建立的排序。  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译并运行此代码，将其粘贴到[PLINQ 数据示例](../../../docs/standard/parallel-programming/plinq-data-sample.md)项目中，添加行，以调用方法中的，从`Main`，并按 F5。  
  
## <a name="see-also"></a>另请参阅  
 [并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
