---
title: 返回两个序列的交集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 3458ebf8f5708496eef6246fa55cf528e8a32bc4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380057"
---
# <a name="return-the-set-intersection-of-two-sequences"></a>返回两个序列的交集
使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。  
  
## <a name="example"></a>示例  
 此示例使用<xref:System.Linq.Queryable.Intersect%2A>以返回所有国家/地区的序列中这两`Customers`和`Employees`live。  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。 针对多重集的语义尚未定义。  
  
## <a name="see-also"></a>请参阅

- [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
