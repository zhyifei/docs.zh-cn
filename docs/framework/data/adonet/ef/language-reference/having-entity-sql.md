---
title: HAVING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a64bc0c9b5e1358046e78429780af796f60e404e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
指定组或聚合的搜索条件。  
  
## <a name="syntax"></a>语法  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>参数  
 `search_condition`  
 指定组或聚合应满足的搜索条件。 当 HAVING 与 GROUP BY ALL 一起使用时，HAVING 子句优先于 ALL。  
  
## <a name="remarks"></a>备注  
 HAVING 子句用于对分组结果指定附加筛选条件。 如果在查询表达式中未指定 GROUP BY 子句，则将使用隐式单集组。  
  
> [!NOTE]
>  HAVING 可仅与[选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)语句。 当[GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)是未使用，HAVING 的行为方式类似的 WHERE 子句。  
  
 HAVING 子句与 WHERE 子句的工作方式类似，只是它应用在 GROUP BY 操作之后。 这意味着 HAVING 子句只能引用分组别名和聚合，如下面的示例所示。  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 上例将组限定为只包含多个产品的组。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 HAVING 和 GROUP BY 运算符指定组或聚合的搜索条件。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2.  将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a>另请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [查询表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
