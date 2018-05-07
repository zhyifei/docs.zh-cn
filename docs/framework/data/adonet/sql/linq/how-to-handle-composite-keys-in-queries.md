---
title: 如何：处理查询中的复合键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 26c281445b84d3b3f85980de6ae4076411bb4fba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-handle-composite-keys-in-queries"></a>如何：处理查询中的复合键
有些运算符只能带一个自变量。 如果你的自变量必须包含数据库中的多个列，则你必须创建一个匿名类型来表示这种组合。  
  
## <a name="example"></a>示例  
 下面的示例显示了调用 `GroupBy` 运算符的查询，此运算符只能带一个 `key` 参数。  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a>示例  
 联接也属于这种情况，如下例中所示：  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
