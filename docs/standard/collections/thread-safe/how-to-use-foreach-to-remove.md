---
title: "如何：使用 ForEach 删除 BlockingCollection 中的项 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d36d440b6a1d79f978e2cf39bbe2cde241af6b
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>如何：使用 ForEach 移除 BlockingCollection 中的项
除了能够使用 <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> 方法获取 <xref:System.Collections.Concurrent.BlockingCollection%601> 中的项外，还可以在添加操作完成且集合为空前使用 [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md)（在 Visual Basic 中使用 [For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md)）删除项。 由于与典型的 `foreach` (`For Each`) 循环不同，此枚举器通过删除项来修改源集合，因此将其称作*转变枚举*或*耗用枚举*。  
  
## <a name="example"></a>示例  
 下面的示例展示了如何使用 `foreach` (`For Each`) 循环删除 <xref:System.Collections.Concurrent.BlockingCollection%601> 中的所有项。  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 此示例在耗用线程中结合使用 `foreach` 循环和 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> 方法，这会在枚举集合时从中删除所有项。 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 限制了集合在任何时候包含的项数上限。 按照此方式枚举集合会在没有项可用或集合为空时阻止使用者线程。 在此示例中，由于制造者线程添加项的速度快于消耗项的速度，因此不需要考虑阻止问题。  
  
 不能保证按照制造者线程添加项的同一顺序来枚举这些项。  
  
 若要在不进行修改的情况下枚举集合，只需使用 `foreach` (`For Each`) 即可，无需使用 <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> 方法。 但是，务必要了解此类枚举表示的是某个精确时间点的集合快照。 如果其他线程在你执行循环的同时添加或删除项，则循环可能不会表示集合的实际状态。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [并行编程](../../../../docs/standard/parallel-programming/index.md)
