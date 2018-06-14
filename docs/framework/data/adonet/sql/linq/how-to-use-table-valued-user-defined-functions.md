---
title: 如何：使用表值用户定义的函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: e0199bb0a783f54931885053681c48d288012404
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362894"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a>如何：使用表值用户定义的函数
表值函数返回单个行集（与存储过程不同，存储过程可返回多个结果形状）。 由于表值函数的返回类型为 `Table`，因此在 SQL 中可以使用表的任何地方均可以使用表值函数。 此外，您还可以完全像处理表那样来处理表值函数。  
  
## <a name="example"></a>示例  
 下面的 SQL 函数显式声明其返回一个 `TABLE`。 因此，隐式定义了所返回的行集结构。  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 按如下方式映射此函数：  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a>示例  
 下面的 SQL 代码说明你可以对此函数返回的表执行联接，以及像处理任何其他表一样处理它：  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，此查询的呈现结果如下：  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [用户定义的函数](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
