---
title: "构建联接和跨产品查询"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b21bee335c5856c961c5abc21ad03c5d1f2c2307
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a>构建联接和跨产品查询
下面的示例演示如何组合来自多个表的结果。  
  
## <a name="example"></a>示例  
 下面的示例在 `From` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `from` 子句）中使用外键导航来选择位于伦敦的客户所下的所有订单。  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a>示例  
 下面的示例在 `Where` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `where` 子句）中使用外键导航来筛选出 `Products` 位于美国的脱销 `Supplier`。  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a>示例  
 下面的示例在 `From` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `from` 子句）中使用外键导航来筛选出位于西雅图的员工并列出它们所在的地区。  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a>示例  
 下面的示例在 `Select` 中的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 子句（在 C# 中为 `select` 子句）中使用外键导航来筛选出存在以下关系的雇员对：其中一位雇员是另一位雇员的下属，且这两位雇员来自同一 `City`。  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 示例查找所有客户和订单，确保相应的订单与客户匹配，并保证对于该列表中的每位客户，都提供了联系人姓名。  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a>示例  
 下面的示例显式联接两个表并投影来自这两个表的结果。  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a>示例  
 下面的示例显式联接三个表并投影来自其中各个表的结果。  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过使用 `LEFT OUTER JOIN` 实现 `DefaultIfEmpty()`。 如果对应的 `DefaultIfEmpty()` 没有 `Order`，则 `Employee` 方法将返回 null。  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a>示例  
 下面的示例投影通过联接获得的 `let` 表达式。  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a>示例  
 下面的示例显示了一个带有组合键的 `join`。  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a>示例  
 下面的示例演示如何构造其中一端可以为 null、另一端不可以为 null 的 `join`。  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a>请参阅  
 [查询示例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
