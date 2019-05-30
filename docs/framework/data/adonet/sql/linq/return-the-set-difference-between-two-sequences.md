---
title: 返回两个序列之间的差集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 5bb7d797ad2adc4374f7a10c11d66be69feeb7a1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380053"
---
# <a name="return-the-set-difference-between-two-sequences"></a>返回两个序列之间的差集
使用 <xref:System.Linq.Queryable.Except%2A> 运算符可返回两个序列之间的差集。  
  
## <a name="example"></a>示例  
 此示例使用<xref:System.Linq.Queryable.Except%2A>可在其中返回的所有国家/地区的序列`Customers`实时但无`Employees`live。  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Except%2A> 运算仅对集合而言是定义完善的。 针对多重集的语义尚未定义。  
  
## <a name="see-also"></a>请参阅

- [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [标准查询运算符转换](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
