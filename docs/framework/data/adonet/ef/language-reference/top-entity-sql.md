---
title: TOP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 10967ac87fa8f8504dc9a6a29be99401e620085e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)
SELECT 子句可以在可选的 ALL/DISTINCT 修饰符之后具有可选的 TOP 子子句。 TOP 子子句指定查询结果中将只返回第一组行。  
  
## <a name="syntax"></a>语法  
  
```  
[ TOP (n) ]  
```  
  
## <a name="arguments"></a>自变量  
 `n`  
 一个数值表达式，指定要返回的行数。 `n` 可以是单个数值或单个参数。  
  
## <a name="remarks"></a>备注  
 TOP 表达式必须是单个数值或单个参数。 如果使用一个常量文本，则该文本类型必须可隐式提升为 Edm.Int64（字节、int16、int32 或 int64，或映射到可提升为 Edm.Int64 的类型的任何提供程序类型），并且其值必须大于或等于零。 否则，将引发异常。 如果将一个参数用作表达式，则该参数类型也必须可隐式提升为 Edm.Int64，但由于参数值是后期绑定的，因此在编译过程中不会对实际参数值进行任何验证。  
  
 下面是常量 TOP 表达式的示例：  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 下面是参数化 TOP 表达式的示例：  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 除非对查询进行排序，否则 TOP 具有不确定性。 如果需要确定的结果，请在 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 子句中使用 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 和 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 子子句。 TOP 和 SKIP/LIMIT 是互斥的。  
  
## <a name="example"></a>示例  
 以下 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 TOP 指定要从查询结果中返回的最上面一行。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## <a name="see-also"></a>请参阅  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
